---
date: 2026-09-04
description: Aspose.Page Java를 사용하여 Java PostScript에 그라디언트를 추가하는 방법을 배우고, LinearGradientPaint를
  이용해 대각선 색상 전환을 만들어 생동감 있는 문서를 만들 수 있습니다.
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: '그라디언트를 추가하는 방법: Aspose.Page Java를 사용한 Java PostScript에서 대각선 그라디언트'
og_description: Aspose.Page Java를 사용하여 Java PostScript에 그라디언트를 추가하는 방법을 배웁니다. 이 가이드는
  몇 단계만으로 LinearGradientPaint를 사용해 대각선 그라디언트를 만드는 방법을 보여줍니다.
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: Aspose.Page Java와 함께 Java PostScript에 그라디언트를 추가하는 방법
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: '그라디언트를 추가하는 방법: Aspose.Page Java를 사용한 Java PostScript에서 대각선 그라디언트'
url: /ko/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript에서 Aspose.Page Java를 사용하여 대각선 그라디언트 추가

## 소개
PostScript 파일에 부드러운 대각선 색상 전환을 추가하고 싶다면 **Aspose.Page Java**가 놀라울 정도로 쉽게 해줍니다. 이 튜토리얼에서는 Java 2D의 `LinearGradientPaint` 클래스를 사용하여 **그라디언트를 추가하는 방법**을 단계별로 배웁니다. 마지막에는 활기찬 대각선 그라디언트를 가진 PostScript 문서를 생성하는 실행 가능한 코드를 얻으며, 이 접근 방식이 원시 PostScript 명령을 직접 코딩하는 것보다 유지 관리가 더 용이한 이유를 이해하게 됩니다.

## Java PostScript에서 그라디언트 추가 방법
그라디언트를 추가하는 것은 그래픽 전용 작업처럼 들릴 수 있지만, Aspose.Page를 사용하면 순수 Java 환경에서 기본 PostScript 명령을 완전히 제어할 수 있습니다. 이 섹션에서는 이 접근 방식이 왜 작동하는지와 원시 PostScript를 직접 코딩하는 것에 비해 얻을 수 있는 이점을 설명합니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Page for Java.  
- **그라디언트를 생성하는 클래스는?** `LinearGradientPaint`.  
- **색상을 변경할 수 있나요?** 예 – `Color[]` 배열을 수정하면 됩니다.  
- **프로덕션에 라이선스가 필요합니까?** 상업용 라이선스가 필요하며, 무료 체험판을 사용할 수 있습니다.  
- **구현에 걸리는 시간은?** 기본 그라디언트의 경우 약 10 분 정도 소요됩니다.

## Aspose.Page Java란?
Aspose.Page Java는 외부 소프트웨어 없이도 개발자가 PostScript 및 PDF 파일을 생성, 편집 및 변환할 수 있는 완전한 기능을 갖춘 API입니다. 이 라이브러리는 **50개 이상의 입력 및 출력 형식**을 지원하며, **500페이지 이상의 문서**도 메모리 사용량을 100 MB 이하로 유지하면서 처리할 수 있습니다.

## 왜 대각선 그라디언트를 사용하나요?
대각선 그라디언트는 차트, 배너 또는 현대적인 외관이 필요한 모든 그래픽 요소에 깊이와 시각적 흥미를 더합니다. 그라디언트가 한 모서리에서 반대 모서리까지 흐르기 때문에 배경, 버튼 스킨, 장식 형태 등에 잘 어울리며, 추가 이미지 자산 없이도 전문적인 마무리를 제공합니다.

