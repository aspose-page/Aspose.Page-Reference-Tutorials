---
date: 2026-09-14
description: Aspose.Page를 사용하여 PostScript 그라디언트 Java를 만드는 방법을 배웁니다. 이 단계별 가이드는 Java
  코드 몇 줄만으로 PostScript 파일에 수직 그라디언트를 추가하는 방법을 보여줍니다.
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: Java PostScript에 수직 그라디언트 추가
og_description: Aspose.Page를 사용하여 PostScript 그라디언트 Java를 만드는 방법을 배웁니다. 이 단계별 가이드는
  Java 코드 몇 줄만으로 PostScript 파일에 수직 그라디언트를 추가하는 방법을 보여줍니다.
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: PostScript 그라디언트 Java 만들기 – 수직 그라디언트
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: PostScript 그라디언트 Java 만들기 – 수직 그라디언트
url: /ko/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Postscript 그라디언트 Java 생성 – 수직 그라디언트

## 소개
Aspose.Page for Java은 PostScript 및 PDF 파일을 프로그래밍 방식으로 생성하고 조작할 수 있게 해주는 라이브러리입니다. 이 포괄적인 튜토리얼에서는 해당 라이브러리를 사용하여 **create postscript gradient java**를 배우게 됩니다. 수직 그라디언트를 추가하면 문서가 더 생동감 있고 전문적으로 보이며, 몇 줄의 코드만으로도 놀라운 시각 효과를 얻을 수 있습니다. 단계별로 안내하고 각 요소가 왜 중요한지 설명하며 일반적인 함정을 피할 수 있는 실용적인 팁을 제공하겠습니다. 이 가이드를 끝까지 따라오면 부드럽고 눈길을 끄는 수직 색상 전환을 가진 PostScript 파일을 생성할 수 있게 됩니다.

## 빠른 답변
- **필요한 라이브러리는 무엇인가요?** Aspose.Page for Java  
- **색상을 사용자 정의할 수 있나요?** Yes, any `java.awt.Color` can be used  
- **회전이 지원되나요?** Yes, you can rotate the gradient with an `AffineTransform`  
- **생성되는 출력 형식은 무엇인가요?** A standard PostScript (.ps) file  
- **프로덕션에 라이선스가 필요합니까?** Yes, a commercial license is required  

## PostScript 문서에 수직 그라디언트를 추가하는 이유
수직 그라디언트를 추가하면 페이지에 깊이가 생기고 시각적 계층 구조가 개선되며, 그라디언트가 래스터 이미지가 아닌 벡터 형태로 정의되기 때문에 파일 크기가 작게 유지됩니다. 이 기술은 보고서 헤더, 기술 매뉴얼, 또는 확장성을 희생하지 않고 현대적인 모습을 필요로 하는 모든 전단지에 적합합니다.

## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 준비되어 있는지 확인하십시오:
- 머신에 설치된 Java Development Kit (JDK).  
- Aspose.Page for Java 라이브러리. [Aspose.Page for Java release page](https://releases.aspose.com/page/java/)에서 다운로드할 수 있습니다.

## 패키지 가져오기
Java 프로젝트에서 시작하기 위해 필요한 패키지를 가져오세요:
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

이제 단계별로 수직 그라디언트를 추가하는 과정을 살펴보겠습니다.

## Postscript 그라디언트 Java 생성 방법
Java 환경을 로드하고 `PsSaveOptions` 인스턴스를 생성한 뒤 `Document.save`를 호출합니다 – 이것이 수직 그라디언트를 포함한 PostScript 파일을 만드는 핵심 순서입니다. API가 색상 보간, 좌표 변환 및 페이지 플러시를 처리해 주므로 사각형과 그라디언트 매개변수 정의에만 집중하면 됩니다.

### 단계 1: 문서 디렉터리 설정
`File` 객체는 출력이 기록될 폴더를 나타냅니다. 스트림을 열기 전에 디렉터리가 존재해야 하며, 그렇지 않으면 `IOException`이 발생합니다.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 단계 2: PostScript 문서를 위한 출력 스트림 생성
`FileOutputStream`은 이진 PostScript 데이터를 디스크에 씁니다. `try‑with‑resources` 블록을 사용하면 예외가 발생하더라도 스트림이 닫히도록 보장됩니다.
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### 단계 3: A4 크기로 저장 옵션 생성
`PsSaveOptions`를 사용하면 페이지 크기, DPI, 폰트 포함 여부를 지정할 수 있습니다. 크기를 A4(595 × 842 포인트)로 설정하면 대부분의 인쇄 문서와 일치합니다.
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### 단계 4: 새 PS 문서 생성
`Document`는 메모리 내에서 단일 PostScript 파일을 나타내는 최상위 객체입니다. 모든 그리기 명령은 이 객체에 대해 실행됩니다.
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### 단계 5: 사각형 생성
`Rectangle2D.Double`은 그라디언트가 채워질 영역을 정의합니다. 사각형 좌표는 포인트 단위(1 포인트 = 1/72 인치)로 표현됩니다.
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### 단계 6: 그라디언트를 위한 색상 및 비율 설정
`float[]` 배열은 각 색상 정지점의 위치(0.0부터 1.0까지)를 정의합니다. `Color` 객체는 실제 RGB 값을 보유합니다. 원하는 `java.awt.Color`를 자유롭게 사용할 수 있습니다.
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### 단계 7: 그라디언트 변환 생성
`AffineTransform`은 그라디언트를 스케일링하고 회전시킵니다. 순수한 수직 그라디언트의 경우 Y축만 스케일링하면 되며, 필요에 따라 회전을 나중에 추가할 수 있습니다.
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### 단계 8: 수직 선형 그라디언트 페인트 생성
`LinearGradientPaint`는 사각형, 색상 정지점 및 변환을 결합합니다. 이 객체는 이후 그래픽 컨텍스트에 전달됩니다.
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### 단계 9: 페인트 설정 및 사각형 채우기
`Graphics2D.setPaint`는 그라디언트를 적용하고, `fill`은 앞서 정의한 사각형 내부에 그라디언트를 그립니다.
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### 단계 10: 현재 페이지 닫고 문서 저장
`document.save`를 호출하면 전체 PostScript 스트림이 출력 파일에 기록되고 모든 네이티브 리소스가 해제됩니다.
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

축하합니다! Aspose.Page for Java를 사용하여 Java PostScript 문서에 수직 그라디언트를 성공적으로 추가했습니다.

## 일반적인 문제 및 해결책
- **그라디언트가 평평하게 보임:** `AffineTransform` 스케일링이 사각형 크기와 일치하는지 확인하십시오.  
- **색상이 흐리게 보임:** 올바른 `ColorSpaceType`(SRGB)을 사용하고 있는지, fractions 배열이 0.0부터 1.0까지 순서대로 정렬되어 있는지 확인하십시오.  
- **파일이 생성되지 않음:** 출력 디렉터리(`dataDir`)가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인하십시오.  

## 자주 묻는 질문
**Q: Aspose.Page for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?**  
A: 예, Aspose.Page for Java는 Apache Commons나 Spring과 같은 다른 Java 라이브러리와 원활하게 함께 작동하도록 설계되었습니다.

**Q: Aspose.Page for Java에 대한 무료 체험이 제공되나요?**  
A: 예, 무료 체험을 받을 수 있습니다 [free trial download page](https://releases.aspose.com/).

**Q: 추가 문서는 어디에서 찾을 수 있나요?**  
A: 자세한 문서는 [Aspose.Page Java API reference](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

**Q: Aspose.Page for Java를 어떻게 구매할 수 있나요?**  
A: Aspose.Page for Java를 구매하려면 [Aspose.Page purchase page](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

**Q: Aspose.Page 토론을 위한 포럼이 있나요?**  
A: 예, 커뮤니티 포럼에 참여할 수 있습니다 [Aspose.Page community forum](https://forum.aspose.com/c/page/39).

## 추가 자주 묻는 질문

**Q: 다른 그라디언트 방향(수평, 대각선)을 만들 수 있나요?**  
A: 물론 가능합니다. `LinearGradientPaint`의 시작점과 끝점을 조정하고 `AffineTransform`에서 회전 각도를 변경하면 됩니다.

**Q: 이것을 PDF 출력에도 사용할 수 있나요?**  
A: `PsSaveOptions` 대신 `PdfSaveOptions`를 사용하면 동일한 그라디언트 로직을 PDF 저장 시에도 적용할 수 있습니다.

**Q: 그라디언트 크기를 동적으로 변경하려면 어떻게 해야 하나요?**  
A: 런타임에 사각형 크기를 계산하고 해당 값을 `Rectangle2D`와 `AffineTransform` 생성자에 전달하면 됩니다.

**마지막 업데이트:** 2026-09-14  
**테스트 대상:** Aspose.Page for Java 24.11 (latest)  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Page for Java를 사용한 PostScript 방사형 그라디언트 만들기](/page/java/postscript-gradient-addition/)
- [Aspose.Page Java API를 사용하여 PostScript를 PDF로 변환하는 방법](/page/java/postscript-conversion/to-pdf/)
- [Aspose.Page 투명도 튜토리얼 – Java PostScript에 투명도 추가](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}