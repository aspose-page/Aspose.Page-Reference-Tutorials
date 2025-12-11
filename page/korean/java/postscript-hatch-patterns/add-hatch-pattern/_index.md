---
date: 2025-12-08
description: Aspose.Page Java를 사용하여 Java PostScript 문서에 해치 패턴을 추가하는 방법을 배워보세요. 이 단계별
  가이드는 해치 패턴 그래픽을 효율적으로 추가하는 방법을 보여줍니다.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: Java PostScript에서 해치 패턴 추가'
url: /ko/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript에 해치 패턴 추가

## Introduction
**Aspose.Page Java**를 사용하고 있으며 PostScript 출력에 텍스처 그래픽을 추가하고 싶다면, 해치 패턴이 빠르고 유연한 솔루션입니다. 이 튜토리얼에서는 PostScript 문서에 **해치 디자인을 추가하는 방법**을 단계별로 살펴보고, 왜 유용한지 설명하며, 바로 실행할 수 있는 완전한 코드 예제를 제공합니다. 끝까지 따라오면 Java 몇 줄만으로 시각적으로 매력적인 해치 채워진 도형과 텍스트를 만들 수 있게 됩니다.

## Quick Answers
- **필요한 라이브러리는?** Aspose.Page for Java (“aspose page java” SDK).  
- **추가하려는 시각 효과는?** 해치 패턴(예: 대각선 라인, 교차 해치).  
- **샘플 실행에 라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 가능하지만, 프로덕션에서는 라이선스가 필요합니다.  
- **코드 라인 수는?** 약 70줄이며, 명확한 단계로 나뉩니다.  
- **PDF에도 같은 방법을 사용할 수 있나요?** 예—Aspose.Page는 PDF를 포함한 여러 출력 형식을 지원합니다.

## Prerequisites
시작하기 전에 다음을 준비하세요:

- **Java Development Environment** – JDK 8 이상 및 원하는 IDE.  
- **Aspose.Page for Java library** – 공식 사이트에서 최신 JAR를 다운로드 [here](https://releases.aspose.com/page/java/).  
- **쓰기 권한** – 생성된 PostScript 파일을 저장할 폴더에 대한 쓰기 권한.

## Import Packages
먼저 프로젝트에 필요한 클래스를 가져옵니다. 이 임포트를 통해 그리기 기본 요소, 색상 처리 및 Aspose.Page API에 접근할 수 있습니다.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Set Up Initial Parameters
출력 스트림을 생성하고 페이지 크기(A4)를 설정한 뒤, 각 해치‑채워진 사각형을 그릴 때 재사용할 레이아웃 변수를 정의합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Step 2: Save Graphics State and Translate
그래픽 상태를 저장하면 나중에 원래 좌표계로 복귀할 수 있고, `translate`는 시작점을 편리한 위치로 이동시킵니다.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Step 3: Create Square for Each Pattern
각 해치‑채워진 셀을 나타낼 재사용 가능한 사각형을 정의합니다.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Step 4: Set Up Pen for Pattern Square Outline
2 포인트 두께의 `BasicStroke`는 모든 사각형 주변에 선명한 외곽선을 제공합니다.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Step 5: Iterate Through Hatch Patterns
`HatchStyle` 열거형의 모든 값을 순회하면서 각 사각형을 해당 텍스처로 채우고 외곽선을 그립니다. 이것이 **해치 패턴 추가** 기능의 핵심입니다.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Step 6: Restore Graphics State
사각형 그리기를 마친 후 원래 좌표계로 복귀합니다.

```java
document.writeGraphicsRestore();
```

## Step 7: Fill Text with Hatch Pattern
여기서는 해치 텍스처를 사용해 텍스트를 채우는 방법을 보여줍니다. 예제는 “ABC”라는 단어를 대각선‑교차 패턴으로 채웁니다.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Step 8: Outline Text with Hatch Pattern
같은 텍스트에 70 % 해치 스타일과 더 두꺼운 스트로크를 사용해 외곽선을 그립니다.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Step 9: Close and Save Document
페이지를 마무리하고 파일을 디스크에 기록한 뒤 리소스를 해제합니다.

```java
document.closePage();
document.save();
```

이 단계들을 따라 하면, **aspose page java**를 기반으로 도형과 텍스트 모두에 다양한 해치 패턴을 적용한 PostScript 파일을 만들 수 있습니다.

## Why Use Hatch Patterns with Aspose.Page Java?
- **시각적 구분** – 해치 채우기는 프린터가 흑백 출력만 지원하더라도 효과적입니다.  
- **성능** – 텍스처가 실시간으로 생성되므로 큰 이미지 파일을 피할 수 있습니다.  
- **다중 형식 지원** – 동일한 코드를 최소한의 수정만으로 PDF, EPS, SVG 등에도 적용할 수 있습니다.

## Common Pitfalls & Tips
- **파일 경로 오류** – `dataDir`가 적절한 파일 구분자(`/` 또는 `\`)로 끝나는지 확인하세요.  
- **지원되지 않는 색상** – 일부 오래된 PostScript 인터프리터는 특정 색상 공간을 처리하지 못할 수 있으니, 호환성을 위해 기본 RGB를 사용하세요.  
- **라이선스 경고** – 유효한 라이선스 없이 샘플을 실행하면 출력에 워터마크가 삽입됩니다.

## Conclusion
해치 패턴을 활용하면 기술 도면, 지도 또는 Java로 생성된 모든 그래픽의 가독성과 미관을 크게 향상시킬 수 있습니다. **Aspose.Page Java**를 사용하면 저수준 PostScript 명령을 추상화한 간결한 API를 제공하므로 파일 형식의 복잡성에 신경 쓰지 않고 디자인에 집중할 수 있습니다.

## Frequently Asked Questions

**Q: Aspose.Page Java를 다른 Java 프레임워크와 함께 사용할 수 있나요?**  
A: 예, 이 라이브러리는 프레임워크에 구애받지 않으며 Spring, Jakarta EE, Android(제한적), 순수 Java SE와 모두 호환됩니다.

**Q: Aspose.Page Java의 체험판이 제공되나요?**  
A: 물론입니다. 무료 30일 체험판을 [here](https://releases.aspose.com/)에서 다운로드하세요.

**Q: 개발용 임시 라이선스는 어떻게 얻나요?**  
A: 임시 라이선스를 [here](https://purchase.aspose.com/temporary-license/)에서 요청하면 평가용 워터마크가 제거됩니다.

**Q: 추가 튜토리얼 및 커뮤니티 지원은 어디서 찾을 수 있나요?**  
A: 공식 포럼 [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)에서 다양한 예제와 Q&A를 확인하세요.

**Q: 모든 클래스와 메서드에 대한 포괄적인 문서는 있나요?**  
A: 예, 전체 API 레퍼런스는 [here](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

---

**Last Updated:** 2025-12-08  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
