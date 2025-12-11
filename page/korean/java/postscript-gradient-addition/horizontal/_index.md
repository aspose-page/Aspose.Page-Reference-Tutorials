---
date: 2025-12-07
description: Aspose.Page for Java와 Linear Gradient Paint Java를 사용하여 Java PostScript에
  수평 그라디언트를 추가하는 방법을 배워보세요.
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: Java PostScript에 Linear Gradient Paint를 사용하여 그라디언트 추가
url: /ko/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript에서 Linear Gradient Paint Java를 사용하여 그라디언트 추가

## 소개
이 포괄적인 튜토리얼에서는 **Linear Gradient Paint Java**를 활용하여 PostScript 문서에 아름다운 수평 그라디언트를 만드는 방법을 알아봅니다. Aspose.Page for Java는 PostScript, PDF 및 기타 벡터 형식을 쉽게 다룰 수 있게 해 주며, `LinearGradientPaint` 클래스는 색상 전환을 세밀하게 제어할 수 있게 해 줍니다. 이 가이드를 마치면 도형 **및** 텍스트에 그라디언트를 적용하여 문서를 전문적이고 눈에 띄게 만들 수 있습니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Page for Java (Linear Gradient Paint Java 지원).  
- **구현 시간은?** 기본 그라디언트는 약 10‑15분 소요.  
- **라이선스가 필요합니까?** 프로덕션 사용을 위해 임시 또는 정식 라이선스가 필요합니다.  
- **지원되는 JDK 버전은?** Java 8 이상.  
- **그라디언트를 도형과 텍스트 모두에 사용할 수 있나요?** 예 – 동일한 그라디언트로 도형을 채우고 텍스트를 스트로크하거나 채울 수 있습니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있는지 확인하세요:

- 머신에 Java Development Kit (JDK) 설치.  
- Aspose.Page for Java 라이브러리. [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)에서 다운로드할 수 있습니다.

## 패키지 가져오기
Java 프로젝트에서 필요한 패키지를 가져오는 것으로 시작합니다. 이러한 import 문을 통해 그래픽 기본 요소, 그라디언트 처리 및 Aspose.Page API에 접근할 수 있습니다.

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

## 단계 1: 사각형 만들기
먼저 출력 스트림, 문서 및 그라디언트를 담을 사각형을 설정합니다.

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

## 단계 2: 수평 Linear Gradient Paint 만들기
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

## 단계 3: 사각형 채우기
앞서 정의한 그라디언트를 사용해 사각형을 채웁니다.

```java
// Fill the rectangle
document.fill(rectangle);
```

## 단계 4: 텍스트를 그라디언트로 채우기
같은 그라디언트를 텍스트에 적용하여 강렬한 시각 효과를 만들 수도 있습니다.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## 단계 5: 텍스트를 그라디언트로 스트로크하기
마지막으로, 그라디언트를 스트로크 색상으로 사용해 텍스트 외곽선을 그립니다.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## 일반적인 문제 및 해결책
| 문제 | 발생 원인 | 해결 방법 |
|------|-----------|-----------|
| 그라디언트가 늘어남 | `AffineTransform` 스케일링이 잘못됨 | 변환의 너비와 높이가 사각형 크기(예시에서는 200 × 100)와 일치하도록 확인하세요. |
| 색상이 흐릿함 | 알파 값이 너무 낮게 설정됨 | `new Color(r,g,b,alpha)`에서 네 번째 값인 알파 컴포넌트를 높이세요. |
| 텍스트가 보이지 않음 | 텍스트를 그리기 전에 Paint가 설정되지 않음 | `document.setPaint(paint)`를 `fillAndStrokeText` 또는 `outlineText` 호출 **이전**에 호출하세요. |

## 자주 묻는 질문
### Aspose.Page for Java를 상업 프로젝트에 사용할 수 있나요?
예, Aspose.Page for Java는 상업 프로젝트에 사용할 수 있습니다. 라이선스 상세 내용은 [Aspose.Purchase](https://purchase.aspose.com/buy)에서 확인하세요.

### 무료 체험판이 있나요?
예, Aspose.Page for Java의 무료 체험판을 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.

### 추가 문서와 지원은 어디서 찾을 수 있나요?
포괄적인 리소스는 [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)을 방문하세요. 커뮤니티 지원은 [Aspose.Page forum](https://forum.aspose.com/c/page/39)에서 확인할 수 있습니다.

### 임시 라이선스는 어떻게 얻나요?
임시 라이선스는 [Aspose.Purchase](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

### Aspose.Page for Java의 시스템 요구 사항은 무엇인가요?
자세한 시스템 요구 사항은 [documentation](https://reference.aspose.com/page/java/)을 참고하세요.

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}