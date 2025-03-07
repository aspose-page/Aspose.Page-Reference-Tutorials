---
title: Aspose.Page .NET을 사용하여 PostScript(PS)에 대각선 그라디언트 추가
linktitle: PostScript에 대각선 그라디언트 추가(PS)
second_title: Aspose.페이지 .NET API
description: Aspose.Page를 사용하여 .NET의 PostScript 문서에 대각선 그라데이션을 추가하는 단순성을 살펴보세요. 역동적인 시각적 요소로 프로젝트를 향상시키세요.
weight: 10
url: /ko/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page .NET을 사용하여 PostScript(PS)에 대각선 그라디언트 추가

## 소개

PostScript(PS) 문서에 대각선 그라디언트를 추가하면 프로젝트에 시각적 매력과 창의성을 더할 수 있습니다. .NET용 Aspose.Page는 이 기능을 애플리케이션에 통합하기 위한 완벽한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Page를 사용하여 PS 문서에 대각선 그라디언트를 추가하는 과정을 단계별로 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET 라이브러리용 Aspose.Page: .NET 라이브러리용 Aspose.Page가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/page/net/).

- 문서 디렉터리: 출력 PS 파일이 저장될 문서 디렉터리를 설정합니다.

이제 단계별 가이드로 넘어가겠습니다.

## 네임스페이스 가져오기

먼저, 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 이러한 네임스페이스는 Aspose.Page 기능을 사용하는 데 중요합니다.

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
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## 2단계: A4 크기로 저장 옵션 만들기

```csharp
	//A4 크기로 저장 옵션 만들기
	PsSaveOptions options = new PsSaveOptions();
```

## 3단계: 새 1페이지 PS 문서 만들기

```csharp
	// 새로운 1페이지 PS 문서 만들기
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## 4단계: 직사각형 매개변수 정의

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## 5단계: 그래픽 경로 생성

```csharp
	//첫 번째 직사각형에서 그래픽 경로 만들기
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## 6단계: 선형 그라디언트 브러시 만들기

```csharp
	//사각형을 경계, 시작 및 끝 색상으로 사용하여 선형 그래디언트 브러시 만들기
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## 7단계: 브러시용 변환 생성

```csharp
	//브러시에 대한 변환을 만듭니다. X 및 Y 스케일 구성요소는 그에 따라 직사각형의 너비 및 높이와 같아야 합니다.
	// 변환 구성요소는 직사각형의 오프셋입니다.
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## 8단계: 브러시에 변환 적용

```csharp
	//그라디언트를 회전한 다음 크기를 조정하고 변환하여 필요한 직사각형에서 눈에 보이는 색상 전환을 얻습니다.
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## 9단계: 변환을 브러시로 설정

```csharp
	//변환 설정
	brush.Transform = brushTransform;
```

## 10단계: 페인트 설정 및 직사각형 채우기

```csharp
	//페인트 세트
	document.SetPaint(brush);

	//직사각형을 채우세요
	document.Fill(path);
```

## 11단계: 현재 페이지 닫기

```csharp
	//현재 페이지 닫기
	document.ClosePage();
```

## 12단계: 문서 저장

```csharp
	//문서 저장
	document.Save();
}
// 연장:1
```

다음 단계를 수행하면 .NET용 Aspose.Page를 사용하여 PostScript 문서에 대각선 그라데이션을 성공적으로 추가할 수 있습니다.

## 결론

대각선 그라디언트로 PS 문서를 향상하면 프로젝트를 시각적으로 매력적이고 역동적으로 만들 수 있습니다. .NET용 Aspose.Page는 이 프로세스를 단순화하여 개발자가 이 기능을 자신의 애플리케이션에 쉽게 통합할 수 있도록 합니다.

## FAQ

### Q1: Aspose.Page는 모든 .NET 프레임워크와 호환됩니까?

A1: Aspose.Page는 다양한 .NET 프레임워크를 지원하여 광범위한 개발 환경과의 호환성을 보장합니다.

### Q2: Aspose.Page에서 그라데이션 색상을 사용자 지정할 수 있나요?

A2: 예, Aspose.Page는 프로젝트 요구 사항에 따라 그라데이션 색상을 선택하고 사용자 정의할 수 있는 유연성을 제공합니다.

### Q3: Aspose.Page에 사용할 수 있는 평가판이 있습니까?

 A3: 예, 평가판을 다운로드하여 Aspose.Page의 기능을 탐색할 수 있습니다.[여기](https://releases.aspose.com/).

### Q4: Aspose.Page에 대한 임시 라이선스를 어떻게 얻을 수 있나요?

 A4: Aspose.Page에 대한 임시 라이선스를 얻습니다.[여기](https://purchase.aspose.com/temporary-license/) 추가 기능의 잠금을 해제합니다.

### Q5: Aspose.Page에 대한 커뮤니티 지원은 어디서 찾을 수 있나요?

 A5: Aspose.Page 커뮤니티에 참여하세요.[법정](https://forum.aspose.com/c/page/39) 도움과 토론을 위해.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
