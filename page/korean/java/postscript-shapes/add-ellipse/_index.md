---
title: Java PostScript에 타원 추가
linktitle: Java PostScript에 타원 추가
second_title: Aspose.페이지 자바 API
description: Aspose.Page를 사용하여 Java로 멋진 PostScript 문서 작성을 마스터하세요. 시각적으로 매력적인 콘텐츠를 위해 타원을 단계별로 추가하는 방법을 알아보세요.
weight: 10
url: /ko/java/postscript-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript에 타원 추가

## 소개
역동적인 Java 개발 세계에서는 시각적으로 매력적인 문서를 만드는 것이 일반적인 요구 사항입니다. Aspose.Page for Java는 개발자가 PostScript 파일을 손쉽게 조작할 수 있도록 지원하는 강력한 라이브러리입니다. 이 튜토리얼에서는 Java용 Aspose.Page를 사용하여 PostScript 문서에 타원을 추가하는 방법을 살펴보겠습니다. 문서 작성 기술을 향상하려면 따라해보세요!
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
1. Java 개발 환경: 컴퓨터에 기능적인 Java 개발 환경이 설치되어 있는지 확인하십시오.
2.  Java 라이브러리용 Aspose.Page: Aspose.Page 라이브러리를 다운로드하여 Java 프로젝트에 포함시킵니다. 도서관을 찾으실 수 있습니다[여기](https://releases.aspose.com/page/java/).
## 패키지 가져오기
Java 코드에서 Aspose.Page 기능을 활용하는 데 필요한 패키지를 가져옵니다. 예는 다음과 같습니다.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## 1단계: 문서 설정
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// PostScript 문서의 출력 스트림 생성
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// A4 크기로 저장 옵션 만들기
PsSaveOptions options = new PsSaveOptions();
// 페이지가 열린 상태에서 새 PS 문서 만들기
PsDocument document = new PsDocument(outPsStream, options, false);
```
## 2단계: 타원을 색상으로 채우기
```java
// 타원을 채우기 위한 페인트 설정
document.setPaint(Color.ORANGE);
// 첫 번째 타원 채우기
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```
## 3단계: 획으로 타원 윤곽 그리기
```java
// 타원을 스트로크하기 위한 페인트 설정
document.setPaint(Color.RED);
// 스트로크 설정
document.setStroke(new BasicStroke(3));
// 두 번째 타원의 획(윤곽선)
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```
## 4단계: 문서 닫기 및 저장
```java
// 현재 페이지 닫기
document.closePage();
// 문서 저장
document.save();
```
이제 Java용 Aspose.Page를 사용하여 PostScript 문서에 타원을 성공적으로 추가했습니다! 다양한 좌표와 치수를 실험하여 시각적 개체를 맞춤설정하세요.
## 결론
 Aspose.Page for Java는 PostScript 문서 생성 및 조작 프로세스를 단순화합니다. 이 튜토리얼에서는 타원을 추가하는 방법에 대한 지식을 제공하여 보다 복잡한 시각화를 위한 견고한 기반을 제공합니다. 다이빙[선적 서류 비치](https://reference.aspose.com/page/java/) 자세한 내용과 기능을 확인하세요.
## 자주 묻는 질문
### Q: Aspose.Page for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?
A: 예, Aspose.Page for Java는 다른 Java 라이브러리와 원활하게 통합되도록 설계되었습니다.
### Q: Aspose.Page for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 A: 임시 면허를 취득하세요[여기](https://purchase.aspose.com/temporary-license/) 테스트 목적으로.
### Q: Aspose.Page는 상업용 프로젝트에 적합합니까?
 답: 물론이죠! 방문하다[여기](https://purchase.aspose.com/buy) 상업적 사용을 위한 라이선스 옵션을 살펴보세요.
### Q: Aspose.Page 관련 쿼리에 대해 도움을 구하거나 논의할 수 있는 곳은 어디입니까?
 A: 다음 커뮤니티에 가입하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 토론과 지원을 위해.
### Q: Aspose.Page for Java에 대해 자세히 알아볼 수 있는 무료 리소스가 있나요?
 A: 활용[무료 시험판](https://releases.aspose.com/) 문서에서 예제를 살펴보세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
