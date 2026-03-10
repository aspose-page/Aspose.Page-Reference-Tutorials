---
date: 2026-02-13
description: Aspose.Page for Java를 사용하여 Java PostScript에 Linear Gradient Paint Java로
  그라디언트를 추가하는 방법을 배워보세요.
linktitle: How to Add Gradient in Java PostScript with Linear Gradient Paint
second_title: Aspose.Page Java API
title: Java PostScript에서 Linear Gradient Paint를 사용해 그라디언트를 추가하는 방법
url: /ko/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript에서 Linear Gradient Paint를 사용하여 그라디언트 추가하는 방법

## 소개
이 포괄적인 튜토리얼에서는 Java를 사용하여 PostScript 문서에 **그라디언트를 추가하는 방법**을 알아봅니다. **Linear Gradient Paint Java** 클래스를 활용하여 아름다운 수평 그라디언트를 만드는 과정을 단계별로 안내합니다. Aspose.Page for Java를 사용하면 도형 **및** 텍스트 모두에 그라디언트를 렌더링할 수 있어 문서가 세련되고 눈에 띄는 외관을 갖게 됩니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Page for Java (Linear Gradient Paint Java 지원).  
- **구현 소요 시간은?** 기본 그라디언트는 약 10‑15분 정도 걸립니다.  
- **라이선스가 필요합니까?** 프로덕션 사용을 위해 임시 또는 정식 라이선스가 필요합니다.  
- **지원되는 JDK 버전은?** Java 8 이상.  
- **그라디언트를 도형과 텍스트 모두에 사용할 수 있나요?** 예 – 동일한 그라디언트로 도형을 채우고 텍스트를 스트로크하거나 채울 수 있습니다.

## 수평 그라디언트란 무엇이며 왜 사용하나요?
수평 그라디언트는 도형이나 텍스트 전체에 걸쳐 왼쪽에서 오른쪽으로 색상을 부드럽게 혼합합니다. 현대적인 UI 요소, 강조된 헤딩, 혹은 보고서의 은은한 배경 효과를 만들기에 이상적입니다. **Linear Gradient Paint Java**를 사용하면 시작 색상과 종료 색상, 투명도, 스케일을 정확히 정의할 수 있어 결과물이 어떤 디바이스에서도 선명하게 표시됩니다.

## 전제 조건
- Java Development Kit (JDK)이 머신에 설치되어 있어야 합니다.  
- Aspose.Page for Java 라이브러리. [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)에서 다운로드할 수 있습니다.

## 패키지 가져오기
Java 프로젝트에서 필요한 패키지를 가져오는 것으로 시작합니다. 이러한 import를 통해 그래픽 기본 요소, 그라디언트 처리 및 Aspose.Page API에 접근할 수 있습니다.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 1단계: 사각형 만들기
먼저, 출력 스트림, 문서, 그리고 그라디언트를 적용할 사각형을 설정합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## 2단계: 수평 Linear Gradient Paint 만들기
여기서는 수평 색상 전환을 정의하는 **Linear Gradient Paint Java** 객체를 생성합니다. `AffineTransform`은 사각형의 너비와 높이에 맞게 그라디언트를 스케일링합니다.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## 3단계: 사각형 채우기
이제 방금 정의한 그라디언트로 사각형을 채웁니다.

```java
// Fill the rectangle
document.fill(rectangle);
```

## 4단계: 텍스트에 그라디언트 채우기
같은 그라디언트를 텍스트에 적용하여 강렬한 시각 효과를 만들 수도 있습니다.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## 5단계: 텍스트에 그라디언트 스트로크 적용
마지막으로, 그라디언트를 스트로크 색상으로 사용하여 텍스트를 외곽선 처리합니다.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## 일반적인 문제 및 해결책

| 문제 | 발생 원인 | 해결 방법 |
|-------|----------------|-----|
| 그라디언트가 늘어짐 | `AffineTransform` 스케일링이 올바르지 않음 | 변환의 너비와 높이가 사각형의 크기(예시에서는 200 × 100)와 일치하도록 확인하세요. |
| 색상이 흐림 | 알파 값이 너무 낮게 설정됨 | 알파 구성 요소(`new Color(r,g,b,alpha)`의 네 번째 값)를 높이세요. |
| 텍스트가 보이지 않음 | 텍스트를 그리기 전에 페인트가 설정되지 않음 | `fillAndStrokeText` 또는 `outlineText` 호출 전에 `document.setPaint(paint)`를 **먼저** 호출하세요. |

## 자주 묻는 질문

**Q:** Aspose.Page for Java를 상업 프로젝트에 사용할 수 있나요?  
**A:** 예, Aspose.Page for Java는 상업 프로젝트에 사용할 수 있습니다. 라이선스 상세는 [Aspose.Purchase](https://purchase.aspose.com/buy)에서 확인하세요.

**Q:** 무료 체험판이 있나요?  
**A:** 예, Aspose.Page for Java의 무료 체험판을 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.

**Q:** 추가 문서와 지원은 어디서 찾을 수 있나요?  
**A:** 포괄적인 자료는 [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)을 방문하세요. 커뮤니티 지원은 [Aspose.Page forum](https://forum.aspose.com/c/page/39)에서 확인할 수 있습니다.

**Q:** 임시 라이선스를 어떻게 얻을 수 있나요?  
**A:** [Aspose.Purchase](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 받을 수 있습니다.

**Q:** Aspose.Page for Java의 시스템 요구 사항은 무엇인가요?  
**A:** 자세한 시스템 요구 사항은 [documentation](https://reference.aspose.com/page/java/)을 참고하세요.

**마지막 업데이트:** 2026-02-13  
**테스트 환경:** Aspose.Page for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}