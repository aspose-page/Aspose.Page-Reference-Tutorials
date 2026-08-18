---
date: 2026-02-18
description: Aspose.Page를 사용하여 Java에서 페인트 색상을 설정하고 PostScript 타원을 만드는 방법을 배웁니다. 이
  가이드는 Java에서 타원을 채우는 방법, 타원 외곽선을 그리는 방법, 그리고 스트로크 두께를 설정하는 방법을 보여줍니다.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Java에서 PostScript 타원을 그리기 위해 페인트 색상 설정
url: /ko/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 PostScript 타원을 그리기 위해 페인트 색상 설정하기

## 소개
벡터 그래픽을 그릴 때 **페인트 색상 설정**이 필요하다면, Aspose.Page for Java 라이브러리를 통해 모든 스트로크와 채우기를 완벽히 제어할 수 있습니다. 이 튜토리얼에서는 **페인트 색상 설정**, **Java에서 타원 채우기**, 그리고 **타원 외곽선 그리기**를 간단한 단계별 접근 방식으로 배우게 됩니다. 마지막까지 진행하면 청구서, 보고서 또는 인쇄 가능한 문서에 고품질 PostScript 타원을 추가할 수 있습니다.

## 빠른 답변
- **Java에서 PostScript 그래픽을 그리기에 가장 적합한 라이브러리는 무엇인가요?** Aspose.Page for Java.  
- **타원을 단색으로 채울 수 있나요?** 예 – `fill` 전에 `document.setPaint(Color.YOUR_COLOR)`를 사용하십시오.  
- **타원의 외곽선만 그리려면 어떻게 해야 하나요?** 페인트와 스트로크를 설정한 뒤 `document.draw(...)`를 호출하십시오.  
- **프로덕션 사용에 라이선스가 필요합니까?** 상업용 라이선스가 필요하며, 테스트용 임시 라이선스가 제공됩니다.  
- **지원되는 Java 버전은 무엇인가요?** 현재 Aspose.Page 릴리스는 Java 8 이상 런타임에서 모두 작동합니다.

## PostScript 타원 이란?
PostScript 타원은 경계 사각형으로 정의되는 벡터 형태입니다. 래스터 이미지와 달리 품질 손실 없이 확대·축소가 가능해 고해상도 인쇄 및 PDF 변환에 이상적입니다.

## 왜 Aspose.Page를 사용해 PostScript 타원을 만들까요?
- **Full control** over drawing primitives (lines, curves, ellipses). → 그리기 기본 요소(선, 곡선, 타원)에 대한 **전체 제어**.  
- **Cross‑platform** – works on Windows, Linux, and macOS. → **크로스 플랫폼** – Windows, Linux, macOS에서 작동.  
- **No external dependencies** – pure Java API, no native code. → **외부 종속성 없음** – 순수 Java API, 네이티브 코드 없음.  
- **Easy integration** with existing Java applications and build tools. → 기존 Java 애플리케이션 및 빌드 도구와 **쉽게 통합**.

## 전제 조건
시작하기 전에 다음을 확인하십시오:

1. JDK 8 이상이 설치된 정상적인 Java 개발 환경.  
2. 프로젝트에 Aspose.Page for Java 라이브러리를 추가했습니다. 라이브러리는 **[here](https://releases.aspose.com/page/java/)**에서 다운로드할 수 있습니다.  

## 패키지 가져오기
Java 소스 파일에서 PostScript 콘텐츠를 그리거나 저장하는 데 필요한 클래스를 가져옵니다.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 타원에 페인트 색상 설정 방법
페인트 색상 설정은 채우기나 스트로크 작업을 수행하기 전 첫 번째 단계입니다. `setPaint` 메서드는 다음 그리기 명령에 사용할 색상을 결정합니다.

### 단계 1: PostScript 문서 설정
출력 스트림을 생성하고 페이지 크기를 구성한 뒤 `PsDocument`를 인스턴스화합니다.

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

### 단계 2: 타원 채우기 – 페인트 색상 사용
**타원을 채우려면** 원하는 채우기 색상으로 `setPaint`를 먼저 호출한 뒤, `Ellipse2D` 인스턴스로 `fill`을 실행해야 합니다.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### 단계 3: 타원 외곽선 그리기 및 스트로크 두께 설정
채우기 후에는 페인트를 다른 색상으로 변경하고, `BasicStroke`를 정의해 선 굵기를 제어한 뒤 타원 외곽선을 그릴 수 있습니다.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### 단계 4: 문서 닫기 및 저장
페이지를 마무리하고 PostScript 파일을 디스크에 기록합니다.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

이제 오렌지색으로 채워진 타원 하나와 빨간색 외곽선 타원 하나가 포함된 PostScript 파일이 생성되었습니다. 좌표, 크기, 색상을 자유롭게 바꿔 디자인 요구에 맞게 실험해 보세요.

## 일반적인 함정 및 문제 해결
- **Incorrect file path** – Ensure `dataDir` ends with a separator (`/` or `\\`) appropriate for your OS. → **잘못된 파일 경로** – OS에 맞는 구분자(`/` 또는 `\\`)로 `dataDir`이 끝나는지 확인하십시오.  
- **Missing license** – Without a valid license, the library runs in evaluation mode and may add watermarks. → **라이선스 누락** – 유효한 라이선스가 없으면 라이브러리가 평가 모드로 실행되어 워터마크가 추가될 수 있습니다.  
- **Color not applied** – Remember to set `document.setPaint(...)` *before* each `fill` or `draw` call; the paint setting does not persist across separate operations automatically. → **색상이 적용되지 않음** – 각 `fill` 또는 `draw` 호출 전에 `document.setPaint(...)`를 설정해야 합니다; 페인트 설정은 별도 작업 간에 자동으로 유지되지 않습니다.

## 자주 묻는 질문

**Q: Aspose.Page for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?**  
A: 예, Aspose.Page for Java는 다른 Java 라이브러리와 원활하게 통합되도록 설계되었습니다.

**Q: Aspose.Page for Java용 임시 라이선스는 어떻게 얻을 수 있나요?**  
A: 테스트 목적의 임시 라이선스는 **[here](https://purchase.aspose.com/temporary-license/)**에서 받을 수 있습니다.

**Q: Aspose.Page가 상업 프로젝트에 적합한가요?**  
A: 물론입니다! 상업용 라이선스 옵션은 **[here](https://purchase.aspose.com/buy)**에서 확인하십시오.

**Q: Aspose.Page와 관련된 질문을 어디서 도움받을 수 있나요?**  
A: 토론 및 지원을 위해 **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** 커뮤니티에 참여하세요.

**Q: Aspose.Page for Java에 대해 더 배울 수 있는 무료 자료가 있나요?**  
A: **[free trial](https://releases.aspose.com/)**을 활용하고 문서에 있는 예제를 살펴보세요.

## 결론
Aspose.Page for Java를 사용하면 **페인트 색상 설정**, **타원 채우기**, 그리고 **타원 외곽선 그리기**가 간단해집니다—단순 채워진 형태든 복잡한 스트로크 그래픽이든 상관없습니다. 위 단계들을 따라 하면 인쇄 가능한 문서에 전문가 수준의 벡터 그래픽을 빠르게 추가할 수 있습니다. 여러 형태 결합, 그라디언트 적용, PDF 변환 등 더 깊이 있는 활용법은 공식 **[documentation](https://reference.aspose.com/page/java/)**을 참고하십시오.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}