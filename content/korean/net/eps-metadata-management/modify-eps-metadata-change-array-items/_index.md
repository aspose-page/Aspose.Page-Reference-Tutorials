---
title: .NET용 Aspose.Page를 사용하여 배열 항목 변경
linktitle: 배열 항목 변경
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 EPS 파일의 배열 항목을 변경하는 방법을 알아보세요. 효율적인 메타데이터 조작을 위한 단계별 가이드를 따르세요.
type: docs
weight: 15
url: /ko/net/eps-metadata-management/modify-eps-metadata-change-array-items/
---
## 소개

.NET용 Aspose.Page를 사용하여 배열 항목을 변경하는 방법에 대한 포괄적인 가이드에 오신 것을 환영합니다! Aspose.Page는 개발자가 EPS 파일을 포함한 다양한 문서 형식으로 작업할 수 있는 강력한 라이브러리입니다. 이 튜토리얼에서는 EPS 파일 내에서 XMP 메타데이터를 조작하는 방법, 특히 배열 항목을 변경하는 방법에 중점을 둘 것입니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1. .NET 라이브러리용 Aspose.Page: .NET 라이브러리용 Aspose.Page가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/page/net/).

2. 개발 환경: Visual Studio이든 .NET 개발을 지원하는 다른 IDE이든 원하는 개발 환경을 설정합니다.

## 네임스페이스 가져오기

.NET 애플리케이션에서 Aspose.Page 기능에 액세스하려면 필요한 네임스페이스를 가져와야 합니다. 코드 시작 부분에 다음 네임스페이스를 추가합니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

```

제공된 예제를 여러 단계로 나누어 보겠습니다.

## 1단계: EPS 파일 입력 스트림 초기화

```csharp
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

 이 단계에서는 EPS 파일 입력 스트림을 초기화하고`PsDocument` 그것의 예.

## 2단계: XMP 메타데이터 가져오기

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

EPS 파일에서 XMP 메타데이터를 검색합니다. 파일에 XMP 메타데이터가 포함되어 있지 않으면 PS 메타데이터 주석의 값을 사용하여 새 파일이 생성됩니다.

## 3단계: XMP 메타데이터 값 변경

```csharp
xmp.SetArrayItem("dc:title", 0, new XmpValue("NewTitle"));
xmp.SetArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

여기서는 XMP 메타데이터 내의 인덱스 0에서 제목과 작성자 항목을 변경합니다.

## 4단계: 변경된 XMP 메타데이터로 EPS 파일 저장

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

출력 스트림을 생성하고 수정된 XMP 메타데이터가 포함된 EPS 파일을 저장합니다.

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 EPS 파일의 배열 항목을 변경하는 방법을 성공적으로 배웠습니다. 이는 문서 내에서 메타데이터를 사용자 정의하고 관리하는 데 있어 중요한 단계일 수 있습니다.

## FAQ

### Q1: Aspose.Page for .NET을 다른 문서 형식과 함께 사용할 수 있습니까?

A1: Aspose.Page는 주로 EPS 파일을 다루지만 Aspose는 다양한 문서 형식 작업을 위한 다양한 라이브러리를 제공합니다.

### Q2: 추가 문서는 어디서 찾을 수 있나요?

 A2: 다음 문서를 참조하세요.[.NET 문서용 Aspose.Page](https://reference.aspose.com/page/net/).

### Q3: 무료 평가판이 제공됩니까?

 A3: 예, 다음에서 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).

### Q4: 임시 라이센스는 어떻게 얻을 수 있나요?

 A4: 임시 라이센스를 받으십시오.[이 링크](https://purchase.aspose.com/temporary-license/).

### Q5: 어디서 지원을 받거나 커뮤니티와 연결할 수 있나요?

 A5: 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 커뮤니티 지원 및 토론을 위해.