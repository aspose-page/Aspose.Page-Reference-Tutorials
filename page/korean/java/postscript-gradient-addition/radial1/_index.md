---
date: 2026-09-09
description: Aspose.Page를 사용하여 Java PostScript에서 radial gradient를 만드는 방법을 배웁니다. 이
  단계별 가이드는 color stops gradient를 추가하고, radii를 설정하며, PS 파일을 빠르게 생성하는 방법을 보여줍니다.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Java에서 radial gradients 마스터하기
og_description: Aspose.Page를 사용하여 Java PostScript에서 radial gradient를 만드는 방법을 배웁니다.
  이 가이드는 color stops gradient를 추가하고, radii를 설정하며, 몇 분 안에 PS 파일을 생성하는 방법을 설명합니다.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Java PostScript에서 radial gradient 만들기 방법
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Java PostScript에서 radial gradient 만들기 방법
url: /ko/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript에서 Aspose.Page를 사용하여 방사형 그라디언트 만들기

## 소개
PostScript 파일 안에 **방사형 그라디언트**를 만들어야 한다면, 올바른 곳에 오셨습니다. 이 튜토리얼에서는 **Aspose.Page for Java**를 사용하여 부드러운 방사형 그라디언트를 포함한 PostScript 문서를 생성하는 데 필요한 모든 단계를 안내합니다. 끝까지 읽으면 API를 이해하고, 완전한 실행 예제를 확인하며, 색상, 위치 및 반경을 원하는 디자인 시나리오에 맞게 조정하는 방법을 알게 됩니다.

## 빠른 답변
- **PostScript에서 방사형 그라디언트를 생성하는 라이브러리는 무엇인가요?** Aspose.Page for Java.  
- **구현에 얼마나 걸리나요?** 기본 예제의 경우 약 10‑15분 정도 소요됩니다.  
- **코드를 실행하려면 라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇인가요?** Java 8 이상.  
- **그라디언트 모양을 변경할 수 있나요?** 예 – `RadialGradientPaint` 생성자에서 반경과 중심점을 조정하면 됩니다.

## Java에서 방사형 그라디언트 만드는 방법
Java 프로젝트를 로드하고 필요한 클래스를 가져온 다음 아래 단계별 가이드를 따라 주세요. 핵심은 색상 스톱을 지정한 `RadialGradientPaint` 객체를 생성하고 이를 `PsDocument`에 그린 사각형에 적용하는 것입니다. 이 두 객체 접근 방식은 모든 저수준 PostScript 명령을 자동으로 처리해 줍니다.

## 방사형 그라디언트란?
`RadialGradientPaint`는 중앙점에서 바깥쪽으로 원형 색상 전환을 정의하는 Java AWT 클래스입니다. 여러 색상 스톱을 부드럽게 혼합하여 스포트라이트, 부드러운 배경 또는 색상이 초점에서 방사되는 모든 효과에 이상적입니다.

## 왜 방사형 그라디언트에 Aspose.Page를 사용하나요?
Aspose.Page는 저수준 PS 구문 처리를 자동화하면서 PostScript 출력에 대한 완전한 프로그래밍 제어를 제공합니다. **50개 이상의 입력 및 출력 형식**을 지원하고, 전체 파일을 메모리에 로드하지 않고도 수백 페이지 문서를 렌더링할 수 있으며, Java 8+을 지원하는 모든 운영 체제에서 실행됩니다. 이러한 정량적 기능은 엔터프라이즈급 그래픽 생성에 신뢰할 수 있는 선택이 됩니다.

