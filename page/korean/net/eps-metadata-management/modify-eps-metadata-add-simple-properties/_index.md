---
title: .NET용 Aspose.Page를 사용하여 간단한 속성 추가
linktitle: 단순 속성 추가
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 EPS 파일을 향상하세요. 맞춤형 문서 메타데이터에 간단한 속성을 손쉽게 추가하세요.
weight: 14
url: /ko/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Page를 사용하여 간단한 속성 추가

## 소개

문서 조작 및 향상 영역에서 .NET용 Aspose.Page는 개발자에게 EPS 파일 내에서 XMP 메타데이터를 원활하게 추가하고 수정할 수 있는 기능을 제공하는 강력한 도구로 등장합니다. 이 튜토리얼은 .NET용 Aspose.Page를 사용하여 EPS 파일에 간단한 속성을 추가하는 과정을 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  .NET용 Aspose.Page: 개발 환경에 .NET용 Aspose.Page가 설치되어 있는지 확인하세요. 그렇지 않은 경우 다운로드할 수 있습니다.[여기](https://releases.aspose.com/page/net/).

2.  문서 디렉터리: EPS 파일을 저장할 디렉터리를 설정합니다. 업데이트`dataDir` 제공된 코드 조각의 변수에 문서 디렉터리 경로를 입력하세요.

## 네임스페이스 가져오기

시작하려면 Aspose.Page for .NET과의 통신을 활성화하는 데 필요한 네임스페이스를 가져옵니다. 코드 파일 시작 부분에 다음 줄을 추가합니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 1단계: EPS 파일 입력 스트림 초기화

```csharp
// ExStart:1
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
// EPS 파일 입력 스트림 초기화
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//스트림에서 PsDocument 인스턴스 만들기
PsDocument document = new PsDocument(psStream);
```

## 2단계: XMP 메타데이터 가져오기

```csharp
// XMP 메타데이터를 가져옵니다. EPS 파일에 XMP 메타데이터가 포함되어 있지 않으면 PS 메타데이터 주석(%%Creator, %%CreateDate, %%Title 등)의 값으로 채워진 새 파일을 얻습니다.
XmpMetadata xmp = document.GetXmpMetadata();
```

## 3단계: XMP 메타데이터 값 변경

```csharp
// XMP 메타데이터 값 변경
DateTime now = DateTime.UtcNow;

// 정수 속성 추가
xmp.Add("xmp:Intg1", new XmpValue(111));

// 날짜/시간 속성 추가
xmp.Add("xmp:Date1", new XmpValue(now));

// Double 속성 추가
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//문자열 속성 추가
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## 4단계: 변경된 XMP 메타데이터로 EPS 파일 저장

```csharp
// 변경된 XMP 메타데이터로 EPS 파일 저장

// 출력 스트림 생성
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // EPS 파일 저장
    document.Save(outPsStream);
}
```

## 5단계: FileStream 닫기

```csharp
finally
{
    psStream.Close();
}
```

다음 단계를 따르면 .NET용 Aspose.Page를 사용하여 간단한 속성을 EPS 파일에 쉽게 통합할 수 있습니다.

## 결론

결론적으로, .NET용 Aspose.Page는 사용자 정의 XMP 메타데이터로 EPS 파일을 향상시키려는 개발자에게 귀중한 자산임이 입증되었습니다. 간단한 속성을 추가하면 특정 요구 사항에 맞게 문서를 사용자 정의하고 강화할 수 있어 문서 조작 가능성의 세계가 열립니다.

## FAQ

### Q1: Aspose.Page for .NET은 모든 EPS 파일과 호환됩니까?

A1: .NET용 Aspose.Page는 광범위한 EPS 파일을 지원합니다. 그러나 호환성은 개별 파일의 복잡성과 구조에 따라 달라질 수 있습니다.

### Q2: .NET용 Aspose.Page를 사용하여 기존 XMP 메타데이터를 수정할 수 있습니까?

A2: 물론이죠! 이 튜토리얼에서 설명한 것처럼 기존 XMP 메타데이터 값을 쉽게 변경하거나 필요에 맞게 새 값을 추가할 수 있습니다.

### Q3: 추가할 수 있는 속성 유형에 제한이 있나요?

A3: .NET용 Aspose.Page는 정수, 날짜, 복식 및 문자열을 포함하여 속성에 대한 다양한 데이터 유형을 지원합니다. 메타데이터에 적합한 유형을 유연하게 선택할 수 있습니다.

### Q4: Aspose.Page for .NET에 대한 기술 지원은 어떻게 받을 수 있나요?

 A4: 기술 지원을 받으려면[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 아니면 탐험해 보세요.[선적 서류 비치](https://reference.aspose.com/page/net/) 종합적인 안내를 위해.

### Q5: Aspose.Page for .NET에 대한 무료 평가판이 있습니까?

 A5: 예, 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
