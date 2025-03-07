---
title: Aspose.Page를 사용하여 명명된 값 추가
linktitle: 명명된 값 추가
second_title: Aspose.페이지 .NET API
description: Aspose.Page를 사용하여 .NET의 EPS 파일에 명명된 값을 추가하는 방법을 알아보세요. 이 포괄적인 튜토리얼은 프로세스를 단계별로 안내합니다.
weight: 12
url: /ko/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용하여 명명된 값 추가

## 소개

.NET을 사용한 문서 처리 영역에서 Aspose.Page는 EPS 파일을 처리하는 강력한 도구로 돋보입니다. Aspose.Page는 개발자가 XMP 메타데이터를 조작하여 명명된 값 추가와 같은 작업을 용이하게 할 수 있도록 지원합니다. 이 튜토리얼에서는 Aspose.Page를 사용하여 EPS 파일에 명명된 값을 추가하는 과정을 단계별로 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본 지식.
- Visual Studio와 같은 통합 개발 환경(IDE)이 설치되어 있습니다.
-  .NET 라이브러리용 Aspose.Page. 설치되어 있지 않은 경우 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/page/net/).

## 네임스페이스 가져오기

먼저 필요한 네임스페이스를 C# 코드로 가져오겠습니다. 이러한 네임스페이스는 Aspose.Page에서 제공하는 기능에 액세스하는 데 필수적입니다.

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

 초기 단계에는 EPS 파일의 입력 스트림을 초기화하는 작업이 포함됩니다. 바꾸다`"Your Document Directory"` 문서 디렉토리 경로:

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## 2단계: XMP 메타데이터 가져오기

EPS 파일에서 XMP 메타데이터를 검색합니다. EPS 파일에 XMP 메타데이터가 없으면 PS 메타데이터 주석의 값으로 채워진 새 파일이 생성됩니다.

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## 3단계: XMP 메타데이터 값 변경

이제 XMP 메타데이터를 변경해 보겠습니다. 이 예에서는 "xmpTPg:MaxPageSize" 구조에 명명된 값을 추가합니다.

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## 4단계: 변경된 XMP 메타데이터로 EPS 파일 저장

업데이트된 XMP 메타데이터로 EPS 파일을 저장합니다. 출력 스트림을 생성하고 수정된 EPS 파일을 저장합니다.

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## 결론

축하해요! .NET에서 Aspose.Page를 사용하여 EPS 파일에 명명된 값을 성공적으로 추가했습니다. 이 튜토리얼은 문서 조작에서 Aspose.Page의 단순성과 효율성을 보여주면서 필수 단계를 안내했습니다.

## FAQ

### Q1: Aspose.Page는 다른 EPS 파일 버전과 호환됩니까?

A1: Aspose.Page는 다양한 EPS 파일 버전을 지원하여 광범위한 문서와의 호환성을 보장합니다.

### Q2: Aspose.Page를 상업용 프로젝트에 사용할 수 있나요?

 A2: 예, Aspose.Page에는 상업용 라이선스가 포함되어 있으며 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy).

### Q3: Aspose.Page에 사용할 수 있는 무료 평가판이 있나요?

 A3: 예, 무료 평가판을 통해 Aspose.Page를 탐색할 수 있습니다.[여기](https://releases.aspose.com/).

### Q4: Aspose 커뮤니티에 어떻게 지원을 받거나 연결할 수 있나요?

 A4: 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지원을 받고 커뮤니티와 연결됩니다.

### Q5: 임시 라이센스란 무엇이며 어떻게 얻을 수 있나요?

 A5: 테스트 또는 평가 목적으로 임시 라이선스가 필요한 경우 라이선스를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
