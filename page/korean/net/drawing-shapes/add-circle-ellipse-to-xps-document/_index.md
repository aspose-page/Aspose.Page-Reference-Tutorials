---
title: .NET용 Aspose.Page를 사용하여 XPS 문서에 원형 타원 추가
linktitle: XPS 문서에 원형 타원 추가
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 생생한 방사형 그라데이션으로 XPS 문서를 향상하세요. 놀라운 시각 효과를 얻으려면 단계별 가이드를 따르십시오.
type: docs
weight: 11
url: /ko/net/drawing-shapes/add-circle-ellipse-to-xps-document/
---
## 소개

시각적으로 매력적인 XPS 문서를 만드는 것은 다양한 응용 프로그램의 일반적인 요구 사항입니다. .NET용 Aspose.Page는 XPS 문서를 효율적으로 조작할 수 있는 강력한 기능 세트를 제공합니다. 이 튜토리얼에서는 .NET용 Aspose.Page를 사용하여 XPS 문서에 원 타원을 추가하는 방법에 중점을 둘 것입니다. 생생한 방사형 그라데이션으로 XPS 문서를 향상하려면 아래 단계를 따르세요.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET 라이브러리용 Aspose.Page를 설치했습니다. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/page/net/).
- 개발 환경(바람직하게는 Visual Studio 또는 기타 .NET 개발 도구).
- C# 프로그래밍에 대한 기본 지식.

## 네임스페이스 가져오기

시작하려면 C# 코드에 필요한 네임스페이스를 포함합니다.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

이제 예제를 여러 단계로 나누어 보겠습니다.

## 1단계: 문서 설정

```csharp
// ExStart:1
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
// 새 XPS 문서 만들기
XpsDocument doc = new XpsDocument();
```

여기서는 .NET용 Aspose.Page를 사용하여 새 XPS 문서를 초기화합니다.

## 2단계: 방사형 그라데이션 타원 정의

```csharp
// 왼쪽 아래에 있는 방사형 그래디언트 스트로크 타원
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 0, 255), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), .25f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 255, 0), .5f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 255, 0), .75f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 0, 0), 1f));

XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250"));
```

이 단계에는 다양한 색상 정지점을 사용하여 방사형 그라데이션 타원을 정의하는 작업이 포함됩니다.

## 3단계: 방사형 그라디언트 브러시 설정

```csharp
path.Stroke = doc.CreateRadialGradientBrush(new PointF(575f, 125f), new PointF(575f, 100f), 75f, 50f);
((XpsGradientBrush)path.Stroke).SpreadMethod = XpsSpreadMethod.Reflect;
((XpsGradientBrush)path.Stroke).GradientStops.AddRange(stops);
stops.Clear();
```

여기서는 타원의 획을 방사형 그래디언트 브러시로 설정하여 필요한 매개변수를 제공합니다.

## 4단계: 획 두께 조정

```csharp
path.StrokeThickness = 12f;
```

이 단계에는 더 나은 시각화를 위해 획의 두께를 조정하는 작업이 포함됩니다.

## 5단계: 결과 XPS 문서 저장

```csharp
// 결과 XPS 문서 저장
doc.Save(dataDir + "AddEllipse_outXPS.xps");
// 연장:1
```

마지막으로 수정된 XPS 문서를 원하는 위치에 저장합니다.

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 XPS 문서에 방사형 그라데이션이 있는 원 타원을 성공적으로 추가했습니다. 문서에서 원하는 시각적 효과를 얻으려면 다양한 매개변수와 색상을 실험해 보세요.

## FAQ

### Q1: Aspose.Page for .NET을 다른 문서 형식과 함께 사용할 수 있습니까?

A1: .NET용 Aspose.Page는 특히 XPS 문서 조작을 다룹니다. 다른 형식의 경우 관련 Aspose 라이브러리를 사용하는 것이 좋습니다.

### Q2: 테스트 목적으로 임시 라이센스를 사용할 수 있습니까?

 A2: 예, 다음 사이트를 방문하면 테스트용 임시 라이센스를 얻을 수 있습니다.[이 링크](https://purchase.aspose.com/temporary-license/).

### 질문 3: 추가 도움말과 토론은 어디에서 찾을 수 있습니까?

 A3: 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 커뮤니티 지원 및 토론을 위해.

### Q4: 참고할 수 있는 샘플 문서가 있습니까?

 A4: 탐색해 보세요.[선적 서류 비치](https://reference.aspose.com/page/net/) 포괄적인 예시와 지침을 확인하세요.

### Q5: .NET용 Aspose.Page를 구입할 수 있나요?

 A5: 예, 라이브러리를 구입할 수 있습니다.[여기](https://purchase.aspose.com/buy).