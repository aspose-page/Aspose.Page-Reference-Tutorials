---
title: Java PostScript 사용자 정의 - Aspose.Page를 사용하여 직사각형 추가
linktitle: Java PostScript에 직사각형 추가
second_title: Aspose.페이지 자바 API
description: Java용 Aspose.Page를 사용하여 Java PostScript 문서에 생생한 직사각형을 추가하는 방법에 대한 단계별 가이드를 살펴보세요. 손쉽게 문서 사용자 정의를 강화하세요!
weight: 11
url: /ko/java/postscript-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript 사용자 정의 - Aspose.Page를 사용하여 직사각형 추가

## 소개
생생한 직사각형으로 Java PostScript 문서를 향상시키고 싶으십니까? 더 이상 보지 마세요! 이 단계별 가이드에서는 Java용 Aspose.Page를 사용하여 PostScript 문서에 직사각형을 추가하는 방법을 살펴보겠습니다. Aspose.Page는 PostScript 파일 작업을 위한 강력한 기능을 제공하는 강력한 라이브러리로, 문서를 조작하고 사용자 정의하려는 개발자에게 이상적인 선택입니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 프로그래밍에 대한 기본 이해.
-  Java 라이브러리용 Aspose.Page가 설치되었습니다. 그렇지 않은 경우 다음에서 다운로드하십시오.[Java 문서용 Aspose.Page](https://reference.aspose.com/page/java/).
- 컴퓨터에 Java 개발 환경이 설정되어 있습니다.
## 패키지 가져오기
Java 프로젝트에서 필요한 패키지를 가져오는 것부터 시작하세요.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## 튜토리얼: Java PostScript에 직사각형 추가하기
## 1단계: 직사각형을 채우기 위한 페인트 설정
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// PostScript 문서의 출력 스트림 생성
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// A4 크기로 저장 옵션 만들기
PsSaveOptions options = new PsSaveOptions();
// 페이지가 열린 상태에서 새 PS 문서 만들기
PsDocument document = new PsDocument(outPsStream, options, false);
// 직사각형을 채우기 위한 페인트 설정
document.setPaint(Color.ORANGE);        
// 첫 번째 직사각형 채우기
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## 2단계: 직사각형 스트로크에 대한 페인트 설정
```java
// 직사각형을 칠하기 위한 페인트 설정
document.setPaint(Color.RED);
// 스트로크 설정
document.setStroke(new BasicStroke(3));
// 두 번째 직사각형을 획(윤곽선)으로 지정합니다.
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## 3단계: 현재 페이지를 닫고 문서 저장
```java
// 현재 페이지 닫기
document.closePage();
// 문서 저장
document.save();
```
축하해요! Aspose.Page를 사용하여 Java PostScript 문서에 생생한 직사각형을 성공적으로 추가했습니다.
## 결론
이 튜토리얼에서는 Java용 Aspose.Page를 사용하여 직사각형으로 Java PostScript 문서를 향상시키는 프로세스를 살펴보았습니다. 이 강력한 라이브러리는 문서를 쉽게 사용자 정의하고 조작하려는 개발자에게 가능성의 세계를 열어줍니다.
문서를 시각적으로 매력적으로 만들기 위해 다양한 모양과 색상을 실험해 보세요!
## 자주 묻는 질문

### 다른 프로그래밍 언어와 함께 Java용 Aspose.Page를 사용할 수 있나요?
Aspose.Page는 주로 Java를 지원하지만 다른 언어에도 유사한 라이브러리를 사용할 수 있습니다.
### Java용 Aspose.Page 평가판이 있습니까?
 예, 다음을 통해 Java용 Aspose.Page의 기능을 탐색할 수 있습니다.[무료 평가판](https://releases.aspose.com/).
### 추가 도움말과 토론은 어디에서 찾을 수 있나요?
 방문하다[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지역사회에 참여하고 도움을 받으려면
### Aspose.Page for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시 라이센스 받기[여기](https://purchase.aspose.com/temporary-license/).
### Java용 Aspose.Page 라이선스 버전을 어디에서 구입할 수 있나요?
 라이선스 버전 구매[여기](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
