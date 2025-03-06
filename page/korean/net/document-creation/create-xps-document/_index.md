---
title: .NET용 Aspose.Page를 사용하여 XPS 문서 만들기
linktitle: XPS 문서 만들기
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 XPS 문서 생성의 세계를 탐험해보세요. 단계별 가이드에 따라 전자 문서를 손쉽게 생성하세요.
weight: 10
url: /ko/net/document-creation/create-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Page를 사용하여 XPS 문서 만들기

## 소개

.NET용 Aspose.Page를 사용하여 XPS 문서를 만드는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. 이 튜토리얼에서는 전자 문서에 널리 사용되는 형식인 XPS 파일을 생성하는 과정을 살펴보겠습니다. 숙련된 개발자이든 Aspose.Page를 처음 시작하는 개발자이든 이 가이드는 명확한 예와 자세한 설명을 통해 XPS 문서를 원활하게 생성하는 데 도움이 되도록 맞춤화되었습니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  .NET 라이브러리용 Aspose.Page: 다음에서 Aspose.Page 라이브러리를 다운로드하고 설치하세요.[다운로드 링크](https://releases.aspose.com/page/net/).

2. 문서 디렉터리: 시스템에서 출력 XPS 파일을 저장할 디렉터리를 선택하거나 만듭니다.

이제 튜토리얼로 넘어가겠습니다!

## 네임스페이스 가져오기

.NET용 Aspose.Page를 사용하려면 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 다음과 같이하세요:

### 1단계: Aspose.Page에 참조 추가

프로젝트에서 .NET용 Aspose.Page 라이브러리에 대한 참조를 추가합니다. 다운로드한 패키지에서 필요한 DLL을 찾을 수 있습니다.

### 2단계: 네임스페이스 가져오기

코드 파일에 다음 네임스페이스를 포함합니다.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

이제 전제 조건을 설정하고 필요한 네임스페이스를 가져왔으므로 XPS 문서를 만드는 과정을 여러 단계로 나누어 보겠습니다.

## 1단계: 문서 디렉터리 설정

```csharp
string dir = "Your Document Directory";
```

 반드시 교체하세요`"Your Document Directory"` 출력 XPS 파일을 저장하려는 실제 경로를 사용합니다.

## 2단계: XPS 문서 만들기

```csharp
XpsDocument xDocs = new XpsDocument();
```

 다음을 사용하여 새 XPS 문서를 초기화합니다.`XpsDocument` 수업.

## 3단계: 문서에 글리프 추가

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

 사용`AddGlyphs` 문서에 글리프(텍스트)를 추가하는 방법입니다. 필요에 따라 글꼴, 크기, 스타일 및 위치를 사용자 정의합니다.

## 4단계: 글리프 채우기 색상 설정

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

추가된 글리프의 채우기 색상을 지정합니다. 이 예에서는 검정색을 사용했지만 어떤 색상이든 선택할 수 있습니다.

## 5단계: 결과 저장

```csharp
xDocs.Save(dir + "output.xps");
```

마지막으로 XPS 문서를 원하는 파일 이름으로 지정된 디렉터리에 저장합니다. 결과 XPS 파일에는 "Hello World!"가 포함됩니다. 텍스트.

축하해요! .NET용 Aspose.Page를 사용하여 XPS 문서를 성공적으로 만들었습니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Page를 사용하여 XPS 문서를 만드는 과정을 살펴보았습니다. 이 강력한 라이브러리는 전자 문서를 쉽게 생성할 수 있는 원활한 방법을 제공합니다. 다양한 글꼴, 스타일 및 콘텐츠를 실험하여 XPS 파일을 특정 요구 사항에 맞게 조정하세요.

## FAQ

### Q1: 내 XPS 문서에서 사용자 정의 글꼴을 사용할 수 있습니까?

A1: 예, XPS 문서에 글리프를 추가할 때 글꼴 모음과 크기를 지정할 수 있습니다.

### Q2: Aspose.Page는 .NET Core와 호환됩니까?

A2: 예, Aspose.Page는 .NET Core를 지원하므로 크로스 플랫폼 애플리케이션에서 사용할 수 있습니다.

### Q3: XPS 문서에 이미지를 어떻게 추가할 수 있나요?

A3: Aspose.Page는 XPS 문서에 이미지를 추가하는 방법을 제공합니다. 자세한 예는 설명서를 참조하세요.

### Q4: 여러 페이지로 구성된 XPS 문서를 만들 수 있습니까?

A4: 물론이죠! Aspose.Page 라이브러리를 사용하여 XPS 문서에 여러 페이지를 추가할 수 있습니다.

### Q5: 평가판을 사용할 수 있나요?

 A5: 예, Aspose.Page를 다운로드하여 기능을 탐색할 수 있습니다.[무료 시험판](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
