---
date: 2026-06-20
description: A4 페이지 크기를 설정하고, Java에서 PostScript 파일을 생성하며, Aspose.Page를 사용하여 사용자 정의
  글꼴을 추가하는 방법을 배워보세요. 오늘 무료 체험을 이용해 보세요!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Java에서 PostScript로 문서 만들기
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Java와 Aspose.Page를 사용하여 A4 페이지 크기를 설정하고 PostScript를 생성하는 방법
url: /ko/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java와 Aspose.Page를 사용하여 A4 페이지 크기를 설정하고 PostScript 생성하기

## 소개
Java에서 PostScript 파일을 생성하면서 **set a4 page size**가 필요하다면, Aspose.Page는 저수준 세부 사항을 숨겨주는 빠르고 안정적인 API를 제공합니다. 이 튜토리얼에서는 전체 워크플로우—PostScript 문서 생성, A4 페이지 차원 구성, 필요 시 **adding custom fonts**—를 단계별로 살펴봅니다. 마지막에는 어떤 Java 프로젝트에도 바로 삽입할 수 있는 사용 가능한 코드 스니펫을 얻을 수 있습니다.

## 빠른 답변
- **Java에서 PostScript를 생성하는 라이브러리는?** Aspose.Page for Java.  
- **이 가이드가 대상으로 하는 페이지 크기는?** A4 (210 mm × 297 mm).  
- **내 자체 글꼴을 포함할 수 있나요?** 예 – 저장 옵션에서 추가 글꼴 폴더를 설정합니다.  
- **프로덕션에 라이선스가 필요합니까?** 상업용 라이선스가 필요하며, 무료 체험판을 사용할 수 있습니다.  
- **지원되는 Java 버전은?** Java 8 이상.

## Java에서 a4 페이지 크기를 설정하고 postscript 생성하는 방법
Aspose.Page 라이브러리를 로드하고 `PsSaveOptions`를 A4 상수로 구성한 뒤, 10줄 이하의 코드로 문서를 파일에 기록합니다. 이 직접적인 접근 방식은 올바른 페이지 차원을 보장하고 추가 설정 없이 사용자 정의 글꼴을 추가할 수 있게 합니다.

## PostScript A4 크기란?
PostScript A4 크기는 ISO 216 표준(210 mm × 297 mm)을 PostScript 페이지 설명 언어로 표현한 것입니다. 프린터와 뷰어가 해석하는 인쇄 영역을 정의하여 플랫폼 간 레이아웃 일관성을 보장합니다. PostScript가 장치 독립적인 방식으로 페이지 내용을 기술하기 때문에 A4 크기를 사용하면 전 세계 모든 A4 지원 프린터나 뷰어에서 동일하게 표시됩니다.

## PostScript 페이지 크기를 설정하기 위해 Aspose.Page를 사용하는 이유
Aspose.Page는 **30개 이상의 PostScript 연산자**를 지원하고 전체 문서를 메모리에 로드하지 않고도 **500 MB**까지 파일을 생성할 수 있습니다. 이는 페이지 차원을 정밀하게 제어하면서 대용량 작업을 효율적으로 처리할 수 있게 합니다. 또한 라이브러리는 복잡한 PostScript 구문을 추상화하고, 리소스를 자동으로 관리하며, 고성능 스트리밍을 제공해 단순한 1페이지 전단지부터 복잡한 다페이지 보고서까지 모두에 적합합니다.

## Java에서 사용자 정의 글꼴 추가하는 방법
고유 폰트를 임베드하면 생성된 문서가 어떤 프린터나 뷰어에서도 설계대로 정확히 표시됩니다. Aspose.Page는 지정된 폴더에 있는 글꼴을 자동으로 검색합니다. 추가 글꼴 폴더를 등록하면 TrueType 또는 OpenType 글꼴을 자유롭게 사용할 수 있어 폰트 대체를 방지하고 모든 출력 장치에서 브랜드 일관성을 유지할 수 있습니다.

## 전제 조건
시작하기 전에 다음이 필요합니다:

