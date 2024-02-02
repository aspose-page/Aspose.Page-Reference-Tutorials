---
title: .NET용 Aspose.Page를 사용하여 XPS 문서에 직사각형 추가
linktitle: XPS 문서에 직사각형 추가
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 문서 생성을 향상하세요. 이 단계별 튜토리얼에서 XPS 문서에 직사각형을 추가하는 방법을 알아보세요.
type: docs
weight: 13
url: /ko/net/drawing-shapes/add-rectangle-to-xps-document/
---
## 소개

Aspose.Page for .NET은 .NET 애플리케이션에서 XPS(XML Paper Spec) 문서 작업을 위한 다양한 기능을 제공하는 강력한 라이브러리입니다. 이 튜토리얼에서는 .NET용 Aspose.Page를 사용하여 XPS 문서에 직사각형을 추가하는 방법에 중점을 둘 것입니다. 문서 작성 프로세스를 향상하려면 이 단계별 가이드를 따르세요.

## 전제 조건

이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  .NET 라이브러리용 Aspose.Page: 개발 환경에 .NET 라이브러리용 Aspose.Page가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/page/net/).

2. 문서 디렉터리: XPS 문서를 저장할 디렉터리를 설정합니다.

## 네임스페이스 가져오기

.NET 애플리케이션에서 Aspose.Page 기능을 사용하는 데 필요한 네임스페이스를 포함합니다.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1단계: 문서 디렉터리 설정

```csharp
// ExStart:3
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
// 연장:3
```

## 2단계: 새 XPS 문서 만들기

```csharp
// ExStart:4
// 새 XPS 문서 만들기
XpsDocument doc = new XpsDocument();
// 연장:4
```

## 3단계: 직사각형 추가

```csharp
// ExStart:5
// 왼쪽 하단에 CMYK(파란색) 단색 스트로크 직사각형
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// 연장:5
```

## 4단계: 문서 저장

```csharp
// ExStart:6
// 결과 XPS 문서 저장
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// 연장:6
```

축하해요! .NET용 Aspose.Page를 사용하여 XPS 문서에 직사각형을 성공적으로 추가했습니다.

## 결론

.NET용 Aspose.Page는 문서 조작 작업을 단순화하여 개발자가 XPS 문서를 쉽게 만들고 수정할 수 있도록 합니다. 이 단계별 가이드에서는 XPS 문서에 직사각형을 추가하여 추가 탐색을 위한 견고한 기반을 제공하는 방법을 보여줍니다.

## FAQ

### Q1: Aspose.Page는 모든 .NET 애플리케이션과 호환됩니까?

A1: 예, Aspose.Page는 모든 .NET 애플리케이션과 원활하게 작동하도록 설계되었습니다.

### Q2: .NET용 Aspose.Page에 대한 설명서는 어디서 찾을 수 있나요?

 A2: 문서를 사용할 수 있습니다.[여기](https://reference.aspose.com/page/net/).

### Q3: 구매하기 전에 Aspose.Page for .NET을 무료로 사용해 볼 수 있나요?

 A3: 예, 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).

### Q4: Aspose.Page for .NET의 임시 라이선스를 어떻게 얻을 수 있나요?

 A4: 방문[이 링크](https://purchase.aspose.com/temporary-license/) 임시면허를 취득하기 위해

### Q5: 어디에서 커뮤니티 지원을 찾거나 Aspose.Page for .NET과 관련된 질문을 할 수 있나요?

 A5: 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지역 사회 지원을 위해.