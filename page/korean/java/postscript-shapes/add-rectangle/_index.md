---
date: 2025-12-11
description: Aspose.Page를 사용하여 Java PostScript에서 사각형 모양을 그리는 방법을 배웁니다. 이 단계별 가이드는
  페인트 설정, Java에서 사각형 색상 설정, 그리고 생생한 그래픽을 만드는 방법을 보여줍니다.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page를 사용한 Java PostScript에서 사각형 그리기
url: /ko/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript에서 사각형 그리기 (Aspose.Page 사용)

## 소개
Java PostScript 파일 안에 **사각형 그리기**가 필요하다면, 바로 이곳이 정답입니다. 이 튜토리얼에서는 Aspose.Page for Java를 사용해 컬러 사각형을 추가하고, 채우기와 스트로크를 제어하며, 결과를 PostScript 문서로 저장하는 과정을 단계별로 안내합니다. **페인트 설정 방법**, 사각형의 기하학 정의 방법, 그리고 이 접근 방식이 프로그래밍으로 인쇄용 그래픽을 생성하는 데 왜 이상적인지 정확히 보여드립니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Page for Java  
- **사각형 색상을 바꿀 수 있나요?** 예 – `setPaint`에 원하는 `java.awt.Color`를 사용하면 됩니다  
- **개발용 라이선스가 필요합니까?** 테스트용 무료 체험판으로 가능하지만, 실제 운영에서는 라이선스가 필요합니다  
- **예제에 사용된 페이지 크기는?** A4 (기본 `PsSaveOptions`)  
- **코드가 Java 8+와 호환되나요?** 물론입니다 – 표준 AWT 클래스를 사용합니다  

## 사전 준비
튜토리얼을 시작하기 전에 다음 사항을 준비하세요:
- Java 프로그래밍에 대한 기본 이해  
- Aspose.Page for Java 라이브러리 설치. 아직 설치하지 않았다면 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)에서 다운로드하세요.  
- 로컬 머신에 Java 개발 환경 구축  

## 패키지 가져오기
Java 프로젝트에서 필요한 패키지를 가져옵니다:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Java PostScript에서 사각형 그리기
아래는 전체 워크플로우를 명확한 단계로 나눈 것입니다. 각 단계마다 짧은 설명과 원본 코드 블록(변경 없음)이 포함됩니다.

### 단계 1: 사각형 채우기를 위한 페인트 설정  
**페인트 설정 방법** – 첫 번째 사각형에 오렌지 색 채우기를 적용합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### 단계 2: 사각형 스트로크를 위한 페인트 설정  
**Set rectangle color java** – 이제 페인트를 빨간색으로 바꾸고 스트로크 두께를 정의합니다.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### 단계 3: 현재 페이지 닫기 및 문서 저장  
그리기를 마친 뒤 페이지를 닫고 파일을 저장합니다.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## 왜 Aspose.Page를 사각형 그래픽에 사용하나요?
- **크로스‑플랫폼**: 모든 프린터에서 동작하는 표준 PostScript를 생성합니다.  
- **세밀한 제어**: 채우기 색, 스트로크 색, 선 두께를 각각 독립적으로 설정할 수 있습니다.  
- **외부 종속성 없음**: 내장된 AWT 기하 클래스만 사용합니다.  

## 흔히 발생하는 문제 및 팁
- **파일 경로 오류** – `dataDir`이 파일 구분자(`/` 또는 `\\`)로 끝나는지 확인하세요.  
- **라이선스 예외** – 체험판은 워터마크를 삽입합니다; 운영 환경에서는 정식 라이선스를 취득하세요.  
- **색상 가시성** – 일부 프린터는 특정 RGB 값을 다르게 해석할 수 있으니, 먼저 검은색 사각형으로 테스트해 보세요.  

## 결론
이 가이드에서는 Java PostScript 문서에 **사각형 그리기** 방법을 시연하고, **페인트 설정 방법**을 다루었으며, Aspose.Page를 사용해 **Set rectangle color java**를 구현하는 과정을 보여드렸습니다. 다양한 형태, 색상, 선 스타일을 실험해 보고 보고서, 청구서 또는 맞춤 인쇄용 풍부한 그래픽을 만들어 보세요.

## 자주 묻는 질문

### Aspose.Page for Java를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
Aspose.Page는 주로 Java를 지원하지만, 다른 언어용 유사 라이브러리도 제공됩니다.

### Aspose.Page for Java 체험판이 있나요?
예, [free trial version](https://releases.aspose.com/)을 통해 Aspose.Page for Java의 기능을 체험할 수 있습니다.

### 추가 도움이나 토론을 어디서 찾을 수 있나요?
[Aspose.Page forum](https://forum.aspose.com/c/page/39)에서 커뮤니티와 소통하고 지원을 받을 수 있습니다.

### Aspose.Page for Java 임시 라이선스를 어떻게 받을 수 있나요?
임시 라이선스는 [here](https://purchase.aspose.com/temporary-license/)에서 신청하세요.

### Aspose.Page for Java 정식 라이선스는 어디서 구매하나요?
정식 라이선스는 [here](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

**추가 Q&A**

**Q:** *사각형 크기를 동적으로 변경할 수 있나요?*  
**A:** 예 – `fill` 또는 `draw` 호출 전에 `Rectangle2D.Float(x, y, width, height)` 매개변수를 수정하면 됩니다.

**Q:** *사각형 안에 텍스트를 넣을 수 있나요?*  
**A:** 물론입니다. 사각형을 그린 뒤 `document.drawString(...)`을 사용해 원하는 폰트와 위치에 텍스트를 추가하면 됩니다.

**Q:** *Aspose.Page가 원이나 다각형 같은 다른 도형도 지원하나요?*  
**A:** 예, API에 `drawEllipse`, `drawPolygon` 등 다양한 벡터 그래픽 메서드가 포함되어 있습니다.

---

**마지막 업데이트:** 2025-12-11  
**테스트 환경:** Aspose.Page for Java 24.12 (최신)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}