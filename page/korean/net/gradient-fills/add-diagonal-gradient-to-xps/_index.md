---
date: 2026-02-23
description: Aspose.Page for .NET를 사용하여 대각선 그라디언트 XPS 문서를 만드는 방법을 배우고 시각적 프레젠테이션을
  손쉽게 향상시키세요.
linktitle: Add Diagonal Gradient to XPS
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET를 사용하여 대각선 그라디언트 XPS 만들기
url: /ko/net/gradient-fills/add-diagonal-gradient-to-xps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET을 사용하여 대각선 그라디언트 XPS 만들기

## Introduction

눈에 띄는 **대각선 그라디언트 XPS** 파일을 만들어야 한다면, Aspose.Page for .NET이 이를 간단하게 해줍니다. 이 튜토리얼에서는 Aspose.Page API를 사용하여 XPS 문서에 대각선 그라디언트를 단계별로 추가하는 방법을 배웁니다. 끝까지 진행하면 어떤 형태나 색 구성에도 적용할 수 있는 재사용 가능한 패턴을 얻게 됩니다.

## Quick Answers
- **API 메서드는 무엇을 하나요?** 경로를 대각선으로 가로지르는 선형 그라디언트 브러시를 생성합니다.  
- **XPS 문서를 나타내는 클래스는 무엇인가요?** `XpsDocument`.  
- **샘플을 실행하려면 라이선스가 필요합니까?** 개발에는 무료 체험판으로 충분하지만, 프로덕션에서는 라이선스가 필요합니다.  
- **그라디언트 방향을 변경할 수 있나요?** 예—시작 및 끝 `PointF` 값을 조정하면 됩니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## What is **create diagonal gradient xps**?
대각선 그라디언트는 형태의 한 모서리에서 반대쪽 모서리까지 부드럽게 색이 변하는 전환입니다. XPS에서는 `LinearGradientBrush`를 경로의 fill 속성에 적용하여 이 효과를 구현합니다. Aspose.Page 라이브러리는 저수준 XPS 마크업을 추상화하여 색상과 기하학에 집중할 수 있게 해줍니다.

## Why use Aspose.Page for diagonal gradients?
- **고충실도 렌더링** – 출력이 XPS 사양과 정확히 일치합니다.  
- **전체 .NET 통합** – C#, VB.NET 및 모든 .NET 언어와 작동합니다.  
- **외부 종속성 없음** – 모든 것이 프로세스 내에서 처리되며 COM이나 Office가 필요하지 않습니다.  
- **복잡한 문서에도 확장 가능** – 동일 페이지에 여러 그라디언트, 이미지 및 텍스트를 결합할 수 있습니다.

## Prerequisites

1. **Aspose.Page for .NET 라이브러리** – [here](https://releases.aspose.com/page/net/)에서 다운로드하십시오.  
2. **개발 환경** – Visual Studio, Rider 또는 .NET 프로젝트를 지원하는 모든 편집기.

이제 코드를 살펴보겠습니다.

## Import Namespaces

.NET 프로젝트에서 Aspose.Page 라이브러리의 필요한 네임스페이스를 포함하여 필요한 클래스와 메서드에 접근하십시오. 코드 시작 부분에 다음 네임스페이스를 추가합니다:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Step 1: Set the Document Directory

먼저 문서 디렉터리 경로를 지정합니다. 여기서 대각선 그라디언트가 적용된 결과 XPS 문서가 저장됩니다.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

## Step 2: Create a New XPS Document

Aspose.Page 라이브러리를 사용하여 새로운 `XpsDocument`를 초기화합니다.

```csharp
XpsDocument doc = new XpsDocument();
```

## Step 3: Define Gradient Colors

`XpsGradientStop` 객체 리스트를 생성하여 대각선 그라디언트의 각 색상을 나타냅니다.

```csharp
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 142, 4), 0f));
// ... Repeat for other colors
stops.Add(doc.CreateGradientStop(doc.CreateColor(0, 199, 80), 1f));
```

## Step 4: Add a Diagonal Gradient to a Path

정의된 기하학을 가진 새로운 경로를 만들고, 그에 대각선 그라디언트를 적용합니다. 필요에 따라 렌더링 변환 및 fill 속성을 조정하십시오.

```csharp
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 10f), new PointF(228f, 100f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
```

## Step 5: Save the Resultant XPS Document

마지막으로 수정된 XPS 문서를 지정된 디렉터리에 저장합니다.

```csharp
doc.Save(dataDir + "AddDiagonalGradient_outXPS.xps");
```

이제 성공적으로 **대각선 그라디언트 XPS** 파일을 만들었습니다. 다양한 색상 스톱, 기하학 문자열 또는 변환 행렬을 실험하여 여러 시각 효과를 만들어 보세요.

## Common Issues and Solutions
- **그라디언트가 보이지 않음** – 경로 기하학이 닫혀 있는지, 브러시의 시작/끝 점이 경로 경계 내에 있는지 확인하십시오.  
- **색상이 올바르지 않음** – 올바른 ARGB 값을 사용하여 `CreateColor`를 호출했는지 확인하십시오; 메서드는 0‑255 범위의 값을 기대합니다.  
- **파일이 저장되지 않음** – `dataDir`이 존재하는 폴더를 가리키고 애플리케이션에 쓰기 권한이 있는지 확인하십시오.

## Frequently Asked Questions

**Q: 문서의 다른 부분에 여러 그라디언트를 적용할 수 있나요?**  
A: 예, 여러 경로를 만들고 각각에 다른 그라디언트를 적용할 수 있습니다.

**Q: 미리 정의된 그라디언트 스타일이 있나요?**  
A: Aspose.Page는 사용자 정의 그라디언트를 허용하여 색 전환을 완전히 제어할 수 있습니다.

**Q: Aspose.Page for .NET을 다른 문서 형식과 함께 사용할 수 있나요?**  
A: Aspose.Page는 주로 XPS 문서 조작에 초점을 맞추고 있습니다.

**Q: 문서 처리와 관련된 오류를 어떻게 처리합니까?**  
A: 오류 처리 모범 사례는 [documentation](https://reference.aspose.com/page/net/)를 참고하십시오.

**Q: 구매 전에 체험판이 있나요?**  
A: 예, [free trial](https://releases.aspose.com/)을 통해 Aspose.Page for .NET을 체험할 수 있습니다.

**Q: 그라디언트 방향을 수직 또는 수평으로 변경하려면 어떻게 해야 하나요?**  
A: `CreateLinearGradientBrush`의 `PointF` 인수를 수정하여 새로운 시작 및 끝 점을 설정하십시오.

**Q: 라이브러리가 그라디언트에서 투명도를 지원하나요?**  
A: 예—`CreateColor`로 색을 만들 때 알파 값을 포함하면 됩니다.

## Conclusion

Aspose.Page for .NET은 XPS 문서에 대각선 그라디언트를 적용하는 과정을 간소화합니다. 이 가이드는 사전 준비부터 최종 파일 저장까지 모든 단계를 안내했습니다. 다양한 형태와 색상 팔레트를 실험하여 XPS 보고서, 브로셔, 청구서를 더욱 돋보이게 하세요.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-02-23  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose