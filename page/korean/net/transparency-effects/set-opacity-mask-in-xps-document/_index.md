---
date: 2026-03-26
description: Aspose.Page for .NET을 사용하여 XPS 문서에서 불투명도 마스크를 설정하고 여러 개의 불투명도 마스크를 적용하는
  방법을 배우세요.
linktitle: Set Opacity Mask in XPS Document
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET을 사용하여 XPS 문서에 여러 불투명도 마스크 설정
url: /ko/net/transparency-effects/set-opacity-mask-in-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET을 사용하여 XPS 문서에 다중 불투명도 마스크 설정

## Introduction

불투명도 마스크를 사용하면 모든 시각 요소의 투명도를 제어할 수 있으며, **다중 불투명도 마스크**를 사용하면 XPS 문서를 돋보이게 하는 정교한 레이어 효과를 구현할 수 있습니다. 이 튜토리얼에서는 도형에 **불투명도 마스크 설정 방법**을 단계별로 안내하고, 여러 마스크를 결합하여 보다 풍부한 시각 결과를 얻는 방법을 보여줍니다. 끝까지 따라오면 몇 줄의 C# 코드만으로 모든 XPS 요소에 하나 이상의 불투명도 마스크를 추가할 수 있게 됩니다.

## Quick Answers
- **불투명도 마스크란?** 도형의 픽셀별 투명도를 정의하는 비트맵, 그라디언트 또는 단색 브러시입니다.  
- **왜 다중 불투명도 마스크를 사용하나요?** 마스크를 겹치면 단일 마스크로는 구현할 수 없는 복잡한 투명도 패턴을 만들 수 있습니다.  
- **어떤 라이브러리가 이를 지원하나요?** Aspose.Page for .NET은 XPS 그래픽에서 불투명도 마스크를 완벽히 지원합니다.  
- **라이선스가 필요합니까?** 무료 체험판으로 개발에 사용할 수 있지만, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## 다중 불투명도 마스크란 무엇인가요?

다중 불투명도 마스크는 하나 이상의 마스크를 순차적으로 또는 레이어 형태로 적용하여 각 마스크가 최종 투명도 맵에 기여하도록 하는 기법을 말합니다. 이 접근 방식은 복잡한 이미지 편집 없이도 그라디언트, 텍스처 또는 패턴화된 투명도를 만드는 데 유용합니다.

## 왜 Aspose.Page for .NET을 사용하여 불투명도 마스크를 설정하나요?
- **전체 XPS 기능 세트** – 모든 XPS 그래픽 기능이 깔끔한 .NET API를 통해 제공됩니다.  
- **외부 종속성 없음** – XPS 객체를 직접 다루며 추가 이미지 라이브러리가 필요하지 않습니다.  
- **성능 최적화** – 대용량 문서와 고해상도 마스크를 효율적으로 처리합니다.  

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건을 확인하십시오:

