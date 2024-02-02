---
title: Java PostScript에 이미지 추가
linktitle: Java PostScript에 이미지 추가
second_title: Aspose.페이지 자바 API
description: PostScript 문서에 이미지를 추가하는 방법에 대한 이 튜토리얼에서 Aspose.Page Java의 원활한 통합을 살펴보세요. 문서 조작 능력을 향상시키세요.
type: docs
weight: 10
url: /ko/java/postscript-image-manipulation/add-image/
---
## 소개
이 튜토리얼에서는 Aspose.Page for Java 라이브러리를 사용하여 Java PostScript 문서에 이미지를 추가하는 방법을 살펴보겠습니다. Aspose.Page는 PostScript 파일 작업을 위한 다양한 기능을 제공하는 강력한 라이브러리로, 개발자가 문서를 원활하게 조작하고 향상시킬 수 있습니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Java 라이브러리용 Aspose.Page. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/page/java/).
- Java 프로그래밍에 대한 기본적인 이해.
## 패키지 가져오기
시작하려면 Java 프로젝트에 필요한 패키지를 가져옵니다. 다음 코드 조각을 참조로 사용하세요.
```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## 1단계: 그래픽 저장 쓰기
첫 번째 단계에서는 그래픽 저장 내용을 문서에 쓰는 작업이 포함됩니다. 이렇게 하면 나중에 수행된 모든 변환이나 수정 사항이 필요한 경우 롤백될 수 있습니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// PostScript 문서의 출력 스트림 생성
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// A4 크기로 저장 옵션 만들기
PsSaveOptions options = new PsSaveOptions();
// 페이지가 열린 상태에서 새 PS 문서 만들기
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```
## 2단계: 번역 및 변환
다음으로 문서를 번역하고 이미지 파일에서 BufferedImage 개체를 만듭니다. AffineTransform을 사용하여 크기 조정 및 회전과 같은 일련의 변환을 적용합니다.
```java
document.translate(100, 100);
// 이미지 파일에서 BufferedImage 객체 생성
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// 이미지 변환 생성
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```
## 3단계: 문서에 이미지 추가
이제 변환된 이미지를 문서에 추가하세요.
```java
document.drawImage(image, transform, null);
```
## 4단계: 그래픽 복원 쓰기
이미지를 추가한 후 그래픽 복원을 작성하여 변경 사항을 마무리합니다.
```java
document.writeGraphicsRestore();
```
## 5단계: 현재 페이지를 닫고 저장
현재 페이지를 닫고 문서를 저장합니다.
```java
document.closePage();
document.save();
```
여러 이미지를 추가하려면 이러한 단계를 반복하거나 요구 사항에 따라 변환을 사용자 정의하세요.
## 결론
 축하해요! Aspose.Page for Java를 사용하여 Java PostScript 문서에 이미지를 추가하는 방법을 성공적으로 배웠습니다. 탐색[선적 서류 비치](https://reference.aspose.com/page/java/) 더 고급 기능을 사용하려면
## 자주 묻는 질문
### 다른 프로그래밍 언어와 함께 Java용 Aspose.Page를 사용할 수 있나요?
Aspose.Page는 주로 Java를 지원하지만 다른 프로그래밍 언어에도 사용할 수 있는 버전이 있습니다.
### Aspose.Page for Java에 대한 무료 평가판이 있습니까?
 예, 무료 평가판에 액세스할 수 있습니다[여기](https://releases.aspose.com/).
### Aspose.Page for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java와 관련된 커뮤니티 지원 및 토론은 어디서 찾을 수 있나요?
 방문하다[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지역 사회 지원을 위해.
### Aspose.Page for Java 구매를 위한 추가 리소스가 있나요?
 도서관을 구매하시면 됩니다[여기](https://purchase.aspose.com/buy).