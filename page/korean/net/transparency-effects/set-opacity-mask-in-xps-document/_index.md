---
title: .NET용 Aspose.Page를 사용하여 XPS 문서에서 불투명 마스크 설정
linktitle: XPS 문서에서 불투명 마스크 설정
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 XPS 문서에서 불투명 마스크를 설정하는 방법을 알아보세요. 손쉽게 문서 미학을 향상시키세요.
type: docs
weight: 12
url: /ko/net/transparency-effects/set-opacity-mask-in-xps-document/
---
## 소개

다양한 수준의 투명도를 사용하여 시각적으로 매력적인 문서를 만들려면 불투명 마스크가 필수적입니다. .NET용 Aspose.Page는 이 프로세스를 단순화하여 개발자에게 XPS 문서를 향상시킬 수 있는 포괄적인 도구 세트를 제공합니다. 이 튜토리얼에서는 단계별 가이드로 불투명 마스크를 설정하는 방법을 살펴보겠습니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.

-  .NET용 Aspose.Page: 라이브러리가 설치되어 있는지 확인하세요. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[웹사이트](https://releases.aspose.com/page/net/).

- 문서 디렉터리: XPS 문서를 저장할 디렉터리를 설정합니다.

## 네임스페이스 가져오기

.NET 프로젝트에서 필요한 네임스페이스를 가져오는 것부터 시작하세요.

```csharp
using Aspose.Page.Xps;
using Aspose.Page.Xps.XpsModel;
using Aspose.Page.Xps.XpsModel.Shapes;
using Aspose.Page.Xps.XpsModel.Text;
using System.Drawing;
```

## 1단계: 새 XPS 문서 만들기

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
// 새 XPS 문서 만들기
XpsDocument doc = new XpsDocument();
```

.NET용 Aspose.Page를 사용하여 새 XPS 문서를 만드는 것부터 시작하세요.

## 2단계: XpsDocument 인스턴스에 캔버스 추가

```csharp
// XpsDocument 인스턴스에 캔버스 추가
XpsCanvas canvas = doc.AddCanvas();
```

이제 XPS 문서에 캔버스를 추가합니다. 캔버스는 다양한 그래픽 요소의 컨테이너 역할을 합니다.

## 3단계: 불투명 마스크로 직사각형 추가

```csharp
// ImageBrush로 마스크된 불투명도가 있는 직사각형
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.OpacityMask = doc.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)path.OpacityMask).TileMode = XpsTileMode.Tile;
```

 캔버스에 직사각형을 추가하고 다음을 사용하여 불투명도를 설정합니다.`OpacityMask`재산. 이 예에서는 이미지를 불투명 마스크로 사용하고 있습니다.

## 4단계: 결과 XPS 문서 저장

```csharp
// 결과 XPS 문서 저장
doc.Save(dataDir + "OpacityMask_out.xps");
```

마지막으로 불투명 마스크가 적용된 수정된 XPS 문서를 저장합니다.

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 XPS 문서에서 불투명 마스크를 설정하는 방법을 성공적으로 배웠습니다. 이 기능은 정교하고 시각적으로 매력적인 문서를 디자인할 수 있는 창의적인 가능성의 영역을 열어줍니다.

## FAQ

### Q1: 직사각형 외의 다른 도형에도 불투명 마스크를 적용할 수 있나요?

A1: 예, .NET용 Aspose.Page를 사용하면 원, 다각형 및 사용자 정의 경로를 포함한 다양한 모양에 불투명 마스크를 적용할 수 있습니다.

### Q2: 불투명 마스크는 이미지에만 국한됩니까?

A2: 아니요. 이 튜토리얼에서는 이미지를 불투명 마스크로 사용했지만 단색, 그라데이션 또는 패턴도 활용할 수 있습니다.

### Q3: 불투명도 수준을 미세 조정하기 위한 고급 옵션이 있습니까?

A3: 물론입니다. .NET용 Aspose.Page는 불투명도 설정에 대한 세부적인 제어 기능을 제공하므로 정확한 투명도 효과를 얻을 수 있습니다.

### Q4: 단일 요소에 여러 개의 불투명 마스크를 적용할 수 있나요?

A4: 예, 여러 개의 불투명 마스크를 겹쳐서 복잡한 투명도 효과를 만들 수 있습니다.

### Q5: Aspose.Page는 다른 문서 형식과 호환됩니까?

A5: Aspose.Page는 주로 XPS 문서에 중점을 두지만 Aspose는 다양한 형식을 처리하기 위한 다양한 제품을 제공합니다.