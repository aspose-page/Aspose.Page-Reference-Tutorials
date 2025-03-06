---
title: .NET용 Aspose.Page를 사용하여 XPS에 수직 그라데이션 추가
linktitle: XPS에 수직 그라데이션 추가
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 수직 그라데이션으로 XPS 문서를 향상시키는 방법을 알아보세요. 원활한 통합을 위한 단계별 가이드를 따르세요.
weight: 15
url: /ko/net/gradient-fills/add-vertical-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Page를 사용하여 XPS에 수직 그라데이션 추가

## 소개

.NET용 Aspose.Page를 사용하여 XPS 문서에 수직 그라데이션을 추가하는 방법에 대한 단계별 튜토리얼에 오신 것을 환영합니다. Aspose.Page는 .NET 애플리케이션에서 XPS(XML Paper Spec) 파일로 작업할 수 있는 강력한 API입니다. 이 튜토리얼에서는 새 XPS 문서를 만들고 경로에 수직 그라데이션을 추가하고 결과를 저장하는 과정을 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET 라이브러리용 Aspose.Page: 개발 환경에 .NET 라이브러리용 Aspose.Page가 설치되어 있는지 확인하세요. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/page/net/).

- 개발 환경: Visual Studio 등 원하는 IDE를 사용하여 .NET 개발 환경을 설정합니다.

이제 .NET용 Aspose.Page를 사용하여 XPS 문서에 수직 그라데이션을 추가하는 작업을 시작해 보겠습니다.

## 네임스페이스 가져오기

.NET 애플리케이션에 Aspose.Page 클래스 및 메서드에 액세스하는 데 필요한 네임스페이스를 포함합니다.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## 1단계: 문서 디렉토리 설정

시작하기 전에 결과 XPS 문서를 저장할 문서 디렉터리의 경로를 설정하세요.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// 연장:3
```

## 2단계: 새 XPS 문서 만들기

다음 코드를 사용하여 새 XPS 문서를 초기화합니다.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// 연장:4
```

## 3단계: 그라데이션 중지점 정의

각 정지점의 색상과 위치를 지정하여 그라데이션 정지점 목록을 만듭니다. 이 예에서는 5개의 정지점이 있는 수직 그라데이션을 정의합니다.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// 연장:5
```

## 4단계: 그라데이션을 사용하여 패스 만들기

형상을 지정하여 경로를 정의하고 선형 그라데이션 브러시를 적용합니다.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// 연장:6
```

## 5단계: 결과 XPS 문서 저장

수정된 XPS 문서를 지정된 디렉터리에 저장합니다.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// 연장:7
```

축하해요! .NET용 Aspose.Page를 사용하여 XPS 문서에 수직 그라데이션을 성공적으로 추가했습니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Page를 활용하여 수직 그라데이션으로 XPS 문서를 향상시키는 방법을 살펴보았습니다. Aspose.Page는 복잡한 작업을 단순화하여 개발자에게 .NET 애플리케이션에서 XPS 파일을 조작할 수 있는 원활한 방법을 제공합니다.

## FAQ

### Q1: Aspose.Page는 Visual Studio 2019와 호환됩니까?

A1: 예, Aspose.Page는 Visual Studio 2019와 호환됩니다. 올바른 버전의 라이브러리가 설치되어 있는지 확인하세요.

### Q2: Aspose.Page를 상업용 프로젝트에 사용할 수 있나요?

 A2: 네, Aspose.Page는 상업용 프로젝트에 사용될 수 있습니다. 방문하다[여기](https://purchase.aspose.com/buy) 라이선스 옵션을 살펴보세요.

### Q3: 무료 평가판이 제공됩니까?

 A3: 예, Aspose.Page의 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).

### Q4: Aspose.Page 문서는 어디서 찾을 수 있나요?

 A4: 문서를 사용할 수 있습니다.[여기](https://reference.aspose.com/page/net/).

### Q5: 어떻게 지원을 받거나 질문을 할 수 있나요?

 A5: 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지역 사회 지원을 위해.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
