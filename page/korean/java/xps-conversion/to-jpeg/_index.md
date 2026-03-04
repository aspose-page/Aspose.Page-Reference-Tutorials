---
date: 2025-12-23
description: Java에서 XPS를 JPEG로 변환하는 방법을 배우고 Aspose.Page를 사용하여 XPS 파일을 효율적으로 변환하는 방법을
  알아보세요. 원활한 통합을 위한 단계별 지침이 포함된 포괄적인 가이드.
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: Java에서 XPS를 JPEG로 변환하는 방법
url: /ko/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS를 Java에서 JPEG로 변환하는 방법

## 소개
이 튜토리얼에서는 강력한 Aspose.Page 라이브러리 for Java를 사용하여 **XPS를 JPEG로 변환하는 방법**을 배웁니다. XPS 파일을 이미지 형식으로 변환하는 것은 웹 또는 데스크톱 애플리케이션에서 문서 페이지를 표시, 미리 보기 또는 추가 처리해야 할 때 흔히 요구되는 작업입니다. 각 단계를 차례로 살펴보고, 각 라인이 왜 중요한지 설명하며, 실용적인 팁을 제공하여 변환 로직을 자신감 있게 프로젝트에 통합할 수 있도록 도와드립니다.

## 빠른 답변
- **변환을 담당하는 라이브러리는 무엇인가요?** Aspose.Page for Java  
- **특정 페이지를 선택할 수 있나요?** 예 – `JpegSaveOptions`에서 `setPageNumbers`를 사용합니다  
- **제어할 수 있는 이미지 품질은 무엇인가요?** 스무딩 모드, 해상도 및 JPEG 품질 설정  
- **프로덕션에 라이선스가 필요합니까?** 예, 상용 라이선스가 필요합니다(무료 체험판 이용 가능)  
- **코드가 Java 8과 호환되나요?** 전적으로 호환됩니다 – API는 Java 8 및 이후 버전에서 동작합니다  

## XPS란 무엇이며 JPEG로 변환하는 이유는?
XPS(XML Paper Specification)는 PDF와 유사한 고정 레이아웃 문서 형식입니다. XPS를 JPEG로 변환하면 썸네일, 이메일 첨부 파일 또는 이미지 파일만 허용하는 시스템과 연동할 때 필요한 래스터 이미지가 생성됩니다. JPEG는 시각적 품질과 파일 크기 사이의 균형이 좋아 웹 기반 미리 보기용으로 이상적입니다.

## 사전 요구 사항
Before we dive into the code, ensure you have the following:

- **Java 개발 환경** – JDK 8 이상이 설치되고 구성되어 있어야 합니다.  
- **Aspose.Page for Java** – 공식 사이트에서 최신 라이브러리를 다운로드하십시오 [여기](https://releases.aspose.com/page/java/).  
- **샘플 XPS 문서** – JPEG 이미지로 변환하려는 XPS 파일.  

## 패키지 가져오기
Begin by importing the necessary classes into your Java source file:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## 단계 1: 경로 초기화 및 XPS 문서 로드
Set the directory that contains your source XPS file and create an `XpsDocument` instance:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **팁:** 플랫폼에 독립적인 경로 처리를 위해 `java.nio.file`의 `Paths.get()`을 사용하세요.

## 단계 2: JPEG 저장 옵션 구성
Define how the JPEG images should be rendered—resolution, smoothing, and which pages to export:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)`은 인쇄에 적합한 고해상도 출력을 생성합니다.  
- `setPageNumbers`를 사용하면 필요한 페이지만 선택할 수 있어 시간과 메모리를 절약합니다.

## 단계 3: 렌더링 디바이스 생성
The `ImageDevice` captures the rendered pages as byte arrays:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## 단계 4: XPS 문서를 JPEG로 렌더링
Invoke the `save` method, passing the device and the options you configured:

```java
document.save(device, options);
```

이 시점에서 `device`는 각 요소가 JPEG 인코딩된 페이지를 나타내는 2차원 배열을 보유합니다.

## 단계 5: 결과를 반복하여 파일 쓰기
Loop over the rendered pages and write each byte array to a separate JPEG file:

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

## 일반적인 문제 및 해결 방법
| 증상 | 가능한 원인 | 해결 방법 |
|---------|--------------|-----|
| **빈 JPEG 파일** | 출력 스트림이 제대로 플러시되거나 닫히지 않음 | `imageStream.close()`가 내부 루프 안에서 호출되는지 확인하십시오(예시와 같이). |
| **대용량 XPS 파일에서 메모리 부족 오류** | 한 번에 모든 페이지를 렌더링하면 RAM 사용량이 과도함 | 페이지를 작은 배치로 처리하거나 JVM 힙(`-Xmx`)을 늘리세요. |
| **페이지 누락** | `setPageNumbers`에 원하는 페이지가 포함되지 않음 | 페이지 번호 배열이 실제 XPS 페이지 인덱스(1부터 시작)와 일치하는지 확인하십시오. |

## 자주 묻는 질문

### Q: Aspose.Page가 상업 프로젝트에 적합한가요?
A: 예, Aspose.Page는 상용 제품이며 라이선스 옵션이 제공됩니다. 자세한 내용은 [여기](https://purchase.aspose.com/buy)에서 확인하십시오.

### Q: 구매 전에 Aspose.Page를 체험할 수 있나요?
A: 예, 무료 체험판을 [여기](https://releases.aspose.com/)에서 받을 수 있습니다.

### Q: Aspose.Page 문서는 어디에서 찾을 수 있나요?
A: 문서는 [여기](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

### Q: Aspose.Page에 대한 지원은 어떻게 받을 수 있나요?
A: 커뮤니티 기반 지원을 위해 [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)을 방문하십시오.

### Q: 테스트를 위해 임시 라이선스가 필요합니까?
A: 예, 임시 라이선스를 [여기](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

## 결론
이제 Aspose.Page for Java를 사용하여 **XPS를 JPEG로 변환하는 방법**을 숙달했습니다. 단계별 가이드를 따라 하면 이 변환 파이프라인을 데스크톱 도구, 웹 서비스 또는 배치 처리 유틸리티 등 모든 Java 애플리케이션에 통합할 수 있습니다. 프로젝트 요구에 맞게 다양한 해상도, 페이지 선택 및 이미지 형식을 자유롭게 실험해 보세요.

---

**마지막 업데이트:** 2025-12-23  
**테스트 환경:** Aspose.Page 24.11 for Java (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}