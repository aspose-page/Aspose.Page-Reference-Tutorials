---
date: 2026-03-26
description: Aspose.Page를 사용하여 텍스처 타일링 패턴이 적용된 .NET PostScript 문서를 만드는 방법을 배워보세요.
  단계별 가이드를 따라 PS 파일에 풍부한 텍스처를 추가하세요.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: 텍스처 타일링을 사용하여 PostScript .NET 문서 만들기
url: /ko/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 텍스처 타일링을 사용한 PostScript .NET 문서 만들기

## 텍스처 타일링을 사용하여 PostScript .NET 문서를 만드는 방법

이 튜토리얼에서는 **PostScript document .NET**을 만드는 방법과 Aspose.Page 라이브러리를 사용하여 텍스처 타일링 패턴으로 풍부하게 만드는 방법을 배웁니다. 프로젝트 설정부터 텍스처 브러시를 사용한 텍스트 채우기 및 스트로크까지 각 단계를 차례대로 안내하므로 몇 분 안에 시각적으로 매력적인 PS 파일을 만들 수 있습니다.

## 빠른 답변
- **사용된 라이브러리는 무엇인가요?** Aspose.Page for .NET  
- **.NET Core를 사용할 수 있나요?** Yes, the library supports .NET Core and .NET 5/6  
- **텍스처에 사용할 수 있는 이미지 형식은 무엇인가요?** Any format supported by System.Drawing (BMP, PNG, JPEG, etc.)  
- **구현에 얼마나 걸리나요?** About 10‑15 minutes for a basic example  
- **라이선스가 필요합니까?** A free trial works for testing; a license is required for production  

## 사전 요구 사항

- [Visual Studio](https://visualstudio.microsoft.com/)가 머신에 설치되어 있어야 합니다.  
- C# 프로그래밍에 대한 기본 지식.  
- [Aspose.Page for .NET library](https://releases.aspose.com/page/net/)를 다운로드하고 설치합니다.  
- 텍스처 패턴에 사용할 이미지 파일 (예: **TestTexture.bmp**).

## 네임스페이스 가져오기

In your C# file, import the required namespaces so the compiler knows where to find the types we’ll use:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 단계 1: 문서 디렉터리 설정

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Replace **Your Document Directory** with the folder where you want the generated PS file to be saved.

## 단계 2: PS 문서를 위한 출력 스트림 생성

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

This block opens a file stream, configures the page size (A4 by default), and creates a fresh **PsDocument** instance that we will draw on.

## 단계 3: 텍스처 타일링 패턴 적용

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

Here we load the bitmap, wrap it in a **TextureBrush**, optionally stretch it horizontally, and tell the **PsDocument** to use this brush for subsequent drawing operations.

## 단계 4: 사각형 경로 생성 및 채우기

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

A simple rectangle is defined and filled with the texture brush we set earlier.

## 단계 5: 스트로크 설정 및 그리기

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

We retrieve the current paint (the texture brush), create a red pen for the outline, and draw the rectangle’s border.

## 단계 6: 텍스처 패턴으로 텍스트 채우기 및 스트로크

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

This step demonstrates the **fill and stroke text** capability: the characters “ABC” are filled with the texture brush and then outlined, giving a striking visual effect.

## 단계 7: 문서 저장 및 닫기

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Closing the page finalizes the drawing commands, and `Save()` writes the PostScript file to disk.

## 일반적인 문제 및 해결책

- **텍스처가 잘못 늘어나는 경우** – `Matrix` 값을 조정하여 X/Y 방향의 스케일을 제어합니다.  
- **이미지를 찾을 수 없음** – `dataDir`이 올바른 폴더를 가리키는지, 파일 이름이 대소문자를 포함해 정확히 일치하는지 확인합니다.  
- **색상이 이상하게 보임** – PostScript는 장치 독립적인 색상 공간을 사용한다는 점을 기억하고, `Color` 객체가 올바르게 매핑되는지 확인합니다.

## 자주 묻는 질문

**Q:** 텍스처 패턴에 다른 이미지 형식을 사용할 수 있나요?  
**A:** 예, `System.Drawing.Bitmap`에서 지원하는 모든 형식(BMP, PNG, JPEG, GIF 등)이 작동합니다.

**Q:** Aspose.Page가 .NET Core와 호환되나요?  
**A:** 물론입니다. 이 라이브러리는 .NET Framework, .NET Core, 그리고 .NET 5/6에서 실행됩니다.

**Q:** 텍스처가 적용된 사각형의 크기를 어떻게 변경하나요?  
**A:** 사각형 생성 단계에서 `RectangleF` 값을 수정합니다(예: `new RectangleF(0, 0, 300, 150)`).

**Q:** 하나의 문서에 여러 텍스처 패턴을 적용할 수 있나요?  
**A:** 예. 다른 이미지를 사용해 새로운 `TextureBrush`를 만든 뒤, 다음 도형이나 텍스트를 그리기 전에 `SetPaint`를 다시 호출하면 됩니다.

**Q:** 더 많은 예제와 API 레퍼런스는 어디서 찾을 수 있나요?  
**A:** 커뮤니티 지원을 위해 [Aspose.Page Forum](https://forum.aspose.com/c/page/39)을 방문하고, 자세한 API 사용법은 공식 [documentation](https://reference.aspose.com/page/net/)을 참고하세요.

## 결론

You now know how to **create PostScript document .NET** and apply a texture tiling pattern, including how to **fill and stroke text** with that texture. Experiment with different images, scaling matrices, and drawing primitives to produce custom‑styled PS files for reports, flyers, or any graphic‑heavy output.

---

**마지막 업데이트:** 2026-03-26  
**테스트 환경:** Aspose.Page 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}