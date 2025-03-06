---
title: Aspose.Page .NET을 사용하여 이미지 채워진 글리프 및 외부 이미지 추가
linktitle: 이미지가 채워진 글리프 및 외국 이미지 추가
second_title: Aspose.페이지 .NET API
description: Aspose.Page를 사용하여 .NET에서 문서 처리 기능을 활용하세요. 이미지로 채워진 글리프를 손쉽게 추가하세요. 시각적 효과를 향상하고 작업 흐름을 간소화하세요.
weight: 11
url: /ko/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page .NET을 사용하여 이미지 채워진 글리프 및 외부 이미지 추가

## 소개

.NET 개발 세계에서 Aspose.Page는 문서 처리 작업을 처리하기 위한 강력한 툴킷으로 돋보입니다. 이 튜토리얼은 .NET용 Aspose.Page를 사용하여 이미지가 채워진 문자 모양을 추가하고 외부 이미지를 통합하는 과정을 안내합니다. 이 가이드를 마치면 문서 처리 기능을 향상시키는 방법을 확실하게 이해하게 될 것입니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET용 Aspose.Page: Aspose.Page 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/page/net/).

- 개발 환경: Visual Studio 또는 기타 선호하는 IDE를 사용하여 작동하는 .NET 개발 환경을 설정합니다.

- 문서 디렉터리: 문서를 저장할 디렉터리를 만듭니다. 코드 예제에서는 이를 "문서 디렉터리"라고 합니다.

## 네임스페이스 가져오기

.NET 애플리케이션에서 Aspose.Page에서 제공하는 클래스와 메서드에 액세스하는 데 필요한 네임스페이스를 가져오는 것부터 시작하세요.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1단계: 첫 번째 XPS 문서 만들기

Aspose.Page를 사용하여 첫 번째 XPS 문서를 만드는 것부터 시작하세요. 이 문서는 이미지로 채워진 글리프를 추가하기 위한 기초 역할을 합니다.

```csharp
// ExStart:1
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";

// 첫 번째 XPS 문서 만들기
XpsDocument doc1 = new XpsDocument();
```

## 2단계: 첫 번째 문서에 글리프 추가

글꼴, 크기, 스타일 및 위치를 지정하여 첫 번째 문서에 글리프를 추가합니다.

```csharp
// 첫 번째 문서에 글리프 추가
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## 3단계: 이미지 브러시로 글리프 채우기

데이터 디렉토리의 이미지를 활용하여 이미지 브러시로 글리프를 채웁니다.

```csharp
// 이미지 브러시로 글리프 채우기
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## 4단계: 두 번째 XPS 문서 만들기

이제 첫 번째 문서의 글리프를 통합할 두 번째 XPS 문서를 만듭니다.

```csharp
// 두 번째 XPS 문서 만들기
XpsDocument doc2 = new XpsDocument();
```

## 5단계: 첫 번째 문서의 글꼴을 사용하여 글리프 추가

첫 번째 문서의 글꼴을 사용하여 두 번째 문서에 글리프를 추가합니다.

```csharp
// 첫 번째 문서의 글꼴이 포함된 글리프를 두 번째 문서에 추가합니다.
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## 6단계: 첫 번째 문서 채우기에서 이미지 브러시 만들기

첫 번째 문서의 채우기에서 이미지 브러시를 만들고 이를 사용하여 두 번째 문서의 글리프를 채웁니다.

```csharp
// 첫 번째 문서의 채우기에서 이미지 브러시를 만들고 두 번째 문서에 글리프를 채웁니다.
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## 7단계: 문서 저장

첫 번째와 두 번째 XPS 문서를 모두 저장합니다.

```csharp
// 첫 번째 XPS 문서 저장
doc1.Save(dataDir + "out1.xps");

// 두 번째 XPS 문서 저장
doc2.Save(dataDir + "out2.xps");
// 연장:1
```

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 이미지가 채워진 문자 모양과 외부 이미지를 성공적으로 추가했습니다. 이 튜토리얼은 문서 처리 기능을 향상시키기 위한 기반을 제공하여 창의적이고 시각적으로 매력적인 문서에 대한 새로운 가능성을 열어줍니다.

## FAQ

### Q1: 글리프를 채우는 데 다른 이미지 형식을 사용할 수 있습니까?

A1: 예, Aspose.Page는 다양한 이미지 형식을 지원합니다. 선택한 이미지 형식과의 호환성을 확인하세요.

### Q2: 글리프의 모양을 추가로 사용자 정의하려면 어떻게 해야 합니까?

A2: 문자 모양 모양을 미세 조정하기 위한 추가 속성 및 방법은 Aspose.Page 설명서를 살펴보세요.

### Q3: Aspose.Page는 대용량 문서 세트를 처리하는 데 적합합니까?

A3: Aspose.Page는 작은 문서 세트와 큰 문서 세트를 모두 효율적으로 처리하도록 설계되었습니다.

### Q4: 개별 글리프에 다양한 스타일을 적용할 수 있나요?

A4: 예, 각 글리프의 스타일을 독립적으로 사용자 정의하여 높은 수준의 유연성을 제공할 수 있습니다.

### Q5: 다른 문서 처리 도구에 비해 Aspose.Page를 사용하면 어떤 이점이 있나요?

A5: Aspose.Page는 포괄적인 기능 세트, 탁월한 성능 및 광범위한 문서를 제공하므로 많은 개발자가 선호하는 선택입니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
