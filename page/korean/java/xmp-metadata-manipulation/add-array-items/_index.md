---
date: 2025-12-18
description: Aspose.Page for Java를 사용하여 EPS 파일의 XMP 메타데이터에 배열 항목을 삽입해 메타데이터를 추가하는
  방법을 배워보세요. 단계별 가이드를 따라가세요.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: 메타데이터 추가 방법 – XMP에서 배열 항목 추가 (Java)
url: /ko/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 XMP 메타데이터에 배열 항목 추가

## 메타데이터 추가 방법
Aspose.Page for Java를 사용하여 EPS 파일에 **메타데이터를 추가하는 방법**에 대한 단계별 가이드에 오신 것을 환영합니다. 이 튜토리얼에서는 XMP 메타데이터에 배열 항목을 추가하는 방법을 안내합니다—제목이나 작성자와 같은 문서 정보를 풍부하게 해야 할 때 흔히 요구되는 작업입니다. 끝까지 읽으면 XMP가 왜 가치 있는지, 프로그래밍으로 어떻게 조작하는지, 업데이트된 EPS 파일을 저장하는 방법을 이해하게 됩니다.

## 빠른 답변
- **어떤 라이브러리를 사용합니까?** Aspose.Page for Java  
- **대상 파일 형식은 무엇입니까?** EPS (Encapsulated PostScript)  
- **여러 개의 제목을 추가할 수 있나요?** 예, `xmp.addArrayItem("dc:title", ...)` 를 반복해서 사용하세요  
- **프로덕션에 라이선스가 필요합니까?** 예, 유효한 Aspose.Page 라이선스가 필요합니다.  
- **코드가 Java 8+와 호환됩니까?** 물론입니다, 모든 최신 Java 버전에서 작동합니다.  

## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건을 확인하세요:
- Aspose.Page for Java 라이브러리가 설치되어 있어야 합니다.
- Java 프로그래밍에 대한 기본 이해가 필요합니다.
- 기존 XMP 메타데이터 또는 PS 메타데이터 주석이 포함된 유효한 EPS 파일이 필요합니다.

## 패키지 가져오기
시작하려면 Aspose.Page를 사용하기 위해 필요한 패키지를 가져와야 합니다. Java 파일의 시작 부분에 다음 코드를 포함하세요:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 1단계: XMP 메타데이터 가져오기
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
이 단계에서는 EPS 파일에서 기존 XMP 메타데이터를 가져옵니다. EPS 파일에 XMP 메타데이터가 없으면 Aspose.Page가 새 메타데이터를 생성하고 PS 메타데이터 주석의 값을 채워 넣습니다.

## 2단계: "dc:title" 배열 항목 추가
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
이제 XMP 메타데이터의 **dc:title** 속성에 새 배열 항목을 추가합니다. `"NewTitle"`을 원하는 제목으로 교체하세요.

## 3단계: "dc:creator" 배열 항목 추가
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
마찬가지로 XMP 메타데이터의 **dc:creator** 속성에 새 배열 항목을 추가합니다. `"NewCreator"`을 원하는 작성자 정보로 교체하세요.

## 4단계: 출력 EPS 파일 스트림 초기화
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
업데이트된 XMP 메타데이터가 포함된 수정된 문서를 저장할 출력 EPS 파일 스트림을 준비합니다.

## 5단계: 변경된 XMP 메타데이터와 함께 문서 저장
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
업데이트된 XMP 메타데이터를 포함한 문서를 출력 EPS 파일에 저장합니다.

## 결론
축하합니다! Aspose.Page for Java를 사용하여 XMP 메타데이터에 배열 항목을 삽입함으로써 **메타데이터를 추가하는 방법**을 성공적으로 배웠습니다. 이 강력한 라이브러리는 EPS 파일을 조작하는 과정을 단순화하고 문서 처리에 대한 광범위한 기능을 제공합니다.

## Frequently Asked Questions

### Aspose.Page for Java를 다른 문서 형식과 함께 사용할 수 있나요?
예, Aspose.Page는 EPS, PDF, XPS를 포함한 다양한 문서 형식을 지원합니다.

### Aspose.Page for Java에 대한 무료 체험이 제공되나요?
예, 무료 체험은 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.

### Aspose.Page for Java 문서는 어디에서 찾을 수 있나요?
문서는 [여기](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

### Aspose.Page for Java를 어떻게 구매할 수 있나요?
제품은 [여기](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

### Aspose.Page for Java에 대한 임시 라이선스가 제공되나요?
예, 임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 얻을 수 있습니다.

## Additional Frequently Asked Questions

**Q: 같은 속성에 배열 항목을 하나 이상 추가할 수 있나요?**  
A: 물론입니다. 같은 속성에 대해 `xmp.addArrayItem`을 여러 번 호출하여 값 목록을 만들 수 있습니다.

**Q: 이 방법이 Dublin Core 외의 기존 XMP 스키마에서도 작동하나요?**  
A: 예, 네임스페이스가 올바르게 지정되어 있는 한 모든 XMP 속성에 배열 항목을 추가할**Q: 메타데이터가 올바르게 추가되었는지 어떻게 확인할 수 있나요?**  
A: XMP를 지원하는 뷰어(e.g., Adobe Bridge)에서 결과 EPS 파일을 열거나 `XmpMetadata` 메서드를 사용해 프로그래밍 방식으로 메타데이터를 추출하면 확인할 수 있습니다.

---

**마지막 업데이트:** 2025-12-18  
**테스트 환경:** Aspose.Page for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}