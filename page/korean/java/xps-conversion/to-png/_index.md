---
title: Java에서 XPS를 PNG로 변환
linktitle: Java에서 XPS를 PNG로 변환
second_title: Aspose.페이지 자바 API
description: Aspose.Page를 사용하여 Java에서 XPS를 PNG로 손쉽게 변환하세요. 안정적이고 개발자 친화적인 솔루션으로 문서 작업을 간소화하세요.
weight: 13
url: /ko/java/xps-conversion/to-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 XPS를 PNG로 변환

## 소개
소프트웨어 개발의 역동적인 세계에서는 XPS(XML Paper Spec) 문서를 PNG(Portable Network Graphics) 이미지로 변환해야 하는 필요성이 자주 발생합니다. Java에서 이 작업을 원활하게 수행하기 위해 Aspose.Page는 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Java용 Aspose.Page를 사용하여 XPS를 PNG로 변환하는 과정을 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 설정되어 있는지 확인하세요.
1. JDK(Java Development Kit): 시스템에 JDK가 설치되어 있는지 확인하세요.
2.  Aspose.Page for Java: Aspose.Page 라이브러리를 다운로드하고 설치하세요. 다운로드 링크를 찾을 수 있습니다[여기](https://releases.aspose.com/page/java/).
3. 통합 개발 환경(IDE): IntelliJ IDEA 또는 Eclipse와 같은 Java 호환 IDE를 선택하세요.
## 패키지 가져오기
Java 프로젝트에서 Aspose.Page 기능을 활용하는 데 필요한 패키지를 가져옵니다. Java 파일 시작 부분에 다음 가져오기 문을 추가합니다.
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## 1단계: 문서 디렉터리 설정
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
```
## 2단계: XPS 문서 로드
```java
// XPS 문서 로드
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## 3단계: 옵션 초기화
```java
// 필요한 매개변수로 옵션 객체를 초기화합니다.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## 4단계: 렌더링 장치 생성
```java
// PDF 형식용 렌더링 장치 만들기
ImageDevice device = new ImageDevice();
```
## 5단계: 저장 및 반복
```java
// 옵션 및 장치를 사용하여 XPS 문서를 PNG로 저장
document.save(device, options);
//문서 파티션(XPS 용어로 고정 문서)을 통해 반복
for (int i = 0; i < device.getResult().length; i++) {
    // 파티션 페이지를 통해 반복
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // 이미지 출력 스트림 초기화
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // 이미지 쓰기
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // 스트림 닫기
        imageStream.close();
    }
}
```
다음 단계를 따르면 Java용 Aspose.Page를 사용하여 XPS 문서를 PNG 이미지로 손쉽게 변환할 수 있습니다.
## 결론
결론적으로 Java용 Aspose.Page는 XPS에서 PNG로의 변환 프로세스를 단순화하여 개발자에게 안정적이고 효율적인 도구를 제공합니다. 이 라이브러리를 Java 프로젝트에 통합하여 문서 조작 작업을 간소화하세요.
## 자주 묻는 질문
### 상용 프로젝트에서 Java용 Aspose.Page를 사용할 수 있나요?
 예, Aspose.Page는 상용 제품입니다. 라이센스 정보를 확인할 수 있습니다.[여기](https://purchase.aspose.com/buy).
### 무료 평가판이 제공되나요?
 예, 무료 평가판을 사용해 볼 수 있습니다[여기](https://releases.aspose.com/).
### Java용 Aspose.Page에 대한 설명서는 어디에서 찾을 수 있나요?
 포괄적인 문서를 사용할 수 있습니다.[여기](https://reference.aspose.com/page/java/).
### 테스트 목적으로 임시 라이센스를 얻으려면 어떻게 해야 합니까?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Aspose.Page 토론을 위한 커뮤니티 포럼이 있습니까?
 예, 커뮤니티 포럼을 방문하세요[여기](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
