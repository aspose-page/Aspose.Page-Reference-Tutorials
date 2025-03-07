---
title: Aspose.Page를 사용하여 PS(PostScript)에 유니코드 문자열이 포함된 텍스트 추가
linktitle: PostScript에 유니코드 문자열이 포함된 텍스트 추가(PS)
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 PostScript 파일에 유니코드 텍스트를 추가하는 방법을 알아보세요. 문서 조작을 쉽게 강화하세요.
weight: 11
url: /ko/net/text-manipulation/add-text-with-unicode-string-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용하여 PS(PostScript)에 유니코드 문자열이 포함된 텍스트 추가

## 소개

문서 조작 영역에서 Aspose.Page for .NET은 개발자가 다양한 문서 형식을 생성, 편집 및 변환할 수 있는 강력한 라이브러리로 돋보입니다. 강력한 기능 중 하나는 유니코드 문자열을 사용하여 PostScript(PS) 파일에 텍스트를 추가하는 기능입니다. 이 튜토리얼에서는 이 작업을 수행하는 단계별 가이드를 살펴보고 Aspose.Page로 작업하는 개발자에게 원활한 환경을 제공합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.

- C# 프로그래밍 언어에 대한 실무 지식.
-  .NET 라이브러리용 Aspose.Page가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[.NET 문서용 Aspose.Page](https://reference.aspose.com/page/net/).
- 필요한 구성으로 설정된 개발 환경입니다.

## 네임스페이스 가져오기

C# 코드에서 .NET 기능용 Aspose.Page를 사용하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 1단계: 문서 디렉터리 및 글꼴 폴더 설정

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Fonts Directory";
```

## 2단계: PostScript 문서에 대한 출력 스트림 생성

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddTextUsingUnocodeString_outPS.ps", FileMode.Create))
{
    // A4 크기로 저장 옵션 만들기
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    // ... (여기서 추가 옵션을 설정할 수 있습니다)
    
    // 새로운 1페이지 PS 문서 만들기
    PsDocument document = new PsDocument(outPsStream, options, false);
    
    // ... (추가 단계는 아래에서 설명합니다)
    
    // 문서 저장
    document.Save();
}
```

## 3단계: 사용자 정의 글꼴로 유니코드 텍스트 추가

```csharp
string str = "試してみます.";  // 유니코드 텍스트
int fontSize = 48;

// 텍스트 채우기에 사용자 정의 글꼴 사용
DrFont drFont = ExternalFontCache.FetchDrFont("Arial Unicode MS", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## 4단계: 현재 페이지 닫기

```csharp
document.ClosePage();
```

## 5단계: 문서 마무리 및 저장

```csharp
document.Save();
```

## 결론

이 튜토리얼에서는 .NET용 Aspose.Page를 사용하여 PostScript 문서에 유니코드 텍스트를 추가하는 과정을 살펴보았습니다. 강력한 기능을 활용하여 개발자는 문서 조작 워크플로우를 향상시켜 유연성과 정확성을 보장할 수 있습니다.

## FAQ

### Q1: Aspose.Page for .NET을 다른 프로그래밍 언어와 함께 사용할 수 있나요?

A1: Aspose.Page는 기본적으로 .NET용으로 설계되었지만 사용 가능한 Java용 다른 버전도 있습니다.

### Q2: Aspose.Page for .NET에 대한 임시 라이선스를 어떻게 얻나요?

 A2: 방문[임시면허](https://purchase.aspose.com/temporary-license/) 임시면허를 취득하기 위해

### Q3: Aspose.Page 토론을 위한 커뮤니티 포럼이 있습니까?

 A3: 그렇습니다.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지역 사회 지원을 위해.

### Q4: .NET용 Aspose.Page에서는 어떤 형식을 사용할 수 있나요?

A4: Aspose.Page는 XPS, PS, EPS, PDF 등을 포함한 다양한 형식을 지원합니다.

### Q5: 추가된 텍스트의 모양을 사용자 정의할 수 있나요?

A5: 예, Aspose.Page에서 텍스트의 글꼴, 크기, 색상 및 기타 속성을 사용자 정의할 수 있습니다.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
