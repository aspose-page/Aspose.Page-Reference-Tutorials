---
title: .NET용 Aspose.Page를 사용하여 XPS를 PDF로 변환
linktitle: XPS를 PDF로 변환
second_title: Aspose.페이지 .NET API
description: Aspose.Page를 사용하여 .NET에서 XPS를 PDF로 쉽게 변환하세요. 라이브러리를 다운로드하고, 문서를 살펴보고, 무료 평가판을 받으세요.
type: docs
weight: 11
url: /ko/net/document-conversion/convert-xps-to-pdf/
---
## 소개

이 튜토리얼에서는 강력한 Aspose.Page for .NET 라이브러리를 사용하여 XPS(XML Paper Spec) 문서를 PDF(Portable Document Format)로 변환하는 과정을 자세히 살펴보겠습니다. .NET용 Aspose.Page는 XPS 파일 작업을 위한 강력한 기능 세트를 제공하므로 개발자는 다양한 사용자 정의 옵션을 사용하여 XPS 파일을 PDF 형식으로 원활하게 변환할 수 있습니다.

## 전제 조건

이 전환 여정을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하십시오.

-  .NET 라이브러리용 Aspose.Page: 개발 환경에 .NET 라이브러리용 Aspose.Page가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Aspose.Page 문서](https://reference.aspose.com/page/net/).

- 개발 환경: Visual Studio 또는 기타 호환 가능한 IDE를 사용하여 .NET 개발 환경을 설정합니다.

- XPS 문서: PDF로 변환하려는 XPS 문서를 준비합니다. 이는 지정된 디렉터리에 저장된 샘플 XPS 파일일 수 있습니다.

## 네임스페이스 가져오기

코드를 살펴보기 전에 코드에서 .NET용 Aspose.Page 기능에 액세스할 수 있도록 필요한 네임스페이스를 가져와 보겠습니다.

```csharp
using Aspose.Page.XPS;
```

## 1단계: 문서 디렉터리 초기화

```csharp
string dataDir = "Your Document Directory";
```

"문서 디렉터리"를 XPS 문서가 포함된 디렉터리 경로로 바꾸세요.

## 2단계: PDF 및 XPS 스트림 초기화

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

출력 PDF 파일과 입력 XPS 파일 모두에 대한 스트림을 엽니다. 적절한 파일 경로가 설정되어 있는지 확인하십시오.

## 3단계: XPS 문서 로드

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

.NET 라이브러리용 Aspose.Page를 사용하여 XPS 문서를 로드합니다.

## 4단계: PDF 저장 옵션 초기화

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

JPEG 품질 수준, 이미지 압축, 텍스트 압축 및 포함할 특정 페이지 번호와 같은 매개변수를 포함한 PDF 저장 옵션을 설정합니다.

## 5단계: PDF 렌더링 장치 만들기

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

.NET용 Aspose.Page 라이브러리를 사용하여 PDF 형식용 렌더링 장치를 만듭니다.

## 6단계: 문서를 PDF로 저장

```csharp
document.Save(device, options);
```

지정된 렌더링 장치 및 옵션을 사용하여 XPS 문서를 PDF로 저장합니다.

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 XPS 문서를 PDF로 성공적으로 변환했습니다. 이 다용도 라이브러리는 개발자에게 다양한 문서 형식을 쉽게 처리할 수 있는 강력한 도구 세트를 제공합니다.

## FAQ

### Q1: .NET용 Aspose.Page를 사용하여 여러 XPS 파일을 단일 PDF로 변환할 수 있습니까?

A1: 예, 여러 XPS 파일을 반복하고 동일한 단계에 따라 단일 PDF로 병합할 수 있습니다.

### Q2: .NET용 Aspose.Page에서 지원하는 다른 출력 형식이 있습니까?

A2: 예, .NET용 Aspose.Page는 TIFF, JPEG, PNG 등을 포함한 다양한 출력 형식을 지원합니다.

### Q3: 변환된 PDF 문서의 모양을 어떻게 사용자 정의할 수 있습니까?

A3: 이미지 압축, 텍스트 압축과 같은 옵션 개체 매개변수를 조정하여 원하는 모양을 얻을 수 있습니다.

### Q4: Aspose.Page for .NET에 사용할 수 있는 평가판이 있습니까?

 A4: 예, 다음에서 무료 평가판을 받아 .NET용 Aspose.Page의 기능을 탐색할 수 있습니다.[여기](https://releases.aspose.com/).

### Q5: .NET용 Aspose.Page에 대한 커뮤니티 지원은 어디서 받을 수 있나요?

 A5: 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 커뮤니티 토론 및 지원을 위해.