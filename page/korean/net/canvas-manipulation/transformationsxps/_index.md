---
title: .NET용 Aspose.Page를 사용한 변환 XPS
linktitle: 변환 XPS
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 XPS 문서를 손쉽게 변환하세요. 원활한 변환을 위한 단계별 가이드를 따르세요.
weight: 13
url: /ko/net/canvas-manipulation/transformationsxps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Page를 사용한 변환 XPS

## 소개

XPS 문서에서 다양한 변환을 쉽게 수행할 수 있는 강력한 라이브러리인 Aspose.Page for .NET의 세계에 오신 것을 환영합니다. 이 튜토리얼에서는 .NET용 Aspose.Page를 사용하여 XPS 문서를 변환하는 프로세스를 살펴보겠습니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 가이드는 개념을 쉽게 이해할 수 있도록 각 단계를 안내합니다.

## 전제 조건

시작하기 전에 다음 사항이 준비되어 있는지 확인하세요.

-  .NET 라이브러리용 Aspose.Page: 다음에서 라이브러리를 다운로드하고 설치하세요.[.NET 문서용 Aspose.Page](https://reference.aspose.com/page/net/).

- 개발 환경: Visual Studio 또는 기타 .NET 개발 도구와 같은 호환 가능한 개발 환경을 설정합니다.

- 문서 디렉터리: 코드의 자리 표시자를 문서 디렉터리의 실제 경로로 바꿉니다.

이제 튜토리얼로 넘어가겠습니다!

## 네임스페이스 가져오기

먼저, 코드에서 .NET용 Aspose.Page 기능을 사용할 수 있도록 필요한 네임스페이스를 가져와야 합니다. 스크립트 시작 부분에 다음 네임스페이스를 추가합니다.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1단계: 새 XPS 문서 만들기

```csharp
// ExStart:1
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";

// 새 XPS 문서 만들기
XpsDocument doc = new XpsDocument();
```

## 2단계: 메인 캔버스 생성

```csharp
// 모든 페이지 요소에 공통되는 기본 캔버스 만들기
XpsCanvas canvas1 = doc.AddCanvas();

// 기본 캔버스에서 왼쪽 및 위쪽 오프셋 만들기
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## 3단계: 직사각형 경로 형상 만들기

```csharp
// 직사각형 경로 형상 생성
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## 4단계: 직사각형 채우기 추가

```csharp
// 직사각형 채우기 만들기
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## 5단계: 변형 없이 새 캔버스 추가

```csharp
// 기본 캔버스에 변형 없이 새 캔버스 추가
XpsCanvas canvas2 = canvas1.AddCanvas();

// 이 캔버스에 직사각형을 만들고 채우세요.
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## 6단계: 번역 변환을 사용하여 새 캔버스 추가

```csharp
// 기본 캔버스에 번역 변환이 포함된 새 캔버스 추가
XpsCanvas canvas3 = canvas1.AddCanvas();

// 이 캔버스를 이동하여 이전 직사각형 아래에 새 직사각형을 배치합니다.
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// 이 캔버스를 페이지 오른쪽으로 번역
canvas3.RenderTransform.Translate(500, 0);

// 이 캔버스에 직사각형을 만들고 채우세요.
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## 7단계: 이중 배율 변환을 사용하여 새 캔버스 추가

```csharp
//기본 캔버스에 이중 크기 변환이 포함된 새 캔버스 추가
XpsCanvas canvas4 = canvas1.AddCanvas();

// 이 캔버스를 이동하여 이전 직사각형 아래에 새 직사각형을 배치합니다.
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// 이 캔버스 크기 조정
canvas4.RenderTransform.Scale(2, 2);

// 이 캔버스에 직사각형을 만들고 채우세요.
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## 8단계: 점 변환을 중심으로 회전하는 새 캔버스 추가

```csharp
// 기본 캔버스에 점 변환을 중심으로 회전하는 새 캔버스를 추가합니다.
XpsCanvas canvas5 = canvas1.AddCanvas();

// 이 캔버스를 이동하여 이전 직사각형 아래에 새 직사각형을 배치합니다.
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// 이 캔버스를 한 점을 중심으로 45도 회전합니다.
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// 이 캔버스에 직사각형을 만들고 채우세요.
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## 9단계: 결과 XPS 문서 저장

```csharp
// 결과 XPS 문서 저장
doc.Save(dataDir + "output1.xps");
// 연장:1
```

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 XPS 문서를 성공적으로 변환했습니다. 이 가이드에서는 필수 구성 요소 설정부터 다양한 변환 수행까지 필수 단계를 다루었습니다. 이러한 기술을 실험하고 프로젝트에서 Aspose.Page for .NET의 잠재력을 최대한 활용해 보세요.

## FAQ

### Q1: Aspose.Page for .NET은 모든 .NET 개발 환경과 호환됩니까?

A1: 예, Aspose.Page for .NET은 Visual Studio를 포함한 다양한 .NET 개발 환경과 원활하게 작동하도록 설계되었습니다.

### Q2: .NET용 Aspose.Page에 대한 추가 예제와 설명서는 어디서 찾을 수 있나요?

 A2: 다음을 방문하세요.[.NET 문서용 Aspose.Page](https://reference.aspose.com/page/net/) 포괄적인 문서와 예제를 보려면

### Q3: 구매하기 전에 Aspose.Page for .NET을 사용해 볼 수 있나요?

 A3: 예, 다음 사이트를 방문하면 무료 평가판을 탐색할 수 있습니다.[Aspose.Page 무료 평가판](https://releases.aspose.com/).

### Q4: Aspose.Page for .NET의 임시 라이선스를 어떻게 얻을 수 있나요?

 A4: 다음 사이트를 방문하여 임시 라이센스를 받으세요.[임시면허](https://purchase.aspose.com/temporary-license/).

### Q5: .NET용 Aspose.Page를 어디서 구입할 수 있나요?

 A5: .NET용 Aspose.Page를 다음에서 구매하세요.[Aspose.Page 구매](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
