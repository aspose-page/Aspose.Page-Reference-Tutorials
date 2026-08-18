---
date: 2026-02-23
description: PostScript 파일에 그라디언트를 추가하고, A4 페이지 크기로 PostScript 파일을 저장하며, Aspose.Page
  for .NET을 사용하여 사각형에 그라디언트를 채우는 방법을 배웁니다.
linktitle: Add Diagonal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Aspose.Page .NET를 사용하여 PostScript(PS)에서 그라디언트 – 대각선 그라디언트 추가 방법
url: /ko/net/gradient-fills/add-diagonal-gradient-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 그라디언트 추가 방법: Aspose.Page .NET을 사용한 PostScript (PS) 대각선 그라디언트

## Introduction

PostScript (PS) 문서에 대각선 그라디언트를 추가하면 시각적 매력이 크게 향상됩니다. 특히 기술 보고서, 브로셔, 그래픽 중심 애플리케이션에서 **그라디언트 추가 방법** 효과가 필요할 때 그렇습니다. 이 튜토리얼에서는 Aspose.Page for .NET을 사용하여 PostScript 파일에 그라디언트를 추가하고, A4 페이지 크기를 설정하며, 사각형을 부드러운 색상 전환으로 채우는 방법을 정확히 보여줍니다.

## Quick Answers
- **필요한 라이브러리는?** Aspose.Page for .NET  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6  
- **그라디언트 방향을 변경할 수 있나요?** 예 – 코드에 표시된 대로 브러시 변환을 회전합니다  
- **결과를 어떻게 저장하나요?** `PsDocument.Save()`를 사용하면 PostScript 파일이 디스크에 기록됩니다  
- **프로덕션에 라이선스가 필요합니까?** 예, 상용 라이선스를 사용하면 전체 기능을 사용할 수 있습니다  

## What is a diagonal gradient in PostScript?

대각선 그라디언트는 형태를 가로질러 각도(보통 45°)로 진행되는 선형 색상 전환입니다. PostScript에서는 `LinearGradientBrush`에 사용자 정의 변환 행렬을 적용하여 그라디언트를 회전, 스케일 및 이동시켜 원하는 사각형에 맞추는 방식으로 구현됩니다.

## Why use Aspose.Page for gradient fills?

Aspose.Page는 저수준 PostScript 명령을 추상화하여 익숙한 .NET 그래픽 객체로 작업할 수 있게 해줍니다. 복잡한 채우기를 만들고, 페이지 크기를 설정하며, 원시 PS 구문을 다루지 않고도 **save PostScript file**로 직접 내보낼 수 있습니다.

## Prerequisites

