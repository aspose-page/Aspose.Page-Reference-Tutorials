---
title: Java XPS에 직사각형 추가
linktitle: Java XPS에 직사각형 추가
second_title: Aspose.페이지 자바 API
description: Aspose.Page를 사용하여 Java XPS에서 직사각형을 추가하는 방법을 알아보세요. 원활한 문서 조작을 위한 단계별 가이드를 따르세요. #JavaXPS #AsposePage
type: docs
weight: 11
url: /ko/java/xps-shapes/add-rectangle/
---
## 소개
Aspose.Page를 사용하여 Java XPS에 직사각형을 추가하는 방법에 대한 포괄적인 가이드에 오신 것을 환영합니다! 숙련된 개발자이든 이제 막 Java XPS를 시작하는 개발자이든 이 튜토리얼에서는 단계별 지침을 통해 프로세스를 안내하여 주제에 대한 깊은 이해를 얻을 수 있습니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 프로그래밍 언어에 대한 기본 지식.
-  Aspose.Page 라이브러리가 설치되었습니다. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[Aspose.Page Java 문서](https://reference.aspose.com/page/java/).
- 작동하는 Java 개발 환경.
## 패키지 가져오기
시작하려면 필요한 패키지를 Java 프로젝트로 가져옵니다. Aspose.Page 라이브러리가 클래스 경로에 올바르게 추가되었는지 확인하세요. 기본적인 예는 다음과 같습니다.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
이제 제공된 예제를 Java XPS에서 사각형을 추가하기 위해 여러 단계로 나누어 보겠습니다.
## 1단계: 문서 디렉터리 설정
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
```
"문서 디렉토리"를 원하는 디렉토리 경로로 바꾸십시오.
## 2단계: 새 XPS 문서 만들기
```java
// 새 XPS 문서 만들기
XpsDocument doc = new XpsDocument();
```
그러면 새 XPS 문서가 초기화됩니다.
## 3단계: CMYK 단색 스트로크 직사각형 추가
```java
// 왼쪽 하단에 CMYK(파란색) 단색 스트로크 직사각형
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
이 단계에서는 CMYK 단색으로 스트로크된 사각형을 추가합니다.
## 4단계: 결과 XPS 문서 저장
```java
// 결과 XPS 문서 저장
doc.save(dataDir + "AddRectangle_out.xps");
```
마지막으로 직사각형이 추가된 수정된 XPS 문서를 저장합니다.
필요에 따라 매개변수를 조정하면서 이 단계를 반복하여 직사각형을 추가로 사용자 정의합니다.
## 결론
축하해요! Aspose.Page를 사용하여 Java XPS에서 직사각형을 추가하는 방법을 성공적으로 배웠습니다. 이 튜토리얼은 XPS 문서 조작 작업을 위한 견고한 기반을 제공합니다.
## 자주 묻는 질문
### 단일 XPS 문서에 여러 개의 직사각형을 추가할 수 있나요?
예, 튜토리얼에 설명된 단계를 반복하여 필요한 만큼 직사각형을 추가할 수 있습니다.
### 직사각형의 색상을 어떻게 바꿀 수 있나요?
 색상 값을 수정하세요.`createColor` 원하는 색상을 얻는 방법.
### Aspose.Page는 복잡한 XPS 문서 조작을 처리하는 데 적합합니까?
전적으로! Aspose.Page는 다양한 XPS 문서 작업을 처리하기 위한 강력한 기능 세트를 제공합니다.
### 추가 예제와 지원은 어디서 찾을 수 있나요?
 탐색[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39)더 많은 사례를 확인하고 커뮤니티의 도움을 받으세요.
### 구매하기 전에 Aspose.Page를 사용해 볼 수 있나요?
 예, 다음을 탐색할 수 있습니다.[무료 시험판](https://releases.aspose.com/) Aspose.Page의 기능을 경험해보세요.