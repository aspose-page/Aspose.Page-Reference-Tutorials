---
title: Java XPS에서 불투명 마스크 설정
linktitle: Java XPS에서 불투명 마스크 설정
second_title: Aspose.페이지 자바 API
description: Aspose.Page를 사용하여 Java XPS에서 불투명 마스크를 설정하는 기능을 알아보세요. 시각적으로 향상된 문서 경험을 위한 단계별 가이드를 따르세요.
type: docs
weight: 11
url: /ko/java/xps-transparency/set-opacity-mask/
---
## 소개
Aspose.Page를 사용하여 Java XPS에서 불투명 마스크를 설정하는 방법에 대한 포괄적인 가이드에 오신 것을 환영합니다. 이 튜토리얼에서는 Java용 Aspose.Page의 강력한 기능을 사용하여 XPS 문서를 만들고, 캔버스를 추가하고, 직사각형에 불투명 마스크를 적용하는 과정을 안내합니다.
## 전제 조건
이 튜토리얼을 시작하기 전에 다음 사항을 확인하세요.
- Java 프로그래밍에 대한 기본적인 이해.
-  Java 라이브러리용 Aspose.Page가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/page/java/).
-  Aspose.Page에 대한 유효한 라이센스입니다. 없으시면 임시면허를 취득하시면 됩니다.[여기](https://purchase.aspose.com/temporary-license/).
- Java 애플리케이션을 실행하기 위해 설정된 개발 환경입니다.
## 패키지 가져오기
필요한 패키지를 Java 프로젝트로 가져오는 것부터 시작하세요. Aspose.Page 라이브러리가 제대로 통합되었는지 확인하세요. 다음은 안내하는 스니펫입니다.
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
이제 예제 코드를 여러 단계로 나누어 보겠습니다.
## 1단계: 새 XPS 문서 만들기
```java
// 새 XPS 문서 만들기
XpsDocument doc = new XpsDocument();
```
## 2단계: 캔버스 추가
```java
// 새 캔버스
XpsCanvas canvas = doc.addCanvas();
```
## 3단계: 불투명 마스크를 사용하여 직사각형 추가
```java
// ImageBrush로 마스크된 불투명도가 있는 왼쪽 중앙의 직사각형
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## 4단계: ImageBrush를 사용하여 불투명 마스크 설정
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## 5단계: 결과 XPS 문서 저장
```java
// 결과 XPS 문서 저장
doc.save(dataDir + "OpacityMask_out.xps"); 
```
Aspose.Page를 사용하여 Java XPS 문서에 불투명 마스크를 통합하려면 다음 단계를 주의 깊게 따르십시오.
## 결론
축하해요! Aspose.Page를 사용하여 Java XPS에서 불투명 마스크를 설정하는 방법을 성공적으로 배웠습니다. 이 기능은 문서에 시각적 풍부함을 추가하여 문서를 더욱 매력적이고 역동적으로 만듭니다.
## 자주 묻는 질문
### Aspose.Page는 모든 Java 개발 환경과 호환됩니까?
예, Aspose.Page는 다양한 Java 개발 환경에서 원활하게 작동하도록 설계되었습니다.
### 라이선스 없이 Aspose.Page를 사용할 수 있나요?
라이선스 없이 Aspose.Page를 사용할 수 있지만, 모든 기능과 지원을 받으려면 Aspose.Page를 구입하는 것이 좋습니다.
### 평가판 버전에 제한이 있나요?
평가판 버전에는 일부 기능 제한이 있을 수 있습니다. 자세한 내용은 설명서를 확인하는 것이 좋습니다.
### Aspose.Page에 대한 지원은 어떻게 받을 수 있나요?
 당신은 방문 할 수 있습니다[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 커뮤니티 지원을 원하거나 프리미엄 지원을 위한 라이선스를 구매하세요.
### Aspose.Page에 대한 환불 보장이 있나요?
 다음을 참조하세요.[구매 페이지](https://purchase.aspose.com/buy) 환불 정책에 대한 정보를 확인하세요.