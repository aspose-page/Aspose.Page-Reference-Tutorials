---
title: .NET용 Aspose.Page를 사용하여 명명된 값 변경
linktitle: 명명된 값 변경
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 EPS 파일의 명명된 값을 변경하는 방법을 알아보세요. 맞춤형 문서 처리를 위해 XMP 메타데이터를 손쉽게 사용자 정의하세요.
weight: 16
url: /ko/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Page를 사용하여 명명된 값 변경

## 소개

문서 처리 분야에서 Aspose.Page for .NET은 EPS 파일을 조작하기 위한 강력한 도구로 돋보입니다. 제공되는 주요 기능 중 하나는 XMP 메타데이터 내에서 명명된 값을 변경하는 기능입니다. 이 튜토리얼은 .NET용 Aspose.Page를 사용하여 명명된 값을 변경하는 과정을 안내하여 특정 요구 사항에 따라 EPS 파일을 사용자 정의할 수 있도록 지원합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET용 Aspose.Page: .NET용 Aspose.Page 라이브러리가 설치되어 있는지 확인하세요. 그렇지 않은 경우 다운로드할 수 있습니다.[여기](https://releases.aspose.com/page/net/).

- 문서 디렉토리: 이름이 지정된 값 변경을 수행할 수 있는 EPS 파일용으로 지정된 디렉토리가 있습니다.

## 네임스페이스 가져오기

.NET 프로젝트에서 Aspose.Page에서 제공하는 기능에 액세스하려면 필요한 네임스페이스를 가져와야 합니다. 코드에 다음 네임스페이스를 추가합니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

이제 포괄적인 이해를 위해 코드를 여러 단계로 나누어 보겠습니다.

## 1단계: EPS 파일 입력 스트림 초기화

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// 연장:1
```

이 단계에서는 수정하려는 EPS 파일에 대한 입력 스트림을 설정합니다. "Your Document Directory"를 문서 디렉터리의 실제 경로로 바꾸십시오.

## 2단계: XMP 메타데이터 가져오기

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

EPS 파일에서 기존 XMP 메타데이터를 검색합니다. EPS 파일에 XMP 메타데이터가 포함되어 있지 않으면 PS 메타데이터 주석의 값을 사용하여 새 파일이 생성됩니다.

## 3단계: XMP 메타데이터 값 변경

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

여기서는 "xmpTPg:MaxPageSize" 구조 내에서 두 개의 명명된 값을 변경하는 방법을 보여줍니다. 특정 요구 사항에 따라 이를 사용자 정의할 수 있습니다.

## 4단계: 변경된 XMP 메타데이터로 EPS 파일 저장

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

수정된 EPS 파일을 출력 스트림에 저장합니다. 이제 파일은 XMP 메타데이터에 대한 변경 사항을 반영합니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Page를 활용하여 EPS 파일의 XMP 메타데이터 내에서 명명된 값을 변경하는 방법을 배웠습니다. 이 기능은 특정 요구 사항에 맞게 문서를 사용자 정의하고 조정할 수 있는 가능성의 세계를 열어줍니다.

## FAQ

### Q1: Aspose.Page for .NET을 다른 문서 형식과 함께 사용할 수 있습니까?

A1: 예, Aspose.Page는 EPS, XPS 및 PDF를 포함한 다양한 문서 형식을 지원합니다.

### Q2: Aspose.Page for .NET에 사용할 수 있는 평가판이 있습니까?

 A2: 예, 무료 평가판에 액세스할 수 있습니다.[여기](https://releases.aspose.com/).

### Q3: .NET용 Aspose.Page에 대한 추가 문서는 어디서 찾을 수 있나요?

 A3: 설명서를 참조하세요[여기](https://reference.aspose.com/page/net/).

### Q4: Aspose.Page for .NET의 임시 라이선스를 어떻게 얻을 수 있나요?

 A4: 임시 라이센스를 얻을 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).

### Q5: .NET 사용자용 Aspose.Page에는 어떤 지원 옵션을 사용할 수 있나요?

 A5: 커뮤니티 포럼을 방문하세요.[여기](https://forum.aspose.com/c/page/39) 지원과 토론을 위해.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
