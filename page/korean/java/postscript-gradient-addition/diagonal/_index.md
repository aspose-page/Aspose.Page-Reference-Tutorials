---
date: 2026-02-13
description: Aspose.Page Java를 사용하여 Java PostScript 문서에 대각선 그라디언트를 적용하세요. Java에서 LinearGradientPaint로
  그라디언트 효과를 추가하고, 손쉽게 생생한 색상 전환을 만들어보세요.
linktitle: 'How to Add Gradient: Diagonal Gradient in Java PostScript using Aspose.Page
  Java'
second_title: Aspose.Page Java API
title: '그라디언트 추가 방법: Aspose.Page Java를 사용한 Java PostScript에서 대각선 그라디언트'
url: /ko/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript에서 Aspose.Page Java를 사용하여 대각선 그라디언트 추가

## 소개
PostScript 파일에 부드러운 대각선 색상 전환을 추가하고 싶다면 **Aspose.Page Java**가 놀라울 정도로 쉽게 해줍니다. 이 튜토리얼에서는 Java 2D의 `LinearGradientPaint` 클래스를 사용하여 **그라디언트를 추가하는 방법**을 단계별로 안내합니다. 마지막까지 진행하면 활기찬 대각선 그라디언트를 가진 PostScript 문서를 생성하는 실행 가능한 코드 스니펫을 얻게 됩니다.

## Java PostScript에서 그라디언트 추가 방법
그라디언트를 추가하는 것이 그래픽 전용 작업처럼 들릴 수 있지만, Aspose.Page를 사용하면 순수 Java 환경에서 기본 PostScript 명령을 완전히 제어할 수 있습니다. 이 섹션에서는 이 접근 방식이 왜 작동하는지와 원시 PostScript를 직접 코딩하는 것에 비해 얻을 수 있는 이점을 설명합니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Page for Java.  
- **그라디언트를 생성하는 클래스는?** `LinearGradientPaint`.  
- **색상을 변경할 수 있나요?** 예 – `Color[]` 배열을 수정하면 됩니다.  
- **프로덕션에 라이선스가 필요합니까?** 상업용 라이선스가 필요하며, 무료 체험판을 사용할 수 있습니다.  
- **구현에 얼마나 걸리나요?** 기본 그라디언트의 경우 약 10 분 정도 소요됩니다.

## Aspose.Page Java란?
Aspose.Page Java는 개발자가 외부 소프트웨어 없이 PostScript 및 PDF 파일을 생성, 편집 및 변환할 수 있게 해주는 강력한 API입니다. 깨끗하고 객체 지향적인 Java 인터페이스를 통해 PostScript 언어의 전체 그래픽 기능을 제공합니다.

## 왜 대각선 그라디언트를 사용하나요?
대각선 그라디언트는 차트, 배너 또는 현대적인 느낌이 필요한 모든 그래픽 요소에 깊이와 시각적 흥미를 더합니다. 그라디언트가 한 모서리에서 반대쪽 모서리까지 흐르기 때문에 배경, 버튼 스킨 및 장식 형태에 잘 어울립니다.

## 사전 요구 사항
Before you start, make sure you have:

- Java Development Kit (JDK) 8 이상.  
- Eclipse, IntelliJ IDEA, VS Code와 같은 IDE.  
- **Aspose.Page for Java** 라이브러리 – 최신 버전을 [official download page](https://releases.aspose.com/page/java/)에서 다운로드하십시오.

## 패키지 가져오기
First, import the Java 2D and Aspose classes you’ll need. These imports give you access to color definitions, geometric shapes, gradient painting, and the PostScript document API.

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
We start by defining the folder where the file will be saved and opening a `FileOutputStream`. This stream will receive the generated PostScript data.

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
출력 스트림과 저장 옵션을 사용하여 `PsDocument`를 인스턴스화합니다. `false` 플래그는 생성자가 자동으로 새 페이지를 열지 않도록 지정하며, 우리는 나중에 페이지를 열 것입니다.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 단계 4: 사각형 생성
그라디언트 채우기를 받을 사각형을 정의합니다. 사각형의 위치 (200, 100)와 크기 (200 × 100)는 그라디언트를 명확히 보이게 하기 위해 선택되었습니다.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## 단계 5: 그라디언트 변환 생성
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

## 단계 6: 대각선 선형 그라디언트 페인트 생성
여기가 **그라디언트를 추가하는 방법**의 핵심입니다 – 이전에 정의한 변환을 사용하여 사각형의 왼쪽 위에서 오른쪽 아래까지 확장되는 `LinearGradientPaint`를 생성합니다. `MultipleGradientPaint.CycleMethod.NO_CYCLE`은 그라디언트가 반복되지 않도록 보장합니다.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## 단계 7: 페인트 설정 및 사각형 채우기
그라디언트 페인트를 문서에 적용하고 사각형 도형을 채웁니다. 이 단계는 PostScript 페이지에 대각선 색상 전환을 렌더링합니다.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## 단계 8: 현재 페이지 닫기 및 문서 저장
마지막으로 페이지를 닫고 스트림을 플러시한 뒤 파일을 저장합니다. 결과물인 `DiagonalGradient_outPS.ps` 파일은 모든 PostScript 뷰어에서 열 수 있습니다.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## 일반적인 문제 및 팁
- **그라디언트가 평평하게 보임** – 회전 각도를 다시 확인하십시오; 45° 회전이 진정한 대각선을 만듭니다.  
- **색상이 흐릿함** – 정확한 색상 렌더링을 위해 `MultipleGradientPaint.ColorSpaceType.SRGB`를 사용하고 있는지 확인하십시오.  
- **파일을 찾을 수 없음 오류** – `dataDir`이 존재하는 폴더를 가리키는지와 애플리케이션에 쓰기 권한이 있는지 확인하십시오.

## 자주 묻는 질문

**Q: 이 라이브러리를 Java의 다른 그래픽 작업에 사용할 수 있나요?**  
A: 예, Aspose.Page for Java는 전체 그리기 기본 요소, 텍스트 렌더링 및 이미지 처리 기능을 제공합니다.

**Q: Aspose.Page Java에 대한 무료 체험판이 있나요?**  
A: 물론입니다. [Aspose 무료 체험 페이지](https://releases.aspose.com/)에서 완전 기능 체험판을 다운로드할 수 있습니다.

**Q: Aspose.Page Java에 대한 문서는 어디서 찾을 수 있나요?**  
A: 공식 API 레퍼런스는 [여기](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

**Q: Aspose.Page Java 라이선스는 어떻게 구매하나요?**  
A: 라이선스는 [Aspose 구매 포털](https://purchase.aspose.com/buy)에서 직접 구매할 수 있습니다.

**Q: 도움이 필요하거나 질문이 있나요?**  
A: Aspose 엔지니어와 다른 개발자들의 도움을 받을 수 있는 커뮤니티 운영 [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)을 방문하십시오.

---
**마지막 업데이트:** 2026-02-13  
**테스트 대상:** Aspose.Page for Java 24.12 (latest)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}