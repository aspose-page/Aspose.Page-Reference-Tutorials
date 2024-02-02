---
title: Java XPS에 수직 그라데이션 추가
linktitle: Java XPS에 수직 그라데이션 추가
second_title: Aspose.페이지 자바 API
description: Aspose.Page를 사용하여 Java XPS 문서에 수직 그라데이션을 추가하는 방법을 알아보세요. 쉽게 시각적 매력을 향상시키세요. 내부의 단계별 가이드.
type: docs
weight: 12
url: /ko/java/xps-gradient-addition/vertical/
---
## 소개
이 튜토리얼에서는 Aspose.Page for Java를 사용하여 Java XPS에 수직 그라데이션을 추가하는 방법을 살펴보겠습니다. XPS 문서에 그라디언트를 추가하면 콘텐츠의 시각적 매력을 향상시켜 콘텐츠를 더욱 매력적이고 미학적으로 즐겁게 만들 수 있습니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- 작동하는 Java 개발 환경.
-  Java 라이브러리용 Aspose.Page. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/page/java/).
- Java 프로그래밍에 대한 기본적인 이해.
## 패키지 가져오기
Java 프로젝트에 필요한 패키지를 가져오는 것부터 시작하세요. 프로젝트 종속성에 Aspose.Page for Java 라이브러리가 포함되어 있는지 확인하세요.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
        
// Java용 Aspose.Page 가져오기
```
## 1단계: 문서 초기화
XPS 문서를 초기화하는 것부터 시작하세요. 이는 문서에 경로 및 그라디언트와 같은 요소를 추가하기 위한 기반을 설정합니다.
```java
// 문서 초기화
XpsDocument doc = new XpsDocument();
```
## 2단계: 수직 그라데이션으로 패스 만들기
이제 수직 그라데이션으로 경로를 만들어 보겠습니다. 여기에는 경로 형상을 정의하고 그라데이션 중지점을 지정하는 작업이 포함됩니다.
```java
// 기하학으로 경로 만들기
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// 수직 그라데이션 정지점 정의
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//경로에 수직 그라데이션 적용
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## 3단계: 문서 저장
마지막으로 수직 그라데이션이 추가된 XPS 문서를 원하는 디렉터리에 저장합니다.
```java
// 문서 저장
doc.save(dataDir + "VerticalGradient.xps");
```
축하해요! Aspose.Page를 사용하여 Java XPS 문서에 수직 그라데이션을 성공적으로 추가했습니다.
## 결론
그라디언트로 XPS 문서를 향상하면 시각적 매력이 크게 향상될 수 있습니다. Aspose.Page for Java는 이 프로세스를 단순화하여 멋진 문서를 쉽게 만들 수 있도록 해줍니다.

### 자주 묻는 질문
### 상용 프로젝트에서 Java용 Aspose.Page를 사용할 수 있나요?
 예, Java용 Aspose.Page는 상업적 용도로 사용 가능합니다. 구매하시면 됩니다[여기](https://purchase.aspose.com/buy).
### Aspose.Page for Java에 대한 무료 평가판이 있습니까?
 예, 무료 평가판에 액세스할 수 있습니다[여기](https://releases.aspose.com/).
### Java용 Aspose.Page에 대한 설명서는 어디에서 찾을 수 있나요?
 문서를 사용할 수 있습니다[여기](https://reference.aspose.com/page/java/).
### Aspose.Page for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시 라이센스 취득[여기](https://purchase.aspose.com/temporary-license/).
### 도움이 필요하거나 질문이 있으신가요?
 Aspose.Page 커뮤니티를 방문하세요[법정](https://forum.aspose.com/c/page/39).