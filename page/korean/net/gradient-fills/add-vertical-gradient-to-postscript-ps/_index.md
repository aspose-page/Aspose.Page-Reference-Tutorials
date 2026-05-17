---
date: 2026-02-25
description: C# 선형 그라디언트 브러시를 사용하여 PS 파일에 그라디언트를 추가하고 Aspose.Page for .NET을 이용해 사각형을
  그라디언트로 채우는 방법을 배워보세요.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# 선형 그라디언트 브러시 – Aspose.Page를 사용해 PostScript(PS)에 수직 그라디언트 추가
url: /ko/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – Aspose.Page를 사용하여 PostScript (PS) 파일에 수직 그라디언트 추가

## Introduction

문서 조작 및 생성 분야에서 **Aspose.Page for .NET**은 개발자에게 강력한 도구로 자리 잡고 있습니다. 이 가이드에서는 **C# linear gradient brush**를 사용하여 **PS** 파일에 **그라디언트를 추가하고 사각형을 그라디언트로 채우는** 방법을 알아봅니다. 튜토리얼을 마치면 필요한 코드와 이 기술이 PostScript 출력에서 부드러운 수직 그라디언트를 생성하는 이유를 단계별로 명확히 이해하게 됩니다.

## Quick Answers
- **What does a C# linear gradient brush do?** 여러 색상 사이에 부드러운 전환을 만들어 형태 전체에 적용합니다.
- **Can I use this with any .NET version?** 예, Aspose.Page는 .NET Framework 4.5+ 및 .NET Core/5+를 지원합니다.
- **Do I need a license for production?** 평가용이 아닌 빌드에는 상용 라이선스가 필요합니다.
- **Is the gradient truly vertical?** 브러시가 90° 회전되어 수직 흐름을 보장합니다.
- **Where is the output saved?** `dataDir`에 지정한 경로에 저장됩니다(예: `VerticalGradient_outPS.ps`).

## What is a C# Linear Gradient Brush?
**C# linear gradient brush**는 정의된 점 사이에 선형 색상 전환을 그리는 GDI+ 객체(`LinearGradientBrush`)입니다. Aspose.Page의 그리기 API와 결합하면 PostScript (PS) 문서에 직접 정교한 그라디언트를 렌더링할 수 있습니다.

## Why Use a Linear Gradient Brush for PostScript?
- **High‑quality output:** 프린터 수준에서 그라디언트가 렌더링되어 품질이 유지됩니다.
- **Full control:** 색상 정지점, 회전 및 스케일을 자유롭게 설정할 수 있습니다.
- **Reusable code:** 동일한 브러시 로직을 PDF, SVG 등 Aspose.Page가 지원하는 다른 형식에도 재사용할 수 있습니다.

## Prerequisites

튜토리얼을 시작하기 전에 다음이 준비되어 있어야 합니다:

- Aspose.Page for .NET: Aspose.Page 라이브러리가 설치되어 있는지 확인하십시오. 필요한 리소스와 문서는 [here](https://reference.aspose.com/page/net/)에서 확인할 수 있습니다.
- Development Environment: .NET 개발을 위한 통합 개발 환경(IDE) 등 적절한 개발 환경을 설정하십시오.
- Basic Understanding: 스트림, 그래픽 경로, 색상 조작 등 .NET 개발 기본 지식을 숙지하십시오.

## Import Namespaces

C# 프로젝트에서 코드 파일 시작 부분에 필요한 네임스페이스를 포함합니다:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Step 1: Set Up the Document Directory

문서가 저장될 디렉터리 경로를 지정합니다.

```csharp
string dataDir = "Your Document Directory";
```

## Step 2: Create Output Stream for PostScript Document

`FileStream` 클래스를 사용해 PostScript 문서용 출력 스트림을 생성합니다.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Step 3: Create Save Options and PS Document

A4 크기의 저장 옵션을 만들고 1페이지 PS 문서를 초기화합니다.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 4: Define Rectangle Dimensions

수직 그라디언트를 적용할 사각형의 위치와 크기를 지정합니다.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Step 5: Create Graphics Path

정의한 사각형으로부터 그래픽 경로를 구축합니다.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Step 6: Define Interpolation Colors

그라디언트에 사용할 보간 색상 배열과 위치를 설정합니다.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Step 7: Create Linear Gradient Brush

사각형 경계를 기준으로 시작 색상과 끝 색상을 지정해 선형 그라디언트 브러시를 만듭니다.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Step 8: Set Brush Transform

브러시의 변환을 설정하여 X와 Y 스케일 구성 요소가 사각형의 너비와 높이에 맞도록 합니다.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Step 9: Set Paint and Fill the Rectangle

문서의 페인트를 설정하고, 앞서 정의한 경로를 사용해 **fill rectangle with gradient**를 수행합니다.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Step 10: Close the Current Page and Save the Document

현재 페이지를 닫고 PostScript 문서를 저장합니다.

```csharp
document.ClosePage();
document.Save();
```

Congratulations! You have successfully **added a vertical gradient to a PostScript document** using a **C# linear gradient brush** with Aspose.Page for .NET. Experiment with different parameters and colors to achieve various visual effects in your documents.

## Common Issues and Solutions

| Issue | Why it Happens | How to Fix |
|-------|----------------|------------|
| Gradient appears horizontal | Brush rotation not applied | `brushTransform.Rotate(90);`을 `brush.Transform`에 할당하기 전에 호출했는지 확인하십시오. |
| Colors look washed out | Low‑resolution output stream | 더 높은 해상도의 `PsSaveOptions`를 사용하거나 문서 크기를 늘리십시오. |
| Output file is empty | Stream not flushed | `using` 블록 외부에서 `document.Save();`가 호출되는지 확인하십시오. |

## Frequently Asked Questions

**Q1: Can I apply multiple gradients to different regions of the same document?**  
A: Yes, you can. Simply repeat the steps for each region with its specific dimensions and color scheme.

**Q2: How can I integrate this code into my existing .NET project?**  
A: Copy and paste the code into your project file and ensure that you have the Aspose.Page library referenced.

**Q3: Are there other gradient types available in Aspose.Page for .NET?**  
A: Aspose.Page supports various gradient types, including radial and path gradients. Refer to the documentation for more details.

**Q4: Can I use Aspose.Page for commercial projects?**  
A: Yes, you can. Visit [here](https://purchase.aspose.com/buy) to explore licensing options.

**Q5: Is there a community forum for Aspose.Page where I can seek help?**  
A: Certainly! Head to the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to connect with other developers and get assistance.

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}