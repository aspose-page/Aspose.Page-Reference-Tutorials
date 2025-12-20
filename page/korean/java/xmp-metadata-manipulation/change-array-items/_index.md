---
date: 2025-12-20
description: Aspose.Page for Java (aspose.page xmp java)를 사용하여 XMP의 배열 항목을 변경하는 방법을
  배워보세요. 단계별 가이드를 통해 메타데이터를 손쉽게 수정하고 오늘 바로 EPS 문서를 향상시키세요.
linktitle: Change Array Items in XMP using Java
second_title: Aspose.Page Java API
title: 'aspose.page xmp java: Java를 사용하여 XMP의 배열 항목 변경'
url: /ko/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp java: Change Array Items in XMP using Java

## Introduction
Aspose.Page for Java의 **XMP에서 배열 항목을 변경**하는 방법에 대한 포괄적인 가이드에 오신 것을 환영합니다. **aspose.page xmp java** 라이브러리를 사용하면 EPS 파일 내부의 XMP 메타데이터를 완벽하게 제어할 수 있어 제목, 작성자 및 기타 속성을 손쉽게 맞춤 설정할 수 있습니다. 이 튜토리얼에서는 배열 항목을 수정하는 데 필요한 모든 단계를 단계별로 안내하므로, 자신 있게 EPS 문서를 향상하고 개인화할 수 있습니다.

## Quick Answers
- **aspose.page xmp java는 무엇을 하나요?** Java에서 EPS 파일의 XMP 메타데이터를 읽고 쓸 수 있게 해줍니다.  
- **체험판을 사용하려면 라이선스가 필요하나요?** 예, 무료 체험판을 제공하지만, 실제 운영 환경에서는 라이선스가 필요합니다.  
- **지원되는 JDK 버전은?** Java 8 이상.  
- **다른 메타데이터 필드도 수정할 수 있나요?** 물론입니다 – 모든 XMP 속성을 읽거나 업데이트할 수 있습니다.  
- **API가 스레드‑안전한가요?** 대부분의 읽기/쓰기 작업은 별도의 문서 인스턴스에서 사용할 경우 안전합니다.

## What is aspose.page xmp java?
`aspose.page xmp java`는 Aspose.Page for Java 제품군의 일부로, XMP(Extensible Metadata Platform) 처리를 전담합니다. 저수준 XMP 구조를 간단한 Java 객체로 추상화하여 배열, bag, 구조화된 속성을 원시 XML을 다루지 않고도 사용할 수 있게 해줍니다.

## Why use aspose.page xmp java for EPS metadata?
- **Precision:** 특정 XMP 배열 항목(예: title, creator)을 직접 지정할 수 있습니다.  
- **Automation:** 메타데이터 업데이트를 빌드 파이프라인이나 배치 프로세스에 통합할 수 있습니다.  
- **Compatibility:** XMP 표준을 따르는 모든 EPS 파일과 호환됩니다.  

## Prerequisites
코드 작성을 시작하기 전에 다음이 준비되어 있는지 확인하세요:

- 시스템에 설치된 Java Development Kit (JDK).  
- Aspose.Page 라이브러리 for Java. 다운로드는 [here](https://releases.aspose.com/page/java/)에서 가능합니다.  

## Import Packages
시작하려면 필요한 클래스를 Java 프로젝트에 임포트하세요. Aspose.Page JAR 파일이 프로젝트의 classpath에 추가되어 있어야 합니다.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## How to Change Array Items with aspose.page xmp java

### Step 1: Get XMP Metadata
먼저 EPS 파일에서 XMP 메타데이터를 가져옵니다. 파일에 XMP 데이터가 없으면 Aspose.Page가 기존 PS 주석(예: %%Creator, %%Title)으로부터 새로운 XMP 블록을 생성합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```

### Step 2: Set "dc:title" Array Item
이제 **dc:title** 배열의 첫 번째 요소를 새로운 문자열로 교체합니다.

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### Step 3: Set "dc:creator" Array Item
마찬가지로 **dc:creator** 배열의 첫 번째 요소를 업데이트합니다.

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### Step 4: Initialize Output EPS File Stream
수정된 메타데이터를 저장할 출력 EPS 파일 스트림을 준비합니다.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

### Step 5: Save Document with Changed XMP Metadata
마지막으로 문서를 저장하여 변경 사항을 영구히 반영합니다.

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Common Pitfalls & Tips
- **Index Out of Bounds:** 지정한 인덱스가 존재하는지 확인하세요. 그렇지 않으면 Aspose가 예외를 발생시킵니다.  
- **Stream Management:** 파일 잠금을 방지하려면 `finally` 블록에서 스트림을 반드시 닫으세요.  
- **License Activation:** 유효한 라이선스를 설정하지 않으면 체험판 모드에서 워터마크가 삽입된 출력이 생성될 수 있습니다.

## Conclusion
축하합니다! 이제 **aspose.page xmp java**를 사용해 XMP 배열 항목을 변경하는 방법을 익혔습니다. 이 단계별 가이드를 통해 EPS 메타데이터를 프로그래밍 방식으로 수정할 수 있게 되었으며, 자동화된 문서 워크플로와 풍부한 콘텐츠 관리의 문을 열었습니다.

## FAQs
### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page는 주로 Java용으로 설계되었지만, Aspose는 다른 언어용 유사한 라이브러리도 제공합니다.  
### Where can I find detailed documentation for Aspose.Page for Java?
문서는 [here](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.  
### Is there a free trial available for Aspose.Page for Java?
예, 무료 체험판은 [here](https://releases.aspose.com/)에서 받을 수 있습니다.  
### How can I obtain a temporary license for Aspose.Page for Java?
임시 라이선스는 [here](https://purchase.aspose.com/temporary-license/)에서 신청할 수 있습니다.  
### Where can I purchase the full version of Aspose.Page for Java?
정식 버전은 [here](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

## Additional Frequently Asked Questions
**Q: Can I update multiple array items in one call?**  
A: 각 인덱스를 수정하려면 `setArrayItem`을 각각 호출해야 하며, 일괄 업데이트 메서드는 제공되지 않습니다.  

**Q: Does aspose.page xmp java support custom namespaces?**  
A: 예, 전체 프리픽스(예: `myNS:customProp`)를 제공하면 등록된 모든 XMP 네임스페이스를 사용할 수 있습니다.  

**Q: How do I verify that the metadata was updated correctly?**  
A: `PsDocument`로 EPS 파일을 다시 로드하고 `getXmpMetadata()`를 호출해 값을 확인하거나 XMP 뷰어로 파일을 검사하세요.  

**Q: Is it possible to remove an array item entirely?**  
A: `removeArrayItem(namespace, index)`를 사용해 XMP 배열에서 특정 항목을 삭제할 수 있습니다.  

**Q: Will the changes affect the visual appearance of the EPS?**  
A: 아니오. XMP 메타데이터는 비시각적이며 EPS 파일의 그래픽 내용에는 영향을 주지 않습니다.

---

**Last Updated:** 2025-12-20  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}