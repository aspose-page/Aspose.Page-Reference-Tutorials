---
date: 2025-12-11
description: Aspose.Page를 사용하여 Java에서 PostScript 타원을 만드는 방법을 배웁니다. 이 단계별 가이드는 색으로
  타원을 채우고 Java로 타원을 그리는 방법을 보여줍니다.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page를 사용하여 Java에서 PostScript 타원을 만드는 방법
url: /ko/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java와 Aspose.Page를 사용하여 PostScript 타원 만들기

## 소개
프로그래밍 방식으로 **PostScript ellipse**를 생성하면 보고서, 청구서 또는 인쇄 가능한 문서에서 벡터 그래픽을 세밀하게 제어할 수 있습니다. 이 튜토리얼에서는 Aspose.Page for Java 라이브러리를 사용하여 **PostScript ellipse** 형태를 만들고, 타원을 색으로 채우며, 타원 외곽선을 그리는 방법을 배웁니다. 마지막까지 진행하면 PostScript 출력에 맞춤형 그래픽을 직접 삽입할 준비가 됩니다.

## 빠른 답변
- **Java에서 PostScript 그래픽을 그리기에 가장 적합한 라이브러리는?** Aspose.Page for Java.  
- **타원을 단색으로 채울 수 있나요?** 예 – `fill` 전에 `document.setPaint(Color.YOUR_COLOR)`를 사용합니다.  
- **타원의 외곽선만 그리려면?** 페인트와 스트로크를 설정한 뒤 `document.draw(...)`를 호출합니다.  
- **프로덕션 사용에 라이선스가 필요합니까?** 상업용 라이선스가 필요합니다; 테스트용 임시 라이선스도 제공됩니다.  
- **지원되는 Java 버전은?** 현재 Aspose.Page 릴리스는 Java 8 이상 런타임에서 작동합니다.

## PostScript ellipse란?
PostScript ellipse는 경계 사각형으로 정의되는 벡터 형태입니다. 래스터 이미지와 달리 품질 손실 없이 확대·축소가 가능해 고해상도 인쇄 및 PDF 변환에 이상적입니다.

## Aspose.Page로 PostScript ellipse를 만드는 이유
- **그리기 기본 요소에 대한 완전한 제어** (선, 곡선, 타원).  
- **크로스‑플랫폼** – Windows, Linux, macOS에서 동작.  
- **외부 종속성 없음** – 순수 Java API, 네이티브 코드 필요 없음.  
- **기존 Java 애플리케이션 및 빌드 도구와 손쉬운 통합**.

## 사전 준비
시작하기 전에 다음을 확인하세요:

1. 기능이 정상적인 Java 개발 환경 (JDK 8 이상).  
2. 프로젝트에 Aspose.Page for Java 라이브러리를 추가했습니다. **[여기](https://releases.aspose.com/page/java/)**에서 다운로드할 수 있습니다.  

## 패키지 가져오기
Java 소스 파일에서 PostScript 내용을 그리기·저장하기 위해 필요한 클래스를 가져옵니다.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 단계별 가이드

### 단계 1: PostScript 문서 설정
출력 스트림을 만들고 페이지 크기를 구성한 뒤 `PsDocument`를 인스턴스화합니다.

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

### 단계 2: 색으로 타원 채우기
원하는 채우기 색으로 페인트를 설정하고 `Ellipse2D` 인스턴스를 사용해 `fill`을 호출합니다.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### 단계 3: 스트로크로 타원 외곽선 그리기
페인트를 스트로크 색으로 전환하고, 선 두께를 지정하는 `BasicStroke`를 정의한 뒤 타원 외곽선을 그립니다.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### 단계 4: 문서 닫고 저장하기
페이지를 마무리하고 PostScript 파일을 디스크에 기록합니다.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

이제 주황색으로 채워진 타원 하나와 빨간색 외곽선 타원 하나가 포함된 PostScript 파일이 생성되었습니다. 좌표, 크기, 색상을 다양하게 실험하여 디자인 요구에 맞게 조정해 보세요.

## 일반적인 실수와 문제 해결
- **잘못된 파일 경로** – `dataDir`이 OS에 맞는 구분자(`/` 또는 `\\`)로 끝나는지 확인하세요.  
- **라이선스 누락** – 유효한 라이선스가 없으면 평가 모드로 실행되며 워터마크가 추가될 수 있습니다.  
- **색상이 적용되지 않음** – 각 `fill` 또는 `draw` 호출 전에 반드시 `document.setPaint(...)`를 **먼저** 설정하세요; 페인트 설정은 별도 작업 간에 자동으로 유지되지 않습니다.

## 자주 묻는 질문

**Q: Aspose.Page for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?**  
A: 예, Aspose.Page for Java는 다른 Java 라이브러리와 원활히 통합되도록 설계되었습니다.

**Q: Aspose.Page for Java용 임시 라이선스는 어떻게 얻나요?**  
A: 테스트용 **[여기](https://purchase.aspose.com/temporary-license/)**에서 임시 라이선스를 받을 수 있습니다.

**Q: Aspose.Page가 상업 프로젝트에 적합한가요?**  
A: 물론입니다! 상업용 라이선스 옵션은 **[여기](https://purchase.aspose.com/buy)**에서 확인하세요.

**Q: Aspose.Page 관련 질문을 어디서 논의할 수 있나요?**  
A: **[Aspose.Page 포럼](https://forum.aspose.com/c/page/39)**에 참여해 토론하고 도움을 받을 수 있습니다.

**Q: Aspose.Page for Java를 배우기 위한 무료 자료가 있나요?**  
A: **[무료 체험](https://releases.aspose.com/)**을 활용하고 문서에 포함된 예제를 살펴보세요.

## 결론
Aspose.Page for Java를 사용하면 **PostScript ellipse** 그래픽을 손쉽게 만들 수 있습니다. 간단한 채우기 형태든 복잡한 스트로크 외곽선이든 위 단계만 따라 하면 인쇄 가능한 문서에 전문적인 벡터 그래픽을 빠르게 추가할 수 있습니다. 여러 형태 결합, 그라디언트 적용, PDF 변환 등 심화 기능은 공식 **[문서](https://reference.aspose.com/page/java/)**를 참고하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2025-12-11  
**테스트 환경:** Aspose.Page for Java 24.11  
**작성자:** Aspose