## 전제 조건
- **Java Development Kit (JDK) 8+** – `java -version`으로 확인하십시오.  
- **Aspose.Page for Java** – 공식 [Aspose.Page download page](https://releases.aspose.com/page/java/)에서 최신 JAR를 다운로드합니다.  
- **선호하는 IDE** – Eclipse, IntelliJ IDEA, 또는 Java 확장 기능이 있는 VS Code.  
- **쓰기 가능한 폴더** – 생성된 `.ps` 파일이 저장될 위치.

## 패키지 가져오기
먼저, 필요한 클래스를 가져옵니다. `java.awt` 패키지는 그라디언트 페인트 객체를 제공하고, `com.aspose.eps`는 PostScript 문서 처리 클래스를 포함합니다.

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

## 단계별 가이드

### 1단계: 사각형을 만들고 PS 문서를 엽니다
`PsDocument`는 Aspose.Page의 클래스이며 PostScript 문서를 나타내고 도형, 텍스트 및 이미지를 그리는 메서드를 제공합니다. 출력 스트림을 만들고 페이지 크기(A4 기본)를 설정한 뒤, 그라디언트를 적용할 사각형을 정의합니다.

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

### 2단계: 색상 및 비율 정의
방사형 그라디언트는 *색상 스톱*(색상)과 *비율*(스톱의 상대 위치)으로 구성됩니다. 여기서는 6가지 색상과 해당 비율 배열을 생성합니다.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Why this matters:** `fractions`를 조정하면 색상이 전환되는 속도를 제어할 수 있어 미묘하거나 극적인 효과를 만들 수 있습니다.

### 3단계: 방사형 그라디언트 페인트 생성
`RadialGradientPaint`는 중심점, 반경, 초점점, 비율, 색상, 사이클 방식 및 색상 공간을 포함한 방사형 색상 그라디언트를 설명하는 핵심 클래스입니다. 이제 위에서 정의한 배열을 사용해 `RadialGradientPaint` 객체를 만듭니다.

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

> **Note:** 추가 스케일링이나 회전이 필요하지 않다면 `transform`은 `null`일 수 있습니다. 기울어진 그라디언트를 위해 `AffineTransform`을 실험해 보세요.

### 4단계: 페인트 설정 및 사각형 채우기
페인트가 준비되면 `PsDocument`에 적용하고 앞서 정의한 사각형을 채웁니다.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

이 시점에서 PostScript 페이지에는 우리가 설정한 방사형 그라디언트가 부드럽게 채워진 사각형이 포함됩니다.

### 5단계: 문서 닫기 및 저장
마지막으로 현재 페이지를 닫고 파일을 디스크에 씁니다.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

`RadialGradient1_outPS.ps` 파일을 任意의 PostScript 뷰어(예: Ghostscript)에서 열면 정의한 대로 그라디언트가 정확히 렌더링된 것을 확인할 수 있습니다.

## 일반적인 문제 및 해결책
| 증상 | 가능한 원인 | 해결 방법 |
|---------|--------------|-----|
| 그라디언트가 단색으로 표시됨 | `fractions` 배열이 `0.0f`로 시작하지 않거나 `1.0f`로 끝나지 않음 | 첫 번째 fraction이 `0.0f`이고 마지막이 `1.0f`인지 확인하십시오. |
| 색상이 흐릿하게 보임 | `ColorSpaceType`을 잘못 사용함 | 보다 선명한 출력을 위해 `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB`로 전환하십시오. |
| 출력 파일이 생성되지 않음 | `FileOutputStream` 경로가 잘못되었거나 쓰기 권한이 없음 | `dataDir`가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인하십시오. |

## 자주 묻는 질문

**Q: Aspose.Page for Java를 상용 프로젝트에 사용할 수 있나요?**  
A: 예. 상용 환경에서는 상업용 라이선스가 필요합니다. 라이선스는 [Aspose licensing page](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

**Q: 공식 API 레퍼런스는 어디에서 찾을 수 있나요?**  
A: 전체 문서는 [Aspose.Page Java API reference](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

**Q: 테스트용 무료 체험판이 있나요?**  
A: 물론입니다. [Aspose.Page releases page](https://releases.aspose.com/)에서 체험판을 다운로드하십시오.

**Q: 평가용 임시 라이선스는 어떻게 얻나요?**  
A: 임시 라이선스는 [temporary license request page](https://purchase.aspose.com/temporary-license/)에서 요청할 수 있습니다.

**Q: 커뮤니티 지원은 어디서 받을 수 있나요?**  
A: [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39)에서 Aspose.Page 커뮤니티 포럼에 참여하세요.

## 결론
이제 Aspose.Page를 사용해 Java PostScript 문서에 **방사형 그라디언트**를 만드는 방법을 알게 되었습니다. 사각형 크기, 색상 스톱 및 그라디언트 반경을 조정하면 미묘한 배경 채우기부터 강렬한 스포트라이트 그래픽까지 무한한 시각 효과를 만들 수 있습니다. `AffineTransform` 값을 실험해 그라디언트를 회전하거나 기울이고, 텍스트와 이미지를 결합해 더 풍부한 PDF 또는 EPS 출력물을 만들어 보세요.

---

**마지막 업데이트:** 2026-09-09  
**테스트 환경:** Aspose.Page for Java 최신 버전 (작성 시점)  
**작성자:** Aspose

## 관련 튜토리얼

- [그라디언트로 도형 채우기: Java PostScript 방사형 예제](/page/java/postscript-gradient-addition/radial2/)
- [Java에서 PostScript 그라디언트 만들기 – 수직 그라디언트 추가](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page 투명도 튜토리얼 – Java PostScript에 투명도 추가](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}