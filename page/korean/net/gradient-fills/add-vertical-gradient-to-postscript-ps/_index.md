---
title: Aspose.Page를 사용하여 PS(PostScript)에 수직 그라데이션 추가
linktitle: PostScript에 수직 그라데이션 추가(PS)
second_title: Aspose.페이지 .NET API
description: Aspose.Page를 사용하여 .NET의 PostScript(PS) 문서에 시각적으로 매력적인 수직 그라데이션을 추가하는 방법을 알아보세요. 이 단계별 가이드를 통해 문서 작성 수준을 높이세요.
weight: 14
url: /ko/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용하여 PS(PostScript)에 수직 그라데이션 추가

## 소개

문서 조작 및 생성 영역에서 Aspose.Page for .NET은 개발자를 위한 강력한 도구로 돋보입니다. 이 튜토리얼은 .NET용 Aspose.Page를 사용하여 PS(PostScript) 문서에 수직 그라데이션을 추가하는 과정을 안내합니다. 이 가이드를 마치면 시각적으로 매력적인 효과를 얻기 위해 필요한 단계를 명확하게 이해하게 될 것입니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 사항이 준비되어 있는지 확인하세요.

-  .NET용 Aspose.Page: Aspose.Page 라이브러리가 설치되어 있는지 확인하세요. 필요한 리소스와 문서를 찾을 수 있습니다.[여기](https://reference.aspose.com/page/net/).

- 개발 환경: .NET 개발을 위한 IDE(통합 개발 환경)를 포함하여 적합한 개발 환경을 설정합니다.

- 기본 이해: 스트림 작업, 그래픽 경로 및 색상 조작을 포함하여 .NET 개발의 기본 사항을 숙지합니다.

## 네임스페이스 가져오기

C# 프로젝트에서 코드 파일 시작 부분에 필수 네임스페이스를 포함합니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 1단계: 문서 디렉터리 설정

문서 디렉토리의 경로를 지정하여 시작하십시오. PS 문서가 저장될 위치입니다.

```csharp
string dataDir = "Your Document Directory";
```

## 2단계: PostScript 문서에 대한 출력 스트림 생성

FileStream 클래스를 사용하여 PostScript 문서에 대한 출력 스트림을 생성합니다.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## 3단계: 저장 옵션 및 PS 문서 생성

A4 크기로 저장 옵션을 생성하고 새로운 1페이지 PS 문서를 초기화합니다.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 4단계: 직사각형 치수 정의

수직 그래디언트를 적용할 직사각형의 크기와 위치를 지정합니다.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## 5단계: 그래픽 경로 생성

정의된 직사각형에서 그래픽 경로를 만듭니다.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## 6단계: 보간 색상 정의

그라디언트의 보간 색상 및 위치 배열을 설정합니다.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## 7단계: 선형 그라디언트 브러시 만들기

직사각형을 경계, 시작 및 끝 색상으로 사용하여 선형 그래디언트 브러시를 형성합니다.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## 8단계: 브러시 변환 설정

X 및 Y 스케일 구성요소가 직사각형의 너비 및 높이와 일치하는지 확인하여 브러시에 대한 변환을 설정합니다.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## 9단계: 페인트 설정 및 직사각형 채우기

문서의 페인트를 설정하고 이전에 정의한 직사각형을 채웁니다.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## 10단계: 현재 페이지를 닫고 문서 저장

현재 페이지를 닫고 PostScript 문서를 저장합니다.

```csharp
document.ClosePage();
document.Save();
```

축하해요! .NET용 Aspose.Page를 사용하여 PostScript 문서에 수직 그라데이션을 성공적으로 추가했습니다. 문서에서 다양한 시각적 효과를 얻으려면 다양한 매개변수와 색상을 실험해 보세요.

## 결론

이 튜토리얼에서는 수직 그라디언트를 통합하여 PostScript 문서를 향상시키는 프로세스를 살펴보았습니다. .NET용 Aspose.Page는 이러한 조작을 위한 원활한 환경을 제공하여 개발자가 시각적으로 멋진 문서를 쉽게 만들 수 있도록 지원합니다.

## FAQ

### Q1: 동일한 문서의 서로 다른 영역에 여러 그라디언트를 적용할 수 있습니까?

A1: 네, 가능합니다. 특정 치수와 색 구성표를 사용하여 각 지역에 대해 단계를 반복하기만 하면 됩니다.

### 질문 2: 이 코드를 기존 .NET 프로젝트에 어떻게 통합할 수 있습니까?

A2: 코드를 복사하여 프로젝트 파일에 붙여넣고 Aspose.Page 라이브러리가 참조되었는지 확인하세요.

### Q3: .NET용 Aspose.Page에서 사용할 수 있는 다른 그라데이션 유형이 있습니까?

A3: Aspose.Page는 방사형 및 경로 그라데이션을 포함한 다양한 그라데이션 유형을 지원합니다. 자세한 내용은 설명서를 참조하세요.

### Q4: Aspose.Page를 상업용 프로젝트에 사용할 수 있나요?

 A4: 네, 가능합니다. 방문하다[여기](https://purchase.aspose.com/buy) 라이선스 옵션을 살펴보세요.

### Q5: 도움을 구할 수 있는 Aspose.Page 커뮤니티 포럼이 있나요?

 A5: 물론이죠! 다음으로 향하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 다른 개발자와 연결하고 도움을 받으려면
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
