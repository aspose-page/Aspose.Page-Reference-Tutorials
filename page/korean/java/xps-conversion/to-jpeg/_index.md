---
title: Java에서 XPS를 JPEG로 변환
linktitle: Java에서 XPS를 JPEG로 변환
second_title: Aspose.페이지 자바 API
description: Aspose.Page를 사용하여 Java에서 XPS를 JPEG로 변환하는 방법을 알아보세요. 원활한 통합을 위한 단계별 지침이 포함된 종합 가이드입니다.
weight: 11
url: /ko/java/xps-conversion/to-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 XPS를 JPEG로 변환

## 소개
이 튜토리얼에서는 Java용 Aspose.Page를 사용하여 XPS(XML Paper Spec) 파일을 JPEG 이미지로 변환하는 방법을 살펴보겠습니다. Aspose.Page는 개발자가 XPS 및 기타 문서 형식을 원활하게 사용할 수 있게 해주는 강력한 Java 라이브러리입니다. 이 단계별 가이드는 프로세스를 이해하고 이를 Java 애플리케이션에 구현하는 데 도움이 됩니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 개발 환경: 컴퓨터에 Java 개발 환경이 설정되어 있는지 확인하세요.
-  Aspose.Page for Java 라이브러리: Aspose.Page for Java 라이브러리를 다운로드하고 설치하세요. 도서관을 찾으실 수 있습니다[여기](https://releases.aspose.com/page/java/).
- 샘플 XPS 문서: JPEG로 변환하려는 샘플 XPS 문서가 있습니다.
## 패키지 가져오기
필요한 패키지를 Java 클래스로 가져오는 것부터 시작하세요.
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## 1단계: 경로 및 XPS 문서 초기화
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// XPS 입력 스트림 초기화
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## 2단계: JpegSaveOptions 설정
```java
// 필요한 매개변수로 옵션 객체를 초기화합니다.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## 3단계: 렌더링 장치 생성
```java
// PDF 형식용 렌더링 장치 만들기
ImageDevice device = new ImageDevice();
```
## 4단계: XPS를 JPEG로 저장
```java
document.save(device, options);
```
## 5단계: JPEG 페이지 반복 및 저장
```java
//문서 파티션(XPS 용어로 고정 문서)을 통해 반복
for (int i = 0; i < device.getResult().length; i++) {
    // 파티션 페이지를 통해 반복
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // 이미지 출력 스트림 초기화
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // 이미지 쓰기
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //스트림을 닫아
        imageStream.close();
    }
}
```
이 일련의 단계는 XPS 문서를 각각 별도로 저장되는 JPEG 이미지로 효과적으로 변환합니다.
## 결론
축하해요! Aspose.Page를 사용하여 Java에서 XPS를 JPEG로 변환하는 방법을 성공적으로 배웠습니다. 이 프로세스는 Java 애플리케이션에서 문서 변환 작업을 하는 개발자에게 매우 중요합니다.
## 자주 묻는 질문

### Q: Aspose.Page는 상업용 프로젝트에 적합합니까?
 A: 예, Aspose.Page는 라이선스 옵션을 사용할 수 있는 상용 제품입니다. 확인하다[여기](https://purchase.aspose.com/buy) 자세한 내용은.
### Q: 구매하기 전에 Aspose.Page를 사용해 볼 수 있나요?
 A: 예, 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Aspose.Page 문서는 어디서 찾을 수 있나요?
 A: 문서를 사용할 수 있습니다.[여기](https://reference.aspose.com/page/java/).
### Q: Aspose.Page에 대한 지원은 어떻게 받을 수 있나요?
 답: 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지역사회 기반 지원을 위해.
### Q: 테스트하려면 임시 라이센스가 필요합니까?
 A: 네, 임시 면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