- Aspose.Page for .NET: 라이브러리가 설치되어 있는지 확인하십시오. 없으면 [website](https://releases.aspose.com/page/net/)에서 다운로드할 수 있습니다.
- Document Directory: XPS 문서를 저장할 디렉터리를 설정합니다.

## 네임스페이스 가져오기

.NET 프로젝트에서 필요한 네임스페이스를 가져오는 것으로 시작합니다:

```csharp
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using Aspose.Page.Xps.XpsModel.Shapes;
using Aspose.Page.Xps.XpsModel.Text;
using System.Drawing;
```

## 단계 1: 새 XPS 문서 만들기

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Aspose.Page for .NET을 사용하여 새 XPS 문서를 생성합니다.

## 단계 2: XpsDocument 인스턴스에 캔버스 추가

```csharp
// Add Canvas to XpsDocument instance
XpsCanvas canvas = doc.AddCanvas();
```

이제 XPS 문서에 캔버스를 추가합니다. 캔버스는 다양한 그래픽 요소를 담는 컨테이너 역할을 합니다.

## 단계 3: 불투명도 마스크가 적용된 사각형 추가

```csharp
// Rectangle with opacity masked by ImageBrush
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.OpacityMask = doc.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)path.OpacityMask).TileMode = XpsTileMode.Tile;
```

캔버스에 사각형을 추가하고 `OpacityMask` 속성을 사용해 투명도를 설정합니다. 이 예제에서는 이미지를 불투명도 마스크로 사용합니다. 다른 브러시를 사용해 이 단계를 반복하면 동일한 도형에 **다중 불투명도 마스크**를 적용하여 레이어형 투명도 효과를 얻을 수 있습니다.

## 단계 4: 결과 XPS 문서 저장

```csharp
// Save resultant XPS document
doc.Save(dataDir + "OpacityMask_out.xps");
```

마지막으로, 불투명도 마스크가 적용된 수정된 XPS 문서를 저장합니다.

## 다중 불투명도 마스크의 일반적인 사용 사례
- **워터마킹** – 텍스트 마스크와 패턴 마스크를 결합하여 반투명 워터마크를 생성합니다.  
- **주제 지도** – 래스터 이미지 위에 그라디언트 마스크를 겹쳐 특정 영역을 강조합니다.  
- **브랜딩** – 로고 이미지 마스크와 색상 그라디언트 마스크를 함께 사용해 정교한 브랜딩 요소를 구현합니다.

## 문제 해결 및 팁
- **마스크 정렬** – 소스 사각형 크기가 대상 도형과 일치하도록 하여 늘어짐을 방지합니다.  
- **TileMode** – 마스크 반복 방식을 제어하려면 `XpsTileMode.Tile` 또는 `XpsTileMode.None`을 실험해 보세요.  
- **성능** – 동일한 마스크를 여러 요소에 적용할 때 `XpsImageBrush` 인스턴스를 재사용합니다.

## FAQ

### Q1: 사각형 외에 다른 도형에도 불투명도 마스크를 적용할 수 있나요?

A1: 예, Aspose.Page for .NET을 사용하면 원, 다각형 및 사용자 정의 경로 등 다양한 도형에 불투명도 마스크를 적용할 수 있습니다.

### Q2: 불투명도 마스크가 이미지에만 제한되나요?

A2: 아니요, 이 튜토리얼에서는 이미지를 사용했지만, 단색, 그라디언트 또는 패턴도 활용할 수 있습니다.

### Q3: 불투명도 수준을 미세 조정할 수 있는 고급 옵션이 있나요?

A3: 물론입니다. Aspose.Page for .NET은 불투명도 설정에 대한 세밀한 제어를 제공하여 정확한 투명도 효과를 구현할 수 있습니다.

### Q4: 하나의 요소에 다중 불투명도 마스크를 적용할 수 있나요?

A4: 예, 여러 불투명도 마스크를 레이어링하여 복잡한 투명도 효과를 만들 수 있습니다.

### Q5: Aspose.Page가 다른 문서 형식과 호환되나요?

A5: Aspose.Page는 주로 XPS 문서에 초점을 맞추지만, Aspose는 다양한 형식을 처리할 수 있는 제품군을 제공합니다.

**추가 질문**

**Q: 동일한 도형에 두 개의 다른 마스크를 어떻게 결합하나요?**  
A: 두 개의 `XpsImageBrush`(또는 그라디언트 브러시) 객체를 생성하고, 하나를 `OpacityMask`에 할당한 뒤 도형을 `XpsCanvas`로 감싸고 두 번째 마스크를 캔버스에 적용합니다.

**Q: API가 애니메이션 불투명도 변화를 지원하나요?**  
A: XPS 자체는 애니메이션을 지원하지 않지만, 마스크 불투명도가 다른 여러 XPS 페이지를 생성하여 애니메이션을 흉내낼 수 있습니다.

---

**마지막 업데이트:** 2026-03-26  
**테스트 환경:** Aspose.Page for .NET 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}