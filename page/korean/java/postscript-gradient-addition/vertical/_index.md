---
date: 2025-12-09
description: Aspose.Page를 사용하여 Java에서 PostScript 그라디언트를 만드는 방법을 배워보세요. 이 단계별 가이드는
  PostScript 문서에 수직 그라디언트를 손쉽게 추가하는 방법을 보여줍니다.
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: Java에서 PostScript 그라디언트 만들기 – 수직 그라디언트 추가
url: /ko/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 PostScript 그라디언트 만들기 – 수직 그라디언트 추가

## 소개
이 포괄적인 튜토리얼에서는 Aspose.Page for Java를 사용하여 **Java에서 PostScript 그라디언트를 만드는 방법**을 배웁니다. 수직 그라디언트를 추가하면 문서가 더욱 생동감 있고 전문적으로 보이며, 몇 줄의 코드만으로도 놀라운 시각 효과를 얻을 수 있습니다. 각 단계를 자세히 안내하고, 왜 해당 단계가 중요한지 설명하며, 흔히 발생하는 문제를 피할 수 있는 실용적인 팁을 제공합니다.  
이 가이드에서는 **Java에서 PostScript 그라디언트를 단계별로 만드는 방법**을 다룹니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Page for Java  
- **색상을 커스터마이징할 수 있나요?** 예, 모든 `java.awt.Color`를 사용할 수 있습니다  
- **회전이 지원되나요?** 예, `AffineTransform`을 사용해 그라디언트를 회전시킬 수 있습니다  
- **생성되는 출력 형식은?** 표준 PostScript(.ps) 파일  
- **프로덕션에 라이선스가 필요합니까?** 예, 상업용 라이선스가 필요합니다  

## 사전 요구 사항
튜토리얼을 시작하기 전에 다음 사전 요구 사항이 준비되어 있는지 확인하세요:
- 머신에 설치된 Java Development Kit (JDK)  
- Aspose.Page for Java 라이브러리. [여기](https://releases.aspose.com/page/java/)에서 다운로드할 수 있습니다.

## 패키지 가져오기
Java 프로젝트에서 시작하기 위해 필요한 패키지를 가져옵니다:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

이제 Java PostScript에 수직 그라디언트를 추가하는 과정을 여러 단계로 나누어 살펴보겠습니다.

## Java에서 PostScript 그라디언트 만드는 방법
아래는 Aspose.Page API를 사용하여 **Java에서 PostScript 그라디언트를 만드는** 정확한 단계별 가이드입니다.

### 단계 1: 문서 디렉터리 설정
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 단계 2: PostScript 문서를 위한 출력 스트림 생성
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### 단계 3: A4 크기로 저장 옵션 만들기
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### 단계 4: 새 PS 문서 만들기
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 단계 5: 사각형 생성
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### 단계 6: 그라디언트를 위한 색상 및 비율 설정
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### 단계 7: 그라디언트 변환 만들기
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### 단계 8: 수직 선형 그라디언트 페인트 만들기
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### 단계 9: 페인트 설정 및 사각형 채우기
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### 단계 10: 현재 페이지 닫고 문서 저장
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

축하합니다! Aspose.Page for Java를 사용하여 Java PostScript 문서에 수직 그라디언트를 성공적으로 추가했습니다.

## PostScript에서 수직 그라디언트를 사용하는 이유
수직 그라디언트는 파일 크기를 크게 늘리지 않으면서 페이지에 깊이와 시각적 흥미를 부여합니다. 특히 다음과 같은 경우에 유용합니다:
- 보고서 헤더 및 푸터  
- 차트나 다이어그램의 배경 채우기  
- 기술 문서의 섹션 강조  

## 일반적인 문제와 해결 방법
- **그라디언트가 평평하게 보임:** `AffineTransform` 스케일이 사각형 크기와 일치하는지 확인하세요.  
- **색상이 흐릿함:** 올바른 `ColorSpaceType`(SRGB)을 사용하고, 비율 배열이 0.0부터 1.0까지 순서대로 정렬되어 있는지 확인하세요.  
- **파일이 생성되지 않음:** 출력 디렉터리(`dataDir`)가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인하세요.  

## 자주 묻는 질문
### Aspose.Page for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?
예, Aspose.Page for Java는 다른 Java 라이브러리와 원활하게 작동하도록 설계되었습니다.

### Aspose.Page for Java의 무료 체험판이 있나요?
예, 무료 체험판을 [여기](https://releases.aspose.com/)에서 받을 수 있습니다.

### 추가 문서는 어디서 찾을 수 있나요?
자세한 문서는 [여기](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

### Aspose.Page for Java를 어떻게 구매하나요?
구매는 [여기](https://purchase.aspose.com/buy)에서 진행할 수 있습니다.

### Aspose.Page 관련 포럼이 있나요?
예, 커뮤니티 포럼은 [여기](https://forum.aspose.com/c/page/39)에서 참여할 수 있습니다.

## 추가 자주 묻는 질문

**Q: 다른 그라디언트 방향(수평, 대각선)도 만들 수 있나요?**  
A: 물론입니다. `LinearGradientPaint`의 시작점과 끝점을 조정하고 `AffineTransform`의 회전 각도를 변경하면 됩니다.

**Q: PDF 출력에서도 동일하게 작동하나요?**  
A: 동일한 그라디언트 로직을 `PsSaveOptions` 대신 `PdfSaveOptions`를 사용하여 PDF 저장 시에도 적용할 수 있습니다.

**Q: 그라디언트 크기를 동적으로 변경하려면 어떻게 해야 하나요?**  
A: 런타임에 사각형 크기를 계산하고 해당 값을 `Rectangle2D`와 `AffineTransform` 생성자에 전달하면 됩니다.

---

**마지막 업데이트:** 2025-12-09  
**테스트 환경:** Aspose.Page for Java 24.11 (최신)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}