- **Aspose.Page for .NET Library** – [여기](https://releases.aspose.com/page/net/)에서 다운로드하세요.  
- **Document Directory** – 생성된 `*.ps` 파일이 기록될 폴더입니다.

이제 기본 사항을 살펴보았으니, 구현 과정을 단계별로 진행해 보겠습니다.

## 네임스페이스 가져오기

먼저, EPS 디바이스, 그리기 유틸리티 및 I/O 클래스를 사용할 수 있게 해주는 네임스페이스를 가져옵니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: PostScript 문서용 출력 스트림 생성 (Create PostScript Document)

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "DiagonaGradient_outPS.ps", FileMode.Create))
{
```

## Step 2: A4 페이지 크기 설정 (Save Options)

```csharp
	//Create save options with A4 size
	PsSaveOptions options = new PsSaveOptions();
```

## Step 3: 새 1페이지 PS 문서 생성

```csharp
	// Create new 1-paged PS Document
	PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 4: 사각형 매개변수 정의

```csharp
	float offsetX = 200;
	float offsetY = 100;
	float width = 200;
	float height = 100;
```

## Step 5: 그래픽 경로 생성

```csharp
	//Create graphics path from the first rectangle
	System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
	path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));
```

## Step 6: Linear Gradient Brush 생성 (사각형 그라디언트 채우기)

```csharp
	//Create linear gradient brush with rectangle as bounds, start, and end colors
	LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(255, 255, 0, 0),
		Color.FromArgb(255, 0, 0, 255), 0f);
```

## Step 7: 브러시용 변환 생성

```csharp
	//Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
	//Translation components are offsets of the rectangle                
	System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
```

## Step 8: 브러시 변환 적용 (회전, 스케일, 이동)

```csharp
	//Rotate gradient, then scale and translate to get visible color transition in required rectangle
	brushTransform.Rotate(-45);
	float hypotenuse = (float)System.Math.Sqrt(200 * 200 + 100 * 100);
	float ratio = hypotenuse / 200;
	brushTransform.Scale(-ratio, 1);
	brushTransform.Translate(100 / brushTransform.Elements[0], 0);
```

## Step 9: 브러시 변환 설정

```csharp
	//Set transform
	brush.Transform = brushTransform;
```

## Step 10: 페인트 설정 및 사각형 채우기

```csharp
	//Set paint
	document.SetPaint(brush);

	//Fill the rectangle
	document.Fill(path);
```

## Step 11: 현재 페이지 닫기

```csharp
	//Close current page
	document.ClosePage();
```

## Step 12: 문서 저장 (Save PostScript File)

```csharp
	//Save the document
	document.Save();
}
// ExEnd:1
```

## PostScript 파일 저장 방법

`PsDocument.Save()` 호출은 **Step 1**에서 연 스트림에 완전한 PostScript 내용을 기록합니다. `using` 블록이 완료되면, 지정한 디렉터리에 `DiagonaGradient_outPS.ps` 파일이 생성됩니다.

## 일반적인 사용 사례

- **기술 문서**에서 미묘한 배경 음영이 필요할 때.  
- **마케팅 브로셔**에서 대각선 그라디언트가 현대적인 느낌을 줄 때.  
- **자동화된 보고서 생성기**가 즉시 인쇄 가능한 PS 파일을 생성할 때.

## 문제 해결 및 팁

- **색상이 올바르지 않음** – `LinearGradientBrush`에 전달된 ARGB 값을 다시 확인하세요.  
- **그라디언트가 보이지 않음** – 변환 행렬이 올바르게 회전 및 스케일되는지 확인하세요; `Rotate(-45)` 호출이 대각선 각도를 설정합니다.  
- **파일이 생성되지 않음** – `dataDir`이 존재하는 폴더를 가리키는지와 애플리케이션에 쓰기 권한이 있는지 확인하세요.

## 자주 묻는 질문

**Q: Aspose.Page가 모든 .NET 프레임워크와 호환되나요?**  
A: Aspose.Page는 .NET Framework 4.5+부터 .NET 6+까지 다양한 .NET 버전을 지원하여 광범위한 호환성을 보장합니다.

**Q: Aspose.Page에서 그라디언트 색상을 사용자 정의할 수 있나요?**  
A: 예, `LinearGradientBrush`를 생성할 때 원하는 ARGB 색상을 지정할 수 있어 시작 및 종료 색조를 완전히 제어할 수 있습니다.

**Q: Aspose.Page의 체험 버전이 있나요?**  
A: 예, [여기](https://releases.aspose.com/)에서 체험 버전을 다운로드하여 Aspose.Page 기능을 살펴볼 수 있습니다.

**Q: Aspose.Page의 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: 평가 기간 동안 추가 기능을 사용하려면 Aspose.Page 임시 라이선스를 [여기](https://purchase.aspose.com/temporary-license/)에서 얻으세요.

**Q: Aspose.Page 커뮤니티 지원을 어디서 찾을 수 있나요?**  
A: 지원 및 토론을 위해 [포럼](https://forum.aspose.com/c/page/39)에서 Aspose.Page 커뮤니티에 참여하세요.

---

**마지막 업데이트:** 2026-02-23  
**테스트 환경:** Aspose.Page for .NET (최신 안정 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}