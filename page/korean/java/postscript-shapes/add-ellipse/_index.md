---
date: 2026-10-31
description: Aspose.Page를 사용하여 Java PostScript에서 paint color를 설정하고 ellipse를 채우는 방법을
  배웁니다. 이 가이드는 ellipse를 채우고, ellipse 외곽선을 그리며, stroke thickness를 설정하는 명확한 코드 단계들을
  보여줍니다.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Java PostScript에 Ellipse 추가
og_description: Aspose.Page를 사용하여 Java PostScript에서 ellipse를 채우고 paint color를 설정하는
  방법을 배웁니다. 몇 초 만에 채워진 ellipse와 외곽선이 있는 ellipse를 그리는 단계별 코드를 따라하세요.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Java PostScript에서 ellipse를 채우고 paint color를 설정하는 방법
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Java PostScript에서 ellipse를 채우고 paint color를 설정하는 방법
url: /ko/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript에서 타원 채우기 및 페인트 색상 설정 방법

## 소개
벡터 그래픽을 그릴 때 **페인트 색상 설정**이 필요하다면 Aspose.Page for Java 라이브러리를 통해 모든 스트로크와 채우기를 완벽히 제어할 수 있습니다. 이 튜토리얼에서는 **페인트 색상 설정**, **타원 채우기**, **타원 외곽선 그리기**를 간단한 단계별 접근 방식으로 배우게 됩니다. 끝까지 진행하면 인보이스, 보고서 또는 인쇄 가능한 문서에 고품질 PostScript 타원을 추가할 수 있습니다.

## 빠른 답변
- **Java에서 PostScript 그래픽을 그리기에 가장 적합한 라이브러리는 무엇인가요?** Aspose.Page for Java.  
- **타원을 단색으로 채울 수 있나요?** Yes – use `document.setPaint(Color.YOUR_COLOR)` before `fill`.  
- **타원의 외곽선만 그리려면 어떻게 해야 하나요?** Set the paint and stroke, then call `document.draw(...)`.  
- **프로덕션 사용에 라이선스가 필요합니까?** A commercial license is required; a temporary license is available for testing.  
- **지원되는 Java 버전은 무엇인가요?** Any Java 8+ runtime works with the current Aspose.Page release.

## PostScript 타원란?
PostScript 타원은 경계 사각형으로 정의되는 벡터 형태입니다. 래스터 이미지와 달리 품질 손실 없이 확대·축소가 가능해 고해상도 인쇄 및 PDF 변환에 이상적입니다. 수학적으로 정의되기 때문에 어떤 크기나 해상도에서도 선명한 가장자리와 부드러운 곡선을 유지합니다.

## PostScript 타원을 만들 때 Aspose.Page를 사용하는 이유
Aspose.Page는 모든 그리기 기본 요소에 대한 결정적인 제어를 제공합니다. **3대 주요 운영 체제(Windows, Linux, macOS)**를 지원하고 **네이티브 종속성 0**이며 일반 서버에서 **초당 50개 이상의 벡터 기본 요소**를 렌더링할 수 있습니다. 라이브러리는 순수 Java이므로 추가 네이티브 라이브러리 없이 Java 8+ 애플리케이션에 바로 포함할 수 있습니다.

## 사전 요구 사항
시작하기 전에 다음을 확인하십시오:

