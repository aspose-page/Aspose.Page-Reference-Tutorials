---
date: 2026-05-30
description: Aspose.Page를 사용하여 Java에서 XPS 문서를 만들고 타일 이미지를 손쉽게 추가하는 방법을 step‑by‑step
  가이드와 함께 배워보세요. XPS 파일을 빠르게 만드는 방법.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Java XPS에 타일 이미지 추가
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Java에서 타일 이미지가 포함된 XPS 문서 만들기
url: /ko/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 타일 이미지가 포함된 XPS 문서 만들기

## 소개
프로그래밍 방식으로 XPS 문서를 만드는 것은 인쇄 가능하고 장치에 독립적인 출력을 필요로 하는 Java 개발자에게 핵심 기술입니다. **How to create XPS** 파일을 효율적으로 만드는 방법은 Aspose.Page for Java가 제공하며, 저수준 XML Paper Specification 세부 정보를 추상화하고 시각 디자인에 집중할 수 있게 해줍니다. 이 가이드에서는 XPS 문서를 만드는 방법, 배경 또는 패턴으로 타일 이미지를 추가하는 방법, 그리고 결과를 저장하는 방법을 정확히 보여줍니다—간결하고 프로덕션 준비된 코드로.

## 빠른 답변
- **Aspose.Page는 무엇을 하나요?** Java에서 XPS 문서를 생성하고 조작하기 위한 고수준 API를 제공합니다.  
- **이미지를 타일링할 수 있나요?** 예 – `XpsImageBrush`와 `XpsTileMode.Tile`을 사용합니다.  
- **라이선스가 필요합니까?** 프로덕션 사용을 위해 임시 또는 상업용 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** JDK 8 이상이면 모두 호환됩니다.  
- **구현에 걸리는 시간은?** 기본 타일 이미지 시나리오의 경우 대략 10–15분 정도 소요됩니다.

## “XPS 문서 만들기”란 무엇인가요?
`XpsDocument`는 메모리 내에서 단일 XPS 파일을 나타내는 Aspose.Page의 최상위 객체입니다. 페이지, 리소스 및 메타데이터를 캡슐화하여 프로그래밍 방식으로 문서를 구축할 수 있게 합니다. XPS 문서를 만든다는 것은 이 클래스를 인스턴스화하고, 시각 요소를 추가한 뒤, `save`를 호출하여 고정 레이아웃 파일을 디스크에 기록하는 것을 의미합니다. 이 접근 방식은 수동 XML 처리를 없애고 XML Paper Specification 준수를 보장합니다.

## 왜 타일 이미지를 추가하나요?
타일링은 그래픽을 정의된 영역 전체에 반복해서 배치하는 것으로, 배경, 워터마크 또는 패턴 채우기에 이상적입니다. `XpsTileMode.Tile`을 사용하면 이미지가 자동으로 반복되어 수동 복제 없이 개발 시간을 절약하고 모든 장치에서 일관된 렌더링을 보장합니다. 타일 이미지는 동일한 비트맵 리소스를 여러 번 삽입하지 않고 재사용하기 때문에 파일 크기도 작게 유지됩니다.

