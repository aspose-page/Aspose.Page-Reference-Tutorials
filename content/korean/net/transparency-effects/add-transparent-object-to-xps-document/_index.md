---
title: Aspose.Page를 사용하여 XPS 문서에 투명 개체 추가
linktitle: XPS 문서에 투명 개체 추가
second_title: Aspose.페이지 .NET API
description: Aspose.Page를 사용하여 .NET의 XPS 문서에 투명 개체를 추가하는 방법을 알아보세요. 단계별 안내를 통해 시각적 매력을 강화하세요.
type: docs
weight: 11
url: /ko/net/transparency-effects/add-transparent-object-to-xps-document/
---
## 소개

이 튜토리얼에서는 Aspose.Page for .NET을 사용하여 XPS 문서에 투명 개체를 추가하는 방법을 살펴보겠습니다. XPS 문서의 투명성은 시각적 매력을 향상시키고 정보를 효과적으로 전달할 수 있습니다. 프로세스를 관리 가능한 단계로 나누어 명확성과 이해의 용이성을 보장합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET용 Aspose.Page: .NET용 Aspose.Page 라이브러리가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[.NET 문서용 Aspose.Page](https://reference.aspose.com/page/net/).

## 네임스페이스 가져오기

시작하려면 프로젝트에 필요한 네임스페이스를 포함하세요.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

이제 단계별 가이드를 진행해 보겠습니다.

## 1단계: 새 XPS 문서 만들기

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
// 새 XPS 문서 만들기
XpsDocument doc = new XpsDocument();
```

이 코드는 .NET용 Aspose.Page를 사용하여 새 XPS 문서를 초기화합니다.

## 2단계: 투명성 입증

```csharp
// 투명성을 보여주기 위해
doc.AddPath(doc.CreatePathGeometry("M120,0 H400 v1000 H120")).Fill = doc.CreateSolidColorBrush(Color.Gray);
doc.AddPath(doc.CreatePathGeometry("M300,120 h600 V420 h-600")).Fill = doc.CreateSolidColorBrush(Color.Gray);
```

이 선은 문서의 투명도 효과를 보여주기 위해 투명한 경로를 만듭니다.

## 3단계: 닫힌 직사각형 형상으로 경로 만들기

```csharp
XpsPath path1 = doc.CreatePath(doc.CreatePathGeometry("M20,20 h200 v200 h-200 z"));
path1.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

여기서는 닫힌 직사각형 형상으로 경로를 만들고 파란색 단색 브러시를 설정하여 채우고 현재 페이지에 추가합니다.

## 4단계: 경로 및 색상 조작

```csharp
XpsPath path2 = doc.Add(path1);
path2.Fill = doc.CreateSolidColorBrush(Color.Green);
```

이 단계에서는 경로를 조작하고 색상을 변경하는 방법을 보여줍니다.

## 5단계: 경로 복제 및 변환

```csharp
XpsPath path3 = doc.Add(path2);
path3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 300);
path3.Fill = doc.CreateSolidColorBrush(Color.Red);
```

경로를 복제 및 변형하고, 복제된 경로의 색상을 이동하고 변경합니다.

## 6단계: 경로 반복 및 수정

```csharp
XpsPath path4 = doc.AddPath(path2.Data);
path4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 300, 0);
path4.Fill = doc.CreateSolidColorBrush(Color.Blue);
```

이전 경로를 기반으로 수정 사항을 적용하여 새 경로를 생성하면서 프로세스를 반복합니다.

## 7단계: 불투명도 관리

```csharp
XpsPath path5 = doc.Add(path4);
path5.RenderTransform = path5.RenderTransform.Clone();
path5.RenderTransform.Translate(0, 300);
path5.Fill.Opacity = 0.8f;
```

다양한 경로에 대해 불투명도를 독립적으로 관리할 수 있는 방법을 보여줍니다.

## 8단계: XPS 문서 저장

```csharp
doc.Save(dataDir + "WorkingWithTransparency_out.xps");
```

마지막으로 투명도가 적용된 결과 XPS 문서를 저장합니다.

## 결론

.NET용 Aspose.Page를 사용하여 XPS 문서에 투명 개체를 추가하면 시각적 표현을 향상시킬 수 있는 다양한 방법이 제공됩니다. 원하는 효과를 얻으려면 다양한 형상, 색상, 불투명도를 실험해 보세요.

## FAQ

### Q1: XPS 문서의 모든 개체에 투명도를 적용할 수 있습니까?

A1: 예, XPS 문서의 경로, 도형, 이미지와 같은 다양한 개체에 투명도를 적용할 수 있습니다.

### Q2: 특정 요소의 불투명도를 어떻게 조정할 수 있나요?

A2: 채우기 또는 획의 불투명도 속성을 설정하여 특정 요소의 투명도를 조정할 수 있습니다.

### Q3: Aspose.Page는 .NET Core와 호환됩니까?

A3: 예, Aspose.Page는 .NET Core를 지원하므로 크로스 플랫폼 개발이 가능합니다.

### Q4: Aspose.Page를 사용하여 XPS 문서를 다른 형식으로 내보낼 수 있나요?

A4: Aspose.Page는 XPS 문서를 PDF 및 이미지를 포함한 다양한 형식으로 내보내는 기능을 제공합니다.

### Q5: 추가 지원 및 커뮤니티 토론은 어디에서 찾을 수 있습니까?

 A5: 추가 지원 및 커뮤니티 토론을 보려면 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39).