- Java 프로그래밍에 대한 기본 지식.  
- Aspose.Page for Java가 설치되어 있어야 합니다. 다운로드는 [here](https://releases.aspose.com/page/java/)에서 가능합니다.  
- 임베드하려는 사용자 정의 글꼴이 들어 있는 `necessary_fonts`(또는 원하는 이름) 폴더.

## 패키지 가져오기
Java 프로젝트에서 필요한 Aspose.Page 클래스를 가져옵니다:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

이제 예제를 명확한 번호 단계로 나누어 보겠습니다.

### 1단계: 문서 디렉터리 설정
`OUTPUT_DIR` 상수는 라이브러리에게 생성된 파일을 어디에 기록할지 알려줍니다.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### 2단계: 글꼴 폴더 정의
`FONTS_FOLDER`는 사용자 정의 TrueType 또는 OpenType 글꼴이 들어 있는 디렉터리를 가리킵니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### 3단계: PostScript 문서를 위한 출력 스트림 생성
`FileOutputStream`은 최종 PostScript A4 출력을 받을 스트림을 엽니다.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### 4단계: A4 크기로 저장 옵션 생성
`PsSaveOptions`를 사용하면 대상 페이지 크기를 지정할 수 있습니다.  
**정의:** `PsPageSize`는 A4, Letter, Legal 등 표준 페이지 크기 상수를 포함하는 열거형입니다.  
`options.setPageSize(PsPageSize.A4)`를 설정하면 문서가 표준 A4 차원으로 구성됩니다.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### 5단계: 페이지 여백 설정 및 사용자 정의 글꼴 폴더 추가
`options.setMargins(0, 0, 0, 0)`은 전체 bleed 페이지를 위해 모든 여백을 제거하고, `options.setAdditionalFontsFolder(FONTS_FOLDER)`는 사용자 정의 글꼴을 등록합니다.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### 6단계: 다중 페이지 또는 단일 페이지 PS 문서 생성
`PsDocument document = new PsDocument(outputStream, options)`가 문서를 생성합니다. `PsDocument`는 하나 이상의 페이지를 포함할 수 있는 PostScript 문서를 나타냅니다. 다중 페이지 출력을 원하면 `multiPaged`를 `true`로 설정합니다.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### 7단계: 현재 페이지 닫고 문서 저장
`document.close()`를 호출하면 파일이 최종화되고 **PostScript A4 size** 출력이 디스크에 기록됩니다.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## 일반적인 문제 및 팁
- **Font not appearing?** 글꼴 파일이 지원되는 TrueType 또는 OpenType 형식인지, `FONTS_FOLDER`가 슬래시(`/`)로 끝나는지 확인하세요.  
- **Margins still showing?** `PsDocument`를 생성하기 **이전**에 `options.setMargins(...)`를 호출하세요.  
- **Multi‑page output looks blank?** 필요한 각 추가 페이지마다 `document.newPage()`를 호출해야 합니다.

## 자주 묻는 질문

**Q: PostScript 문서에 사용자 정의 글꼴을 사용할 수 있나요?**  
A: 예, 저장 옵션에서 추가 글꼴 폴더를 설정하면 (Step 5 참고) Aspose.Page가 자동으로 글꼴을 임베드합니다.

**Q: Aspose.Page for Java에 대한 체험 버전이 있나요?**  
A: 예, 무료 체험판을 [here](https://releases.aspose.com/)에서 받을 수 있습니다.

**Q: 전체 API 레퍼런스는 어디서 확인할 수 있나요?**  
A: 문서화된 내용을 [here](https://reference.aspose.com/page/java/)에서 확인하세요.

**Q: Aspose.Page for Java 라이선스는 어디서 구매하나요?**  
A: 라이선스를 [here](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

**Q: 커뮤니티에 도움을 요청하려면 어디로 가야 하나요?**  
A: Aspose.Page 포럼 [forum](https://forum.aspose.com/c/page/39)에서 질문하세요.

**Q: 다중 페이지 PostScript 파일을 생성할 수 있나요?**  
A: 물론입니다—Step 6에서 `multiPaged`를 `true`로 설정하고 각 추가 페이지마다 `document.newPage()`를 호출하면 됩니다.

## 결론
이 단계들을 따라 하면 **how to set a4 page size**와 **PostScript** 파일을 Java와 Aspose.Page로 생성하는 방법을 알게 되었으며, **add custom fonts java**를 통해 글꼴을 추가하고 페이지 크기 옵션을 제어할 수 있습니다. Aspose.Page가 복잡한 작업을 처리해 주므로 문서 내용에 집중할 수 있습니다.

---

**Last Updated:** 2026-06-20  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Page Java Tutorial – set custom page size while Adding Pages in PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [How to Add Text in PostScript with Aspose.Page for Java](/page/java/postscript-text-manipulation/)
- [Aspose Page Java Tutorial - Convert PostScript to PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```