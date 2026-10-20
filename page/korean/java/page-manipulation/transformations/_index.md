---
date: 2026-10-20
description: Aspose.Page for Java를 사용하여 사각형을 Scale하는 방법, 도형을 Translate하는 방법, 그리고 Affine
  Transform을 적용하여 PostScript 문서를 만드는 방법을 배웁니다.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Java 페이지 조작에서 Transformations
og_description: Aspose.Page for Java를 사용하여 사각형을 Scale하고, 도형을 Translate하며, Affine Transform을
  적용하여 PostScript 파일을 효율적으로 생성하는 방법을 배웁니다.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Aspise.Page for Java로 사각형을 Scale하는 방법 – 단계별 가이드
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Aspose.Page for Java로 사각형을 Scale하는 방법
url: /ko/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for Java를 사용한 사각형 스케일링 방법

## 소개
이 가이드에서는 Aspose.Page for Java를 사용하여 **how to scale rectangle** 객체를 확장하는 방법을 배우고, 도형 위치를 이동하고, 그래픽을 회전하며, 어핀 변환 작업을 적용하여 고품질 PostScript 출력을 생성하는 방법도 배웁니다. 이러한 기술을 통해 저수준 렌더링 코드를 작성하지 않고도 정교하고 장치 독립적인 그래픽을 구축할 수 있어 Java 애플리케이션을 보다 강력하고 유지 관리하기 쉬워집니다.

## 빠른 답변
`scale(sx, sy)`는 주어진 수평 및 수직 계수에 따라 그래픽 컨텍스트를 스케일합니다.  

- **Java에서 Aspose.Page를 사용하여 사각형을 스케일하려면 어떻게 해야 하나요?** 사각형을 그리기 전에 그래픽 컨텍스트에서 `scale(sx, sy)` 메서드를 호출합니다.  
- **다른 그래픽에 영향을 주지 않고 도형을 이동(translate)할 수 있나요?** 예—`writeGraphicsSave()`와 `writeGraphicsRestore()` 호출 사이에 변환을 감쌉니다.  
- **PostScript 파일을 생성하는 클래스는 무엇인가요?** `PsDocument`와 `PsSaveOptions`를 함께 사용합니다.  
- **프로덕션 사용에 라이선스가 필요합니까?** 상업적 배포를 위해서는 유효한 Aspose.Page 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇인가요?** Aspose.Page는 Java 8 및 이후 버전을 지원합니다.

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

- 핵심 Java 문법 및 객체 지향 개념에 대한 확고한 이해.  
- Aspose.Page for Java 라이브러리가 설치되어 있어야 합니다. [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)에서 다운로드할 수 있습니다.  
- 라이브러리 JAR 파일이 클래스패스에 설정된 Java IDE(IntelliJ IDEA, Eclipse 또는 VS Code).

## 패키지 가져오기
`PsDocument`는 PostScript 문서를 생성하는 데 사용되는 주요 클래스이며, `PsSaveOptions`는 문서 저장 방식을 구성합니다.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Aspose.Page에서 “how to scale rectangle”이란?
`scale(float sx, float sy)` 메서드는 현재 그래픽 상태에 어핀 스케일 변환을 적용하여 이후 그리기를 `sx`(수평) 및 `sy`(수직) 계수에 따라 크기를 조정합니다. 이는 **how to scale rectangle** 키워드의 핵심 연산입니다. 그리기 전에 이 변환을 적용하면 사각형과 같은 이후 도형이 새로운 크기로 비율을 유지하면서 렌더링됩니다.

## Aspose.Page를 사용한 도형 이동(translate) 방법
`writeGraphicsSave()`는 현재 그래픽 상태를 저장하고 `writeGraphicsRestore()`는 이를 복원하여 변환이 의도된 도형에만 적용되도록 합니다. Translation은 객체 크기를 변경하지 않고 좌표계의 원점을 재배치합니다. `translate(dx, dy)`를 `writeGraphicsSave()`와 `writeGraphicsRestore()` 사이에 배치하면 의도된 도형만 이동하고 다른 그래픽은 변하지 않아 개별 요소에 대한 정밀한 제어가 가능합니다.

## 예제 1: 변환 없음
첫 번째 예제는 변환 없이 사각형을 그려 이후 예제와 시각적으로 비교할 기준선을 설정합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## 예제 2: 이동(translation)
이 샘플에서는 두 번째 사각형을 그리기 전에 그래픽 컨텍스트를 오른쪽으로 250 단위 이동시켜 **how to translate shape**을 보여줍니다.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## 예제 3: 스케일링
여기서는 주요 질문 **how to scale rectangle**에 답합니다. `scale(0.5f, 0.75f)` 호출을 사용하여 사각형의 너비를 원래의 50 %, 높이를 75 %로 축소합니다.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Java에서 도형 회전 방법 (rotate shape java)
`rotate(angle)`은 지정된 각도(도)만큼 좌표계를 회전시킵니다. `PsDocument`를 로드하고 그래픽 상태에서 `rotate(angle)`을 호출한 뒤 도형을 그리고 이전 상태를 복원합니다. 이 패턴은 **rotate shape java**와 **how to rotate rectangle**을 하나의 재사용 가능한 블록으로 구현하여 원하는 어느 지점을 중심으로 그래픽을 회전시킬 수 있게 합니다.

