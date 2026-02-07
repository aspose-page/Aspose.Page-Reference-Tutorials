---
date: 2026-02-07
description: Aspose.Page for Java를 사용하여 사각형을 스케일링하는 방법, 도형을 이동하는 방법, 그리고 어파인 변환을 적용해
  PostScript 문서를 만드는 방법을 배웁니다.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Aspose.Page for Java로 사각형 크기 조정하는 방법
url: /ko/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for Java를 사용한 사각형 스케일링 방법

## Introduction
강력한 **Aspose.Page for Java** 기능을 활용하여 다양한 페이지 변환을 수행하는 포괄적인 가이드에 오신 것을 환영합니다. 이 튜토리얼에서는 **사각형 스케일링 방법**, 도형 이동, 객체 회전 및 **affine transform** 기술을 적용하면서 **PostScript 문서**를 만드는 방법을 배웁니다. 이러한 기능을 통해 저수준 렌더링 코드를 직접 다루지 않고도 그래픽‑집약적인 Java 애플리케이션을 손쉽게 구축할 수 있습니다.

## Quick Answers
- **How do I scale a rectangle in Java with Aspose.Page?** Use the `document.scale()` method before drawing the shape.  
- **Can I move (translate) a shape without affecting other graphics?** Yes—save the graphics state, call `document.translate(x, y)`, draw, then restore the state.  
- **What class creates a PostScript file?** `PsDocument` together with `PsSaveOptions`.  
- **Do I need a license for production use?** A valid Aspose.Page license is required for commercial deployments.  
- **Which Java version is supported?** Aspose.Page works with Java 8 and later.

## Prerequisites
Step‑by‑step 가이드를 진행하기 전에 다음 사전 조건을 확인하십시오:

- Java 프로그래밍에 대한 기본 지식.  
- Aspose.Page for Java 라이브러리가 설치되어 있어야 합니다. [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)에서 다운로드할 수 있습니다.  
- 머신에 Java 통합 개발 환경(IDE)이 설정되어 있어야 합니다.

## Import Packages
Java 프로젝트에서 Aspose.Page for Java를 사용하기 위해 필요한 패키지를 import합니다:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## What is “how to scale rectangle” in Aspose.Page?
사각형을 스케일링한다는 것은 X축과 Y축을 따라 크기를 변경하면서 형태는 유지하는 것을 의미합니다. Aspose.Page는 현재 그래픽 상태에 **affine transform**을 적용하는 `scale(float sx, float sy)` 메서드를 제공합니다. 이것이 **how to scale rectangle** 키워드의 핵심 기술입니다.

## How to Translate Shape with Aspose.Page
도형을 이동한다는 것은 크기를 변경하지 않고 새로운 위치로 옮기는 것을 의미합니다. 이것이 **how to translate shape**의 본질입니다. 그래픽 상태를 저장하고 `translate(dx, dy)`를 적용한 뒤 도형을 그린 다음 상태를 복원하면 다른 객체에 영향을 주지 않습니다.

## Example 1: No Transformations
첫 번째 예제는 변환을 적용하지 않은 단순 사각형을 그립니다. 이는 이후 예제와 비교하기 위한 기준선 역할을 합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Example 2: Translation
여기서는 **how to translate shape**를 시연하기 위해 두 번째 사각형을 그리기 전에 그래픽 컨텍스트를 오른쪽으로 250 단위 이동합니다.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Example 3: Scaling
이 예제는 주요 질문인 **how to scale rectangle**에 답합니다. 사각형을 원래 너비의 50 %와 높이의 75 %로 축소합니다.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## How to Rotate Shape Java (rotate shape java)
회전은 또 다른 일반적인 affine 연산입니다. 회전에 대한 코드 스니펫은 간결함을 위해 생략했지만 패턴은 동일합니다: 그래픽 상태를 저장하고 `document.rotate(angle)`를 호출한 뒤 도형을 그리고 상태를 복원합니다. 이는 **rotate shape java** 및 **how to rotate rectangle**을 실제로 보여줍니다.

## Why This Matters – Real‑World Benefits
- **Device‑independent output** – 한 번 작성하면 플랫폼‑특정 조정 없이 PostScript 또는 XPS를 생성할 수 있습니다.  
- **Fine‑grained control** – 정확한 레이아웃 요구를 충족하기 위해 이동, 스케일링, 전단, 회전을 조합할 수 있습니다.  
- **Performance‑oriented** – 대용량 문서의 배치 처리에 적합한 저오버헤드 API입니다.  

## Common Use Cases
- 인보이스와 같은 인쇄 가능한 문서 생성 – 예를 들어 로고와 바코드를 정확히 배치하는 **printable invoice java** 솔루션.  
- 정밀한 스케일링 및 위치 지정이 필요한 기술 다이어그램 제작.  
- PostScript 형식의 다중 페이지 보고서를 자동으로 생성.

## Common Issues and Solutions
- **Transformation not resetting** – 원치 않는 누적 효과를 방지하려면 `document.writeGraphicsSave()`와 `document.writeGraphicsRestore()`를 항상 짝으로 사용하십시오.  
- **Unexpected colors** – 각 변환 후에 페인트를 다시 설정하십시오; 그래픽 상태는 복원 후 이전 색상 설정을 유지하지 않습니다.  
- **File size too large** – 래스터 그래픽을 삽입할 때는 `PsSaveOptions`를 사용해 압축을 활성화하거나 이미지 해상도를 낮추십시오.

## FAQ's
### Can I use Aspose.Page for Java for other document formats?
Aspose.Page는 주로 PostScript 및 XPS 형식의 페이지 조작에 초점을 맞추고 있습니다.

### Where can I find more examples and documentation for Aspose.Page for Java?
자세한 정보는 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)을 참고하십시오.

### Is there a free trial available for Aspose.Page for Java?
예, 무료 체험을 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.

### How can I get a temporary license for Aspose.Page for Java?
임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

### Where can I seek community support or ask questions about Aspose.Page for Java?
커뮤니티 토론은 [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)에서 확인하십시오.

## Frequently Asked Questions

**Q: What is the difference between `translate` and `scale`?**  
A: `translate`는 좌표계의 원점을 이동시키고, `scale`은 X 및/또는 Y 축을 따라 그려진 객체의 크기를 변경합니다.

**Q: Can I combine multiple transformations in a single graphics state?**  
A: 예—`translate`, `scale`, `rotate`, `shear`를 순차적으로 호출하면 결합된 affine 변환을 만들 수 있습니다.

**Q: How do I reset transformations after drawing a shape?**  
A: `document.writeGraphicsRestore()`를 사용해 이전에 저장한 그래픽 상태로 되돌립니다.

**Q: Is it possible to rotate a rectangle around its center?**  
A: 물론 가능합니다. 사각형을 원점으로 이동한 뒤 `rotate(angle)`를 적용하고, 다시 원래 위치로 이동한 후 그립니다.

**Q: Does Aspose.Page support anti‑aliasing for smoother graphics?**  
A: 예—`PsSaveOptions`에서 적절한 렌더링 옵션을 설정하면 안티앨리어싱을 활성화할 수 있습니다.

---

**Last Updated:** 2026-02-07  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}