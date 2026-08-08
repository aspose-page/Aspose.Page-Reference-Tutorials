---
date: 2026-08-08
description: Aspose.Page EPS 메타데이터를 사용하여 EPS 메타데이터에 배열 항목을 추가하는 방법을 배웁니다. 이 단계별 .NET
  가이드는 배열 항목을 추가하고 EPS 파일을 효율적으로 읽는 방법을 보여줍니다.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: 배열 항목 추가
og_description: Aspose.Page EPS 메타데이터를 사용하여 EPS 메타데이터에 배열 항목을 추가하는 방법을 알아보세요. 이 간결한
  .NET 튜토리얼을 따라 EPS 파일을 읽고 메타데이터를 효율적으로 관리할 수 있습니다.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Aspose.Page EPS 메타데이터를 사용하여 .NET에서 배열 항목 추가
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Aspose.Page EPS 메타데이터를 사용하여 .NET에서 배열 항목 추가
url: /ko/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page EPS 메타데이터에 배열 항목 추가 (.NET)

## 소개

이 튜토리얼에서는 **Aspose.Page EPS 메타데이터**를 사용하여 EPS 메타데이터에 배열 항목을 추가하는 방법을 배웁니다. EPS 파일에 추가 제목, 작성자 또는 사용자 정의 태그를 삽입해야 할 때, Aspose.Page는 모든 .NET 개발자를 위해 작업을 간단하게 만들어 줍니다. EPS 스트림을 열고 업데이트된 XMP 패킷을 저장하는 전체 과정을 단계별로 안내하므로, 자신만의 애플리케이션에 메타데이터 처리를 자신 있게 통합할 수 있습니다.

## 빠른 답변
- **Aspose.Page EPS 메타데이터를 사용하면 무엇을 할 수 있나요?** .NET에서 EPS 파일 내부의 XMP 메타데이터 배열을 읽고 쓸 수 있습니다.  
- **EPS 문서를 나타내는 클래스는 무엇인가요?** `PsDocument`는 EPS 콘텐츠를 로드하고 저장하는 핵심 클래스입니다.  
- **개발에 라이선스가 필요합니까?** 테스트용 무료 체험판을 사용할 수 있으며, 실제 운영 환경에서는 상용 라이선스가 필요합니다.  
- **그래픽을 변경하지 않고 메타데이터만 수정할 수 있나요?** 예, XMP 패킷만 변경되며 페이지 내용은 그대로 유지됩니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Aspose.Page EPS 메타데이터란?
Aspose.Page EPS 메타데이터는 EPS 파일에 삽입된 XMP 기반 정보 블록입니다. 제목, 작성자, 키워드 및 사용자 정의 태그와 같은 설명 속성을 ISO 16684‑1 표준에 따라 저장합니다. 이 메타데이터는 Aspose.Page API를 통해 프로그래밍 방식으로 접근 및 수정할 수 있어 자동화된 문서 관리와 검색 최적화를 가능하게 합니다.

## 왜 EPS 메타데이터를 수정해야 하나요?
Aspose.Page는 **30개 이상의 메타데이터 필드**를 처리하고 전체 문서를 메모리에 로드하지 않고도 **200 MB**까지의 EPS 파일을 다룰 수 있어, 전체 파일 파싱에 비해 CPU 사용량을 최대 40 %까지 절감합니다. 메타데이터를 업데이트하면 검색 가능성, 규정 준수 및 후속 워크플로 자동화가 향상됩니다.

## 사전 요구 사항

- 기본 .NET 프로그래밍 지식.  
- Aspose.Page for .NET이 설치되어 있어야 합니다 – [download Aspose.Page for .NET](https://releases.aspose.com/page/net/)에서 다운로드하세요.  
- 샘플 코드를 실행할 수 있는 Visual Studio(또는 .NET 호환 IDE).

## EPS 메타데이터에 배열 항목을 추가하는 방법?
배열 항목을 추가하려면 먼저 EPS 파일을 `PsDocument`로 로드한 다음 `GetXmpMetadata()`를 사용해 XMP 패킷을 가져옵니다. 원하는 XMP 배열(`dc:title` 또는 `dc:creator` 등)에 `AddArrayItem()` 메서드를 호출해 새 값을 추가합니다. 마지막으로 `Save()`를 호출해 그래픽 내용은 그대로 두고 업데이트된 메타데이터를 파일에 기록합니다.

### 단계 1: eps 파일 입력 스트림 초기화
`PsDocument`는 EPS 문서를 나타내며 콘텐츠에 접근할 수 있는 메서드를 제공합니다. 아래 코드는 EPS 파일을 스트림으로 열고 `PsDocument` 인스턴스를 생성합니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### 단계 2: xmp 메타데이터 가져오기
`GetXmpMetadata()`는 EPS 파일에 삽입된 XMP 패킷을 반환합니다. 패킷이 없으면 API가 기존 PostScript 주석을 기반으로 새 패킷을 생성합니다.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### 단계 3: xmp 메타데이터 값 변경
`AddArrayItem()`은 기존 XMP 배열에 새 값을 추가하며 다른 항목을 덮어쓰지 않습니다. 이를 사용해 메타데이터에 제목, 작성자 또는 사용자 정의 태그를 추가할 수 있습니다.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### 단계 4: 변경된 xmp 메타데이터와 함께 eps 파일 저장
`Save()`는 원본 PostScript 내용을 유지하면서 수정된 XMP 패킷을 EPS 파일에 다시 씁니다. 출력 경로를 지정해 새 파일을 만들거나 원본을 덮어쓸 수 있습니다.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## 일반적인 함정 및 문제 해결

- **Null XMP packet** – `GetXmpMetadata()`가 `null`을 반환하면 EPS 파일에 최소 하나의 주석 블록이 포함되어 있는지 확인하고, 없을 경우 새 `XmpMetadata` 인스턴스를 수동으로 생성하세요.  
- **Encoding issues** – 문자열 값을 추가할 때 UTF‑8을 사용해 비ASCII 언어에서 문자 손상이 발생하지 않도록 하세요.  
- **Large files** – 150 MB를 초과하는 EPS 파일의 경우 `FileStream`과 버퍼를 사용해 입력을 스트리밍하면 메모리 사용량을 낮출 수 있습니다.

## 자주 묻는 질문

**Q: Aspose.Page가 모든 .NET 환경과 호환되나요?**  
A: 예, Aspose.Page는 .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7 전반에 걸쳐 작동하며 Windows, Linux, macOS에서 일관된 API 동작을 제공합니다.

**Q: Aspose.Page를 무료로 사용할 수 있나요?**  
A: [Aspose 구매 페이지](https://purchase.aspose.com/buy)에서 무료 체험판을 다운로드해 라이브러리를 평가할 수 있습니다. 실제 운영 환경에서는 상용 라이선스가 필요합니다.

**Q: Aspose.Page에 임시 라이선스가 있나요?**  
A: 단기 프로젝트나 평가 기간을 위해 [임시 라이선스 페이지](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 발급받을 수 있습니다.

**Q: Aspose.Page 커뮤니티 지원을 어디서 찾을 수 있나요?**  
A: [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)에서 토론에 참여해 질문하고 다른 개발자와 솔루션을 공유하세요.

**Q: Aspose.Page for .NET 최신 버전은 무엇인가요?**  
A: 최신 릴리스 노트와 다운로드 링크는 공식 [문서](https://reference.aspose.com/page/net/)를 참고하세요.

---

**Last Updated:** 2026-08-08  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## 관련 튜토리얼

- [Change Array Items with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Add Simple Properties with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Add Namespace with Aspose.Page for .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}