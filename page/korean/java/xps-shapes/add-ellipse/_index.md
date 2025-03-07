---
title: Aspose.Page를 사용하여 방사형 그라데이션 타원 추가
linktitle: Java XPS에 타원 추가
second_title: Aspose.페이지 자바 API
description: Java용 Aspose.Page를 사용하여 Java XPS에서 방사형 그래디언트 스트로크 타원을 추가하는 방법에 대한 단계별 가이드를 살펴보세요. 손쉽게 문서 작성 기능을 향상해 보세요.
weight: 10
url: /ko/java/xps-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용하여 방사형 그라데이션 타원 추가

## 소개
Java용 Aspose.Page를 사용하여 Java XPS에 타원을 추가하는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. Aspose.Page는 개발자가 XPS 문서를 쉽게 작업할 수 있게 해주는 강력한 Java 라이브러리입니다. 이 튜토리얼에서는 방사형 그래디언트 스트로크 타원을 만들고 이를 XPS 문서로 저장하는 과정을 안내합니다.
## 전제 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- 컴퓨터에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Java 라이브러리용 Aspose.Page가 다운로드되었습니다. 당신은 그것을 얻을 수 있습니다[여기](https://releases.aspose.com/page/java/).
- Java 코드를 작성하고 실행하기 위해 원하는 코드 편집기(Eclipse, IntelliJ 등).
## 패키지 가져오기
Aspose.Page를 사용하려면 Java 프로젝트에 필요한 패키지를 가져왔는지 확인하세요. Java 파일 상단에 다음 가져오기 문을 추가합니다.
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## 1단계: 문서 디렉토리 설정
XPS 문서가 저장될 문서 디렉터리의 경로를 정의합니다.
```java
String dataDir = "Your Document Directory";
```
## 2단계: XPS 문서 만들기
다음 코드를 사용하여 새 XPS 문서를 초기화합니다.
```java
XpsDocument doc = new XpsDocument();
```
## 3단계: 방사형 경사 정지점 정의
방사형 그라데이션 스트로크 타원에 대한 그라데이션 중지점 목록을 만듭니다.
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## 4단계: 경로 형상 생성
경로 형상을 사용하여 방사형 그래디언트 스트로크 타원을 정의합니다.
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## 5단계: 캔버스 및 경로 추가
문서에 새 캔버스를 추가하고 정의된 지오메트리가 포함된 경로를 추가합니다.
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## 6단계: 획 및 그라데이션 설정
방사형 그래디언트 브러시를 사용하여 경로의 획을 구성합니다.
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## 7단계: 획 두께 설정
경로의 획 두께를 지정합니다.
```java
path.setStrokeThickness(12f);
```
## 8단계: 문서 저장
결과 XPS 문서를 저장합니다.
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
축하해요! Java용 Aspose.Page를 사용하여 Java XPS에 방사형 그래디언트 스트로크 타원을 성공적으로 추가했습니다.
## 결론
이 튜토리얼에서는 시각적으로 매력적인 방사형 그래디언트 스트로크 타원을 사용하여 XPS 문서를 만드는 단계를 살펴보았습니다. Java용 Aspose.Page는 XPS 문서 조작을 단순화하여 개발자에게 강력한 도구 세트를 제공합니다.
## 자주 묻는 질문
### 다른 Java 라이브러리와 함께 Java용 Aspose.Page를 사용할 수 있나요?
예, Aspose.Page for Java는 다른 Java 라이브러리와 원활하게 통합될 수 있습니다.
### Aspose.Page는 대규모 문서 처리에 적합합니까?
전적으로! Aspose.Page는 대규모 문서 처리를 효율적으로 처리하도록 설계되었습니다.
### Java용 Aspose.Page에 대한 추가 튜토리얼과 예제는 어디에서 찾을 수 있나요?
 방문하다[Java 문서용 Aspose.Page](https://reference.aspose.com/page/java/)포괄적인 튜토리얼과 예제를 보려면
### Aspose.Page for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Aspose.Page 토론을 위한 커뮤니티 포럼이 있습니까?
 응, 가입해[Aspose.Page 커뮤니티 포럼](https://forum.aspose.com/c/page/39) 다른 개발자와 소통하고 도움을 받으려면
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
