---
title: .NET용 Aspose.Page를 사용하여 XPS 문서에 텍스트 추가
linktitle: XPS 문서에 텍스트 추가
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 XPS 문서에 텍스트를 추가하는 방법에 대한 단계별 가이드를 살펴보세요. .NET 프로젝트를 손쉽게 향상하세요.
weight: 13
url: /ko/net/text-manipulation/add-text-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Page를 사용하여 XPS 문서에 텍스트 추가

## 소개

.NET 개발의 역동적인 세계에서 Aspose.Page는 XPS 문서 작업을 위한 강력한 도구로 돋보입니다. XPS 문서에 텍스트를 추가하는 것은 일반적인 요구 사항이며 Aspose.Page는 이 프로세스를 단순화합니다. 이 튜토리얼에서는 .NET용 Aspose.Page를 사용하여 XPS 문서에 텍스트를 원활하게 추가하는 방법을 살펴보겠습니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- .NET용 Aspose.Page: Aspose.Page 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[.NET 문서용 Aspose.Page](https://reference.aspose.com/page/net/).

-  개발 환경: .NET 개발 환경을 설정합니다. 아직 이 작업을 수행하지 않은 경우 다음 페이지에 제공된 설치 지침을 따르세요.[선적 서류 비치](https://reference.aspose.com/page/net/).

- 문서 디렉터리: 문서를 저장할 디렉터리를 만듭니다. 제공된 코드 조각의 "문서 디렉터리"를 실제 경로로 바꾸세요.

이제 단계별 가이드로 넘어가겠습니다.

## 네임스페이스 가져오기

먼저, 프로젝트를 시작하는 데 필요한 네임스페이스를 가져오겠습니다.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1단계: 새 XPS 문서 만들기

Aspose.Page 작업을 시작하려면 새 XPS 문서를 만드세요. 이것이 텍스트를 추가하는 캔버스가 될 것입니다.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// 연장:3
```

## 2단계: 텍스트용 브러시 만들기

이제 텍스트 색상을 정의하는 브러시를 만들어 보겠습니다. 이 예에서는 검정색 브러시를 사용하고 있습니다.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// 연장:4
```

## 3단계: 문서에 글리프 추가

문자 모양은 XPS 문서의 텍스트를 나타냅니다. 원하는 글꼴, 크기, 스타일 및 위치로 문서에 글리프를 추가합니다.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// 연장:5
```

## 4단계: 결과 XPS 문서 저장

마지막으로 텍스트가 추가된 XPS 문서를 지정된 디렉터리에 저장합니다.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// 연장:6
```

이러한 간단한 단계를 따르면 .NET용 Aspose.Page를 사용하여 XPS 문서에 텍스트를 성공적으로 추가했습니다.

## 결론

결론적으로 .NET용 Aspose.Page는 .NET 프로젝트의 XPS 문서에 텍스트를 추가하기 위한 간단한 솔루션을 제공합니다. 강력한 기능과 결합된 라이브러리의 단순성은 문서 조작을 위한 귀중한 도구입니다.

## 자주 묻는 질문

### Q1: 추가된 텍스트의 글꼴과 크기를 사용자 정의할 수 있나요?

 A1: 예, 글꼴과 크기를 완전히 제어할 수 있습니다. 매개변수를 조정하세요.`AddGlyphs` 그에 따른 방법.

### Q2: Aspose.Page는 .NET Core와 호환됩니까?

A2: 물론이죠! Aspose.Page는 .NET Core를 지원하여 최신 .NET 기술과의 호환성을 보장합니다.

### Q3: Aspose.Page를 사용하기 위한 라이선스 요구 사항이 있나요?

 A3: 예, 유효한 라이센스가 필요합니다. 라이선스 옵션 살펴보기[여기](https://purchase.aspose.com/buy).

### 질문4: 어떻게 지원을 받거나 도움을 구할 수 있나요?

 A4: 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지역사회와 연결하고 도움을 받으려면

### Q5: 무료 평가판이 제공됩니까?

 A5: 물론이죠! 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
