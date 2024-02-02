---
title: .NET용 Aspose.Page를 사용하여 XPS 클리핑
linktitle: XPS 클리핑
second_title: Aspose.페이지 .NET API
description: XPS 문서 클리핑에 대한 단계별 가이드에서 .NET용 Aspose.Page의 강력한 기능을 살펴보세요. XPS 파일을 손쉽게 생성, 조작 및 저장하세요.
type: docs
weight: 11
url: /ko/net/canvas-manipulation/clippingxps/
---
## 소개

.NET용 Aspose.Page를 사용하여 XPS 클리핑에 대한 포괄적인 튜토리얼에 오신 것을 환영합니다! 이 가이드에서는 .NET용 Aspose.Page를 사용하여 XPS 문서를 생성, 조작 및 저장하는 과정을 안내합니다. XPS(XML Paper Spec)는 표준화된 개방형 문서 형식이며 .NET용 Aspose.Page는 .NET 애플리케이션에서 XPS 문서로 작업할 수 있는 강력한 도구를 제공합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- 컴퓨터에 Visual Studio가 설치되어 있습니다.
-  .NET 라이브러리용 Aspose.Page가 프로젝트에 추가되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/page/net/).
- C# 프로그래밍 언어에 대한 기본 지식.

## 네임스페이스 가져오기

.NET 기능용 Aspose.Page를 사용하려면 필요한 네임스페이스를 프로젝트로 가져와야 합니다. 다음과 같이하세요:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

이제 제공한 예제 코드를 여러 단계로 분석해 보겠습니다.

## 1단계: 문서 디렉터리 경로를 설정합니다.

```csharp
string dataDir = "Your Document Directory";
```

"Your Document Directory"를 문서 디렉터리의 실제 경로로 바꾸십시오.

## 2단계: 새 XPS 문서를 만듭니다.

```csharp
XpsDocument doc = new XpsDocument();
```

그러면 작업할 새 XPS 문서가 생성됩니다.

## 3단계: 메인 캔버스를 만듭니다.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

이 단계에서는 모든 페이지 요소에 공통되는 기본 캔버스를 만듭니다.

## 4단계: 기본 캔버스에서 왼쪽 및 위쪽 오프셋을 설정합니다.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

요구 사항에 따라 왼쪽 및 위쪽 오프셋을 조정합니다.

## 5단계: 직사각형 경로 형상을 만듭니다.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

이렇게 하면 직사각형에 대한 경로 형상이 생성됩니다.

## 6단계: 직사각형 채우기를 만듭니다.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

직사각형의 채우기 색상을 정의합니다.

## 7단계: 클립이 포함된 다른 캔버스를 기본 캔버스에 추가합니다.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

이 단계에서는 기본 캔버스에 다른 캔버스를 추가합니다.

## 8단계: 클립용 원 형상을 만듭니다.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

이렇게 하면 원형 클립 형상이 생성되어 두 번째 캔버스에 적용됩니다.

## 9단계: 두 번째 캔버스에 직사각형을 만들고 채웁니다.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

이 단계에서는 두 번째 캔버스에 직사각형을 만들고 채웁니다.

## 10단계: 스트로크된 직사각형이 있는 두 번째 캔버스를 기본 캔버스에 추가합니다.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

이렇게 하면 기본 캔버스에 다른 캔버스가 추가됩니다.

## 11단계: 세 번째 캔버스에 직사각형을 만들고 스트로크합니다.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

그러면 세 번째 캔버스에 직사각형이 생성되고 여기에 획이 적용됩니다.

## 12단계: 결과 XPS 문서를 저장합니다.

```csharp
doc.Save(dataDir + "output2.xps");
```

그러면 XPS 문서가 지정된 디렉터리에 저장됩니다.

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 XPS를 클립하는 방법을 성공적으로 배웠습니다. 이 가이드에서는 프로세스와 관련된 단계에 대한 자세한 안내를 제공했습니다.

## FAQ

### Q1: Aspose.Page for .NET을 다른 문서 형식과 함께 사용할 수 있습니까?

A1: .NET용 Aspose.Page는 주로 XPS 문서에 중점을 두지만 Aspose는 다양한 문서 형식을 위한 다른 라이브러리를 제공합니다.

### Q2: Aspose.Page for .NET은 초보자에게 적합합니까?

A2: 예, Aspose.Page for .NET은 사용자 친화적으로 설계되었으며 초보자는 적절한 문서를 통해 기능을 빠르게 이해할 수 있습니다.

### Q3: 더 많은 예시와 리소스는 어디에서 찾을 수 있나요?

 A3: 다음을 방문하세요.[선적 서류 비치](https://reference.aspose.com/page/net/) 그리고[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 광범위한 리소스와 예시를 확인하세요.

### Q4: Aspose.Page for .NET의 임시 라이선스를 어떻게 얻을 수 있나요?

 A4: 임시 라이센스를 얻을 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).

### Q5: Aspose.Page for .NET에 대한 무료 평가판이 있습니까?

 A5: 예, 무료 평가판을 사용해 볼 수 있습니다.[여기](https://releases.aspose.com/).