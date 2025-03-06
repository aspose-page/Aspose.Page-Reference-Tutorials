---
title: Aspose.Page를 사용하여 배열 항목 추가
linktitle: 배열 항목 추가
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 EPS 파일에 배열 항목을 추가하는 방법을 살펴보세요. 원활한 문서 조작을 위한 단계별 가이드를 따르세요.
weight: 11
url: /ko/net/eps-metadata-management/modify-eps-metadata-add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용하여 배열 항목 추가

## 소개

.NET의 문서 조작 및 처리 영역에서 Aspose.Page는 강력한 도구로 돋보입니다. 많은 기능 중에서 EPS 파일 내의 배열 항목을 처리하는 것은 일반적인 요구 사항입니다. 이 튜토리얼에서는 .NET 환경에서 Aspose.Page를 사용하여 배열 항목을 추가하는 단계별 프로세스를 살펴보겠습니다. 노련한 개발자이든 신규 개발자이든 이 가이드는 프로세스를 명확하고 정확하게 안내할 것입니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- .NET 프로그래밍에 대한 기본적인 이해.
-  .NET용 Aspose.Page가 설치되었습니다. 그렇지 않은 경우 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/page/net/).
- 예제와 함께 사용할 Visual Studio와 같은 코드 편집기.

## 네임스페이스 가져오기

.NET 프로젝트에서 Aspose.Page 기능을 활용하려면 필요한 네임스페이스를 가져와야 합니다. 코드 시작 부분에 다음 줄을 추가합니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

이러한 네임스페이스는 EPS 파일 조작에 필요한 필수 클래스 및 메서드에 대한 액세스를 제공합니다.

## 1단계: EPS 파일 입력 스트림 초기화

```csharp
// ExStart:3
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
// EPS 파일 입력 스트림 초기화
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//스트림에서 PsDocument 인스턴스 만들기
PsDocument document = new PsDocument(psStream);            
// 연장:3
```

 여기서는 EPS 파일의 초기 입력 스트림을 설정하고`PsDocument` 사례.

## 2단계: XMP 메타데이터 가져오기

```csharp
// ExStart:4
// XMP 메타데이터를 가져옵니다. EPS 파일에 XMP 메타데이터가 포함되어 있지 않으면 PS 메타데이터 주석(%%Creator, %%CreateDate, %%Title 등)의 값으로 채워진 새 파일을 얻습니다.
XmpMetadata xmp = document.GetXmpMetadata();
// 연장:4
```

EPS 파일에서 XMP 메타데이터를 검색합니다. EPS 파일에 XMP 메타데이터가 없으면 PS 메타데이터 주석의 값을 사용하여 새 파일이 생성됩니다.

## 3단계: XMP 메타데이터 값 변경

```csharp
// ExStart:5
// XMP 메타데이터 값 변경

// 제목을 하나 더 추가하세요. 기본적으로 배열의 끝에 추가됩니다.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// 크리에이터를 한 명 더 추가하세요. 인덱스(0)를 기준으로 배열에 추가됩니다.
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// 연장:5
```

새로운 타이틀과 제작자를 배열에 추가하여 XMP 메타데이터를 수정합니다.

## 4단계: 변경된 XMP 메타데이터로 EPS 파일 저장

```csharp
// ExStart:6
// 변경된 XMP 메타데이터로 EPS 파일 저장

// 출력 스트림 생성
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // EPS 파일 저장
    document.Save(outPsStream);
}
// 연장:6
```

마지막으로 업데이트된 XMP 메타데이터가 포함된 EPS 파일을 저장합니다. 배열 항목에 대한 변경 사항은 출력 파일에 반영됩니다.

## 결론

.NET에서 Aspose.Page를 사용하여 배열 항목을 추가하는 것은 이 튜토리얼에서 설명한 것처럼 간단한 프로세스입니다. 올바른 전제 조건과 단계별 가이드를 통해 개발자는 EPS 파일을 원활하게 조작하여 문서가 특정 메타데이터 요구 사항을 충족하도록 할 수 있습니다.

## FAQ

### Q1: Aspose.Page는 모든 .NET 환경과 호환됩니까?

A1: 예, Aspose.Page는 모든 .NET 환경에서 원활하게 작동하도록 설계되어 플랫폼 전반에 걸쳐 일관된 기능을 제공합니다.

### Q2: Aspose.Page를 무료로 사용할 수 있나요?

 A2: Aspose.Page는 사용자가 기능을 탐색할 수 있도록 무료 평가판을 제공합니다. 계속 사용하려면 라이센스를 구입해야 합니다.[여기](https://purchase.aspose.com/buy).

### Q3: Aspose.Page에 임시 라이선스를 사용할 수 있나요?

 A3: 예, 임시 라이센스는 다음에서 얻을 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/) 단기 프로젝트 요구에 적합합니다.

### Q4: Aspose.Page에 대한 커뮤니티 지원은 어디서 찾을 수 있나요?

답변 4: 커뮤니티 토론 및 지원을 받으려면 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39).

### Q5: .NET용 Aspose.Page의 최신 버전은 무엇입니까?

 A5: .NET용 Aspose.Page의 최신 버전에 액세스하려면 다음을 참조하세요.[선적 서류 비치](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
