---
date: 2025-12-03
description: Aspose.Page for Java를 사용하여 EPS를 PNG로 저장하고 메터드 라이선스를 구성하는 방법을 배우세요. 전체
  코드 예제가 포함된 단계별 가이드.
language: ko
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Aspose.Page Java(계량 라이선스)로 EPS를 PNG로 저장
url: /java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java (Metered License)로 EPS를 PNG로 저장하기

## 소개
Java 애플리케이션에서 **EPS를 PNG로 저장**해야 하고 라이선스 관리를 간편하게 하고 싶다면 이곳이 정답입니다. 이 튜토리얼에서는 Aspose.Page의 Metered 라이선스를 설정하고, PostScript(EPS) 파일을 로드한 뒤 PNG 이미지로 변환하는 과정을 단계별로 자세히 안내합니다.

## 빠른 답변
- **“EPS를 PNG로 저장”이란 무엇인가요?** 벡터 EPS 파일을 래스터 PNG 이미지로 변환하는 것입니다.  
- **Metered 라이선스를 사용하는 이유는?** 처리한 페이지 수만큼만 비용을 지불하므로 가변 워크로드에 최적입니다.  
- **인터넷 연결이 필요한가요?** 아니요, Metered 키는 로컬에서 검증됩니다.  
- **필요한 Java 버전은?** Java 8 이상.  
- **설정에 걸리는 시간은?** 기본 구현 기준 약 10 분.

## “EPS를 PNG로 저장”이란?
EPS를 PNG로 저장한다는 것은 확장 가능한 Encapsulated PostScript 문서를 널리 지원되는 비트맵 형식으로 변환하는 것을 의미합니다. PNG는 투명도를 유지하고 손실 없는 압축을 제공해 웹 그래픽, 썸네일, 인쇄 미리보기 등에 이상적입니다.

## 이 작업에 Aspose.Page를 사용하는 이유
- **Pure Java API** – 네이티브 종속성이 없습니다.  
- **고충실도** – 벡터 그래픽을 정확하게 렌더링합니다.  
- **Metered 라이선스** – 변환한 만큼만 비용을 지불합니다.  
- **다양한 출력 포맷 지원** – PNG, JPEG, TIFF 등.

## 사전 준비 사항
시작하기 전에 다음을 확인하세요:

- Java 프로그래밍 기본 지식.  
- Aspose.Page 라이브러리 설치 – [여기](https://releases.aspose.com/page/java/)에서 다운로드.  
- Aspose 계정을 통해 발급받은 Metered 공개 키와 비공개 키.

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다. 코드는 그대로 유지해야 컴파일 오류가 발생하지 않습니다.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## 단계 1: 문서 및 이미지 포맷 초기화
Metered 키를 설정하고 출력 포맷(PNG)을 정의합니다. 이는 **EPS를 PNG로 저장** 작업의 기반이 됩니다.

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

## 단계 2: PostScript 입력 스트림 초기화
변환하려는 EPS 파일을 엽니다. 스트림은 문서를 Aspose.Page에 전달합니다.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## 단계 3: 문서 라이선스 확인
처리 전에 Metered 라이선스가 올바르게 적용되었는지 항상 확인합니다.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## 단계 4: 옵션 및 이미지 디바이스 초기화
변환 설정을 제어하는 옵션 객체와 렌더링된 이미지를 받을 디바이스를 생성합니다.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## 단계 5: EPS 파일을 이미지로 저장
핵심 **EPS를 PNG로 저장** 호출입니다. 문서는 설정한 옵션을 사용해 이미지 디바이스에 렌더링됩니다.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## 단계 6: 이미지 바이트 가져와 저장
디바이스에서 PNG 바이트를 추출하고 디스크에 파일로 씁니다.

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

## 일반적인 문제와 해결 방법
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **License not recognized** | Keys are incorrect or placed in the wrong order. | Double‑check the public/private key strings and ensure `setMeteredKey` is called before any document processing. |
| **Output file is empty** | `device.getImagesBytes()` returned `null`. | Verify that the EPS file is valid and that the `ImageSaveOptions` are not set to a zero‑size canvas. |
| **OutOfMemoryError on large EPS** | Rendering large vector files consumes a lot of memory. | Process pages one‑at‑a‑time or increase JVM heap (`-Xmx2g`). |

## 자주 묻는 질문

**Q: Metered 공개 키와 비공개 키는 어떻게 얻나요?**  
A: Aspose 계정을 통해 발급받을 수 있습니다.

**Q: Aspose.Page 라이브러리는 무료인가요?**  
A: 무료 체험판과 유료 버전이 모두 제공됩니다. 무료 체험은 [여기](https://releases.aspose.com/)에서 받아보세요.

**Q: 상업 프로젝트에 Aspose.Page를 사용할 수 있나요?**  
A: 네, 상업용 라이선스가 제공됩니다. 구매는 [여기](https://purchase.aspose.com/buy)에서 가능합니다.

**Q: 추가 문서는 어디서 찾을 수 있나요?**  
A: 문서는 [여기](https://reference.aspose.com/page/java/)에서 확인하세요.

**Q: 임시 라이선스는 어떻게 얻나요?**  
A: 임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 발급받을 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Page 24.12 for Java  
**Author:** Aspose  

---