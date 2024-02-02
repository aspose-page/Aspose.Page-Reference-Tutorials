---
title: Java XPS에 수평 그라데이션 추가
linktitle: Java XPS에 수평 그라데이션 추가
second_title: Aspose.페이지 자바 API
description: Aspose.Page를 사용하여 Java의 XPS 문서에 놀라운 수평 그라데이션을 추가하는 방법을 알아보세요. 원활한 통합을 위한 단계별 가이드를 따르세요.
type: docs
weight: 11
url: /ko/java/xps-gradient-addition/horizontal/
---
## 소개
Java용 Aspose.Page를 사용하여 Java XPS에 수평 그라데이션을 추가하는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. Aspose.Page for Java는 개발자가 XPS(XML Paper Spec) 문서를 원활하게 작업할 수 있게 해주는 강력한 라이브러리입니다.
이 튜토리얼에서는 XPS 문서에 수평 그라데이션을 추가하기 위해 Java 애플리케이션을 만드는 과정을 안내합니다. 이를 쉽게 달성하려면 아래 단계를 따르십시오.
## 전제 조건
시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. Java 개발 환경: 시스템에 Java가 설치되어 있는지 확인하십시오. 그렇지 않은 경우 최신 버전의 Java를 다운로드하여 설치하십시오.[java.com](https://www.java.com).
2.  Aspose.Page for Java 라이브러리: Aspose.Page for Java 라이브러리가 필요합니다. 다음에서 다운로드할 수 있습니다.[Java 문서용 Aspose.Page](https://reference.aspose.com/page/java/).
## 패키지 가져오기
Java 애플리케이션에 필요한 패키지를 가져오는 것부터 시작하세요. 프로젝트에 Java 라이브러리용 Aspose.Page를 포함합니다. 다음 코드 줄을 추가하면 됩니다.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## 1단계: 문서 초기화
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
//문서 초기화
XpsDocument doc = new XpsDocument();
```
## 2단계: 수평 그라데이션 만들기
```java
// 수평 그라데이션
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## 3단계: 그라데이션으로 경로 추가
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## 4단계: 문서 저장
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
필요에 따라 이러한 단계를 반복하고 특정 요구 사항에 따라 매개변수를 조정합니다.
## 결론
축하해요! Java용 Aspose.Page를 사용하여 XPS 문서에 수평 그라데이션을 성공적으로 추가했습니다. 이 튜토리얼은 그라데이션 효과로 Java 애플리케이션을 향상시키려는 개발자를 위한 포괄적인 가이드를 제공했습니다.
## 자주 묻는 질문
### Q: 단일 XPS 문서에 여러 그라디언트를 적용할 수 있습니까?
예, 다양한 그라데이션이 포함된 여러 경로를 추가하여 복잡한 디자인을 만들 수 있습니다.
### Q: Aspose.Page는 최신 Java 버전과 호환됩니까?
Aspose.Page for Java는 최신 Java 릴리스와의 호환성을 보장하기 위해 정기적으로 업데이트됩니다.
### Q: Aspose.Page에서 사용할 수 있는 다른 그라데이션 유형이 있나요?
예, 선형 그래디언트 외에도 Aspose.Page는 보다 다양한 효과를 위해 방사형 그래디언트를 지원합니다.
### Q: 그라데이션 정지점의 색상과 위치를 사용자 정의할 수 있습니까?
전적으로! 각 그라데이션 중지점의 색상과 위치를 완전히 제어할 수 있습니다.
### Q: 도움을 구할 수 있는 Aspose.Page 커뮤니티 포럼이 있나요?
 네, 방문하실 수 있습니다[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지역사회와 연결하고 도움을 받으려면