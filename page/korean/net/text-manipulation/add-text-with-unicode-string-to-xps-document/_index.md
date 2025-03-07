---
title: Aspose.Page를 사용하여 XPS 문서에 유니코드 문자열이 포함된 텍스트 추가
linktitle: XPS 문서에 유니코드 문자열이 포함된 텍스트 추가
second_title: Aspose.페이지 .NET API
description: XPS 문서에 유니코드 텍스트를 추가하는 방법에 대한 단계별 가이드를 통해 .NET용 Aspose.Page의 강력한 기능을 살펴보세요.
weight: 12
url: /ko/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용하여 XPS 문서에 유니코드 문자열이 포함된 텍스트 추가

## 소개

끊임없이 진화하는 .NET 개발 환경에서 Aspose.Page는 XPS 문서 처리를 위한 강력한 도구로 돋보입니다. 많은 기능 중에서 유니코드 문자열이 포함된 텍스트를 XPS 문서에 추가하는 기능은 중요한 기능입니다. 이 단계별 가이드는 프로세스를 안내하여 이 기능을 효과적으로 활용할 수 있도록 해줍니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- .NET 개발에 대한 기본적인 이해.
- 컴퓨터에 Visual Studio가 설치되어 있습니다.
-  .NET 라이브러리용 Aspose.Page. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/page/net/).

## 네임스페이스 가져오기

시작하려면 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 이는 Aspose.Page 작업에 필요한 클래스와 기능을 제공합니다. 필수 네임스페이스는 다음과 같습니다.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1단계: 문서 설정

먼저 유니코드 텍스트를 추가할 새 XPS 문서를 만듭니다. 아래 코드 조각을 따르십시오.

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
// 새 XPS 문서 만들기
XpsDocument doc = new XpsDocument();
```

## 2단계: 유니코드 텍스트 추가

이제 XPS 문서에 유니코드 텍스트를 추가해 보겠습니다. 이 예에서는 Arial 글꼴을 사용하고 글꼴 크기를 20으로 설정하며 텍스트를 좌표(400f, 200f)에 배치합니다. 이 경우 유니코드 문자열은 "TEN.rof SPX.esopsA"입니다. 아래 코드 조각을 확인하세요.

```csharp
// 텍스트 추가
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## 3단계: 문서 저장

유니코드 텍스트가 추가되면 결과 XPS 문서를 저장합니다. 마지막 단계는 다음과 같습니다.

```csharp
// 결과 XPS 문서 저장
doc.Save(dataDir + "AddTextRTL_out.xps");
```

축하해요! .NET용 Aspose.Page를 사용하여 XPS 문서에 유니코드 텍스트를 성공적으로 추가했습니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Page를 사용하여 XPS 문서에 유니코드 텍스트를 추가하는 과정을 살펴보았습니다. 이 기능을 사용하면 .NET 환경 내에서 다양하고 동적인 문서 생성이 가능해집니다.

## FAQ

### Q1: Aspose.Page는 최신 .NET 프레임워크와 호환됩니까?

A1: 예, Aspose.Page는 최신 .NET 프레임워크와의 호환성을 보장하기 위해 정기적으로 업데이트됩니다.

### Q2: 텍스트를 추가할 때 글꼴 스타일과 크기를 사용자 정의할 수 있나요?

A2: 물론이죠! 제공된 예제 코드를 사용하면 글꼴 스타일, 크기 및 기타 속성을 쉽게 사용자 정의할 수 있습니다.

### Q3: Aspose.Page에 대한 추가 문서는 어디서 찾을 수 있나요?

 A3: 문서를 참조할 수 있습니다.[여기](https://reference.aspose.com/page/net/) 포괄적인 정보와 예시를 보려면

### Q4: Aspose.Page를 시작하는 데 필요한 무료 리소스가 있나요?

 A4: 예, 다음을 탐색할 수 있습니다.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 커뮤니티 지원 및 토론을 위해.

### Q5: 구매하기 전에 체험판을 사용할 수 있나요?

 A5: 물론이죠! 무료 평가판에 액세스할 수 있습니다[여기](https://releases.aspose.com/) 구매하기 전에.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
