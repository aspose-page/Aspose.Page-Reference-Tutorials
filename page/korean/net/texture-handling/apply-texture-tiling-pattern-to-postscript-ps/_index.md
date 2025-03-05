---
title: Aspose.Page를 사용하여 PostScript(PS)에 텍스처 타일링 패턴 적용
linktitle: PostScript에 텍스처 타일링 패턴 적용(PS)
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 텍스처 타일링 패턴으로 PostScript(PS) 문서를 향상하세요. 창의적인 터치를 위한 단계별 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
---
## 소개

.NET용 Aspose.Page를 사용하여 PS(PostScript) 문서에 텍스처 타일링 패턴을 적용하는 방법에 대한 단계별 튜토리얼에 오신 것을 환영합니다. Aspose.Page는 다양한 문서 형식으로 작업할 수 있는 강력한 라이브러리이며, 이 튜토리얼에서는 텍스처 타일링 패턴을 추가하여 PS 문서를 향상시키는 방법을 살펴보겠습니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.

- [비주얼 스튜디오](https://visualstudio.microsoft.com/) 귀하의 컴퓨터에 설치되었습니다.
- C# 프로그래밍에 대한 기본 지식.
-  다운로드 및 설치[.NET 라이브러리용 Aspose.Page](https://releases.aspose.com/page/net/).
- 텍스처 패턴에 대한 이미지 파일(예: "TestTexture.bmp").

## 네임스페이스 가져오기

C# 코드에서 필요한 네임스페이스를 가져왔는지 확인하세요.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

제공된 예제를 여러 단계로 나누어 프로세스를 안내해 보겠습니다.

## 1단계: 문서 디렉토리 설정

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
```

"Your Document Directory"를 PS 문서를 저장하려는 경로로 바꾸십시오.

## 2단계: PS 문서용 출력 스트림 생성

```csharp
// PostScript 문서의 출력 스트림 생성
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // A4 크기로 저장 옵션 만들기
    PsSaveOptions options = new PsSaveOptions();

    // 새로운 1페이지 PS 문서 만들기
    PsDocument document = new PsDocument(outPsStream, options, false);
```

이 단계에서는 문서 크기 정의를 포함하여 PS 문서의 출력 스트림을 설정합니다.

## 3단계: 텍스처 타일링 패턴 적용

```csharp
// 이미지 파일에서 비트맵 개체 만들기
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // 이미지에서 텍스처 브러시 만들기
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    //패턴에 X 방향의 크기 조정 추가
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // 이 텍스처 브러시를 현재 페인트로 설정
    document.SetPaint(brush);
}
```

이 단계에는 이미지에서 텍스처 브러시를 만들고 이를 문서의 현재 페인트로 설정하는 작업이 포함됩니다.

## 4단계: 직사각형 경로 만들기 및 채우기

```csharp
// 직사각형 경로 만들기
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// 직사각형 채우기
document.Fill(path);
```

여기서는 직사각형 경로를 정의하고 이전에 설정된 텍스처 브러시로 채웁니다.

## 5단계: 획 설정 및 그리기

```csharp
// 현재 페인트 가져오기
Brush paint = document.GetPaint();

// 빨간색 획 설정
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// 직사각형을 획을 긋습니다.
document.Draw(path);
```

이 단계에는 획 속성을 설정하고 윤곽선이 있는 사각형을 그리는 작업이 포함됩니다.

## 6단계: 텍스처 패턴으로 텍스트 채우기 및 윤곽선 지정

```csharp
// 텍스처 패턴으로 텍스트 채우기
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// 텍스처 패턴이 있는 텍스트 개요
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

마지막으로 텍스처 패턴으로 텍스트를 채우고 윤곽을 잡아 문서의 시각적 매력을 향상시킵니다.

## 7단계: 문서 저장 및 닫기

```csharp
// 현재 페이지 닫기
document.ClosePage();

// 문서 저장
document.Save();
```

변경 사항을 적용하려면 현재 페이지를 닫고 문서를 저장하세요.

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 PostScript 문서에 텍스처 타일링 패턴을 적용하는 방법을 성공적으로 배웠습니다. 다양한 이미지와 패턴을 실험하여 PS 문서를 더욱 맞춤화하세요.

## FAQ

### Q1: 텍스처 패턴에 다른 이미지 형식을 사용할 수 있나요?

A1: 예, Aspose.Page는 다양한 이미지 형식을 지원합니다. 라이브러리 문서와의 호환성을 확인하세요.

### Q2: Aspose.Page는 .NET Core와 호환됩니까?

A2: 예, Aspose.Page는 .NET Framework 및 .NET Core와 모두 호환됩니다.

### Q3: 질감이 있는 직사각형의 크기를 어떻게 조정할 수 있나요?

 A3: 치수를 수정하세요.`RectangleF` 경로 생성 중 매개변수.

### Q4: 단일 문서에 여러 텍스처 패턴을 추가할 수 있습니까?

A4: 예, 다른 이미지와 경로로 프로세스를 반복할 수 있습니다.

### Q5: 추가 리소스와 지원은 어디서 찾을 수 있나요?

 A5: 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지역사회 지원을 위해[선적 서류 비치](https://reference.aspose.com/page/net/).
