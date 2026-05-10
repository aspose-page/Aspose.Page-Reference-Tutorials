---
date: 2026-03-05
description: Aspose.Page for Java를 사용하여 EPS 파일의 XMP 메타데이터에 dc:title 배열 항목을 추가하는 방법을
  배워보세요. 빠른 결과를 위해 단계별 가이드를 따라하세요.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Java를 사용하여 XMP 메타데이터에 dc:title 배열 항목 추가하는 방법
url: /ko/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 XMP 메타데이터에 배열 항목 추가

## Introduction
이 튜토리얼에서는 Aspose.Page for Java를 사용하여 EPS 파일 내부의 XMP 메타데이터에 **dc:title**(및 기타 배열 항목)을 추가하는 방법을 알아봅니다. XMP 메타데이터를 업데이트하면 제목, 제작자, 키워드와 같은 검색 가능한 정보를 그래픽 파일에 직접 삽입할 때 유용합니다. 각 단계를 차근차근 살펴보고, 각 코드 라인이 왜 중요한지 설명하며, 변경 사항을 확인하는 방법을 보여드립니다.

## Quick Answers
- **“dc:title”은 무엇을 의미하나요?** XMP 배열로 저장되는 Dublin Core 제목 속성입니다.  
- **왜 XMP 메타데이터를 수정하나요?** 자산 관리, 검색 가능성 및 표준 준수를 향상시킵니다.  
- **기존 XMP 블록이 필요합니까?** 아니요—Aspose.Page는 누락된 경우 PS 주석을 기반으로 자동으로 생성합니다.  
- **필요한 라이브러리 버전은?** 최신 Aspose.Page for Java 릴리스이면 모두 사용 가능(2026 최신 빌드 테스트).  
- **다른 배열 속성도 추가할 수 있나요?** 예—`dc:creator`와 같은 속성에도 동일한 `addArrayItem` 메서드를 사용합니다.

## Prerequisites
시작하기 전에 다음이 준비되어 있어야 합니다:

- Aspose.Page for Java 라이브러리 설치(프로젝트 클래스패스에 JAR 추가).  
- 기본 Java 개발 경험(JDK 8+ 권장).  
- XMP 메타데이터가 이미 포함되어 있거나 최소한 PS 메타데이터 주석(`%%Title`, `%%Creator` 등)이 있는 EPS 파일.  

## Import Packages
읽기, 조작 및 EPS 파일 저장에 필요한 클래스를 가져옵니다:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Step 1: Load the EPS Document and Retrieve XMP Metadata
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

여기서는 EPS 파일을 열고 Aspose.Page에 XMP 블록을 요청합니다. 파일에 XMP가 없으면 라이브러리가 기존 PS 주석을 사용해 자동으로 생성하므로 언제든지 메타데이터 컨테이너를 사용할 수 있습니다.

## Step 2: Add a New **dc:title** Array Item  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

이 코드는 **dc:title을 추가하는 방법**을 보여줍니다. `"NewTitle"`을 삽입하려는 실제 제목으로 교체하세요. 메서드는 기존 제목 배열에 값을 추가하여 이전 제목을 보존합니다.

## Step 3: Add a New **dc:creator** Array Item  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

마찬가지로 `dc:creator` 속성을 풍부하게 만들 수 있습니다. 여러 제작자를 저장할 수 있으며, 호출할 때마다 새로운 항목이 추가됩니다.

## Step 4: Prepare the Output Stream  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

수정된 EPS 파일을 위한 스트림을 생성합니다. 다른 파일명(`xmp3_changed.eps`)을 사용하면 원본 파일을 그대로 유지할 수 있습니다.

## Step 5: Save the Document with Updated XMP Metadata  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

`save` 호출은 업데이트된 XMP 블록과 함께 EPS 데이터를 기록합니다. `finally` 블록은 예외가 발생하더라도 파일 핸들이 해제되도록 보장합니다.

## Why This Matters
정확한 `dc:title` 및 `dc:creator` 값을 삽입하면 다음이 개선됩니다:

- 디지털 자산 관리(DAM) 시스템에서의 **검색 가능성**.  
- 메타데이터를 요구하는 출판 표준에 대한 **준수**.  
- **협업** 효율성—팀원이 EPS를 열지 않고도 파일 내용을 빠르게 파악할 수 있습니다.

## Common Pitfalls & Tips
- **Pitfall:** 기존 배열 항목을 의도치 않게 덮어쓰기.  
  **Tip:** `xmp.getArrayItems("dc:title")`을 사용해 현재 값을 확인한 후 새 항목을 추가하세요.  
- **Pitfall:** 스트림을 닫지 않아 파일이 잠김.  
  **Tip:** 예시와 같이 I/O를 try‑with‑resources 또는 `finally` 블록으로 감싸세요.  
- **Tip:** 여러 `addArrayItem` 호출을 체인으로 연결해 한 번에 여러 제목이나 제작자를 추가할 수 있습니다.

## Frequently Asked Questions

### Can I use Aspose.Page for Java with other document formats?
예, Aspose.Page는 EPS, PDF, XPS 등 다양한 문서 형식을 지원합니다.

### Is there a free trial available for Aspose.Page for Java?
예, 무료 체험은 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.

### Where can I find the documentation for Aspose.Page for Java?
문서는 [여기](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

### How can I purchase Aspose.Page for Java?
제품 구매는 [여기](https://purchase.aspose.com/buy)에서 가능합니다.

### Are temporary licenses available for Aspose.Page for Java?
예, 임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 발급받을 수 있습니다.

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Page for Java (latest 2026 release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}