## 사전 요구 사항
1. **Java Development Kit (JDK)** – JDK 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Page for Java** – [website](https://releases.aspose.com/page/java/)에서 다운로드하십시오.  
3. **쓰기 가능한 디렉터리** – 생성된 XPS 파일이 저장될 위치.

## 패키지 가져오기
In your Java project, import the necessary classes:

`XpsDocument`는 XPS 파일을 나타내는 주요 객체입니다.  
`XpsImageBrush`는 이미지 소스를 사용해 도형을 채웁니다.  
`XpsTileMode`는 이미지가 타일링되는 방식을 지정합니다.  
`Rectangle2D`는 위치 지정용 사각형 영역을 설명합니다.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## 단계별 가이드

### 단계 1: 프로젝트 설정
Aspose.Page JAR 파일을 프로젝트의 클래스패스에 추가하고, import 문이 오류 없이 컴파일되는지 확인하십시오.

### 단계 2: XPS 문서 만들기
`XpsDocument`는 페이지, 경로 및 리소스를 보유하는 핵심 컨테이너입니다. 원하는 페이지 크기로 인스턴스화한 뒤 그래픽 요소를 추가할 수 있습니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### 단계 3: 타일 이미지 경로 정의
`dataDir`이 가리키는 디렉터리 안에 타일링할 이미지(예: `R08LN_NN.jpg`)를 배치하십시오. 이 이미지는 브러시 패턴으로 사용됩니다.

### 단계 4: 타일 이미지 추가
사각형 경로를 만들고 `XpsImageBrush`로 채우십시오. 타일 모드를 `Tile`로 설정하면 이미지가 사각형 전체에 반복됩니다. 소스 및 대상 사각형을 조정하여 타일 크기와 위치를 제어합니다.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### 단계 5: 문서 저장
XPS 파일을 디스크에 저장하십시오. 출력 파일에는 방금 정의한 타일 이미지가 포함되며, 모든 XPS 뷰어에서 열 수 있습니다.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

같은 XPS 문서 내의 다른 페이지나 도형에 **타일 이미지 추가**가 필요할 때마다 이 단계를 반복하십시오.

## 일반적인 문제 및 해결책

| 문제 | 해결책 |
|-------|----------|
| 이미지가 표시되지 않음 | 파일 경로(`dataDir + "R08LN_NN.jpg"`)가 올바르고 이미지에 접근할 수 있는지 확인하십시오. |
| 타일 패턴이 늘어짐 | `Rectangle2D`의 소스 및 대상 값을 조정하여 타일 크기를 제어하십시오. |
| 불투명도가 적용되지 않음 | 브러시의 불투명도가 타일 모드 설정 **후**에 적용되었는지 확인하십시오. |

## 자주 묻는 질문

**Q:** Aspose.Page가 모든 Java 버전과 호환됩니까?  
**A:** Aspose.Page는 Java 8부터 Java 21까지 지원합니다; 전체 호환성 매트릭스는 [here](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

**Q:** Aspose.Page를 상업 프로젝트에 사용할 수 있나요?  
**A:** 예, 프로덕션 사용을 위해 상업용 라이선스가 필요합니다. 구매 옵션은 [here](https://purchase.aspose.com/buy)에서 확인하십시오.

**Q:** 무료 체험판이 있나요?  
**A:** 완전 기능을 갖춘 무료 체험판은 Aspose 릴리스 페이지 [here](https://releases.aspose.com/)에서 다운로드할 수 있습니다.

**Q:** 커뮤니티 지원은 어디서 받을 수 있나요?  
**A:** 질문을 하고 예제를 공유하려면 [forum](https://forum.aspose.com/c/page/39)에서 Aspose.Page 커뮤니티 포럼에 참여하십시오.

**Q:** 평가용 임시 라이선스는 어떻게 얻나요?  
**A:** 임시 라이선스는 Aspose 포털을 통해 요청 시 제공됩니다([here](https://purchase.aspose.com/temporary-license/)).

## 결론
이제 Aspose.Page for Java를 사용하여 타일 이미지가 포함된 **XPS 문서 만들기**에 대한 완전하고 프로덕션 준비된 워크플로우를 갖추었습니다. `XpsImageBrush`와 `XpsTileMode.Tile`을 활용하면 파일 크기를 늘리지 않고 풍부하고 반복 가능한 그래픽을 생성할 수 있습니다. 다양한 타일 크기, 불투명도 수준, 도형을 실험하여 정교한 문서 레이아웃을 구축해 보세요. 다음 단계로 벡터 도형이나 텍스트 오버레이를 추가하여 XPS 파일을 더욱 향상시킬 수 있습니다.

---

**마지막 업데이트:** 2026-05-30  
**테스트 대상:** Aspose.Page for Java 24.12 (latest)  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Java XPS 문서에 이미지 추가 방법 – Aspose.Page 간단 가이드](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - XPS에 페이지 추가 튜토리얼](/page/java/xps-page-manipulation/add-page/)
- [Aspose.Page Java를 사용하여 Java에서 XPS를 PDF로 변환](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}