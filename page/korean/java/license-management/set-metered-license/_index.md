---
title: Aspose.Page Java와 간편한 측정 라이선스 통합
linktitle: Java에서 측정 라이센스 설정
second_title: Aspose.페이지 자바 API
description: Aspose.Page와 Java의 원활한 통합을 살펴보세요. 계량형 라이선스를 손쉽게 설정하고 문서 처리 기능을 향상하세요.
weight: 10
url: /ko/java/license-management/set-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java와 간편한 측정 라이선스 통합

## 소개
Aspose.Page를 사용하여 Java에서 계량 라이선스를 설정하는 방법에 대한 종합 가이드에 오신 것을 환영합니다. 문서 처리 기능을 향상시키고 Aspose.Page와의 원활한 통합을 원하신다면 올바른 위치에 오셨습니다. 이 튜토리얼에서는 각 단계를 쉽게 소화할 수 있는 단위로 나누어 프로세스를 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
-  Aspose.Page 라이브러리가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/page/java/).
- Aspose 계정을 통해 얻을 수 있는 측정된 공개 및 개인 키.
## 패키지 가져오기
Java 프로그램에 필요한 패키지를 가져오는 것부터 시작해 보겠습니다. Aspose.Page 라이브러리가 프로젝트에 통합되어 있는지 확인하세요.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## 1단계: 문서 및 이미지 형식 초기화
첫 번째 단계는 문서를 설정하고 원하는 이미지 형식을 정의하는 것입니다.
```java
// 측정된 공개 및 개인 키 설정
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// setMeteredKey 속성에 액세스하고 공개 키와 개인 키를 매개변수로 전달합니다.
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## 2단계: PostScript 입력 스트림 초기화
이 단계에서는 처리를 위해 PostScript 입력 스트림을 초기화합니다.
```java
// PostScript 입력 스트림 초기화
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## 3단계: 문서 라이선스 확인
계속하기 전에 문서에 적절한 라이선스가 부여되었는지 확인하는 것이 중요합니다.
```java
// 문서에 라이선스가 있는지 확인하세요.
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## 4단계: 옵션 및 이미지 장치 초기화
이제 기본 매개변수를 사용하여 옵션과 이미지 장치를 초기화해 보겠습니다.
```java
// 기본 매개변수를 사용하여 옵션 개체를 초기화합니다.
ImageSaveOptions options = new ImageSaveOptions();
// 기본 매개변수를 사용하여 ImageDevice 객체를 초기화합니다.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## 5단계: EPS 파일을 이미지로 저장
정의된 옵션과 장치를 사용하여 EPS 파일을 이미지로 저장합니다.
```java
// EPS 파일을 이미지로 저장
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## 6단계: 이미지 바이트 가져오기 및 저장
이미지 바이트를 검색하여 파일에 저장합니다.
```java
// 이미지 바이트를 가져옵니다. 한 페이지에 대한 1바이트 배열입니다. 우리의 경우에는 한 페이지가 있습니다.
byte[][] imagesBytes = device.getImagesBytes();
// 이미지 바이트를 파일에 저장
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## 결론
축하해요! Aspose.Page를 사용하여 Java에서 계량 라이선스를 성공적으로 설정했습니다. 이 튜토리얼에서는 원활한 통합 프로세스를 보장하기 위한 단계별 가이드를 제공했습니다.
## 자주 묻는 질문
### Q: 측정된 공개 및 개인 키를 얻으려면 어떻게 해야 합니까?
Aspose 계정을 통해 이러한 키를 얻을 수 있습니다.
### Q: Aspose.Page 라이브러리는 무료인가요?
 Aspose.Page는 무료 평가판과 유료 버전을 모두 제공합니다. 방문하다[여기](https://releases.aspose.com/) 무료 평가판을 받으려면.
### Q: Aspose.Page를 상업용 프로젝트에 사용할 수 있나요?
 예, Aspose.Page는 상업용 라이선스를 제공합니다. 당신은 그들을 구입할 수 있습니다[여기](https://purchase.aspose.com/buy).
### Q: 추가 문서는 어디서 찾을 수 있나요?
 문서를 참조하세요[여기](https://reference.aspose.com/page/java/).
### Q: 임시 라이센스는 어떻게 얻을 수 있나요?
 임시면허 취득 가능[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
