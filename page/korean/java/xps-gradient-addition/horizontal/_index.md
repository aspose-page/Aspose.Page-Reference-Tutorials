---
date: 2025-12-25
description: Aspose.Page를 사용하여 Java에서 XPS 문서에 그라디언트를 추가하는 방법과 눈부신 수평 효과를 위한 그라디언트
  스톱을 맞춤 설정하는 방법을 배워보세요.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Java XPS에서 그라디언트 추가하기 – 수평 그라디언트
url: /ko/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS에서 그라디언트 추가 – 수평 그라디언트

## Introduction
이 단계별 가이드에 오신 것을 환영합니다. **그라디언트를 추가하는 방법**을 Java를 사용해 XPS 문서에 적용하는 방법을 안내합니다. 이 튜토리얼에서는 수평 그라디언트를 추가하는 방법, 시각적 완성도를 높이는 이유, 그리고 정밀한 색상 제어를 위해 **그라디언트 스톱을 커스터마이즈**하는 방법을 배웁니다. Aspose.Page for Java는 XPS(XML Paper Specification) 문서 작업을 간편하게 해 주어, 저수준 파일 처리보다 디자인에 집중할 수 있게 해 줍니다.

## Quick Answers
- **필요한 라이브러리는?** Aspose.Page for Java  
- **어떤 Java 버전이 작동합니까?** Java 8 이상 런타임이면 모두 사용 가능  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하며, 운영 환경에서는 상용 라이선스가 필요합니다  
- **그라디언트 방향을 바꿀 수 있나요?** 예 – 선형 브러시의 시작/끝 좌표만 수정하면 됩니다  
- **여러 개의 그라디언트를 추가할 수 있나요?** 물론 – 다른 브러시를 사용해 경로 생성 단계를 반복하면 됩니다  

## What is a Horizontal Gradient in XPS?
수평 그라디언트는 도형을 가로 방향(왼쪽에서 오른쪽)으로 색상이 부드럽게 전환되는 효과입니다. XPS에서는 정의된 **그라디언트 스톱** 사이를 보간하는 선형 그라디언트 브러시로 표현됩니다. 이 시각 효과는 배너, 버튼, 배경 채우기 등에 흔히 사용됩니다.

## Why Use Aspose.Page for Java?
- **Full XPS support** – 타사 도구 없이 생성, 편집, 렌더링이 가능합니다.  
- **Simple API** – `XpsDocument`, `XpsPath`, `XpsGradientBrush`와 같은 고수준 객체가 XML 복잡성을 숨겨 줍니다.  
- **Performance** – 대용량 문서와 배치 처리에 최적화되어 있습니다.  

## Prerequisites
시작하기 전에 다음을 준비하십시오:

1. **Java Development Environment** – 최신 JDK를 [java.com](https://www.java.com)에서 설치하세요.  
2. **Aspose.Page for Java Library** – [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)에서 JAR 파일을 다운로드하세요.  

## Import Packages
필요한 클래스를 가져옵니다. 이 임포트문을 통해 문서 생성, 그라디언트 처리 및 기본 기하학 기능에 접근할 수 있습니다.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Step 1: Initialize the XPS Document
새 `XpsDocument` 인스턴스를 만들고 결과를 저장할 폴더를 지정합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Step 2: Create Horizontal Gradient
색상과 위치를 제어하는 **그라디언트 스톱** 목록을 정의합니다. 아래 예시는 활기찬 무지개 색상의 그라디언트를 생성합니다.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### How to customize gradient stops
- **Color** – `doc.createColor(alpha, red, green, blue)`를 사용해任意의 ARGB 값을 설정합니다.  
- **Position** – 두 번째 인자(`float` 0~1 사이)는 그라디언트 라인 상에서 스톱이 나타나는 위치를 정의합니다. 이 값을 조정해 색상을 왼쪽이나 오른쪽으로 이동시킬 수 있습니다.

## Step 3: Add Path with Gradient
사각형 경로를 만들고 필요하면 변환을 적용한 뒤, 선형 그라디언트 브러시로 채웁니다. 브러시는 두 점(`(10,0)` → `(228,0)`)을 사용해 수평 효과를 만듭니다.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Pro tip:** 동일한 `stops` 리스트를 여러 경로에 재사용하면 성능이 향상되지만, 새로운 스톱을 추가하기 전에 `clear()` 호출을 잊지 마세요.

## Step 4: Save the Document
XPS 파일을 디스크에 저장합니다. 이제 XPS 뷰어에서 열어 수평 그라디언트가 적용된 모습을 확인할 수 있습니다.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Common Issues & Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| Gradient appears solid | No gradient stops added or brush not set | Ensure `path.setFill(...)` uses a `LinearGradientBrush` and that stops are added via `getGradientStops().addAll(stops)`. |
| Colors look muted | Incorrect alpha value (first parameter) | Use `255` for fully opaque colors unless transparency is desired. |
| Path size is off | Transform matrix values are wrong | Adjust the matrix parameters (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Frequently Asked Questions

**Q: Can I apply multiple gradients in a single XPS document?**  
A: Yes, you can add multiple paths, each with its own gradient brush, to create complex layered designs.

**Q: Is Aspose.Page compatible with the latest Java versions?**  
A: Aspose.Page for Java is regularly updated and works with Java 8 and newer releases.

**Q: Are there other gradient types available in Aspose.Page?**  
A: Besides linear gradients, Aspose.Page also supports radial gradients for circular color transitions.

**Q: Can I customize the colors and positions of gradient stops?**  
A: Absolutely! You have full control over each stop’s ARGB color and its relative position (0‑1 range).

**Q: Is there a community forum for Aspose.Page where I can seek help?**  
A: Yes, you can visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) to connect with the community and get assistance.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}