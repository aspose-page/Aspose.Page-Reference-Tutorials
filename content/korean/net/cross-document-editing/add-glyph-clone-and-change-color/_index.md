---
title: .NET용 Aspose.Page를 사용하여 글리프 복제 추가 및 색상 변경
linktitle: 글리프 복제 추가 및 색상 변경
second_title: Aspose.페이지 .NET API
description: 이 포괄적인 튜토리얼에서 .NET용 Aspose.Page의 강력한 기능을 살펴보세요. 쉽게 XPS 문서에서 글리프 클론을 추가하고 색상을 변경하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/net/cross-document-editing/add-glyph-clone-and-change-color/
---
## 소개

.NET용 Aspose.Page를 사용하여 XPS 문서에서 글리프 복제본을 추가하고 색상을 변경하는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. Aspose.Page for .NET은 XPS 파일을 원활하게 사용할 수 있게 해주는 강력한 라이브러리입니다. 이 튜토리얼에서는 글리프 클론을 추가하고 색상을 변경하여 문서의 시각적 매력을 향상시키는 프로세스에 중점을 둘 것입니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- C# 프로그래밍 언어에 대한 기본적인 이해.
- Visual Studio 또는 기타 기본 C# 개발 환경이 설치되어 있습니다.
-  .NET 라이브러리용 Aspose.Page. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/page/net/).
- XPS 문서 형식에 익숙합니다.

## 네임스페이스 가져오기

시작하려면 C# 프로젝트에 필요한 네임스페이스를 포함하세요.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1단계: 문서 디렉터리 설정

문서가 저장될 디렉터리를 설정하는 것부터 시작하세요.

```csharp
string dataDir = "Your Document Directory";
```

## 2단계: 첫 번째 XPS 문서 만들기

이제 첫 번째 XPS 문서를 만들어 보겠습니다.

```csharp
XpsDocument doc1 = new XpsDocument();
```

## 3단계: 첫 번째 문서에 글리프 추가

지정된 매개변수를 사용하여 첫 번째 문서에 글리프를 추가합니다.

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## 4단계: 첫 번째 문서의 글리프를 색상으로 채우기

첫 번째 문서의 글리프를 녹색과 같은 단색으로 채웁니다.

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

## 5단계: 두 번째 XPS 문서 만들기

이제 두 번째 XPS 문서를 만듭니다.

```csharp
XpsDocument doc2 = new XpsDocument();
```

## 6단계: 첫 번째 문서에서 복제된 글리프 추가

첫 번째 문서의 글리프를 복제하여 두 번째 문서에 추가합니다.

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

## 7단계: 두 번째 문서의 글리프를 다른 색상으로 채우기

두 번째 문서에서 복제된 문자 모양의 색상을 빨간색으로 변경합니다(예: 빨간색).

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

## 8단계: 첫 번째 XPS 문서 저장

첫 번째 XPS 문서를 저장합니다.

```csharp
doc1.Save(dataDir + "out1.xps");
```

## 9단계: 두 번째 XPS 문서 저장

두 번째 XPS 문서를 저장합니다.

```csharp
doc2.Save(dataDir + "out2.xps");
```

축하해요! .NET용 Aspose.Page를 사용하여 XPS 문서에서 글리프 복제본을 성공적으로 추가하고 색상을 변경했습니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Page를 활용하여 XPS 문서의 시각적 요소를 향상시키는 방법을 살펴보았습니다. 글리프 클론을 추가하고 색상을 조정하여 특정 요구 사항에 맞는 시각적으로 매력적이고 역동적인 문서를 만들 수 있습니다.

## FAQ

### Q1: Aspose.Page for .NET을 다른 문서 형식과 함께 사용할 수 있습니까?

A1: .NET용 Aspose.Page는 XPS 문서 작업을 위해 특별히 설계되었습니다. 다른 형식을 조작해야 하는 경우 해당 형식에 맞는 다른 Aspose 라이브러리를 탐색할 수 있습니다.

### Q2: Aspose.Page for .NET에 임시 라이선스를 사용할 수 있나요?

 A2: 예, 테스트 목적으로 임시 라이센스를 얻을 수 있습니다. 방문하다[여기](https://purchase.aspose.com/temporary-license/) 자세한 내용은.

### Q3: 문제에 대한 지원을 받거나 도움을 구하려면 어떻게 해야 합니까?

 A3: 부담 없이 방문해 주세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지역사회와 연결하고 도움을 구합니다.

### Q4: 무료 평가판에 제한 사항이 있나요?

A4: 무료 평가판에는 몇 가지 제한 사항이 있으므로 사용하기 전에 설명서에서 자세한 내용을 검토하는 것이 좋습니다.

### Q5: .NET용 Aspose.Page에 대한 포괄적인 문서는 어디에서 찾을 수 있습니까?

 A5: 문서를 참조할 수 있습니다.[여기](https://reference.aspose.com/page/net/) 자세한 정보와 예시를 확인하세요.