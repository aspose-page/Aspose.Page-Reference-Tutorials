---
date: 2026-01-20
description: Aspose.Page for .NET를 사용하여 XPS 문서를 고품질 PDF로 병합하면서 PDF에 페이지 번호를 손쉽게 추가하세요.
  XPS를 PDF로 변환하는 단계별 가이드를 따라보세요.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: PDF에 페이지 번호 추가 – Aspose.Page를 사용하여 XPS를 PDF로 병합
url: /ko/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PDF에 페이지 번호 추가 – Aspose.Page를 사용한 XPS를 PDF로 병합

## 소개

XPS 파일을 병합하면서 **PDF에 페이지 번호를 추가**해야 한다면, Aspose.Page for .NET이 과정을 손쉽게 해줍니다. 이 튜토리얼에서는 XPS 문서를 고품질 PDF로 변환하고, 이미지 압축을 제어하며, 최종 PDF에 페이지 번호를 자동으로 삽입하는 완전한 프로덕션‑레디 예제를 단계별로 살펴봅니다. 끝까지 진행하면 C# 프로젝트 어디에든 넣을 수 있는 재사용 가능한 코드 스니펫을 얻게 됩니다.

## 빠른 답변
- **XPS를 PDF로 병합할 때 페이지 번호를 추가할 수 있나요?** 예 – `PdfSaveOptions.PageNumbers` 속성이 바로 그 기능을 수행합니다.  
- **변환을 담당하는 라이브러리는 무엇인가요?** Aspose.Page for .NET.  
- **프로덕션 사용에 라이선스가 필요합니까?** 유효한 Aspose.Page 라이선스가 필요합니다; 테스트용 임시 라이선스를 제공받을 수 있습니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core 3.1+, 및 .NET 5/6+.  
- **고품질 이미지 출력이 가능한가요?** 물론입니다 – `JpegQualityLevel`을 100으로 설정하고 `PdfImageCompression.Jpeg`을 선택하십시오.

## 사전 요구 사항

튜토리얼을 시작하기 전에 다음 사전 요구 사항이 준비되어 있는지 확인하십시오:

- Aspose.Page for .NET: Aspose.Page 라이브러리가 설치되어 있는지 확인하십시오. [여기](https://releases.aspose.com/page/net/)에서 다운로드할 수 있습니다.
- 문서 파일: 지정한 디렉터리에 XPS 문서(`input.xps`)가 준비되어 있어야 합니다.

## 네임스페이스 가져오기

.NET 프로젝트에서 Aspose.Page를 사용하기 위해 필요한 네임스페이스를 포함하십시오:

```csharp
using Aspose.Page.XPS;
```

이 단계는 문서 변환에 필요한 클래스와 메서드에 접근할 수 있게 합니다.

## XPS 문서를 병합할 때 PDF에 페이지 번호를 추가하는 방법

`PdfSaveOptions.PageNumbers` 컬렉션을 사용하면 출력 PDF에 포함될 페이지(또는 페이지 범위)를 정확히 지정할 수 있습니다. 원하는 페이지 번호를 채워 넣으면 Aspose.Page가 자동으로 올바른 번호를 삽입합니다.

### 단계 1: 스트림 초기화

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

이 단계에서는 XPS 및 PDF 파일에 대한 입력 및 출력 스트림을 설정합니다. 올바른 경로와 파일 이름을 사용했는지 확인하십시오.

### 단계 2: XPS 문서 로드

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

여기서는 XPS 문서를 `XpsDocument` 객체에 로드하여 이후 처리 준비를 합니다.

### 단계 3: 저장 옵션 초기화 (XPS를 PDF로 병합)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

`PdfSaveOptions` 객체를 원하는 대로 맞춤 설정합니다. 이미지 압축, 텍스트 압축, 최종 PDF에 표시될 **페이지 번호**와 같은 매개변수를 지정합니다. `JpegQualityLevel`을 100으로 설정하면 **고품질 PDF 이미지**가 보장됩니다.

### 단계 4: 렌더링 디바이스 생성

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice`는 XPS 문서를 PDF 형식으로 렌더링하는 도구입니다.

### 단계 5: 문서 저장 (C# XPS를 PDF로)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

마지막으로, 렌더링 디바이스와 지정된 옵션을 사용해 문서를 저장합니다. 출력 PDF에는 선택된 페이지와 자동으로 추가된 페이지 번호가 포함됩니다.

## 이 변환에 Aspose.Page를 사용하는 이유

- **신뢰성** – 복잡한 XPS 기능을 손실 없이 처리합니다.  
- **성능** – 스트림 기반 처리로 전체 파일을 메모리에 로드하지 않습니다.  
- **유연성** – 이미지 품질, 압축 및 페이지 번호에 대한 세밀한 제어가 가능합니다.  
- **크로스‑플랫폼** – .NET Core와 함께 Windows, Linux, macOS에서 작동합니다.

## 일반적인 문제와 해결책

| 문제 | 해결책 |
|-------|----------|
| **출력 PDF가 비어 있음** | XPS 파일 경로가 올바른지, 파일이 손상되지 않았는지 확인하십시오. |
| **페이지 번호가 표시되지 않음** | `PageNumbers`가 올바른 0 기반 페이지 인덱스로 설정되어 있는지 확인하십시오(예: `new int[] {1,2,6}`). |
| **저품질 이미지** | `JpegQualityLevel`을 높이고 `PdfImageCompression.Jpeg`을 선택하십시오. |
| **큰 XPS 파일이 메모리 압박을 일으킴** | XPS를 더 작은 청크로 처리하거나 애플리케이션의 메모리 제한을 늘리십시오. |

## 자주 묻는 질문

### Q1: 여러 XPS 파일을 하나의 PDF로 병합할 수 있나요?

A1: 예, 가능합니다. `PdfSaveOptions`의 `PageNumbers` 매개변수를 조정하여 서로 다른 XPS 파일에서 원하는 페이지를 포함하거나, 각 XPS를 순차적으로 로드한 뒤 동일한 `PdfDevice`에서 `document.Save`를 호출하면 됩니다.

### Q2: Aspose.Page for .NET에 대한 임시 라이선스를 제공하나요?

A2: 예, 테스트 용도로 임시 라이선스를 [여기](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

### Q3: Aspose.Page를 사용한 문서 변환 시 파일 크기에 제한이 있나요?

A3: Aspose.Page for .NET은 파일 크기에 엄격한 제한을 두지 않지만, 적당한 크기의 파일에서 최적의 성능을 발휘합니다. 매우 큰 XPS 문서는 스트림으로 처리하여 메모리 사용량을 줄이는 것을 고려하십시오.

### Q4: 출력 PDF를 워터마크나 주석 추가 등으로 더 커스터마이즈할 수 있나요?

A4: 예, Aspose.Page for .NET은 PDF 조작을 위한 다양한 기능을 제공합니다. 변환 후에는 Aspose.PDF 라이브러리를 사용해 워터마크, 주석 또는 기타 향상을 추가할 수 있습니다.

### Q5: Aspose.Page for .NET이 크로스‑플랫폼 개발을 지원하나요?

A5: 예, Aspose.Page for .NET은 .NET Core 또는 .NET 5/6과 함께 사용할 때 Windows, Linux, macOS 등 다양한 플랫폼에서 원활히 작동하도록 설계되었습니다.

**마지막 업데이트:** 2026-01-20  
**테스트 대상:** Aspose.Page 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}