---
date: 2026-02-25
description: Aspose.Page for .NET을 사용하여 수평 채우기가 적용된 XPS 그라디언트를 만드는 방법을 배워보세요. 문서의
  시각적 매력을 손쉽게 높이세요.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'XPS 그라디언트 만들기: Aspose.Page for .NET를 사용한 가로 채우기'
url: /ko/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS 그라디언트 만들기 – Aspose.Page for .NET으로 XPS에 수평 그라디언트 추가

## Introduction

이 튜토리얼에서는 페이지 전체에 수평으로 적용되는 **XPS 그라디언트** 채우기를 만들게 됩니다. 수평 그라디언트를 추가하면 특히 보고서, 브로셔 또는 시각적으로 풍부한 출력물에서 XPS 문서가 보다 세련되고 매력적으로 보입니다. 환경 설정부터 최종 XPS 파일 저장까지 Aspose.Page for .NET을 사용한 전체 과정을 단계별로 안내합니다.

## Quick Answers
- **What does this tutorial cover?** Aspose.Page for .NET으로 XPS 문서에 수평 그라디언트를 추가합니다.  
- **Which library is required?** Aspose.Page for .NET (최근 버전).  
- **Do I need a license?** 개발 단계에서는 평가판으로 충분하지만, 제품 환경에서는 상용 라이선스가 필요합니다.  
- **How long does implementation take?** 기본 그라디언트의 경우 약 5–10분 정도 소요됩니다.  
- **Can I change the gradient direction?** 예 – `LinearGradientBrush`의 시작/끝 지점을 수정하면 됩니다.

## Aspose.Page for .NET으로 XPS 그라디언트 만들기

아래에서는 각 코드 라인이 **왜** 존재하는지, **무엇을** 하는지 설명하는 단계별 가이드를 제공합니다. Visual Studio 또는 선호하는 .NET 편집기에서 따라 해 보세요.

## Prerequisites

시작하기 전에 다음 전제 조건을 확인하십시오:

1. Aspose.Page for .NET Library: 개발 환경에 Aspose.Page for .NET 라이브러리가 설치되어 있는지 확인하십시오. [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/)에서 다운로드할 수 있습니다.

2. Development Environment: Visual Studio와 같은 코드 편집기를 포함한 적절한 개발 환경을 설정하십시오.

## Import Namespaces

프로젝트에 필요한 네임스페이스를 가져옵니다. 이 네임스페이스들은 Aspose.Page for .NET 작업에 필수적입니다:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

이제 제공된 예제를 여러 단계로 나누어 살펴보겠습니다.

## Step 1: Set the Document Directory Path

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Step 2: Create a New XPS Document

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Step 3: Initialize Gradient Stops

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Step 4: Create a New Path

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Step 5: Save the Resultant XPS Document

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

이제 Aspose.Page for .NET을 사용하여 XPS 문서에 수평 그라디언트를 성공적으로 추가했습니다.

## Common Issues and Solutions

| Issue | Reason | Fix |
|-------|--------|-----|
| Gradient appears solid color | Gradient stops not added correctly | Ensure `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` is executed after setting the brush. |
| Saved file is empty | `dataDir` points to a non‑existent folder | Verify the folder exists or use an absolute path. |
| Compilation error on `PointF` | Missing `System.Drawing` reference | Add a reference to `System.Drawing.Common` (for .NET Core/5+). |

## FAQ's

### Q1: Where can I find the Aspose.Page for .NET documentation?

A1: You can find the documentation [here](https://reference.aspose.com/page/net/).

### Q2: How do I download Aspose.Page for .NET?

A2: You can download the library from the [Aspose.Page for .NET download page](https://releases.aspose.com/page/net/).

### Q3: Where can I purchase Aspose.Page for .NET?

A3: You can purchase Aspose.Page for .NET from the [purchase page](https://purchase.aspose.com/buy).

### Q4: Is there a free trial available?

A4: Yes, you can get a free trial from [here](https://releases.aspose.com/).

### Q5: How do I get a temporary license for Aspose.Page for .NET?

A5: You can obtain a temporary license from [this link](https://purchase.aspose.com/temporary-license/).

## Frequently Asked Questions

**Q: Can I use this gradient technique with XPS documents that already contain images?**  
A: Absolutely. The gradient is applied to a path layer, so existing images remain untouched.

**Q: Is it possible to create a vertical gradient instead?**  
A: Yes. Change the `LinearGradientBrush` start and end points to have different Y‑coordinates while keeping X constant.

**Q: Does Aspose.Page support .NET Core?**  
A: The library is fully compatible with .NET Core, .NET 5, and later versions.

**Q: How can I reuse the same gradient across multiple pages?**  
A: Create the `XpsLinearGradientBrush` once, store it in a variable, and assign it to paths on each page.

## Conclusion

그라디언트를 활용하면 XPS 문서의 시각적 매력이 크게 향상되고 사용자 경험도 더욱 풍부해집니다. Aspose.Page for .NET을 사용하면 **XPS 그라디언트** 채우기를 빠르고 안정적으로 만들 수 있어 보고서, 브로셔, 전자책 등에 전문적인 마무리를 제공할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page for .NET 24.11  
**Author:** Aspose