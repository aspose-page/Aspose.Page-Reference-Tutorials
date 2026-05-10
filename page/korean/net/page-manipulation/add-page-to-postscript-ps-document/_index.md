---
date: 2026-03-03
description: Aspose.Page for .NET을 사용하여 사용자 지정 페이지 크기를 설정하고 PostScript 문서에 두 번째 PS
  페이지를 추가하는 방법을 배우세요.
linktitle: Add Page to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Aspose.Page를 사용하여 PS 문서의 사용자 정의 페이지 크기 설정
url: /ko/net/page-manipulation/add-page-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용하여 PostScript (PS) 문서에 페이지 추가하기

## 소개

.NET 개발에서 **사용자 지정 페이지 크기 설정** 및 **두 번째 PS 페이지 추가** 기능을 활용하면 생성된 인쇄물, 보고서 또는 그래픽의 레이아웃을 세밀하게 제어할 수 있습니다. Aspose.Page for .NET은 깔끔하고 객체 지향적인 API를 제공하여 이 작업을 간단하게 만들어 줍니다. 이 튜토리얼에서는 다중 페이지 PS 파일을 만들고, 각 페이지에 사용자 지정 크기를 정의한 뒤, 결과를 저장하는 방법을 몇 줄의 C# 코드만으로 배우게 됩니다.

## 빠른 답변
- **사용자 지정 페이지 크기를 설정할 수 있나요?** 예 – 페이지를 열 때 너비와 높이를 전달하면 됩니다.  
- **두 번째 PS 페이지를 어떻게 추가하나요?** `document.OpenPage(width, height)`를 두 번째로 호출하면 됩니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **라이선스가 필요합니까?** 테스트용 임시 라이선스로 가능하지만, 실제 운영 환경에서는 정식 라이선스가 필요합니다.  
- **Aspose.Page를 어디서 다운로드할 수 있나요?** 아래 공식 다운로드 페이지에서 받을 수 있습니다.

## 사전 요구 사항

튜토리얼을 진행하기 전에 다음 사항을 준비하십시오:

- .NET 개발에 대한 기본 지식.  
- 머신에 Visual Studio가 설치되어 있어야 합니다.  
- Aspose.Page for .NET 라이브러리([여기](https://releases.aspose.com/page/net/)에서 다운로드 가능).  
- 테스트용 문서 디렉터리.

## 네임스페이스 가져오기

Aspose.Page에서 제공하는 기능을 사용하려면 프로젝트에 필요한 네임스페이스를 포함해야 합니다. 예제에서는 네임스페이스가 암시적으로 포함되어 있지만, 프로젝트 구조에 따라 확인하고 조정하는 것이 중요합니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 단계 1: 프로젝트 설정

Visual Studio에서 새 .NET 프로젝트를 만들고 필요한 구성을 설정합니다. 프로젝트에 Aspose.Page 라이브러리를 참조하는 것을 잊지 마세요.

## 사용자 지정 페이지 크기 설정 및 두 번째 PS 페이지 추가

이 섹션에서는 각 페이지에 **사용자 지정 페이지 크기**를 설정하고, 동일한 문서에 **두 번째 PS 페이지**를 추가하는 방법을 정확히 보여줍니다.

### 단계 2: 문서 초기화

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "document1.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create a new 2-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, 2);
```

### 단계 3: 첫 번째 페이지 추가 (기본 크기)

```csharp
    // Add the first page
    document.OpenPage();

    // Add content

    // Close the first page
    document.ClosePage();
```

### 단계 4: 다른 (사용자 지정) 크기로 두 번째 페이지 추가

```csharp
    // Add the second page with a different size
    document.OpenPage(400, 700);

    // Add content

    // Close the second page
    document.ClosePage();
```

### 단계 5: 문서 저장

```csharp
    // Save the document
    document.Save();
}
// ExEnd:1
```

위 단계를 차근차근 따라 하면 Aspose.Page for .NET을 사용해 PostScript 문서에 **사용자 지정 페이지 크기**를 설정하고 **두 번째 PS 페이지**를 성공적으로 추가할 수 있습니다.

## 왜 중요한가요

- **정밀 레이아웃** – 사용자 지정 페이지 치수를 사용하면 프린터 사양에 맞추거나 독특한 브로셔 형식을 만들 수 있습니다.  
- **다중 페이지** – 두 번째 페이지(또는 그 이상)를 추가하면 외부 병합 도구 없이도 다중 페이지 보고서를 만들 수 있습니다.  
- **크로스 플랫폼** – 생성된 PS 파일은 PostScript 호환 장치에서 렌더링하거나 나중에 PDF로 변환할 수 있습니다.

## 흔히 발생하는 문제 및 해결 방법

- **잘못된 경로** – `dataDir`이 경로 구분자로 끝나는지 확인하거나 `Path.Combine`을 사용하세요.  
- **라이선스 문제** – 유효한 라이선스가 없으면 라이브러리가 워터마크를 추가하거나 페이지 수를 제한할 수 있습니다.  
- **단위 혼동** – 너비와 높이는 포인트 단위(1포인트 = 1/72인치)로 측정됩니다. 이에 맞게 조정하세요.

## 자주 묻는 질문

**Q1: Aspose.Page가 다양한 문서 형식을 지원하나요?**  
A1: Aspose.Page는 주로 PostScript 문서 조작에 초점을 맞추고 있습니다. 다른 형식이 필요하면 해당 목적에 맞는 Aspose 라이브러리를 살펴보세요.

**Q2: Aspose.Page에서 페이지 크기를 커스터마이즈할 수 있나요?**  
A2: 물론입니다! 튜토리얼에서 보여준 것처럼 각 페이지마다 원하는 크기를 지정할 수 있습니다.

**Q3: 더 많은 예제와 문서는 어디서 찾을 수 있나요?**  
A3: 포괄적인 정보와 다양한 예제가 포함된 [문서](https://reference.aspose.com/page/net/)를 확인하세요.

**Q4: Aspose.Page의 임시 라이선스는 어떻게 얻나요?**  
A4: 테스트 목적의 임시 라이선스는 [이 링크](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

**Q5: 커뮤니티 지원이나 질문은 어디서 받을 수 있나요?**  
A5: 다른 개발자와 소통하고 경험을 공유하며 도움을 받을 수 있는 [Aspose.Page 커뮤니티 포럼](https://forum.aspose.com/c/page/39)에 참여하세요.

---

**마지막 업데이트:** 2026-03-03  
**테스트 환경:** Aspose.Page 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}