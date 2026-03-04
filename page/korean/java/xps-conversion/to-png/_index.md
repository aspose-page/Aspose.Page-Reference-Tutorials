---
date: 2025-12-23
description: Aspose.Page를 사용하여 Java에서 **XPS를 PNG로 변환**을 손쉽게 수행합니다. 이 가이드는 신뢰할 수 있고
  개발자 친화적인 솔루션으로 XPS를 이미지 파일로 렌더링하는 방법을 보여줍니다.
linktitle: Convert XPS to PNG in Java
second_title: Aspose.Page Java API
title: Java에서 XPS를 PNG로 변환
url: /ko/java/xps-conversion/to-png/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 XPS를 PNG로 변환하기

## 소개
동적인 소프트웨어 개발 환경에서 **XPS를 PNG로 변환**(XML Paper Specification → Portable Network Graphics)해야 하는 경우가 자주 발생합니다. Java에서 이 작업을 원활하게 수행하려면 Aspose.Page가 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Page for Java를 사용하여 XPS를 PNG로 변환하는 과정을 단계별로 안내합니다.

## 빠른 답변
- **어떤 라이브러리가 변환을 담당하나요?** Aspose.Page for Java  
- **어떤 포맷이 사용되나요?** XPS(소스) → PNG(출력)  
- **프로덕션에서 라이선스가 필요합니까?** 예, 상용 라이선스가 필요합니다  
- **이미지 해상도를 설정할 수 있나요?** 예, `PngSaveOptions.setResolution()`을 사용합니다  
- **특정 페이지만 선택할 수 있나요?** 물론입니다 – 옵션 객체에 페이지 번호를 지정하면 됩니다  

## XPS를 PNG로 변환해야 하는 이유
XPS를 이미지 파일로 렌더링하면 웹에서 문서를 표시하거나 보고서에 삽입하거나 미리보기용 썸네일을 생성할 때 유용합니다. PNG는 무손실 압축과 광범위한 브라우저 지원을 제공하므로 XPS 콘텐츠를 고품질 시각적으로 표현하기에 이상적인 선택입니다.

## 사전 요구 사항
튜토리얼을 시작하기 전에 다음 요구 사항이 준비되어 있는지 확인하세요:
1. **Java Development Kit (JDK)**: 시스템에 JDK가 설치되어 있어야 합니다.  
2. **Aspose.Page for Java**: Aspose.Page 라이브러리를 다운로드하고 설치합니다. 다운로드 링크는 [여기](https://releases.aspose.com/page/java/)에서 확인할 수 있습니다.  
3. **통합 개발 환경 (IDE)**: IntelliJ IDEA 또는 Eclipse와 같은 Java 호환 IDE를 선택합니다.  

## Java에서 XPS를 PNG로 변환하는 방법
아래 단계별 가이드는 **XPS 문서를 PNG 이미지**로 변환하는 방법을 설명하며, 프로젝트에 바로 복사해 사용할 수 있는 코드 스니펫을 포함합니다.

### 패키지 가져오기
Java 프로젝트에서 Aspose.Page 기능을 사용하려면 필요한 패키지를 가져와야 합니다. Java 파일의 시작 부분에 다음 import 구문을 추가하세요:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

### 단계 1: 문서 디렉터리 설정
소스 XPS 파일이 위치한 폴더와 PNG 파일을 저장할 폴더를 정의합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 단계 2: XPS 문서 로드
소스 XPS 파일을 로드하는 `XpsDocument` 인스턴스를 생성합니다.

```java
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### 단계 3: 옵션 초기화
PNG 출력 옵션을 구성합니다. 여기서 스무딩, 해상도 및 렌더링할 페이지를 지정할 수 있습니다.

```java
// Initialize options object with necessary parameters.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

### 단계 4: 렌더링 디바이스 생성
렌더링된 이미지 데이터를 보관할 `ImageDevice`를 생성합니다.

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

### 단계 5: 저장 및 반복
XPS 문서를 렌더링한 뒤, 생성된 각 PNG 바이트 배열을 디스크에 파일로 기록합니다.

```java
// Save XPS document to PNG using options and device
document.save(device, options);
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Close the Stream
        imageStream.close();
    }
}
```

이 단계를 따르면 Aspose.Page for Java를 사용해 **XPS를 이미지** 파일(PNG 형식)로 손쉽게 렌더링할 수 있습니다.

## 결론
Aspose.Page for Java는 XPS를 PNG로 변환하는 과정을 단순화하여 개발자에게 신뢰성 높고 효율적인 도구를 제공합니다. 이 라이브러리를 Java 프로젝트에 통합하면 문서 조작 작업을 보다 원활하게 수행할 수 있습니다.

## 추가 자주 묻는 질문

**Q: XPS 파일의 특정 페이지만 변환할 수 있나요?**  
A: 물론입니다. `PngSaveOptions`의 `setPageNumbers` 메서드를 사용해 렌더링할 페이지를 지정하면 됩니다.

**Q: 고품질 PNG를 위한 권장 이미지 해상도는 얼마인가요?**  
A: 300 dpi 정도가 품질과 파일 크기의 균형을 잘 맞춥니다. `options.setResolution()`을 통해 원하는 값으로 조정할 수 있습니다.

**Q: 대용량 문서에 대해 멀티스레드 변환을 지원하나요?**  
A: 예, 각 페이지 또는 문서 파티션을 별도의 스레드에서 변환하도록 로직을 구성할 수 있습니다.

**Q: 매우 큰 XPS 파일을 변환할 때 메모리 사용량을 어떻게 관리하나요?**  
A: 페이지를 순차적으로 처리하고, 각 쓰기 작업 후 `FileOutputStream`을 해제하는 방식으로 메모리를 효율적으로 관리합니다. 샘플 코드에 예시가 포함되어 있습니다.

**Q: 생성된 PNG 파일에 사용자 정의 메타데이터를 추가할 수 있나요?**  
A: `PngSaveOptions` 자체에서는 메타데이터 필드를 직접 제공하지 않지만, 표준 이미지 라이브러리를 사용해 PNG 파일을 후처리하여 메타데이터를 삽입할 수 있습니다.

---

**마지막 업데이트:** 2025-12-23  
**테스트 환경:** Aspose.Page for Java 24.12 (최신)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}