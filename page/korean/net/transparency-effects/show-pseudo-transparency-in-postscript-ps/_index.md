---
title: Aspose.Page를 사용하여 PostScript(PS)에서 의사 투명성 표시
linktitle: PostScript(PS)에서 의사 투명성 표시
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 PostScript의 의사 투명성 기능을 살펴보세요. 시각적으로 멋진 문서를 보려면 단계별 가이드를 따르세요.
type: docs
weight: 13
url: /ko/net/transparency-effects/show-pseudo-transparency-in-postscript-ps/
---
## 소개

의사 투명성을 통합하여 PostScript(PS) 문서의 시각적 매력을 향상시키고 싶으십니까? .NET용 Aspose.Page는 이러한 효과를 손쉽게 달성할 수 있는 강력한 솔루션을 제공합니다. 이 단계별 튜토리얼에서는 Aspose.Page를 사용하여 PostScript에서 의사 투명성을 표시하는 과정을 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- .NET용 Aspose.Page: .NET용 Aspose.Page 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Aspose.Page 문서](https://reference.aspose.com/page/net/).

- 문서 디렉토리: PostScript 문서를 저장할 디렉토리를 설정합니다.

이제 무기고에 필요한 도구가 있으므로 Aspose.Page를 사용하여 PostScript에서 의사 투명성을 보여주는 방법을 살펴보겠습니다.

## 네임스페이스 가져오기

예제를 살펴보기 전에 필수 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 1단계: PostScript 문서에 대한 출력 스트림 만들기

```csharp
// ExStart:1
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
//PostScript 문서의 출력 스트림 생성
using (Stream outPsStream = new FileStream(dataDir + "ShowPseudoTransparency_outPS.ps", FileMode.Create))
{
	//A4 크기로 저장 옵션 만들기
	PsSaveOptions options = new PsSaveOptions();

	// 새로운 1페이지 PS 문서 만들기
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## 2단계: 불투명한 그라데이션 채우기로 직사각형 만들기

```csharp
	float offsetX = 50;
	float offsetY = 100;
	float width = 200;
	float height = 100;

	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	LinearGradientBrush opaqueBrush = new LinearGradientBrush(new RectangleF(0, 0, 200, 100), Color.FromArgb(0, 0, 0),
		Color.FromArgb(40, 128, 70), 0f);
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	opaqueBrush.Transform = brushTransform;
	Aspose.Page.EPS.GradientBrush gradientBrush = new GradientBrush(opaqueBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## 3단계: 반투명 그라디언트 채우기로 직사각형 만들기

```csharp
	offsetX = 350;

	//첫 번째 직사각형에서 그래픽 경로 만들기
	path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

	//투명도가 255가 아닌 150과 50인 선형 그래디언트 브러시 색상을 만듭니다. 따라서 반투명합니다.
	LinearGradientBrush translucentBrush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
		Color.FromArgb(50, 40, 128, 70), 0f);

	brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
	translucentBrush.Transform = brushTransform;
	gradientBrush = new Aspose.Page.EPS.GradientBrush(translucentBrush);
	gradientBrush.WrapMode = WrapMode.Clamp;

	document.SetPaint(gradientBrush);
	document.Fill(path);
```

## 4단계: 현재 페이지를 닫고 문서 저장

```csharp
	document.ClosePage();
	document.Save();
}
// 연장:1
```

다음 단계를 수행하면 Aspose.Page for .NET을 사용하여 PostScript 문서에 유사 투명성을 원활하게 통합할 수 있습니다.

## 결론

결론적으로 .NET용 Aspose.Page는 PostScript 문서의 시각적 요소를 향상시키는 간단하고 효율적인 방법을 제공합니다. 위에 설명된 단계는 의사 투명성을 통합하기 위한 명확한 경로를 제공하여 시각적으로 놀라운 출력을 생성할 수 있도록 합니다.

## FAQ

### Q1: Aspose.Page는 모든 버전의 .NET과 호환됩니까?

A1: Aspose.Page for .NET은 다양한 버전의 .NET 프레임워크와 호환되므로 유연성과 통합 용이성을 보장합니다.

### Q2: 직사각형 이외의 다른 모양에도 의사 투명도를 적용할 수 있나요?

A2: 예, GraphicsPath를 적절하게 조정하여 다른 셰이프에도 동일한 원칙을 적용할 수 있습니다.

### Q3: 추가 예제와 문서는 어디에서 찾을 수 있습니까?

 A3: 탐색해 보세요.[Aspose.Page 문서](https://reference.aspose.com/page/net/) 포괄적인 예제와 자세한 문서를 보려면

### Q4: Aspose.Page에 사용할 수 있는 무료 평가판이 있나요?

 A4: 예, 다음에서 Aspose.Page 무료 평가판에 액세스할 수 있습니다.[이 링크](https://releases.aspose.com/).

### Q5: Aspose.Page에 대한 임시 라이선스를 어떻게 얻을 수 있나요?

 A5: 방문[이 링크](https://purchase.aspose.com/temporary-license/) Aspose.Page에 대한 임시 라이센스를 얻으려면.