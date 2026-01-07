---
date: 2026-01-07
description: Aspose.Page를 사용하여 .NET에서 XPS 문서를 만드는 방법을 배워보세요. 이 가이드는 이미지로 채워진 글리프와
  외부 이미지를 추가하여 문서 시각 효과를 풍부하게 하는 방법을 보여줍니다.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Aspose.Page를 사용한 .NET XPS 문서 만들기 – 이미지 채워진 글리프 및 외부 이미지
url: /ko/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page와 함께 .NET에서 XPS 문서 만들기 – 이미지 채워진 글리프 및 외부 이미지

## 소개

**XPS 문서 .NET** 애플리케이션을 깔끔하고 전문적으로 만들고 싶다면, Aspose.Page를 사용하면 이미지를 글리프에 직접 삽입하고 그래픽 리소스를 문서 간에 재사용할 수 있습니다. 이 튜토리얼에서는 두 개의 XPS 파일을 만들고, 이미지 브러시로 글리프를 채운 뒤, 그 브러시를 두 번째 문서에서 재사용하는 과정을 단계별로 살펴봅니다. 마지막까지 진행하면 이 방법이 메모리를 절약하고 스타일링을 단순화하며, 보고서, 청구서 또는 인쇄 가능한 모든 콘텐츠에 창의적인 가능성을 제공한다는 것을 이해하게 됩니다.

## 빠른 답변
- **이 튜토리얼에서는 무엇을 다루나요?** Aspose.Page for .NET을 사용해 이미지‑채워진 글리프를 추가하고 XPS 문서 간에 재사용하는 방법.  
- **주요 키워드는?** `create xps document .net`.  
- **전제 조건은?** .NET 개발 환경, Aspose.Page for .NET, 그리고 XPS 파일을 저장할 폴더.  
- **구현 시간은?** 작동 프로토타입을 만드는 데 약 10‑15분.  
- **다른 이미지 형식도 사용할 수 있나요?** 네 – .NET의 `System.Drawing.Image`에서 지원하는 모든 형식 사용 가능.

## 전제 조건

코드를 진행하기 전에 다음 항목을 준비하십시오:

- **Aspose.Page for .NET** – 최신 라이브러리를 [here](https://releases.aspose.com/page/net/)에서 다운로드.  
- **개발 환경** – Visual Studio 2022(또는 .NET 6 이상을 지원하는 IDE).  
- **문서 디렉터리** – 입력 이미지와 생성된 XPS 파일을 보관할 폴더를 만들고, 예시에서는 **Your Document Directory**라고 부릅니다.

## 네임스페이스 가져오기

XPS 객체와 그리기 유틸리티를 사용하기 위해 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 단계별 가이드

### 단계 1: 첫 번째 XPS 문서 만들기

이미지‑채워진 글리프를 담을 빈 XPS 문서를 인스턴스화합니다.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### 단계 2: 첫 번째 문서에 글리프 추가

나중에 이미지 브러시로 채울 글리프(텍스트 문자)를 추가합니다.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### 단계 3: 이미지 브러시로 글리프 채우기

데이터 디렉터리에 있는 TIFF 파일로 `ImageBrush`를 생성하고 글리프에 적용합니다. 브러시의 타일 모드를 설정해 글리프 영역이 이미지 크기를 초과하면 이미지가 반복되도록 합니다.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### 단계 4: 두 번째 XPS 문서 만들기

첫 번째 문서에서 사용한 글리프 스타일과 이미지 브러시를 재사용할 두 번째 XPS 문서를 생성합니다.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### 단계 5: 첫 번째 문서의 폰트를 사용해 글리프 추가

두 번째 문서에 글리프를 추가하면서 첫 번째 문서의 동일한 폰트 객체를 재사용합니다. 이렇게 하면 두 파일 모두 시각적 일관성을 유지할 수 있습니다.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### 단계 6: 첫 번째 문서의 채우기에서 이미지 브러시 만들기

이미지를 다시 로드하는 대신 `glyphs1`에서 브러시를 복제해 `glyphs2`에 할당합니다. 이를 통해 **XPS 문서 .NET** 워크플로우에서 리소스를 효율적으로 공유하는 방법을 보여줍니다.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### 단계 7: 문서 저장

마지막으로 두 XPS 파일을 디스크에 저장합니다. 이제 XPS 뷰어로 열어 이미지‑채워진 글리프 효과를 확인할 수 있습니다.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## .NET에서 XPS 문서를 만들 때 이미지‑채워진 글리프를 사용하는 이유는?

- **시각적 임팩트** – 일반 텍스트를 전체 페이지를 래스터화하지 않고도 그래픽 풍부한 요소로 변환합니다.  
- **리소스 재사용** – 브러시와 폰트를 여러 문서에서 공유해 메모리 사용량을 줄입니다.  
- **유연성** – 이미지 브러시를 타일링, 스트레칭, 회전시켜 맞춤 패턴이나 브랜드 아이덴티티를 구현합니다.

## 일반적인 문제 및 팁

- **파일 경로 오류** – `dataDir`이 OS에 맞는 경로 구분자(`\` 또는 `/`)로 끝나는지 확인하십시오.  
- **지원되지 않는 이미지 형식** – Aspose.Page는 TIFF, PNG, JPEG에 최적화되어 있습니다. 다른 형식은 사용 전에 변환하세요.  
- **TileMode 적용 안 됨** – `TileMode`를 설정하기 전에 `XpsImageBrush`로 캐스팅했는지 확인하십시오. 그렇지 않으면 속성이 무시됩니다.

## 자주 묻는 질문

### Q1: 글리프를 채우는 데 다른 이미지 형식을 사용할 수 있나요?

**A:** 네, Aspose.Page는 TIFF, PNG, JPEG, BMP, GIF를 지원합니다. `CreateImageBrush` 호출 시 올바른 파일 확장자를 지정하면 됩니다.

### Q2: 글리프의 외관을 더 세밀하게 조정하려면 어떻게 해야 하나요?

**A:** `XpsGlyphs`의 `Opacity`, `RenderTransform`, `Stroke` 등 추가 속성을 활용해 렌더링을 미세 조정할 수 있습니다.

### Q3: 대량의 문서 세트를 처리하는 데 Aspose.Page가 적합한가요?

**A:** 물론입니다. 이 라이브러리는 고성능 시나리오에 최적화되어 있어 배치 작업으로 수천 개의 XPS 파일을 처리할 수 있습니다.

### Q4: 개별 글리프에 서로 다른 스타일을 적용할 수 있나요?

**A:** 가능합니다. 각 `XpsGlyphs` 인스턴스는 자체 fill, stroke, 변환을 가질 수 있어 세밀한 제어가 가능합니다.

### Q5: 다른 문서 처리 도구보다 Aspose.Page를 사용할 때 장점은 무엇인가요?

**A:** Aspose.Page는 XPS 생성, 조작, 변환을 위한 완전한 라이선스‑무료 API를 제공하며, 방대한 문서와 24/7 지원을 갖추고 있습니다.

---

**마지막 업데이트:** 2026-01-07  
**테스트 환경:** Aspose.Page 24.12 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}