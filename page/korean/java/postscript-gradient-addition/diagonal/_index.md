---
date: 2025-12-07
description: Aspose.Page Java를 사용하여 Java PostScript 문서에 대각선 그라디언트를 적용하세요. Java에서 LinearGradientPaint를
  사용해 그라디언트 효과를 추가하고, 손쉽게 생동감 있는 색상 전환을 만들어 보세요.
language: ko
linktitle: Add Diagonal Gradient in Java PostScript using Aspose.Page Java
second_title: Aspose.Page Java API
title: Aspose.Page Java를 사용하여 Java PostScript에 대각선 그라데이션 추가
url: /java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java를 사용한 Java PostScript에 대각선 그라디언트 추가

## 소개
PostScript 파일에 부드러운 대각선 색상 전환을 추가하고 싶다면 **Aspose.Page Java**가 놀라울 정도로 쉽게 해줍니다. 이 튜토리얼에서는 Java 2D의 `LinearGradientPaint` 클래스를 사용하여 **how to add gradient** 효과를 단계별로 살펴봅니다. 마지막에는 활기찬 대각선 그라디언트를 가진 PostScript 문서를 생성하는 실행 가능한 코드 스니펫을 얻을 수 있습니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Page for Java.  
- **그라디언트를 생성하는 클래스는?** `LinearGradientPaint`.  
- **색상을 변경할 수 있나요?** 예 – `Color[]` 배열을 수정하면 됩니다.  
- **프로덕션에 라이선스가 필요합니까?** 상업용 라이선스가 필요합니다; 무료 체험판을 제공합니다.  
- **구현에 걸리는 시간은?** 기본 그라디언트의 경우 약 10 분 정도 소요됩니다.

## Aspose.Page Java란?
Aspose.Page Java는 외부 소프트웨어 없이도 개발자가 PostScript 및 PDF 파일을 생성, 편집 및 변환할 수 있게 해주는 강력한 API입니다. 깨끗하고 객체 지향적인 Java 인터페이스를 통해 PostScript 언어의 전체 그래픽 기능을 노출합니다.

## 왜 대각선 그라디언트를 사용하나요?
대각선 그라디언트는 차트, 배너 또는 현대적인 느낌이 필요한 모든 그래픽 요소에 깊이와 시각적 흥미를 더합니다. 그라디언트가 한 모서리에서 반대 모서리로 흐르기 때문에 배경, 버튼 스킨, 장식 형태 등에 적합합니다.

## 사전 요구 사항
시작하기 전에 다음이 준비되어 있는지 확인하세요:

- Java Development Kit (JDK) 8 이상.  
- Eclipse, IntelliJ IDEA, VS Code와 같은 IDE.  
- **Aspose.Page for Java** 라이브러리 – 최신 버전을 [공식 다운로드 페이지](https://releases.aspose.com/page/java/)에서 다운로드하세요.

## 패키지 가져오기
먼저 Java 2D와 Aspose 클래스를 가져옵니다. 이러한 임포트를 통해 색상 정의, 기하학적 도형, 그라디언트 페인팅 및 PostScript 문서 API에 접근할 수 있습니다.

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

## 단계 1: PostScript 문서를 위한 출력 스트림 생성
파일이 저장될 폴더를 정의하고 `FileOutputStream`을 엽니다. 이 스트림은 생성된 PostScript 데이터를 받게 됩니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## 단계 2: A4 크기로 저장 옵션 생성
`PsSaveOptions`를 사용하면 페이지 크기, 해상도 및 기타 출력 설정을 지정할 수 있습니다. 여기서는 기본 A4 크기를 사용합니다.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## 단계 3: 새 PS 문서 생성
출력 스트림과 저장 옵션을 사용해 `PsDocument`를 인스턴스화합니다. `false` 플래그는 생성자가 자동으로 새 페이지를 열지 않도록 하며, 우리는 나중에 페이지를 열 것입니다.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 단계 4: 사각형 생성
그라디언트 채우기를 적용할 사각형을 정의합니다. 사각형의 위치(200, 100)와 크기(200 × 100)는 그라디언트를 명확히 보이게 하기 위해 선택되었습니다.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## 단계 5: 그라디언트 변환 생성
`AffineTransform`을 사용해 그라디언트를 회전, 스케일 및 이동시켜 사각형을 대각선으로 가로지르게 합니다. 아래 수식은 빗변을 계산하고 스케일 비율을 조정합니다.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## 단계 6: 대각선 선형 그라디언트 페인트 생성
여기가 **how to add gradient**의 핵심입니다 – 사각형의 좌상단에서 우하단까지 확장되는 `LinearGradientPaint`를 이전에 정의한 변환과 함께 만듭니다. `MultipleGradientPaint.CycleMethod.NO_CYCLE`은 그라디언트가 반복되지 않도록 합니다.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## 단계 7: 페인트 설정 및 사각형 채우기
그라디언트 페인트를 문서에 적용하고 사각형 형태를 채웁니다. 이 단계에서 대각선 색상 전환이 PostScript 페이지에 렌더링됩니다.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## 단계 8: 현재 페이지 닫기 및 문서 저장
마지막으로 페이지를 닫고 스트림을 플러시한 뒤 파일을 저장합니다. 생성된 `DiagonalGradient_outPS.ps` 파일은 모든 PostScript 뷰어에서 열 수 있습니다.

```java
// Close current page and save the document
document.closePage();
document.save();
```

위의 여덟 단계를 따라 **Aspose.Page Java**를 사용해 PostScript 문서에 대각선 그라디언트를 성공적으로 추가했습니다. 다양한 색상, 각도 및 사각형 크기로 실험해 맞춤형 시각 효과를 만들어 보세요.

## 일반적인 문제 및 팁
- **그라디언트가 평평하게 보임** – 회전 각도를 다시 확인하세요; 45° 회전이 진정한 대각선을 만듭니다.  
- **색상이 흐릿함** – 정확한 색상 렌더링을 위해 `MultipleGradientPaint.ColorSpaceType.SRGB`를 사용하고 있는지 확인하세요.  
- **파일을 찾을 수 없음 오류** – `dataDir`가 존재하는 폴더를 가리키는지, 애플리케이션에 쓰기 권한이 있는지 검증하세요.

## 자주 묻는 질문

**Q: 이 라이브러리를 Java에서 다른 그래픽 작업에도 사용할 수 있나요?**  
A: 예, Aspose.Page for Java는 풍부한 그리기 원시 요소, 텍스트 렌더링 및 이미지 처리 기능을 제공합니다.

**Q: Aspose.Page Java에 무료 체험판이 있나요?**  
A: 물론입니다. [Aspose 무료 체험 페이지](https://releases.aspose.com/)에서 완전 기능 체험판을 다운로드할 수 있습니다.

**Q: Aspose.Page Java 문서는 어디서 찾을 수 있나요?**  
A: 공식 API 레퍼런스는 [여기](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

**Q: Aspose.Page Java 라이선스는 어떻게 구매하나요?**  
A: 라이선스는 [Aspose 구매 포털](https://purchase.aspose.com/buy)에서 직접 구매할 수 있습니다.

**Q: 도움이 필요하거나 질문이 있나요?**  
A: Aspose 엔지니어와 다른 개발자들이 활동하는 커뮤니티 기반 [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)에서 도움을 받을 수 있습니다.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}