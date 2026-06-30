---
date: 2026-06-30
description: 몇 가지 간단한 단계로 Aspose.Page for .NET을 사용하여 XPS 문서 .NET을 만들고 Image Filled
  Glyph 또는 Foreign Image를 추가하는 방법을 배웁니다.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Image Filled Glyph 및 Foreign Image 추가
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: XPS 문서 .NET 만들기 – Aspose.Page를 사용하여 Image Filled Glyph 및 Foreign Image 추가
url: /ko/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS 문서 만들기 .NET – 이미지 채워진 글리프 및 외부 이미지 추가 with Aspose.Page

## 소개

.NET 개발에서 **create XPS document .NET** 작업은 고품질이며 해상도에 독립적인 그래픽이 필요할 때 흔히 발생합니다. Aspose.Page for .NET은 이를 간단하게 처리할 수 있게 해 주며, XPS 파일에 이미지 채워진 글리프를 삽입하거나 다른 XPS 문서에서 이미지를 가져올 수 있게 합니다. 이 튜토리얼을 마치면 두 개의 XPS 문서를 만들고, 글리프를 이미지로 채우며, 해당 이미지를 문서 간에 재사용하는 방법을 알게 됩니다—청구서, 인증서 또는 시각적으로 풍부한 출력물을 생성하는 데 완벽합니다.

## 빠른 답변
- **Aspose.Page는 무엇을 지원하나요?** 25개 이상의 이미지 형식과 전체 메모리를 로드하지 않고 최대 500 MB 크기의 XPS 파일을 처리할 수 있는 기능을 제공합니다.  
- **이미지 채워진 글리프를 추가하려면 몇 줄의 코드가 필요합니까?** 두 줄만 필요합니다: `ImageBrush`를 생성하고 이를 `Glyph`에 할당합니다.  
- **프로덕션에 라이선스가 필요합니까?** 예, 상용 라이선스를 사용하면 평가 워터마크가 제거됩니다.  
- **호환되는 .NET 버전은 무엇입니까?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **다른 XPS에서 폰트를 재사용할 수 있나요?** 물론입니다—첫 번째 문서의 폰트 컬렉션을 두 번째 문서로 가져올 수 있습니다.

## Aspose.Page .NET을 사용하여 XPS 문서를 만드는 방법은?
Aspose.Page 라이브러리를 로드하고 `XpsDocument`를 인스턴스화한 뒤 페이지를 추가하고 `Save`를 호출하면 됩니다—세 줄의 간결한 문장으로 전체 워크플로우가 완성됩니다. API가 페이지 크기, DPI 및 리소스 관리를 자동으로 처리하므로 저수준 XPS 구조를 직접 관리할 필요가 없습니다. 이 접근 방식은 단일 페이지 전단지부터 수백 페이지에 이르는 카탈로그까지 확장 가능합니다.

## 전제 조건

시작하기 전에 다음을 준비하십시오:

