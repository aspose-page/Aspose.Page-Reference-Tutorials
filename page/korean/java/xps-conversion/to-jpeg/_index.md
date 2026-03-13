---
date: 2026-03-13
description: Aspose.Page Java를 사용하여 Java에서 XPS를 JPEG로 변환하는 방법을 배워보세요. 이 단계별 가이드는 Aspose.Page
  Java 라이브러리를 활용해 XPS를 JPEG로 효율적으로 변환하는 방법을 보여줍니다.
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: Aspose.Page Java를 사용하여 Java에서 XPS를 JPEG로 변환하는 방법
url: /ko/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 Aspose.Page Java를 사용하여 XPS를 JPEG로 변환하는 방법

## Aspose.Page Java 소개
이 튜토리얼에서는 **Aspose.Page Java** 라이브러리를 사용하여 **XPS를 JPEG로 변환하는 방법**을 배웁니다. XPS 파일을 JPEG 이미지로 변환하는 것은 웹 포털, 데스크톱 뷰어 또는 이메일 첨부 파일에서 문서 페이지를 래스터 그래픽으로 표시해야 할 때 자주 요구됩니다. 코드 한 줄 한 줄을 자세히 살펴보고, 각 설정이 왜 중요한지 설명하며, 실용적인 팁을 공유하여 자신만의 Java 애플리케이션에 이 변환 파이프라인을 자신 있게 삽입할 수 있도록 도와드립니다.

## 빠른 답변
- **어떤 라이브러리가 변환을 담당하나요?** Aspose.Page Java  
- **특정 페이지만 선택할 수 있나요?** 예 – `JpegSaveOptions`의 `setPageNumbers` 사용  
- **어떤 이미지 품질을 제어할 수 있나요?** 스무딩 모드, 해상도, JPEG 품질 설정  
- **프로덕션에 라이선스가 필요합니까?** 예, 상용 라이선스가 필요합니다(무료 체험판 제공)  
- **코드가 Java 8과 호환되나요?** 물론입니다 – API는 Java 8 및 그 이후 버전에서 작동합니다  

## XPS란 무엇이며 왜 XPS를 JPEG로 변환해야 할까요?
XPS(XML Paper Specification)는 PDF와 유사한 고정 레이아웃 문서 형식입니다. XPS를 JPEG로 변환하면 썸네일, 이메일 첨부 파일 또는 이미지 파일만 허용하는 시스템과 통합할 때 래스터 이미지가 필요할 때 유용합니다. JPEG는 시각적 품질과 파일 크기 사이에 좋은 균형을 제공하므로 웹 기반 미리보기용으로 이상적입니다.

## 사전 요구 사항
코드에 들어가기 전에 다음을 준비하십시오:

- **Java 개발 환경** – JDK 8 이상이 설치되고 설정되어 있어야 합니다.  
- **Aspose.Page for Java** – 공식 사이트에서 최신 라이브러리를 [여기](https://releases.aspose.com/page/java/)에서 다운로드하십시오.  
- **샘플 XPS 문서** – JPEG 이미지로 변환하려는 XPS 파일  

## 패키지 가져오기
Java 소스 파일에 필요한 클래스를 가져옵니다:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## 1단계: 경로 초기화 및 XPS 문서 로드
소스 XPS 파일이 들어 있는 디렉터리를 지정하고 `XpsDocument` 인스턴스를 생성합니다:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **프로 팁:** 플랫폼에 독립적인 경로 처리를 위해 `java.nio.file`의 `Paths.get()`을 사용하세요.

## 2단계: JPEG 저장 옵션 구성
JPEG 이미지가 어떻게 렌더링될지 정의합니다 – 해상도, 스무딩, 내보낼 페이지 등:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)`은 인쇄에 적합한 고해상도 출력을 생성합니다.  
- `setPageNumbers`를 사용하면 필요한 페이지만 선택하여 시간과 메모리를 절약할 수 있습니다.

## 3단계: 렌더링 디바이스 생성
`ImageDevice`는 렌더링된 페이지를 바이트 배열로 캡처합니다:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## 4단계: XPS 문서를 JPEG로 렌더링
구성한 옵션과 디바이스를 전달하여 `save` 메서드를 호출합니다:

```java
document.save(device, options);
```

이 시점에서 `device`는 각 요소가 JPEG 인코딩된 페이지를 나타내는 2차원 배열을 보유합니다.

## 5단계: 결과를 순회하며 파일 쓰기
렌더링된 페이지를 반복하고 각 바이트 배열을 별도의 JPEG 파일로 저장합니다:

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

각 파일은 `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg` 형식으로 이름이 지정되어 원본 문서와 페이지 번호를 쉽게 식별할 수 있습니다.

## 일반 사용 사례
- 문서 관리 시스템을 위한 **썸네일 생성**  
- 이미지 형식만 지원하는 웹 애플리케이션에 **페이지 미리보기 삽입**  
- 대용량 XPS 아카이브를 **JPEG로 일괄 변환**하여 보관 또는 보고용으로 활용  

## 일반적인 문제 및 해결 방법
| 증상 | 가능 원인 | 해결 방법 |
|------|-----------|-----------|
| **빈 JPEG 파일** | 출력 스트림이 제대로 플러시되거나 닫히지 않음 | 내부 루프에서 `imageStream.close()`가 호출되는지 확인합니다(예시 참조). |
| **대용량 XPS 파일에서 메모리 부족 오류** | 모든 페이지를 한 번에 렌더링해 메모리를 과다 사용 | 페이지를 작은 배치로 처리하거나 JVM 힙(`-Xmx`)을 늘립니다. |
| **페이지 누락** | `setPageNumbers`에 원하는 페이지가 포함되지 않음 | 페이지 번호 배열이 실제 XPS 페이지 인덱스(1부터 시작)와 일치하는지 확인합니다. |

## 자주 묻는 질문

### Q: Aspose.Page를 상업 프로젝트에 사용할 수 있나요?
A: 예, Aspose.Page는 상용 제품이며 라이선스 옵션이 제공됩니다. 자세한 내용은 [여기](https://purchase.aspose.com/buy)에서 확인하십시오.

### Q: 구매 전에 Aspose.Page를 체험해볼 수 있나요?
A: 예, 무료 체험판을 [여기](https://releases.aspose.com/)에서 받을 수 있습니다.

### Q: Aspose.Page 문서는 어디에서 찾을 수 있나요?
A: 문서는 [여기](https://reference.aspose.com/page/java/)에서 제공됩니다.

### Q: Aspose.Page에 대한 지원은 어떻게 받을 수 있나요?
A: 커뮤니티 기반 지원은 [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)에서 확인하십시오.

### Q: 테스트용 임시 라이선스가 필요합니까?
A: 예, 임시 라이선스를 [여기](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

## 결론
이제 **Aspose.Page Java**를 사용하여 **XPS를 JPEG로 변환하는 방법**을 마스터했습니다. 단계별 가이드를 따라 하면 데스크톱 도구, 웹 서비스 또는 배치 처리 유틸리티 등 어떤 Java 애플리케이션에도 이 변환 파이프라인을 손쉽게 통합할 수 있습니다. 프로젝트 요구에 맞게 다양한 해상도, 페이지 선택 및 이미지 형식을 실험해 보세요.

---

**마지막 업데이트:** 2026-03-13  
**테스트 환경:** Aspose.Page 24.11 for Java (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}