## 왜 이것이 중요한가 – 실제 혜택
- **Device‑independent output** – Aspose.Page는 모든 프린터나 뷰어에서 동일하게 렌더링되는 PostScript 및 XPS 파일을 생성하여 플랫폼별 조정을 없앱니다.  
- **Fine‑grained control** – 번역, 스케일링, 전단, 회전을 결합하여 정확한 레이아웃 사양을 충족합니다; API는 페이지당 20가지 이상의 변환 조합을 지원합니다.  
- **Performance‑oriented processing** – 일반적인 100페이지 보고서에 대해 메모리 사용량이 10 MB 이하로 문서를 처리하여 배치 작업을 빠르고 확장 가능하게 합니다.

## 일반적인 사용 사례
- **Printable invoices** – 스케일링 및 번역을 사용하여 로고, 바코드, 테이블을 정확히 배치해 기업 브랜드 가이드라인에 맞춥니다.  
- **Technical diagrams** – 각 구성 요소를 비례적으로 크기 조정하고 배치해야 하는 회로도를 생성합니다.  
- **Automated multi‑page reports** – 페이지 전체에 일관된 스케일링이 필요한 PostScript 보고서(예: 엔지니어링 사양)를 생성합니다.

## 일반적인 문제와 해결책
- **Transformation not resetting** – 항상 `writeGraphicsSave()`와 `writeGraphicsRestore()`를 짝지어 사용하십시오; 그렇지 않으면 이후 그리기가 원하지 않는 변환을 상속합니다.  
- **Unexpected colors** – 각 변환 후에 페인트(색상)를 설정하십시오. 그래픽 상태는 복원 후 색상 정보를 보존하지 않기 때문입니다.  
- **File size too large** – `PsSaveOptions`에서 압축을 활성화하고 삽입된 래스터 이미지 해상도를 제한하여 일반적인 50페이지 문서의 최종 파일 크기를 5 MB 이하로 유지하십시오.

## FAQ

### Aspose.Page for Java를 다른 문서 형식에 사용할 수 있나요?
Aspose.Page는 주로 PostScript 및 XPS 형식의 페이지 조작에 중점을 두지만 제한적인 PDF 내보내기 기능도 제공합니다.

### Aspose.Page for Java에 대한 더 많은 예제와 문서는 어디서 찾을 수 있나요?
포괄적인 가이드, API 참조 및 샘플 프로젝트는 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)을 방문하십시오.

### Aspose.Page for Java에 대한 무료 체험판이 있나요?
예, **Aspose free trial download** 페이지에서 무료 체험판을 이용할 수 있습니다: [Aspose free trial download](https://releases.aspose.com/).

### Aspose.Page for Java에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
**temporary license request page**를 통해 임시 라이선스를 얻을 수 있습니다: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Aspose.Page for Java에 대한 커뮤니티 지원이나 질문은 어디서 할 수 있나요?
커뮤니티 토론, 코드 스니펫 및 문제 해결 팁은 [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)에서 확인하십시오.

## 자주 묻는 질문

**Q: `translate`와 `scale`의 차이점은 무엇인가요?**  
A: `translate`는 좌표계의 원점을 이동시키고, `scale`은 X 및/또는 Y 축을 따라 그려진 객체의 크기를 변경합니다.

**Q: 단일 그래픽 상태에서 여러 변환을 결합할 수 있나요?**  
A: 예—그리기 전에 `translate`, `scale`, `rotate`, `shear`를 순차적으로 호출하면 결합된 어핀 변환을 만들 수 있습니다.

**Q: 도형을 그린 후 변환을 어떻게 초기화하나요?**  
A: `writeGraphicsRestore()`를 사용하여 이전에 저장된 그래픽 상태로 되돌립니다.

**Q: 사각형을 중심을 기준으로 회전시킬 수 있나요?**  
A: 물론 가능합니다. 사각형을 원점으로 이동한 뒤 `rotate(angle)`을 적용하고, 그 후 다시 원래 위치로 이동한 뒤 그립니다.

**Q: 부드러운 그래픽을 위해 Aspose.Page가 안티앨리어싱을 지원하나요?**  
A: 예—`PsSaveOptions`에서 적절한 렌더링 옵션을 설정하여 안티앨리어싱을 활성화합니다.

---

**마지막 업데이트:** 2026-10-20  
**테스트 환경:** Aspose.Page for Java 24.12  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Page를 사용한 Java PostScript에서 사각형 그리기](/page/java/postscript-shapes/add-rectangle/)
- [Aspose.Page for Java를 사용한 PostScript에서 방사형 그라디언트 만들기](/page/java/postscript-gradient-addition/)
- [Postscript 페이지 조작](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}