1. JDK 8 이상이 설치된 Java 개발 환경.  
2. 프로젝트에 Aspose.Page for Java 라이브러리를 추가했습니다. **[Aspose.Page for Java 릴리스 페이지에서 다운로드](https://releases.aspose.com/page/java/)** 할 수 있습니다.  

## 패키지 가져오기
Java 소스 파일에서 PostScript 콘텐츠를 그리기 및 저장하는 데 필요한 클래스를 가져옵니다.

`java.awt` 패키지는 `Color`, `Ellipse2D`, `BasicStroke`와 같은 기본 그래픽 타입을 제공합니다. `com.aspose.page` 패키지는 PostScript 출력을 작성하는 `PsDocument` 클래스를 제공합니다.

- **`Color`** – 페인팅에 사용되는 sRGB 색상을 나타냅니다.  
- **`Ellipse2D`** – 경계 사각형으로 정의된 타원 형태를 설명합니다.  
- **`BasicStroke`** – 외곽선을 그릴 때 선 굵기, 대시 패턴 및 끝 모양을 지정합니다.  
- **`PsDocument`** – PostScript 문서를 나타내며 그래픽을 그리거나 페이지를 관리하는 메서드를 제공합니다.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 타원에 페인트 색상 설정 방법
첫 번째 단계는 다음 그리기 작업에 사용할 색상을 문서에 지정하는 것입니다. `setPaint` 메서드는 채우기든 스트로크든 이후 호출에 적용될 고체 색상을 설정합니다.

### 단계 1: PostScript 문서 설정
출력 스트림을 만들고 페이지 크기를 구성한 뒤 `PsDocument`를 인스턴스화합니다.

`PsDocument`는 메모리 내에서 PostScript 파일을 나타내는 핵심 클래스입니다. 모든 그리기 명령은 이 객체를 통해 라우팅되며 페이지 레이아웃, 리소스 관리 및 최종 파일 생성을 담당합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 단계 2: 타원 채우기 – set paint 색상 사용
**타원을 채우려면** 먼저 원하는 채우기 색상으로 `setPaint`를 호출한 뒤 `Ellipse2D` 인스턴스로 `fill`을 호출해야 합니다.

`setPaint`는 이후 채우기 또는 스트로크 작업에 사용될 현재 그리기 색상을 설정합니다.  
`Ellipse2D`는 타원의 기하학적 경계를 정의하며, 생성자는 왼쪽 위 좌표와 너비·높이를 받습니다.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### 단계 3: 타원 외곽선 그리기 및 스트로크 두께 설정
채우기 후 다른 색상으로 페인트를 변경하고 `BasicStroke`를 정의해 선 굵기를 제어한 뒤 타원 외곽선을 그릴 수 있습니다.

`BasicStroke`는 선 굵기, 대시 패턴 및 끝 모양을 지정합니다. `width` 속성을 조정하면 타원 테두리의 두께를 제어할 수 있습니다.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### 단계 4: 문서 닫기 및 저장
페이지를 마무리하고 PostScript 파일을 디스크에 씁니다.

`document.close()`를 호출하면 모든 대기 중인 그리기 명령이 플러시되고 리소스가 해제됩니다. 생성된 `.ps` 파일은 어떤 PostScript 뷰어에서도 열 수 있으며 PDF로 변환할 수도 있습니다.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

이제 주황색으로 채워진 타원 하나와 빨간색 외곽선 타원 하나를 포함한 PostScript 파일이 생성되었습니다. 디자인 요구에 맞게 좌표, 크기 및 색상을 자유롭게 실험해 보세요.

## 일반적인 함정 및 문제 해결
- **잘못된 파일 경로** – `dataDir`이 OS에 맞는 구분자(`/` 또는 `\\`)로 끝나는지 확인하십시오.  
- **라이선스 누락** – 유효한 라이선스가 없으면 라이브러리가 평가 모드로 실행되며 워터마크가 추가될 수 있습니다.  
- **색상이 적용되지 않음** – 각 `fill` 또는 `draw` 호출 전에 `document.setPaint(...)`를 설정해야 합니다; 페인트 설정은 별도의 작업 간에 자동으로 유지되지 않습니다.

## 자주 묻는 질문

**Q: Aspose.Page for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?**  
A: Yes, Aspose.Page for Java is designed to seamlessly integrate with other Java libraries.

**Q: Aspose.Page for Java의 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)** for testing purposes.

**Q: Aspose.Page가 상업 프로젝트에 적합한가요?**  
A: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)** to explore licensing options for commercial use.

**Q: Aspose.Page 관련 문의를 어디서 도움받거나 토론할 수 있나요?**  
A: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** for discussions and assistance.

**Q: Aspose.Page for Java에 대해 더 배울 수 있는 무료 자료가 있나요?**  
A: Utilize the **[Aspose free trial page](https://releases.aspose.com/)** and explore examples in the documentation.

## 결론
Aspose.Page for Java를 사용하면 **페인트 색상 설정**, **타원 채우기**, **타원 외곽선 그리기**가 간단해집니다—단순 채워진 형태든 복잡한 스트로크 그래픽이든 관계없이 말이죠. 위 단계들을 따라 하면 인쇄 가능한 문서에 전문적인 벡터 그래픽을 빠르게 추가할 수 있습니다. 여러 형태 결합, 그라디언트 적용, PDF 변환 등 더 깊이 탐색하려면 공식 **[Aspose.Page Java 문서](https://reference.aspose.com/page/java/)**를 참고하십시오.

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## 관련 튜토리얼

- [Java PostScript에서 Aspose.Page로 사각형 그리기](/page/java/postscript-shapes/add-rectangle/)
- [Java PostScript에서 Aspose.Page로 유니코드 텍스트 추가하기](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Java용 Aspose.Page로 PostScript에서 방사형 그라디언트 만들기](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}