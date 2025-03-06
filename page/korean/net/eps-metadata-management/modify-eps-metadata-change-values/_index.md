---
title: .NET용 Aspose.Page를 사용하여 값 변경
linktitle: 값 변경
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 EPS 파일 조작을 마스터하세요. XMP 메타데이터 값을 쉽게 변경할 수 있습니다.
weight: 17
url: /ko/net/eps-metadata-management/modify-eps-metadata-change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Page를 사용하여 값 변경

## 소개

역동적인 문서 처리 세계에서 Aspose.Page for .NET은 개발자에게 EPS 파일을 쉽게 조작할 수 있는 기능을 제공하는 강력한 도구로 돋보입니다. 이 튜토리얼에서는 .NET용 Aspose.Page를 사용하여 EPS 파일 내에서 값을 변경하는 프로세스를 살펴보겠습니다. 숙련된 개발자이든 호기심이 많은 초보자이든 이 단계별 가이드는 EPS 파일에서 XMP 메타데이터를 효율적으로 수정하는 데 필요한 기술을 제공합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

### 1. .NET 라이브러리용 Aspose.Page

개발 환경에 Aspose.Page for .NET 라이브러리가 설치되어 있는지 확인하세요. 그렇지 않은 경우 다운로드할 수 있습니다.[여기](https://releases.aspose.com/page/net/).

### 2. 문서 디렉토리

문서에 대한 디렉토리를 설정하십시오. 이것이 EPS 파일이 저장되는 위치입니다.

이제 전제 조건이 정렬되었으므로 다음 중요한 단계로 넘어가겠습니다.

## 네임스페이스 가져오기

모든 .NET 프로젝트에서는 Aspose.Page의 기능을 활용하기 위해 필요한 네임스페이스를 가져오는 것이 필수적입니다. 방법은 다음과 같습니다.

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
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
// EPS 파일 입력 스트림 초기화
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## 2단계: 스트림에서 PsDocument 인스턴스 만들기

```csharp
//스트림에서 PsDocument 인스턴스 만들기
PsDocument document = new PsDocument(psStream);
```

이제 준비가 완료되었으므로 튜토리얼의 핵심인 EPS 파일 내에서 XMP 메타데이터 값을 변경해 보겠습니다.

## 3단계: XMP 메타데이터 가져오기

```csharp
// XMP 메타데이터를 가져옵니다. EPS 파일에 XMP 메타데이터가 포함되어 있지 않으면 PS 메타데이터 주석(%%Creator, %%CreateDate, %%Title 등)의 값으로 채워진 새 파일을 얻습니다.
XmpMetadata xmp = document.GetXmpMetadata();
```

## 4단계: XMP 메타데이터 값 수정

이제 XMP 메타데이터에서 일부 주요 값을 변경해 보겠습니다.

### 4.1단계: ModifyDate 값 변경

```csharp
// ModifyDate 값 변경
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### 4.2단계: Creator 값 변경

```csharp
// Creator 가치 변경
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### 4.3단계: 제목 값 변경

```csharp
// 제목 값 변경
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

이렇게 변경한 후 마지막 단계인 수정된 EPS 파일을 저장하는 단계로 넘어갑니다.

## 5단계: 변경된 XMP 메타데이터로 EPS 파일 저장

### 5.1단계: 출력 스트림 생성

```csharp
// 출력 스트림 생성
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### 5.2단계: EPS 파일 저장

```csharp
// EPS 파일 저장
document.Save(outPsStream);
```

마지막으로 입력 스트림을 닫습니다.

```csharp
finally
{
    psStream.Close();
}
```

축하해요! .NET용 Aspose.Page를 사용하여 EPS 파일의 XMP 메타데이터 값을 성공적으로 수정했습니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Page를 사용하여 EPS 파일 내에서 값을 변경하는 원활한 프로세스를 살펴보았습니다. 개발자로서 이제 효율적인 문서 조작을 위한 강력한 도구를 사용할 수 있습니다.

## FAQ

### Q1: Aspose.Page for .NET을 다른 파일 형식과 함께 사용할 수 있습니까?

A1: Aspose.Page는 주로 EPS 파일 조작에 중점을 둡니다. 다른 형식의 경우 Aspose의 다양한 제품을 살펴보세요.

### Q2: 평가판을 사용할 수 있나요?

 A2: 예, 무료 평가판을 통해 .NET용 Aspose.Page를 사용해 볼 수 있습니다.[여기](https://releases.aspose.com/).

### Q3: 자세한 문서는 어디서 찾을 수 있나요?

 A3: 포괄적인 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/page/net/).

### Q4: 임시 라이센스는 어떻게 얻나요?

 A4: 임시 라이센스를 얻을 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).

### Q5: .NET용 Aspose.Page를 구입할 수 있나요?

 A5: 물론이죠! 구매 페이지 방문[여기](https://purchase.aspose.com/buy) 라이센스 옵션에 대해
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
