---
date: 2025-12-18
description: Aspose.Page를 사용하여 Java XPS 문서에 그리드와 투명 사각형을 추가하는 방법을 배웁니다. XPS 문서를 효율적으로
  저장하는 단계별 가이드.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Java에서 Visual Brush를 사용하여 그리드 추가하는 방법
url: /ko/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 Visual Brush를 사용하여 그리드 추가하는 방법

## Introduction
Java로 생성된 XPS 문서에 **그리드 추가** 요소를 넣고 싶다면, 바로 이곳이 정답입니다. 이 튜토리얼에서는 Visual Brush를 사용해 그리드를 추가하고, 투명 사각형을 겹친 뒤, Aspose.Page Java API를 이용해 **XPS 문서 저장**까지 진행하는 방법을 단계별로 안내합니다. 최종적으로 보고서, 청구서 또는 문서가 많은 애플리케이션에서 재사용 가능한 깔끔한 시각 요소를 얻을 수 있습니다.

## Quick Answers
- **Visual Brush는 무엇을 하나요?** 정의된 영역을 재사용 가능한 시각 콘텐츠로 채워 그리드와 같은 반복 패턴을 만들기에 적합합니다.  
- **그리드 색상을 변경할 수 있나요?** 예 – 브러시의 solid‑color 설정을 수정하면 됩니다.  
- **그리드 위에 투명 사각형을 어떻게 추가하나요?** 고정 색으로 채운 경로에 `setOpacity`를 사용합니다.  
- **파일을 저장하는 메서드는 무엇인가요?** `doc.save(...)`가 XPS 파일을 디스크에 씁니다.  
- **라이선스가 필요하나요?** 프로덕션 사용을 위해 임시 또는 정식 라이선스가 필요합니다.

## What is a Visual Brush Grid?
Visual Brush를 사용하면 작은 시각(그리드 패턴)을 정의하고 이를 큰 영역에 타일링할 수 있습니다. 이 방식은 각 선을 개별적으로 그리는 것보다 메모리 효율이 높으며 픽셀 단위로 정확한 반복을 제공합니다.

## Why use Aspose.Page for this task?
- **Cross‑platform** – Java를 지원하는 모든 OS에서 작동합니다.  
- **High‑fidelity rendering** – 색상, 투명도 및 타일링을 정밀하게 제어합니다.  
- **No external dependencies** – 모든 것이 Aspose.Page 라이브러리를 통해 처리됩니다.

## Prerequisites
시작하기 전에 다음을 준비하세요:

- 기본 Java 프로그래밍 지식.  
- Aspose.Page 라이브러리 설치 – [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)에서 다운로드할 수 있습니다.  
- 개발 머신에 JDK 8 이상이 설정되어 있어야 합니다.

## Import Packages
먼저, 컴파일러가 사용할 타입을 찾을 수 있도록 필요한 클래스를 import합니다:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Step‑by‑Step Guide

### Step 1: Set Up Your Project
새 `XpsDocument` 인스턴스를 생성하고 출력 파일을 저장할 폴더를 지정합니다.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Step 2: Create a Magenta Grid Visual Brush
그리드 영역에 타일링될 작은 마젠타 형태를 정의합니다.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Step 3: Define Geometry for the Grid Brush
타일링된 시각이 적용될 사각형 영역을 설정합니다.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Step 4: Create a New Canvas for the Document
문서에 캔버스를 추가하고 그리드가 표시될 위치를 지정합니다.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Step 5: Add the Grid to the Canvas
시각 브러시를 기하학 객체에 적용해 타일링을 활성화합니다.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Step 6: Add a Transparent Red Rectangle (Secondary Feature)
여기서는 **투명 사각형 추가**를 시연하여 그리드 위에 강조 효과를 줍니다.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Step 7: Save the Resulting XPS Document
마지막으로 문서를 디스크에 기록합니다—이 단계가 **XPS 문서 저장**입니다.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

이 단계를 따라 하면 프로그래밍 방식으로 생성된 투명 오버레이가 적용된 전문적인 그리드를 얻을 수 있습니다.

## Common Issues & Tips

- **Incorrect tile size:** 브러시용 `Rectangle2D`가 의도한 반복 크기와 일치하는지 확인하세요. 그렇지 않으면 패턴이 늘어날 수 있습니다.  
- **Opacity not applied:** 투명하게 만들 경로에 `setOpacity`를 호출해야 하며, 브러시 자체에는 영향을 주지 않습니다.  
- **File not saved:** `dataDir`가 존재하는 폴더를 가리키는지, 애플리케이션에 쓰기 권한이 있는지 확인하세요.

## Frequently Asked Questions

**Q: Aspose.Page가 전문 문서 생성에 적합한가요?**  
A: 예, Aspose.Page는 Java에서 고품질 XPS 및 PDF 생성을 위해 설계된 강력한 라이브러리입니다.

**Q: Visual Brush를 사용해 그리드 색상을 커스터마이즈할 수 있나요?**  
A: 물론입니다! 브러시의 `setFill` 호출에서 `createColor` 매개변수를 원하는 RGBA 값으로 변경하면 됩니다.

**Q: Aspose.Page에 대한 추가 지원은 어디서 찾을 수 있나요?**  
A: 커뮤니티 도움과 공식 답변을 위해 [Aspose.Page forum](https://forum.aspose.com/c/page/39)을 방문하세요.

**Q: Aspose.Page의 무료 체험판이 있나요?**  
A: 예, 모든 기능을 구매 전 체험할 수 있는 [free trial](https://releases.aspose.com/)이 제공됩니다.

**Q: 테스트용 임시 라이선스는 어떻게 얻나요?**  
A: 개발 및 평가용으로 작동하는 [temporary license](https://purchase.aspose.com/temporary-license/)를 획득하세요.

---

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}