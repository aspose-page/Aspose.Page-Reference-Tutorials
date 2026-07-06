---
date: 2026-02-13
description: Aspose.Page for Java를 사용하여 방사형 색상 스톱 그라디언트가 포함된 PostScript 그라디언트를 만드는
  방법을 배워보세요. 이 단계별 가이드는 문서에 색상 스톱 그라디언트를 추가하는 방법을 보여줍니다.
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: PostScript 그라디언트 만들기 – Java에서 방사형 그라디언트
url: /ko/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript에서 Aspose.Page를 사용하여 방사형 그라디언트 추가하는 방법

## Introduction
부드럽고 눈길을 끄는 색상 전환을 갖는 **PostScript 그라디언트**를 만들어야 할 때, 방사형 그라디언트를 추가하는 방법을 배우는 것이 시작하기에 완벽합니다. 이 튜토리얼에서는 **Aspose.Page for Java** 라이브러리를 사용하여 아름다운 방사형 그라디언트를 포함하는 PostScript 파일을 생성하는 데 필요한 모든 단계를 단계별로 안내합니다. 끝까지 읽으면 API를 이해하고, 완전한 실행 예제를 확인하며, 색상, 위치 및 반경을 원하는 디자인에 맞게 조정하는 방법을 알게 됩니다.

## Quick Answers
- **What library creates radial gradients in PostScript?** Aspose.Page for Java.  
- **How long does the implementation take?** About 10‑15 minutes for a basic example.  
- **Do I need a license to run the code?** A free trial works for development; a commercial license is required for production.  
- **Which Java version is supported?** Java 8 or higher.  
- **Can I change the gradient’s shape?** Yes – adjust the radius and center point in the `RadialGradientPaint` constructor.

## How to Create PostScript Gradient with Radial Fill
아래에서는 방사형 채우기를 사용하여 **PostScript 그라디언트** 콘텐츠를 정확히 만드는 방법을 보여주는 간결한 단계별 가이드를 제공합니다. 각 단계에는 짧은 설명과 원본 코드 블록(변경 없음)이 포함됩니다.

## What is a Radial Gradient?
방사형 그라디언트는 중앙 지점에서 바깥쪽으로 색상이 방사되며 점차 가장자리로 블렌딩되는 방식으로 색을 칠합니다. 선형 그라디언트와 달리 색상 전환이 원형(또는 타원형) 패턴을 따라 진행되므로 하이라이트, 스포트라이트 또는 부드러운 배경 채우기에 이상적입니다.

## Why Use Aspose.Page for Radial Gradients?
- **Full control over PostScript output** – 저수준 PS 명령을 직접 작성할 필요가 없습니다.  
- **Cross‑platform** – Java가 실행되는 모든 OS에서 작동합니다.  
- **Rich color management** – 여러 색상 정지점, 다양한 색상 공간 및 사이클 방식을 지원합니다.  
- **Integration‑ready** – 텍스트, 이미지 및 벡터 도형과 같은 다른 Aspose.Page 기능과 결합할 수 있습니다.

## Prerequisites
코드 작성을 시작하기 전에 다음 항목을 준비하십시오:

