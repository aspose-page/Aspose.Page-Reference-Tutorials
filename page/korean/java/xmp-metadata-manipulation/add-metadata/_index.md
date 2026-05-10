---
date: 2026-03-08
description: Aspose Page Java 튜토리얼을 통해 EPS 파일에 XMP 메타데이터를 추가하는 방법을 배워보세요. 문서 관리를 향상시키기
  위해 이 단계별 가이드를 따라가세요.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Aspose Page Java 튜토리얼 – EPS 파일에 XMP 메타데이터 추가
url: /ko/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 XMP에 메타데이터 추가

## 소개
이 **aspose page java tutorial**에서는 Java를 사용해 문서의 메타데이터에 XMP 정보를 추가하는 방법을 배웁니다. 이 단계별 가이드는 기존 EPS 파일을 읽고, XMP 메타데이터를 추출한 뒤, Aspose.Page for Java 라이브러리를 사용해 변경 사항을 디스크에 저장하는 과정을 안내합니다. 튜토리얼을 마치면 EPS 워크플로우에서 XMP를 다루는 견고하고 재사용 가능한 패턴을 갖게 됩니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Page for Java  
- **모든 EPS 파일에 XMP를 추가할 수 있나요?** 예 – API는 XMP 블록이 없을 경우 새 블록을 생성합니다.  
- **개발에 라이선스가 필요합니까?** 평가용 무료 체험판을 사용할 수 있지만, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** Java 8 이상.  
- **구현 시간은 얼마나 걸리나요?** 기본 메타데이터 업데이트는 보통 10분 이내에 완료됩니다.

## Aspose Page Java란?
Aspose.Page for Java(일반적으로 **aspose page java**라고 함)는 Adobe 소프트웨어 없이도 개발자가 PostScript 및 EPS 파일을 생성, 편집, 변환할 수 있게 해 주는 고성능 API입니다. 또한 XMP 메타데이터에 대한 완전한 접근을 제공하여 그래픽 파일에 검색 가능한 정보를 직접 삽입할 수 있습니다.

## EPS 파일에 XMP 메타데이터를 추가하는 이유
XMP 메타데이터를 삽입하면 자산 관리, 검색 가능성 및 IPTC, Dublin Core와 같은 산업 표준 준수가 향상됩니다. 제작자, 제목, 생성 날짜와 같은 필드를 추가하면 DAM, 검색 엔진, 인쇄 워크플로와 같은 하위 시스템이 EPS 자산을 자동으로 색인하고 조직할 수 있습니다.

## Aspose Page Java 튜토리얼 개요
이 튜토리얼은 EPS 파일에서 XMP 메타데이터를 조작하기 위해 필요한 핵심 단계를 보여줍니다. 이러한 단계를 이해하면 메타데이터 처리를 더 큰 문서 처리 파이프라인에 통합하고, 검색성을 개선하며, 디지털 자산 관리에 대한 산업 표준을 준수할 수 있습니다.

## 사전 요구 사항
튜토리얼을 시작하기 전에 다음이 준비되어 있는지 확인하십시오:
- Java 프로그래밍에 대한 기본 지식.  
- Aspose.Page for Java 라이브러리 설치. [여기](https://releases.aspose.com/page/java/)에서 다운로드할 수 있습니다.  
- 수정하려는 EPS 파일.

## 패키지 가져오기
먼저 Java 프로그램에 필요한 패키지를 가져옵니다:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## 단계 1: XMP 메타데이터 가져오기
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

`"Your Document Directory"`를 실제 문서가 저장된 경로로 교체하십시오.

## 단계 2: CreatorTool 값 가져오기
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## 단계 3: CreateDate 값 가져오기
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## 단계 4: Title 값 가져오기
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## 단계 5: Format 값 가져오기
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## 단계 6: Creator 값 가져오기
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## 단계 7: MetadataDate 값 가져오기
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## 단계 8: 새로운 XMP 메타데이터와 함께 문서 저장
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

마지막으로 입력 EPS 스트림을 닫는 것을 잊지 마세요:

```java
// Close input EPS stream
psStream.close();
```

이제 Aspose.Page for Java를 사용해 EPS 파일에 메타데이터를 성공적으로 추가했습니다!

## 일반적인 문제와 해결 방법
- **XMP 블록이 없음** – API가 자동으로 생성하지만, EPS 파일이 손상되지 않았는지 확인하십시오.  
- **지원되지 않는 문자** – XMP 값은 UTF‑8이어야 하며, 메타데이터 필드에 비표준 기호를 사용하지 마세요.  
- **대용량 EPS 파일** – 메모리 사용량을 낮게 유지하려면 스트림 방식(예시와 같이)으로 파일을 처리하고, `finally` 블록에서 스트림을 반드시 닫으세요.

## 결론
이 **aspose page java tutorial**에서는 Aspose.Page for Java 라이브러리를 사용해 EPS 파일에 XMP 메타데이터를 추가하는 방법을 살펴보았습니다. 이 강력한 API를 통해 문서 메타데이터를 프로그래밍 방식으로 조작하여 자산을 체계적으로 관리하고 검색 가능하게 만들 수 있습니다.

## 자주 묻는 질문

**Q: Aspose.Page for Java는 무료로 사용할 수 있나요?**  
A: Aspose.Page for Java는 상업용 제품입니다. 무료 체험판은 [여기](https://releases.aspose.com/)에서 확인할 수 있습니다.

**Q: Aspose.Page for Java 문서는 어디에서 찾을 수 있나요?**  
A: 문서는 [여기](https://reference.aspose.com/page/java/)에서 제공됩니다.

**Q: Aspose.Page for Java 임시 라이선스는 어떻게 얻나요?**  
A: 임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

**Q: Aspose.Page for Java가 지원하는 파일 형식은 무엇인가요?**  
A: EPS, PDF, XPS 등 다양한 형식을 지원합니다.

**Q: Aspose.Page for Java를 구매할 수 있나요?**  
A: 예, [여기](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

**Q: 메타데이터를 추가할 때 대용량 EPS 파일은 어떻게 처리하나요?**  
A: 스트리밍 방식으로 파일을 처리하여 메모리 사용량을 낮게 유지하고, 스트림을 즉시 닫으세요.

**Q: 기존 XMP 필드를 읽기만이 아니라 수정할 수 있나요?**  
A: 물론입니다 – `xmp.put(key, value)`를 사용해 저장 전에 기존 항목을 업데이트하거나 새 항목을 추가할 수 있습니다.

---

**마지막 업데이트:** 2026-03-08  
**테스트 환경:** Aspose.Page for Java 24.12 (최신)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}