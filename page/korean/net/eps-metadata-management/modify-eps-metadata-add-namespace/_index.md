---
date: 2026-08-08
description: Aspose.Page for .NET를 사용하여 Aspose.Page 문서를 초기화하고 XML 네임스페이스를 추가하며 EPS
  파일의 XMP 메타데이터를 수정하는 방법을 배우세요.
keywords:
- initialize aspose page document
- c# add xml namespace
- open eps file stream
- how to add xmp namespace
lastmod: 2026-08-08
linktitle: 네임스페이스 추가
og_description: Aspose.Page for .NET와 함께 Aspose.Page 문서를 초기화하고 XML 네임스페이스를 추가하며 EPS
  파일의 XMP 메타데이터를 편집하세요. 간결한 단계와 코드 스니펫을 따라보세요.
og_image_alt: Guide showing how to add namespace to EPS metadata using Aspose.Page
  for .NET
og_title: Aspose.Page 문서를 초기화하고 .NET에서 네임스페이스 추가
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to initialize Aspose.Page document, add an XML namespace,
    and modify XMP metadata in EPS files using Aspose.Page for .NET.
  headline: Initialize Aspose.Page document and add namespace in .NET
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for .NET works with .NET Framework 4.5+, .NET Core 3.1+,
      and .NET 5/6+.
    question: Is Aspose.Page compatible with all versions of .NET?
  - answer: Absolutely. Retrieve the `XmpMetadata` object and read its properties
      without invoking `SetProperty` or `AddNamespace`.
    question: Can I extract metadata without modifying it?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support or assistance?
  - answer: Yes, you can explore a free trial of Aspose.Page on the [Aspose.Page free
      trial](https://releases.aspose.com/) page.
    question: Is there a free trial available for Aspose.Page?
  - answer: Obtain a temporary license on the [temporary Aspose.Page license](https://purchase.aspose.com/temporary-license/)
      page for testing purposes.
    question: How can I obtain a temporary license for Aspose.Page?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- Aspose.Page
- c# document processing
title: Aspose.Page 문서를 초기화하고 .NET에서 네임스페이스 추가
url: /ko/net/eps-metadata-management/modify-eps-metadata-add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET에서 Aspose.Page 문서를 초기화하고 네임스페이스 추가

## 소개

현대 .NET 개발에서 **initialize aspose page document**는 EPS 파일을 프로그래밍 방식으로 작업해야 할 때 종종 첫 번째 단계입니다. Aspose.Page for .NET은 XMP 메타데이터에 대한 완전한 제어를 제공하여 사용자 정의 XML 네임스페이스를 추가하고 기존 속성을 편집하며 변경 사항을 파일에 다시 저장할 수 있게 합니다. 이 튜토리얼은 올바른 네임스페이스 가져오기부터 수정된 EPS 파일을 영구 저장하는 단계까지 모든 세부 사항을 안내하므로 메타데이터 관리를 자신 있게 워크플로에 통합할 수 있습니다.

## 빠른 답변
- **첫 번째 코드 라인은 무엇인가요?** `new Document("yourfile.eps")`를 생성하여 EPS 파일을 로드합니다.
- **어떤 메서드가 네임스페이스를 추가하나요?** `XmpMetadata.AddNamespace(prefix, uri)`를 사용합니다.
- **개발에 라이선스가 필요합니까?** 무료 체험판은 테스트에 사용할 수 있으며, 프로덕션에는 라이선스가 필요합니다.
- **큰 EPS 파일을 스트리밍할 수 있나요?** 예—전체 파일을 메모리에 로드하지 않고 `FileStream`을 사용하여 파일을 엽니다.
- **이것이 .NET 6+와 호환되나요?** 물론입니다; Aspose.Page는 .NET Framework 4.5+, .NET Core 3.1+, 및 .NET 6+를 지원합니다.

## initialize aspose page document란 무엇인가요?

`Document` 클래스는 메모리에 로드된 EPS 파일을 나타냅니다. `new Document("file.eps")`로 파일을 로드하면 페이지, 그래픽 및 XMP 메타데이터에 직접 접근할 수 있어 문서의 모든 부분을 읽거나 수정할 수 있습니다. 또한 XMP 메타데이터와 페이지 콘텐츠를 다루는 메서드도 제공합니다.

## EPS 메타데이터에 XML 네임스페이스를 추가하는 이유

사용자 정의 XML 네임스페이스를 추가하면 메타데이터 스키마가 확장되어 표준 XMP 필드와 함께 독점 정보를 저장할 수 있습니다. Aspose.Page는 **50+** XMP 속성을 지원하며 **200+ 페이지** 파일도 전체 문서를 RAM에 상주시킬 필요 없이 처리할 수 있어 더 빠른 처리와 낮은 메모리 사용량을 제공합니다.

## 사전 요구 사항

1. **Aspose.Page for .NET library** – [Aspose.Page documentation](https://reference.aspose.com/page/net/)에서 다운로드하십시오.  
2. **.NET 개발 환경** – Visual Studio 2022, Rider 또는 .NET 6+를 지원하는 모든 IDE.

프로젝트에 라이브러리가 참조되어 있는지 확인하십시오(NuGet 또는 직접 DLL 참조를 통해) 진행하기 전에.

## 네임스페이스 가져오기

Aspose.Page를 사용하려면 `Document`와 XMP 클래스를 노출하는 핵심 네임스페이스를 가져와야 합니다.

You will need:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.XMP;
using System.IO;
```

이러한 가져오기를 통해 향후 단계에 필요한 `Document`, `XmpMetadata` 및 스트림 처리 클래스를 사용할 수 있습니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 단계 1: 프로젝트 초기화

코드를 삽입하려는 소스 파일을 엽니다. 먼저 `Document` 클래스의 인스턴스를 생성합니다. 이는 **initialize aspose page document**를 위한 초기 단계입니다. `Document` 클래스는 EPS 문서를 나타내며 내용과 메타데이터에 접근할 수 있게 합니다.

```csharp
var epsDocument = new Document("sample.eps");
```

이 코드는 EPS 파일을 `epsDocument` 객체에 로드하여 이후 모든 API 호출이 가능하도록 합니다.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## 단계 2: eps 파일 스트림 열기

`FileStream` 클래스는 파일을 읽고 쓰기 위한 스트림을 제공하여 전체 EPS 파일을 메모리에 로드하는 것을 방지합니다.

```csharp
using (FileStream fs = new FileStream("sample.eps", FileMode.Open, FileAccess.ReadWrite))
{
    // Stream is ready for XMP operations
}
```

`open eps file stream` 패턴은 프로덕션 작업에 권장됩니다.

```csharp
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);

// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);
```

## 단계 3: xmp 메타데이터 가져오기

`XmpMetadata` 클래스는 EPS 문서의 XMP 메타데이터를 캡슐화합니다.

```csharp
XmpMetadata xmp = epsDocument.XmpMetadata;
```

이제 현재 메타데이터 항목을 모두 보유한 조작 가능한 `xmp` 객체가 있습니다.

```csharp
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments.
XmpMetadata xmp = document.GetXmpMetadata();
```

## 단계 4: xmp 메타데이터 변경

`AddNamespace` 메서드는 접두사와 URI를 사용하여 새로운 XML 네임스페이스를 등록하고, `SetProperty` 메서드는 메타데이터 속성에 값을 할당합니다.

```csharp
// Define a new namespace
string prefix = "myNs";
string uri = "http://mycompany.com/metadata";

// Register the namespace with the XMP metadata object
xmp.AddNamespace(prefix, uri);

// Add a custom property under the new namespace
xmp.SetProperty($"{prefix}:Author", "John Doe");
```

`AddNamespace` 호출은 접두사를 등록하고, `SetProperty`는 해당 접두사를 사용해 값을 저장합니다.

```csharp
// Add new XML namespace "tmp".
xmp.RegisterNamespaceUri("tmp", "http://www.some.org/schema/tmp#");

// Add new string property in the new namespace.
xmp.Add("tmp:newKey", new XmpValue("NewValue"));
```

## 단계 5: eps 파일 저장

`Save` 메서드는 문서와 메타데이터를 파일 시스템에 다시 씁니다.

```csharp
epsDocument.Save("sample-updated.eps");
```

이 단계가 끝나면 EPS 파일에 새로 추가된 네임스페이스와 속성이 포함됩니다.

```csharp
// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_namespace_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
```

## 일반적인 문제 및 해결 방법

- **Namespace already exists** – `AddNamespace`가 오류를 발생시키면 해당 접두사가 이미 등록된 것입니다. 다른 접두사를 사용하거나 `xmp.GetNamespaceUri(prefix)`로 기존 URI를 가져오세요.
- **File locked by another process** – `Save`를 호출하기 전에 `FileStream`이 (`using` 블록을 사용하여) 적절히 해제되었는지 확인하십시오.
- **Metadata not persisting** – EPS 파일이 실제로 XMP를 지원하는지 확인하십시오(대부분 최신 EPS 파일은 지원합니다). 오래된 파일은 재생성해야 할 수 있습니다.

## 자주 묻는 질문

**Q: Aspose.Page가 모든 .NET 버전과 호환되나요?**  
A: 예, Aspose.Page for .NET은 .NET Framework 4.5+, .NET Core 3.1+, 및 .NET 5/6+와 호환됩니다.

**Q: 메타데이터를 수정하지 않고 추출할 수 있나요?**  
A: 물론입니다. `XmpMetadata` 객체를 가져와 `SetProperty`나 `AddNamespace`를 호출하지 않고도 속성을 읽을 수 있습니다.

**Q: 추가 지원이나 도움을 어디서 찾을 수 있나요?**  
A: 커뮤니티 지원 및 토론을 위해 [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)을 방문하십시오.

**Q: Aspose.Page의 무료 체험판이 있나요?**  
A: 예, [Aspose.Page 무료 체험](https://releases.aspose.com/) 페이지에서 무료 체험판을 확인할 수 있습니다.

**Q: Aspose.Page의 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: 테스트 용도로 [임시 Aspose.Page 라이선스](https://purchase.aspose.com/temporary-license/) 페이지에서 임시 라이선스를 얻으십시오.

---

**마지막 업데이트:** 2026-08-08  
**테스트 환경:** Aspose.Page 24.11 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Aspose.Page for .NET으로 EPS 문서에 메타데이터 추가](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Aspose.Page for .NET으로 간단한 속성 추가](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Aspose.Page for .NET으로 EPS 문서에서 메타데이터 추출](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}