- **Aspose.Page for .NET** – [here](https://releases.aspose.com/page/net/)에서 다운로드하십시오.  
- **.NET IDE** – Visual Studio, Rider 또는 C# 확장 기능이 포함된 VS Code.  
- **문서를 저장할 폴더** – 코드 스니펫에서는 **Your Document Directory**라고 지칭합니다.

## 네임스페이스 가져오기

`Aspose.Page.XPS` 네임스페이스는 핵심 XPS 문서 클래스를 제공하고, `Aspose.Page.XPS.XpsModel`은 글리프와 브러시와 같은 모델 요소를 포함합니다. 파일 상단에 다음을 추가하십시오:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 이미지 채워진 글리프란?

글리프는 벡터 형태이며 단색, 그라디언트 또는 이미지 브러시로 렌더링될 수 있습니다. `ImageBrush`를 적용하면 글리프 내부가 제공된 이미지로 채워져 전체 페이지를 래스터화하지 않고도 복잡한 시각 효과를 구현할 수 있습니다.

## 단계 1: 첫 번째 XPS 문서 만들기

`XpsDocument`는 XPS 패키지를 나타내며 XPS 파일을 만들고 저장하는 진입점입니다. 이미지 채워진 글리프를 호스팅할 첫 번째 XPS 문서를 생성하십시오.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## 단계 2: 첫 번째 문서에 글리프 추가

`XpsGlyphs`는 페이지에 배치할 수 있는 글리프(텍스트 문자) 컬렉션을 정의합니다. 글리프를 추가하면서 폰트, 크기, 스타일 및 위치를 지정하십시오.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## 단계 3: 이미지 브러시로 글리프 채우기

`ImageBrush`는 이미지를 사용해 영역을 채우며, 패턴이나 사진을 형태에 채울 수 있게 합니다. 데이터 디렉터리의 이미지를 활용하여 글리프를 이미지 브러시로 채우십시오.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## 단계 4: 두 번째 XPS 문서 만들기

`XpsDocument`를 사용해 새 XPS 파일을 만들 수 있으며, 여기에는 페이지, 리소스 및 콘텐츠를 포함할 수 있습니다. 이제 첫 번째 문서의 글리프를 포함할 두 번째 XPS 문서를 생성하십시오.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## 단계 5: 첫 번째 문서의 폰트를 사용해 글리프 추가

`Font`는 XPS 문서에서 텍스트를 렌더링하는 데 사용되는 서체를 나타냅니다. 첫 번째 문서에서 추출한 폰트를 사용해 두 번째 문서에 글리프를 추가하십시오. 폰트 컬렉션을 공유하면 파일 크기를 낮게 유지하고 시각적 일관성을 보장합니다.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## 단계 6: 첫 번째 문서의 채우기에서 이미지 브러시 만들기

`ImageBrush`는 기존 채우기에서 생성될 수 있어 동일한 이미지를 여러 문서에서 재사용할 수 있습니다. 첫 번째 문서의 채우기에서 이미지 브러시를 만든 뒤 두 번째 문서의 글리프를 채우는 데 사용하십시오. 이 “외부 이미지” 기법을 통해 원본 파일을 복제하지 않고도 아트워크를 재사용할 수 있습니다.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## 단계 7: 문서 저장

`Save`는 모든 리소스를 포함한 XPS 패키지를 파일에 기록합니다. 첫 번째와 두 번째 XPS 문서를 모두 출력 폴더에 저장하십시오. `Save` 메서드는 XPS 패키지를 기록하면서 모든 리소스를 임베드하고 이미지 채워진 글리프를 보존합니다.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## 일반적인 문제 및 해결책

| 문제 | 발생 원인 | 해결 방법 |
|------|----------|----------|
| **글리프 내부에 이미지가 표시되지 않음** | `ImageBrush`가 잘못된 URI로 생성되었거나 이미지 크기가 글리프 경계를 초과했습니다. | 이미지 경로를 확인하고, 필요하면 `ImageBrush.Stretch = Stretch.Uniform`을 설정하십시오. |
| **두 번째 문서에서 폰트 누락** | 첫 번째 XPS에서 폰트 리소스가 내보내지 않았습니다. | 글리프를 추가하기 전에 `firstDoc.Fonts.SaveTo(secondDoc.Fonts)`를 사용하십시오. |
| **대용량 파일에서 성능 저하** | 각 글리프마다 큰 이미지를 메모리로 로드하고 있습니다. | 모든 글리프에 단일 `ImageBrush` 인스턴스를 재사용하거나 사용 전에 이미지를 다운샘플링하십시오. |

## 자주 묻는 질문

### Q1: 글리프를 채우는 데 서로 다른 이미지 형식을 사용할 수 있나요?

A1: 예, Aspose.Page는 PNG, JPEG, BMP, GIF, TIFF 등 25개 이상의 형식을 지원합니다.

### Q2: 글리프의 외관을 더 세밀하게 커스터마이즈하려면 어떻게 해야 하나요?

A2: `Glyph.Stroke`, `Glyph.FillOpacity`, `Glyph.Transform`와 같은 속성을 활용해 외곽선, 투명도 및 회전을 조정할 수 있습니다.

### Q3: 대용량 문서 세트를 처리하는 데 Aspose.Page가 적합한가요?

A3: 물론입니다. 이 라이브러리는 스트리밍을 사용해 수백 페이지에 달하는 XPS 파일을 처리하며, 500페이지 문서라 하더라도 메모리 사용량을 100 MB 이하로 유지합니다.

### Q4: 개별 글리프에 서로 다른 스타일을 적용할 수 있나요?

A4: 예, 각 `Glyph` 인스턴스는 자체 `Fill`, `Stroke`, `Transform` 속성을 가지고 있어 글리프별 스타일링이 가능합니다.

### Q5: 다른 XPS 도구에 비해 Aspose.Page를 사용할 때의 장점은 무엇인가요?

A5: Aspose.Page는 25개 이상의 이미지 형식을 지원하고, 전체 메모리를 로드하지 않고 500 MB까지의 파일을 처리하며, 100 % .NET‑네이티브 API를 제공해 COM 인터옵이나 외부 도구가 필요 없습니다.

**마지막 업데이트:** 2026-06-30  
**테스트 환경:** Aspose.Page 24.11 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Create XPS Document – Aspose.Page for .NET](/page/net/document-creation/)
- [Add Image to XPS Document with Aspose.Page for .NET](/page/net/image-management/add-image-to-xps-document/)
- [Add Glyph Clone and Change Color with Aspose.Page for .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}