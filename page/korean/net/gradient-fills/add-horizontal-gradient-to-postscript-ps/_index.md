---
title: Aspose.Page를 사용하여 PostScript(PS)에 수평 그라데이션 추가
linktitle: PostScript에 수평 그라데이션 추가(PS)
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 멋진 수평 그라데이션으로 PostScript 문서를 향상하세요. 원활한 구현을 위해 단계별 튜토리얼을 따르십시오.
type: docs
weight: 12
url: /ko/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
---
## 소개

.NET용 Aspose.Page를 사용하여 PostScript(PS) 문서에 수평 그라데이션을 추가하는 방법에 대한 포괄적인 튜토리얼에 오신 것을 환영합니다. Aspose.Page는 다양한 형식의 문서 조작을 용이하게 하는 강력한 라이브러리로, 개발자에게 문서를 원활하게 생성, 수정 및 렌더링하는 데 필요한 도구를 제공합니다.

이 튜토리얼에서는 눈길을 끄는 수평 그라데이션을 통합하여 PostScript 문서를 향상시키는 데 중점을 둘 것입니다. 프로세스의 각 단계를 안내하여 구현에 대해 확실하게 이해할 수 있도록 도와드립니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET 라이브러리용 Aspose.Page: .NET용 Aspose.Page 라이브러리가 개발 환경에 통합되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[.NET 문서용 Aspose.Page](https://reference.aspose.com/page/net/).

- 문서 디렉터리: 문서를 저장할 디렉터리를 설정하고 제공된 코드의 "문서 디렉터리"를 실제 경로로 바꿉니다.

이제 PostScript 문서에 가로 그라데이션을 추가하는 방법을 단계별로 살펴보겠습니다.

## 네임스페이스 가져오기

시작하기 전에 Aspose.Page에서 제공하는 기능에 액세스하려면 필요한 네임스페이스를 가져와야 합니다. 코드 시작 부분에 다음 네임스페이스를 추가합니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 1단계: 문서 설정

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";

// PostScript 문서의 출력 스트림 생성
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // A4 크기로 저장 옵션 만들기
    PsSaveOptions options = new PsSaveOptions();

    // 새로운 1페이지 PS 문서 만들기
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## 2단계: 그라데이션 직사각형 및 색상 정의

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // 첫 번째 직사각형에서 그래픽 경로 만들기
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    //사각형을 경계, 시작 및 끝 색상으로 사용하여 선형 그래디언트 브러시 만들기
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## 3단계: 브러시 변환 설정

```csharp
    // 브러시에 대한 변환을 만듭니다. X 및 Y 스케일 구성요소는 그에 따라 직사각형의 너비 및 높이와 같아야 합니다.
    // 변환 구성요소는 직사각형의 오프셋입니다.
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // 변환 설정
    brush.Transform = brushTransform;
```

## 4단계: 페인트 설정 및 직사각형 채우기

```csharp
    // 페인트 세트
    document.SetPaint(brush);

    // 직사각형을 채우세요
    document.Fill(path);
```

## 5단계: 그라데이션으로 텍스트 채우기

```csharp
    // 그라데이션으로 텍스트 채우기
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## 6단계: 획 및 윤곽선 텍스트 설정

```csharp
    // 현재 스트로크 설정
    document.SetStroke(new Pen(brush, 5));
    // 그라데이션이 포함된 텍스트 윤곽선
    document.OutlineText("ABC", font, 200, 400);
```

## 7단계: 현재 페이지를 닫고 문서 저장

```csharp
    // 현재 페이지 닫기
    document.ClosePage();

    // 문서 저장
    document.Save();
}
```

축하해요! .NET용 Aspose.Page를 사용하여 PostScript 문서에 수평 그라데이션을 성공적으로 추가했습니다.

## 결론

이 튜토리얼에서는 .NET용 Aspose.Page 라이브러리를 사용하여 수평 그라데이션으로 PostScript 문서를 향상시키는 프로세스를 다루었습니다. 단계별 가이드를 따르면 문서 조작을 위한 이 강력한 도구를 활용하는 데 대한 귀중한 통찰력을 얻을 수 있습니다.

## FAQ

### Q1: 직사각형 외에 다른 도형에도 그라데이션을 적용할 수 있나요?

 A1: 예, Aspose.Page를 사용하여 다양한 모양에 그라데이션을 적용할 수 있습니다. 수정하다`GraphicsPath` 특정 모양에 맞게 생성합니다.

### Q2: 그라데이션 색상을 어떻게 변경할 수 있나요?

 A2: 조정`Color.FromArgb` 의 값`LinearGradientBrush` 원하는 그라데이션 색상을 얻기 위해 인스턴스화합니다.

### Q3: Aspose.Page는 다른 문서 형식과 호환됩니까?

A3: Aspose.Page는 XPS, PS, PDF 등을 포함한 다양한 문서 형식을 지원합니다. 전체 목록은 설명서를 참조하세요.

### Q4: Aspose.Page를 상업용 프로젝트에 사용할 수 있나요?

 A4: 예, Aspose.Page에는 상업용 라이선스 옵션이 함께 제공됩니다. 방문하다[여기](https://purchase.aspose.com/buy) 자세한 내용은.

### Q5: Aspose.Page 사용자를 위한 커뮤니티 포럼이 있습니까?

 A5: 예, Aspose.Page 커뮤니티에 가입하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 다른 사용자와 연결하고 도움을 구합니다.