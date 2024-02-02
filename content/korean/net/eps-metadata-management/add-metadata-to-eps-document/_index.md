---
title: .NET용 Aspose.Page를 사용하여 EPS 문서에 메타데이터 추가
linktitle: EPS 문서에 메타데이터 추가
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 EPS 문서 구성을 강화하세요. 향상된 접근성과 정보 검색을 위해 메타데이터를 손쉽게 추가하세요.
type: docs
weight: 10
url: /ko/net/eps-metadata-management/add-metadata-to-eps-document/
---
## 소개

끊임없이 진화하는 디지털 문서 환경에서 메타데이터는 콘텐츠, 원본 및 기타 필수 세부 정보에 대한 정보를 제공하는 데 중요한 역할을 합니다. .NET용 Aspose.Page는 개발자가 EPS(Encapsulated PostScript) 문서에 메타데이터를 원활하게 추가하여 접근성과 유용성을 향상시킬 수 있도록 지원합니다.

## 전제 조건

단계별 가이드를 살펴보기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET용 Aspose.Page 라이브러리: 다음에서 .NET용 Aspose.Page 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/page/net/).
- 문서 디렉터리: EPS 문서가 저장되는 디렉터리를 설정합니다.

## 네임스페이스 가져오기

.NET 프로젝트에 Aspose.Page의 기능을 활용하는 데 필요한 네임스페이스를 포함합니다. 다음 네임스페이스를 가져옵니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

EPS 문서에 메타데이터를 추가하는 과정을 여러 단계로 나누어 보겠습니다.

## 1단계: EPS 파일 입력 스트림 초기화

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// 연장:3
```

## 2단계: XMP 메타데이터 가져오기

```csharp
// ExStart:4
XmpMetadata xmp = document.GetXmpMetadata();
// 연장:4
```

## 3단계: 메타데이터 값 확인 및 설정

PS 메타데이터 주석에서 추출된 메타데이터 값을 확인하고 새 XMP 메타데이터에 설정합니다.

### CreatorTool 값 얻기

```csharp
// ExStart:5
if (xmp.Contains("xmp:CreatorTool"))
    Console.WriteLine("CreatorTool: " + xmp["xmp:CreatorTool"].ToStringValue());
// 연장:5
```

### CreateDate 값 가져오기

```csharp
// ExStart:6
if (xmp.Contains("xmp:CreateDate"))
    Console.WriteLine("CreateDate: " + xmp["xmp:CreateDate"].ToStringValue());
// 연장:6
```

### 형식 값 가져오기

```csharp
// ExStart:7
if (xmp.Contains("dc:format"))
    Console.WriteLine("Format: " + xmp["dc:format"].ToStringValue());
// 연장:7
```

### 타이틀 값 얻기

```csharp
// ExStart:8
if (xmp.Contains("dc:title"))
    Console.WriteLine("Title: " + xmp["dc:title"].ToArray()[0].ToStringValue());
// 연장:8
```

### 크리에이터 가치 얻기

```csharp
// ExStart:9
if (xmp.Contains("dc:creator"))
    Console.WriteLine("Creator: " + xmp["dc:creator"].ToArray()[0].ToStringValue());
// 연장:9
```

### MetadataDate 값 가져오기

```csharp
// ExStart:10
if (xmp.Contains("xmp:MetadataDate"))
    Console.WriteLine("MetadataDate: " + xmp["xmp:MetadataDate"].ToStringValue());
// 연장:10
```

## 4단계: 새 XMP 메타데이터로 EPS 파일 저장

```csharp
// ExStart:11
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
// 연장:11
```

## 결론

EPS 문서에 메타데이터를 추가하는 것은 문서의 구성과 접근성을 향상시키는 중요한 단계입니다. .NET용 Aspose.Page를 사용하면 이 프로세스가 간소화되고 효율적이 되어 개발자가 메타데이터를 쉽게 관리할 수 있습니다.

## FAQ

### Q1: 여러 EPS 문서에 동시에 메타데이터를 추가할 수 있습니까?

A1: 예, EPS 문서 모음을 반복하고 메타데이터 추출 및 추가 프로세스를 각 파일에 적용할 수 있습니다.

### Q2: Aspose.Page for .NET이 처리할 수 있는 EPS 문서의 크기에 제한이 있습니까?

A2: Aspose.Page for .NET은 다양한 크기의 EPS 문서를 처리하도록 설계되었습니다. 그러나 매우 큰 파일의 경우 메모리 사용량을 모니터링하는 것이 좋습니다.

### Q3: XMP 메타데이터는 모든 EPS 문서에 대해 표준화되어 있습니까?

A3: XMP 메타데이터는 표준 구조를 따르지만 그 내용은 작성자와 문서 작성 중에 제공된 정보에 따라 달라질 수 있습니다.

### Q4: 특정 요구 사항에 맞게 메타데이터 필드를 사용자 정의할 수 있습니까?

A4: 예, .NET용 Aspose.Page는 애플리케이션의 필요에 따라 메타데이터 필드를 사용자 정의할 수 있는 유연성을 제공합니다.

### Q5: 메타데이터 추가 프로세스 중 오류를 처리하려면 어떻게 해야 합니까?

A5: 메타데이터 추출 및 추가 프로세스 중 발생할 수 있는 오류를 해결하려면 코드에서 적절한 예외 처리를 확인하세요.