## 전제 조건
- Java Development Kit (JDK) 8 이상.  
- Eclipse, IntelliJ IDEA, VS Code와 같은 IDE.  
- **Aspose.Page for Java** 라이브러리 – 최신 버전은 [공식 다운로드 페이지](https://releases.aspose.com/page/java/)에서 다운로드합니다.

## 패키지 가져오기
`java.awt` 패키지는 핵심 그래픽 클래스를 제공하고, `com.aspose.page` 패키지는 PostScript 전용 API에 접근할 수 있게 해줍니다.

`LinearGradientPaint` 클래스는 Aspose.Page가 Java 2D 그라디언트 기능과 연결하는 다리 역할을 합니다.  
`AffineTransform`은 그라디언트를 회전 및 스케일링하여 대각선으로 정렬할 수 있게 합니다.

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

## Step 1: PostScript 문서를 위한 출력 스트림 생성
먼저 파일이 저장될 폴더를 정의하고 `FileOutputStream`을 엽니다. 이 스트림은 생성된 PostScript 데이터를 받습니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Step 2: A4 크기로 저장 옵션 생성
`PsSaveOptions`를 사용하면 페이지 크기, 해상도 및 기타 출력 설정을 지정할 수 있습니다. 여기서는 기본 A4 크기(72 dpi에서 595 × 842 포인트)를 사용합니다.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Step 3: 새로운 PS 문서 생성
`PsDocument` 클래스는 PostScript 문서를 나타내며 페이지 생성 및 그래픽 그리기 메서드를 제공합니다.  
출력 스트림과 저장 옵션을 사용하여 `PsDocument`를 인스턴스화합니다. `false` 플래그는 생성자가 자동으로 새 페이지를 열지 않도록 지정하며, 우리는 나중에 페이지를 열 것입니다.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Step 4: 사각형 생성
그라디언트 채우기를 받을 사각형을 정의합니다. 사각형의 위치는 (200, 100)이며 크기는 (200 × 100)으로, 그라디언트를 명확히 볼 수 있도록 선택했습니다.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Step 5: 그라디언트 변환 생성
`AffineTransform`을 사용하면 그라디언트를 회전, 스케일 및 이동시켜 사각형을 대각선으로 가로지르게 할 수 있습니다. 아래 수식은 빗변을 계산하고 그에 따라 스케일 비율을 조정합니다.

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

## Step 6: 대각선 선형 그라디언트 페인트 생성
`LinearGradientPaint`는 색상 전환을 생성하는 핵심 클래스입니다. 이전에 정의한 변환을 사용하여 사각형의 왼쪽 위에서 오른쪽 아래까지 적용됩니다. `MultipleGradientPaint.CycleMethod.NO_CYCLE`은 그라디언트가 반복되지 않도록 보장합니다.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Step 7: 페인트 설정 및 사각형 채우기
그라디언트 페인트를 문서에 적용하고 사각형 형태를 채웁니다. 이 단계에서 대각선 색상 전환이 PostScript 페이지에 렌더링됩니다.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Step 8: 현재 페이지 닫기 및 문서 저장
마지막으로 페이지를 닫고 스트림을 플러시한 뒤 파일을 저장합니다. 결과물인 `DiagonalGradient_outPS.ps` 파일은 모든 PostScript 뷰어에서 열 수 있습니다.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## 일반적인 문제 및 팁
- **그라디언트가 평평하게 보임** – 회전 각도를 다시 확인하세요; 45° 회전이 진정한 대각선을 만듭니다.  
- **색상이 흐릿함** – 정확한 색상 렌더링을 위해 `MultipleGradientPaint.ColorSpaceType.SRGB`를 사용하고 있는지 확인하세요.  
- **파일을 찾을 수 없음 오류** – `dataDir`이 존재하는 폴더를 가리키는지와 애플리케이션에 쓰기 권한이 있는지 확인하세요.  
- **대용량 문서에서 메모리 급증** – 메모리 사용량을 줄이려면 `PsSaveOptions.setCompress(true)`를 사용하세요.

## 자주 묻는 질문
**Q: 이 라이브러리를 Java에서 다른 그래픽 작업에도 사용할 수 있나요?**  
A: 예, Aspose.Page for Java는 다양한 그리기 기본 요소, 텍스트 렌더링 및 이미지 처리 기능을 완전하게 제공합니다.

**Q: Aspose.Page Java에 대한 무료 체험판이 있나요?**  
A: 물론입니다. [Aspose 무료 체험 페이지](https://releases.aspose.com/)에서 완전 기능을 갖춘 체험판을 다운로드할 수 있습니다.

**Q: Aspose.Page Java에 대한 문서는 어디서 찾을 수 있나요?**  
A: 공식 API 레퍼런스는 [Aspose.Page Java API reference](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

**Q: Aspose.Page Java 라이선스를 어떻게 구매할 수 있나요?**  
A: 라이선스는 [Aspose 구매 포털](https://purchase.aspose.com/buy)에서 직접 구매할 수 있습니다.

**Q: 도움이 필요하거나 질문이 있나요?**  
A: Aspose 엔지니어와 다른 개발자들의 도움을 받을 수 있는 커뮤니티 운영 [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)을 방문하세요.

---

**마지막 업데이트:** 2026-09-04  
**테스트 환경:** Aspose.Page for Java 24.12 (latest)  
**작성자:** Aspose

## 관련 튜토리얼
- [Aspose.Page for Java를 사용하여 PostScript에서 방사형 그라디언트 만들기](/page/java/postscript-gradient-addition/)
- [Linear Gradient Paint를 사용하여 Java PostScript에 그라디언트 추가 방법](/page/java/postscript-gradient-addition/horizontal/)
- [Java에서 PostScript 그라디언트 만들기 – 수직 그라디언트 추가](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}