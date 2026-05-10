---
date: 2026-03-08
description: Java에서 XPS를 BMP로 변환하고 Aspose.Page Java 이미지 변환 라이브러리를 사용하여 BMP 해상도를 설정하는
  방법을 배웁니다. 이 가이드는 고품질 출력과 메모리 친화적인 팁을 다룹니다.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Java에서 XPS를 BMP로 변환 – 고품질 출력을 위한 해상도 설정
url: /ko/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 XPS를 BMP로 변환하기

## 소개
Java에서 **XPS를 BMP로 변환**하고 Aspose.Page를 사용하여 최적의 이미지 품질을 위해 해상도를 설정하는 단계별 가이드에 오신 것을 환영합니다. 인쇄 파이프라인을 구축하거나 썸네일을 생성하거나 고해상도 그래픽이 필요하든, DPI를 제어하면 모든 요구 사항을 충족할 수 있는 유연성을 제공합니다.

## 빠른 답변
- **어떤 라이브러리를 사용해야 하나요?** Aspose.Page for Java는 XPS → BMP를 위한 가장 완전한 **java image conversion library**입니다.  
- **이미지 품질을 제어할 수 있나요?** 예 – `BmpSaveOptions`를 사용하여 **BMP 해상도**와 스무딩 모드를 설정합니다.  
- **대용량 XPS 파일을 처리할 때 OutOfMemoryError Java를 어떻게 피할 수 있나요?** 페이지를 파티션으로 렌더링하거나 JVM 힙(`-Xmx`)을 늘립니다.  
- **특정 페이지만 변환해야 하나요?** 물론입니다, `options.setPageNumbers()`를 사용하면 정확한 페이지를 선택할 수 있습니다.  
- **지원되는 Java 버전은 무엇인가요?** 최신 Java 버전(8 이상) 모두 원활하게 작동합니다.

## 해상도 설정의 목적은 무엇인가요?
해상도는 생성된 BMP 이미지의 인치당 점 수(DPI)를 결정합니다. 높은 DPI는 더 선명한 이미지를 제공하며, 이는 인쇄 또는 정밀 그래픽 작업에 필수적입니다. 해상도를 조정하면 **convert xps to bmp** 워크플로우의 출력 품질을 완전히 제어할 수 있습니다.

## XPS → BMP 변환에 Aspose.Page를 사용하는 이유는?
- **고품질** – 원본 XPS의 벡터 품질을 유지합니다.  
- **세밀한 제어** – DPI, 스무딩을 설정하고 변환할 특정 페이지까지 선택할 수 있습니다.  
- **외부 종속성 없음** – 순수 Java이며 네이티브 라이브러리가 필요하지 않습니다.  
- **확장성** – 단일 페이지 문서뿐만 아니라 대형 다중 페이지 XPS 파일에서도 작동합니다.  

## 전제 조건
변환 프로세스를 시작하기 전에 다음 전제 조건을 확인하십시오:
- **Java 개발 환경** – 머신에 Java 8 이상이 설치되어 있어야 합니다.  
- **Aspose.Page for Java 라이브러리** – 프로젝트에 Aspose.Page for Java 라이브러리를 다운로드하여 포함합니다. 라이브러리는 [여기](https://releases.aspose.com/page/java/)에서 찾을 수 있습니다.  
- **샘플 XPS 파일** – BMP로 변환하려는 샘플 XPS 문서를 준비합니다.

## 패키지 가져오기
Java 코드에 필요한 Aspose.Page 패키지를 포함합니다:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## XPS를 BMP로 변환할 때 해상도 설정 방법
아래는 해상도를 설정하는 위치와 방법, 그리고 **특정 페이지를 변환**하는 방법을 정확히 보여주는 간결한 번호 매기기 단계별 안내입니다.

### 1단계: XPS 문서 로드
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### 2단계: 옵션 초기화 (해상도 및 페이지 선택)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### 3단계: 렌더링 디바이스 생성
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### 4단계: 옵션을 사용해 문서 저장
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### 5단계: 렌더링된 이미지 반복 및 파일 쓰기
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

변환 과정에서 추가적인 사용자 지정이나 수정이 필요할 경우 이 단계를 반복하십시오.

## 대용량 XPS 파일 변환 시 OutOfMemoryError Java를 방지하는 방법
- **파티션으로 처리** – 예제는 이미 문서를 파티션(`device.getResult()`)으로 렌더링하므로 메모리 부담을 줄입니다.  
- **JVM 힙 증가** – `-Xmx` 플래그(예: `-Xmx2g`)를 사용하여 대형 문서에 더 많은 메모리를 할당합니다.  
- **리소스 해제** – 작업이 끝나면 `document.close()`를 호출하여 네이티브 리소스를 해제합니다.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|-------|----------|
| **저품질 BMP 출력** | `options.setResolution()`가 300 DPI 이상으로 설정되어 있는지 확인하십시오. |
| **문서의 일부만 변환됨** | `options.setPageNumbers()`에 원하는 모든 페이지 인덱스가 포함되어 있는지 확인하십시오. |
| **대형 XPS 파일에서 OutOfMemoryError** | 문서를 더 작은 파티션으로 처리하거나 JVM 힙 크기(`-Xmx`)를 늘리십시오. |
| **파일을 찾을 수 없음** | `dataDir` 경로와 입력 XPS 파일이 존재하는지 다시 확인하십시오. |

## 자주 묻는 질문
### Q: BMP 이미지의 해상도를 맞춤 설정할 수 있나요?
A: 예, 코드에서 `options.setResolution()` 매개변수를 수정하여 해상도를 조정할 수 있습니다.

### Q: Aspose.Page가 다양한 Java 버전과 호환되나요?
A: 예, Aspose.Page는 다양한 Java 버전을 지원합니다. 호환되는 버전이 설치되어 있는지 확인하십시오.

### Q: 특정 페이지 범위의 XPS 파일을 변환하려면 어떻게 해야 하나요?
A: 변환하려는 페이지 번호를 지정하려면 `options.setPageNumbers()` 메서드를 사용하십시오.

### Q: Aspose.Page가 지원하는 다른 출력 형식이 있나요?
A: 예, Aspose.Page는 다양한 출력 형식을 지원합니다. 자세한 목록은 문서를 참조하십시오.

### Q: 추가 도움이나 지원을 어디서 찾을 수 있나요?
A: 커뮤니티 지원 및 토론을 위해 [Aspose.Page Forum](https://forum.aspose.com/c/page/39) 를 방문하십시오.

---

**마지막 업데이트:** 2026-03-08  
**테스트 환경:** Aspose.Page for Java 24.12  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}