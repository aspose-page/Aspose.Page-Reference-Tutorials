---
date: 2026-02-05
description: Aspose.Page for Java를 사용하여 EPS를 PNG로 저장하고 메터드 라이선스를 구성하는 방법을 배워보세요. 전체
  코드 예제가 포함된 단계별 가이드.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Aspose.Page Java로 EPS를 PNG로 저장 (Metered License)
url: /ko/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java (Metered License)로 EPS를 PNG로 저장하기

## Introduction
Java 애플리케이션에서 **EPS를 PNG로 저장**해야 하고 라이선스 관리를 간편하게 하고 싶다면 이곳이 정답입니다. 이 튜토리얼에서는 Aspose.Page에 대한 미터링 라이선스를 설정하고, PostScript(EPS) 파일을 로드한 뒤 PNG 이미지로 변환하는 과정을 단계별로 자세히 안내합니다. 마지막에는 **EPS를 PNG로 렌더링**하는 방법과 **Java에서 PNG 파일 쓰기** 코드를 실제 운영 환경에 적용할 수 있도록 이해하게 됩니다.

## Quick Answers
- **“save EPS as PNG”가 무슨 뜻인가요?** 벡터 EPS 파일을 래스터 PNG 이미지로 변환한다는 의미입니다.  
- **왜 미터링 라이선스를 사용하나요?** 처리한 페이지 수만큼만 비용을 지불하므로 가변적인 워크로드에 적합합니다.  
- **인터넷 연결이 필요합니까?** 아니요, 미터링 키는 로컬에서 검증됩니다.  
- **필요한 Java 버전은?** Java 8 이상.  
- **설정에 얼마나 걸리나요?** 기본 구현 기준 약 10 분 정도 소요됩니다.  

## What is “save EPS as PNG”?
EPS를 PNG로 저장한다는 것은 확장 가능한 Encapsulated PostScript 문서를 널리 지원되는 비트맵 형식으로 변환하는 것을 의미합니다. PNG는 투명도를 유지하고 무손실 압축을 제공하므로 웹 그래픽, 썸네일, 인쇄 미리보기 등에 이상적입니다.

## Why render EPS to PNG with Aspose.Page?
- **Pure Java API** – 네이티브 의존성이 없으므로 JVM이 지원되는 어디서든 실행할 수 있습니다.  
- **High fidelity rendering** – 벡터 그래픽을 정확하게 래스터화하여 선 품질을 보존합니다.  
- **Metered licensing** – 변환한 양에만 비용을 지불하므로 비용 예측이 용이합니다.  
- **Multiple output options** – PNG 외에도 JPEG, TIFF 등 다양한 포맷을 생성할 수 있어 프로젝트마다 유연하게 선택할 수 있습니다.

## Prerequisites
시작하기 전에 다음을 준비하세요:

- Java 프로그래밍에 대한 기본 지식.  
- Aspose.Page 라이브러리 설치 – [여기](https://releases.aspose.com/page/java/)에서 다운로드.  
- Aspose 계정을 통해 발급받은 미터링 공개 키와 비공개 키.

## Import Packages
먼저 필요한 클래스를 import합니다. 코드를 그대로 복사해 import 블록을 유지해야 컴파일 오류가 발생하지 않습니다.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## How to save EPS as PNG using Aspose.Page Java
아래 단계별 가이드는 라이선스 설정, 파일 로드, 렌더링, 최종 PNG 파일 저장까지의 전체 흐름을 보여줍니다.

### Step 1: Initialize Document and Image Format
미터링 키를 설정하고 출력 포맷(PNG)을 정의합니다. 이는 **save EPS as PNG** 작업의 기본이 됩니다.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### Step 2: Initialize PostScript Input Stream
변환하려는 EPS 파일을 엽니다. 스트림은 문서를 Aspose.Page에 전달합니다.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Step 3: Check Document License
처리 전에 미터링 라이선스가 올바르게 적용됐는지 항상 확인합니다.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Step 4: Initialize Options and Image Device
변환 설정을 제어하는 옵션 객체와 렌더링된 이미지를 받을 디바이스를 생성합니다.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Step 5: Save EPS File as Image
핵심 **save EPS as PNG** 호출입니다. 앞서 설정한 옵션을 사용해 문서를 이미지 디바이스에 렌더링합니다.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Step 6: Get and Save Image Bytes
디바이스에서 PNG 바이트 배열을 추출하고 디스크에 파일로 저장합니다. 이 단계는 **write PNG file Java**를 안전하게 수행하는 방법을 보여줍니다.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **License not recognized** | Keys are incorrect or placed in the wrong order. | Double‑check the public/private key strings and ensure `setMeteredKey` is called before any document processing. |
| **Output file is empty** | `device.getImagesBytes()` returned `null`. | Verify that the EPS file is valid and that the `ImageSaveOptions` are not set to a zero‑size canvas. |
| **OutOfMemoryError on large EPS** | Rendering large vector files consumes a lot of memory. | Process pages one‑at‑a‑time or increase JVM heap (`-Xmx2g`). |

## Frequently Asked Questions

**Q: How do I obtain metered public and private keys?**  
A: You can obtain these keys through your Aspose account.

**Q: Is the Aspose.Page library free?**  
A: Aspose.Page offers both free trial and paid versions. Visit [here](https://releases.aspose.com/) for a free trial.

**Q: Can I use Aspose.Page for commercial projects?**  
A: Yes, Aspose.Page offers commercial licenses. You can purchase them [here](https://purchase.aspose.com/buy).

**Q: Where can I find additional documentation?**  
A: Refer to the documentation [here](https://reference.aspose.com/page/java/).

**Q: How can I get temporary licenses?**  
A: Temporary licenses can be obtained [here](https://purchase.aspose.com/temporary-license/).

**Q: What if I need to convert multi‑page EPS files?**  
A: Loop through each page using `device.getImagesBytes()` and write each byte array to a separate PNG file.

**Q: Can I change the PNG quality or color depth?**  
A: Yes, configure `ImageSaveOptions` (e.g., `options.setCompressionLevel(...)`) before calling `document.save(...)`.

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Page 24.12 for Java  
**Author:** Aspose  

**Last Updated:** 2026-02-05  
**Tested With:** Aspose.Page 24.12 for Java (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}