---
date: 2026-02-25
description: Aspose.Page for .NET을 사용하여 선형 그라디언트 사각형으로 PostScript 문서를 향상시키세요. 단계별
  가이드를 따라 그라디언트 채우기 텍스트와 외곽선 텍스트 그라디언트를 배워보세요.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Aspose.Page를 사용하여 PostScript(PS)에 선형 그라디언트 사각형 추가
url: /ko/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript (PS)에 Linear Gradient Rectangle 추가하기 (Aspose.Page 사용)

## 소개

Aspose.Page for .NET을 사용하여 PostScript (PS) 문서에 **linear gradient rectangle**를 추가하는 포괄적인 튜토리얼에 오신 것을 환영합니다. Aspose.Page는 다양한 형식의 문서를 생성, 수정 및 렌더링할 수 있는 강력한 라이브러리이며, 오늘은 PS 파일에 눈에 띄는 그라디언트를 적용하는 방법에 집중합니다.

### 빠른 답변
- **linear gradient rectangle는 무엇을 하나요?** 한쪽에서 다른 쪽으로 부드러운 색상 전환으로 사각형 영역을 채웁니다.  
- **그라디언트 채우기 텍스트를 처리하는 API는?** `LinearGradientBrush`와 `SetPaint`, `FillAndStrokeText`를 결합합니다.  
- **그라디언트로 텍스트 외곽선을 만들 수 있나요?** 예—그라디언트 브러시와 함께 `SetStroke`를 사용하고 `OutlineText`를 호출합니다.  
- **프로덕션에 라이선스가 필요합니까?** 평가용이 아닌 사용을 위해서는 상업용 Aspose.Page 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## 사전 요구 사항

시작하기 전에 다음을 확인하십시오:

- Aspose.Page for .NET 라이브러리: 프로젝트에 라이브러리가 참조되어 있는지 확인하십시오. [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/)에서 다운로드할 수 있습니다.
- Document Directory: 생성된 PS 파일이 저장될 디스크상의 폴더를 만들고 코드에서 **“Your Document Directory”**를 해당 경로로 교체하십시오.

## 네임스페이스 가져오기

시작하려면 drawing 및 PS‑specific 클래스를 사용할 수 있는 네임스페이스를 가져옵니다:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Linear Gradient Rectangle란?

**linear gradient rectangle**는 내부가 선형 그라디언트로 칠해진 사각형 형태입니다—색상이 직선에 따라 부드럽게 전환되며, 일반적으로 왼쪽에서 오른쪽(수평) 또는 위에서 아래(수직) 방향으로 진행됩니다. Aspose.Page에서는 사각형을 정의하는 `GraphicsPath`와 색상 전환을 설명하는 `LinearGradientBrush`를 결합하여 이를 구현합니다.

## 왜 Gradient Fill Text와 Outline Text Gradient를 사용하나요?

- **시각적 매력:** Gradient‑filled 텍스트는 보고서, 청구서 또는 홍보 자료에 깊이감과 현대적인 스타일을 추가합니다.  
- **브랜드 일관성:** 정확한 ARGB 값으로 기업 색상을 맞춥니다.  
- **다재다능함:** 동일한 브러시를 도형 채우기, 텍스트 채우기, 외곽선 그라디언트 등에 재사용하여 코드 중복을 줄입니다.

## 단계 1: 문서 설정

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## 단계 2: Gradient Rectangle 및 색상 정의

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## 단계 3: 브러시 변환 설정

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## 단계 4: Paint 설정 및 사각형 채우기

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Gradient Fill Text 적용 방법

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Outline Text Gradient 사용

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## 단계 7: 현재 페이지 닫고 문서 저장

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

축하합니다! 이제 **linear gradient rectangle**를 PostScript 문서에 성공적으로 추가했으며 동일한 브러시를 **gradient fill text**와 **outline text gradient**에 사용했습니다.

## 일반적인 사용 사례 및 팁

- **보고서 헤더:** 섹션 제목을 강조하기 위해 큰 텍스트 블록을 그라디언트로 채웁니다.  
- **브랜드 로고:** 일관된 브랜딩을 위해 로고 형태를 그라디언트 채우기 도형으로 재현합니다.  
- **프로 팁:** 여러 그리기 호출에 동일한 `LinearGradientBrush` 인스턴스를 재사용하여 도형과 텍스트 전반에 색상이 완벽히 정렬되도록 합니다.

## 자주 묻는 질문

### Q1: 사각형 외에 다른 도형에도 그라디언트를 적용할 수 있나요?
**A:** 예, `GraphicsPath`로 정의된 모든 도형에 그라디언트를 적용할 수 있습니다. `document.Fill(path)`를 호출하기 전에 원, 다각형 또는 사용자 정의 경로를 추가하면 됩니다.

### Q2: 그라디언트 색상을 어떻게 변경하나요?
**A:** `LinearGradientBrush`를 생성할 때 `Color.FromArgb` 값을 수정합니다. 첫 번째 색상이 시작 색상이고 두 번째 색상이 그라디언트의 끝 색상입니다.

### Q3: Aspose.Page가 다양한 문서 형식과 호환되나요?
**A:** 물론입니다. Aspose.Page는 XPS, PS, PDF 및 여러 기타 벡터 형식을 지원합니다. 전체 목록은 공식 문서를 확인하십시오.

### Q4: Aspose.Page를 상업 프로젝트에 사용할 수 있나요?
**A:** 예, 상업용 라이선스를 제공하고 있습니다. 자세한 내용은 구매 페이지를 참고하십시오: [here](https://purchase.aspose.com/buy).

### Q5: 커뮤니티 지원을 어디서 받을 수 있나요?
**A:** Aspose.Page 커뮤니티 포럼에 참여하세요: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page 24.10 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}