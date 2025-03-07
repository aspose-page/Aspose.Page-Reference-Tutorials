---
title: .NET용 Aspose.Page를 사용하여 XPS에 수평 그라데이션 추가
linktitle: XPS에 수평 그라데이션 추가
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 XPS 문서에 놀라운 수평 그라데이션을 추가하는 방법을 알아보세요. 손쉽게 시각적 매력을 높여보세요.
weight: 13
url: /ko/net/gradient-fills/add-horizontal-gradient-to-xps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Page를 사용하여 XPS에 수평 그라데이션 추가

## 소개

이 튜토리얼에서는 .NET용 Aspose.Page를 사용하여 수평 그라데이션을 추가하여 XPS 문서를 향상시키는 방법을 살펴보겠습니다. Aspose.Page for .NET은 .NET 애플리케이션에서 XPS(XML Paper Spec) 문서를 원활하게 처리할 수 있는 강력한 라이브러리입니다. 그라디언트를 추가하면 문서에 시각적인 매력을 더할 수 있으며 이 가이드에서는 프로세스를 단계별로 안내합니다.

## 전제 조건

시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  .NET 라이브러리용 Aspose.Page: 개발 환경에 .NET 라이브러리용 Aspose.Page가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[.NET 문서용 Aspose.Page](https://reference.aspose.com/page/net/).

2. 개발 환경: Visual Studio와 같은 코드 편집기를 포함하여 적합한 개발 환경을 설정합니다.

## 네임스페이스 가져오기

필요한 네임스페이스를 프로젝트로 가져오는 것부터 시작하세요. 이러한 네임스페이스는 .NET용 Aspose.Page 작업에 필수적입니다.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

이제 제공된 예제를 여러 단계로 나누어 보겠습니다.

## 1단계: 문서 디렉터리 경로 설정

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

## 3단계: 경사 정지점 초기화

```csharp
// ExStart:5
// XpsGradientStop 목록 초기화
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// 연장:5
```

## 4단계: 새 경로 만들기

```csharp
// ExStart:6
//약어 형식으로 지오메트리를 정의하여 새 경로 생성
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// 연장:6
```

## 5단계: 결과 XPS 문서 저장

```csharp
// ExStart:7
// 결과 XPS 문서 저장
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// 연장:7
```

이제 .NET용 Aspose.Page를 사용하여 XPS 문서에 수평 그라데이션을 성공적으로 추가했습니다.

## 결론

그라디언트로 XPS 문서를 향상하면 시각적 매력이 향상될 뿐만 아니라 더욱 매력적인 사용자 경험도 제공됩니다. .NET용 Aspose.Page는 이 프로세스를 단순화하여 전문적인 결과를 쉽게 얻을 수 있도록 해줍니다.

## FAQ

### Q1: .NET용 Aspose.Page 설명서는 어디에서 찾을 수 있습니까?

 A1: 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/page/net/).

### Q2: .NET용 Aspose.Page를 어떻게 다운로드하나요?

 A2: 다음에서 라이브러리를 다운로드할 수 있습니다.[.NET 다운로드 페이지용 Aspose.Page](https://releases.aspose.com/page/net/).

### Q3: .NET용 Aspose.Page를 어디서 구입할 수 있나요?

 A3: .NET용 Aspose.Page를 다음에서 구입할 수 있습니다.[구매 페이지](https://purchase.aspose.com/buy).

### Q4: 무료 평가판이 제공됩니까?

 A4: 예, 다음에서 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).

### Q5: .NET용 Aspose.Page에 대한 임시 라이선스를 어떻게 얻나요?

 A5: 다음에서 임시 라이센스를 얻을 수 있습니다.[이 링크](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
