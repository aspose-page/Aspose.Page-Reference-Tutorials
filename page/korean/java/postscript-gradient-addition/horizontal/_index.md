---
title: Java PostScript에 수평 그라데이션 추가
linktitle: Java PostScript에 수평 그라데이션 추가
second_title: Aspose.페이지 자바 API
description: Java용 Aspose.Page를 사용하여 Java PostScript에 수평 그라데이션을 추가하는 방법을 알아보세요. 시각적으로 멋진 문서를 손쉽게 만들어보세요.
type: docs
weight: 11
url: /ko/java/postscript-gradient-addition/horizontal/
---
## 소개
Java용 Aspose.Page를 사용하여 Java PostScript에 수평 그라데이션을 추가하는 방법에 대한 포괄적인 튜토리얼에 오신 것을 환영합니다. Aspose.Page는 개발자가 PostScript 및 기타 문서 형식으로 작업할 수 있는 강력한 Java 라이브러리입니다. 이 튜토리얼에서는 단계별 예제를 사용하여 가로 그라데이션이 있는 PostScript 문서를 만드는 과정을 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
- 컴퓨터에 JDK(Java Development Kit)가 설치되어 있습니다.
- Java 라이브러리용 Aspose.Page. 다음에서 다운로드할 수 있습니다.[Aspose.Page Java 문서](https://reference.aspose.com/page/java/).
## 패키지 가져오기
Java 프로젝트에 필요한 패키지를 가져오는 것부터 시작하세요. 이 패키지는 Aspose.Page 작업에 중요합니다.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## 1단계: 직사각형 만들기
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// PostScript 문서의 출력 스트림 생성
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// A4 크기로 저장 옵션 만들기
PsSaveOptions options = new PsSaveOptions();
// 페이지가 열린 상태에서 새 PS 문서 만들기
PsDocument document = new PsDocument(outPsStream, options, false);
//직사각형 만들기
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## 2단계: 수평 선형 그라데이션 페인트 만들기
```java
// 수평 선형 그라데이션 페인트를 만듭니다. 변환의 크기 조정 구성요소는 직사각형의 너비 및 높이와 같아야 합니다.
// 변환 구성요소는 직사각형의 오프셋입니다.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// 페인트 세트
document.setPaint(paint);
```
## 3단계: 직사각형 채우기
```java
// 직사각형을 채우세요
document.fill(rectangle);
```
## 4단계: 그라데이션으로 텍스트 채우기
```java
// 그라디언트로 텍스트 채우기
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## 5단계: 그라디언트로 텍스트 획 지정
```java
// 그라디언트로 텍스트 스트로크
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## 결론
축하해요! Java용 Aspose.Page를 사용하여 Java PostScript에 수평 그라데이션을 성공적으로 추가했습니다. 이 튜토리얼에서는 시각적으로 매력적인 PostScript 문서를 만드는 데 도움이 되는 자세한 단계별 가이드를 제공했습니다.
## 자주 묻는 질문
### 상용 프로젝트에서 Java용 Aspose.Page를 사용할 수 있나요?
예, Java용 Aspose.Page는 상용 프로젝트에서 사용할 수 있습니다. 라이선스에 대한 자세한 내용을 보려면 다음을 방문하세요.[Aspose.구매](https://purchase.aspose.com/buy).
### 무료 평가판이 제공되나요?
 예, Aspose.Page for Java 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).
### 추가 문서와 지원은 어디서 찾을 수 있나요?
 방문하다[Aspose.Page Java 문서](https://reference.aspose.com/page/java/) 포괄적인 자원을 위해. 커뮤니티 지원을 받으려면 다음을 확인하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39).
### 임시 라이센스는 어떻게 얻을 수 있나요?
 임시면허를 취득하실 수 있습니다.[Aspose.구매](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java의 시스템 요구 사항은 무엇입니까?
 다음을 참조하세요.[선적 서류 비치](https://reference.aspose.com/page/java/) 자세한 시스템 요구사항을 확인하세요.