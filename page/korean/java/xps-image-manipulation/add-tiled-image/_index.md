---
title: Java XPS에 타일식 이미지 추가
linktitle: Java XPS에 타일식 이미지 추가
second_title: Aspose.페이지 자바 API
description: Aspose.Page를 사용하여 원활한 Java XPS 문서 조작을 살펴보세요. 이 단계별 가이드를 사용하여 타일식 이미지를 쉽게 추가하는 방법을 알아보세요.
type: docs
weight: 11
url: /ko/java/xps-image-manipulation/add-tiled-image/
---
## 소개
Java 개발의 역동적인 세계에서는 효율적인 문서 조작 및 생성에 대한 필요성이 점점 더 커지고 있습니다. Aspose.Page for Java는 개발자에게 XPS 문서를 원활하게 작업할 수 있는 기능을 제공하는 강력한 도구로 등장합니다. 이 튜토리얼은 Java XPS 문서에 타일 이미지를 추가하는 특정 작업에 중점을 둡니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Aspose.Page for Java: 다음 사이트에서 Aspose.Page for Java를 다운로드하고 설치하세요.[웹사이트](https://releases.aspose.com/page/java/).
3. 문서 디렉터리: XPS 문서를 저장할 디렉터리를 선택하거나 만듭니다.
## 패키지 가져오기
Java 프로젝트에서 Aspose.Page 기능을 활용하는 데 필요한 패키지를 가져옵니다.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
이제 Java XPS 문서에 타일 이미지를 추가하는 프로세스를 명확하고 관리 가능한 단계로 나누어 보겠습니다.
## 1단계: 프로젝트 설정
먼저 Java 프로젝트를 설정하고 Aspose.Page for Java가 제대로 통합되었는지 확인하세요.
## 2단계: XPS 문서 만들기
다음 코드를 사용하여 새 XPS 문서를 초기화합니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 새 XPS 문서 만들기
XpsDocument doc = new XpsDocument();
```
## 3단계: 타일식 이미지 경로 정의
XPS 문서에 추가하려는 타일 이미지의 경로를 지정합니다.
## 4단계: 타일식 이미지 추가
XPS 문서에 타일 이미지를 추가하려면 아래 코드 조각을 활용하세요.
```java
// 타일 이미지
// 아래 오른쪽 상단에 있는 ImageBrush로 채워진 직사각형
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## 5단계: 문서 저장
마지막으로 아래 코드를 사용하여 결과 XPS 문서를 저장합니다.
```java
// 결과 XPS 문서 저장
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Aspose.Page를 사용하여 타일 이미지를 Java XPS 문서에 쉽게 통합하려면 이러한 단계를 반복하세요.
## 결론
Aspose.Page for Java는 XPS 문서 작업 프로세스를 간소화하여 개발자에게 문서 조작을 위한 효율적인 솔루션을 제공합니다. 이 단계별 가이드를 따르면 Java XPS 문서에 타일 이미지를 쉽게 추가할 수 있습니다.

## 자주 묻는 질문
### Aspose.Page는 모든 Java 버전과 호환됩니까?
 Aspose.Page는 다양한 Java 버전에서 작동하도록 설계되었습니다. 설명서를 확인하여 호환성을 확인하세요.[여기](https://reference.aspose.com/page/java/).
### Aspose.Page를 상업용 프로젝트에 사용할 수 있나요?
예, Aspose.Page는 상업용 라이선스를 제공합니다. 구매하세요[여기](https://purchase.aspose.com/buy).
### 무료 평가판이 제공되나요?
 예, 무료 평가판으로 Aspose.Page 기능을 살펴보세요[여기](https://releases.aspose.com/).
### 커뮤니티 지원과 토론은 어디서 찾을 수 있나요?
 Aspose.Page 커뮤니티에 참여하세요.[법정](https://forum.aspose.com/c/page/39).
### Aspose.Page에 대한 임시 라이선스를 어떻게 얻을 수 있나요?
 임시 라이센스 취득[여기](https://purchase.aspose.com/temporary-license/).