- **Java Development Kit (JDK) 8+** – `java -version` 명령으로 확인합니다.  
- **Aspose.Page for Java** – 공식 [Aspose.Page 다운로드 페이지](https://releases.aspose.com/page/java/)에서 최신 JAR를 다운로드합니다.  
- **IDE of your choice** – Eclipse, IntelliJ IDEA 또는 Java 확장이 포함된 VS Code 등.  
- **A writable folder** – 생성된 `.ps` 파일이 저장될 폴더입니다.

## Import Packages
먼저 필요한 클래스를 가져옵니다. `java.awt` 패키지는 그라디언트 페인트 객체를 제공하고, `com.aspose.eps`는 PostScript 문서 처리 클래스를 포함합니다.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step‑by‑Step Guide

### Step 1: Create a Rectangle and Open a PS Document
출력 스트림을 만들고 페이지 크기(A4 기본)를 설정한 뒤, 그라디언트를 담을 사각형을 정의합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Pro tip:** 사각형 좌표(`200, 100, 200, 200`)를 조정하여 페이지 어디에든 그라디언트를 배치할 수 있습니다.

### Step 2: Define Colors and Fractions
방사형 그라디언트는 *색상 정지점*(colors)과 *분수*(fractions, 정지점의 상대 위치)로 구성됩니다. 여기서는 6가지 색상과 해당 분수를 배열로 생성합니다.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Why this matters:** `fractions` 값을 조정하면 색상이 전환되는 속도를 제어할 수 있어 미묘하거나 극적인 효과를 만들 수 있습니다.

### Adding Color Stops Gradient to Your Radial Fill
**add color stops gradient**가 필요할 때는 `colors`와 `fractions` 배열이 핵심입니다. 시각적 디자인에 맞게 순서를 바꾸거나, 추가하거나, 제거해도 됩니다.

### Step 3: Create Radial Gradient Paint
이제 `RadialGradientPaint` 객체를 생성합니다. 생성자는 그라디언트 중심점, 반경, 초점점, 분수 배열, 색상 배열, 사이클 방식, 색상 공간 및 선택적 변환을 받습니다.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Note:** 추가적인 스케일링이나 회전이 필요하지 않다면 `transform`을 `null`로 설정할 수 있습니다. `AffineTransform`을 사용해 기울어진 그라디언트를 실험해 보세요.

### Step 4: Set Paint and Fill the Rectangle
페인트가 준비되면 `PsDocument`에 적용하고 앞서 정의한 사각형을 채웁니다.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

이 시점에서 PostScript 페이지에는 방사형 그라디언트가 부드럽게 채워진 사각형이 포함됩니다.

### Step 5: Close and Save the Document
마지막으로 현재 페이지를 닫고 파일을 디스크에 씁니다.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

`RadialGradient1_outPS.ps` 파일을 任意의 PostScript 뷰어(예: Ghostscript)에서 열면 정의한 대로 그라디언트가 정확히 렌더링됩니다.

## Common Issues & Solutions
| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| Gradient appears as a solid color | `fractions` array does not start at `0.0f` or end at `1.0f` | Ensure the first fraction is `0.0f` and the last is `1.0f`. |
| Colors look washed out | Using the wrong `ColorSpaceType` | Switch to `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` for more vibrant output. |
| No output file generated | `FileOutputStream` path is invalid or not writable | Verify `dataDir` exists and the application has write permissions. |

## Frequently Asked Questions

**Q: Can I use Aspose.Page for Java in commercial projects?**  
A: Yes. A commercial license is required for production use. You can purchase one from the [Aspose licensing page](https://purchase.aspose.com/buy).

**Q: Where can I find the official API reference?**  
A: The full documentation is available [here](https://reference.aspose.com/page/java/).

**Q: Is a free trial available for testing?**  
A: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).

**Q: How do I obtain a temporary license for evaluation?**  
A: A temporary license can be requested [here](https://purchase.aspose.com/temporary-license/).

**Q: Where can I get community support?**  
A: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusion
이제 **방사형 그라디언트를** Java PostScript 문서에 Aspose.Page를 사용해 추가하는 방법을 알게 되었습니다. 사각형 크기, 색상 정지점 및 그라디언트 반경을 조정하면 미묘한 배경 채우기부터 대담한 스포트라이트 그래픽까지 무한한 시각 효과를 만들 수 있습니다. 다양한 `AffineTransform` 값을 실험해 그라디언트를 회전하거나 기울여 보시고, 텍스트와 이미지와 결합해 보다 풍부한 PDF 또는 EPS 출력물을 만들어 보세요.

---

**Last Updated:** 2026-02-13  
**Tested With:** Aspose.Page for Java latest (as of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}