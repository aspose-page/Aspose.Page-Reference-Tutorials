---
date: 2026-01-18
description: Aspose.Page for .NET를 사용하여 .NET에서 포스트스크립트 문서를 만들고 사각형을 추가하는 방법을 배웁니다.
  단계별 가이드와 코드 샘플 포함.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: PostScript 문서 생성 .NET – Aspose.Page로 사각형 추가
url: /ko/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET을 사용하여 PostScript (PS)에 사각형 추가

## 소개

PostScript 문서 .net을 **생성**하려는 경우, Aspose.Page는 PostScript 파일을 처리하기 위한 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Page for .NET을 사용하여 PostScript 문서에 사각형을 추가하는 방법을 단계별로 안내하여 보다 풍부한 그래픽 생성의 탄탄한 기반을 마련해 드립니다.

## 빠른 답변
- **필요한 라이브러리는 무엇인가요?** Aspose.Page for .NET.
- **처음부터 PostScript 문서를 만들 수 있나요?** 예 – API를 통해 프로그래밍 방식으로 PS 파일을 구축할 수 있습니다.
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **개발에 라이선스가 필요합니까?** 무료 체험판으로 테스트가 가능하며, 프로덕션에서는 라이선스가 필요합니다.
- **구현에 걸리는 시간은 얼마나 되나요?** 기본 도형의 경우 일반적으로 10분 미만 소요됩니다.

## .NET에서 PostScript 문서를 생성한다는 것은 무엇인가요?
.NET에서 PostScript 문서를 생성한다는 것은 Aspose.Page API를 사용하여 페이지 내용(텍스트, 그래픽 또는 도형)을 설명하는 .ps 파일을 프로그래밍 방식으로 만드는 것을 의미합니다. 이 접근 방식은 서버‑사이드 그래픽 생성, 자동 보고서 작성 또는 출력 형식에 대한 정밀한 제어가 필요한 모든 시나리오에 이상적입니다.

## 왜 Aspose.Page for .NET를 사용하나요?
- **Full control over graphics** – 저수준 PS 구문을 다루지 않고도 도형을 그리며 색상과 스트로크를 설정할 수 있습니다.
- **Cross‑platform** – Windows, Linux, macOS 런타임에서 모두 작동합니다.
- **No external dependencies** – 라이브러리가 내부적으로 모든 PS 생성을 처리합니다.
- **Rich documentation & examples** – 빠르게 시작할 수 있는 풍부한 문서와 예제가 제공됩니다.

## 전제 조건

- **Aspose.Page for .NET Library** – [here](https://releases.aspose.com/page/net/)에서 다운로드하고 설치합니다.
- **Development Environment** – Visual Studio, VS Code 또는 .NET‑호환 IDE 중 하나.

## 네임스페이스 가져오기

코딩을 시작하기 전에 필요한 클래스를 노출하는 네임스페이스를 가져옵니다:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

이제 예제를 명확한 번호 단계로 나누어 보겠습니다.

## 단계 1: 문서 디렉터리 설정

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

`"Your Document Directory"`를 결과 PS 파일을 저장하려는 폴더 경로로 바꾸세요.

## 단계 2: PostScript 문서를 위한 출력 스트림 생성

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

이 스트림은 **AddRectangle_outPS.ps**를 가리킵니다. 필요에 따라 파일 이름을 바꾸거나 위치를 변경해도 됩니다.

## 단계 3: 저장 옵션 설정 및 PS 문서 생성

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

여기서는 Aspose.Page에 A4 페이지 크기를 사용하고 단일 페이지 문서를 만들도록 지정합니다.

## 단계 4: 채워진 사각형 추가

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

(250, 100) 위치에 너비 150, 높이 100인 사각형을 정의하고 오렌지 브러시를 설정하여 도형을 채웁니다.

## 단계 5: 외곽선 사각형 추가

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

두 번째 사각형은 페이지 하단에 생성되며, 이번에는 빨간색 3포인트 스트로크를 사용합니다.

## 단계 6: 페이지 닫기 및 문서 저장

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

페이지를 닫으면 그리기가 완료되고, `Save()`가 PS 파일을 디스크에 기록합니다.

## 일반적인 문제 및 팁

- **Incorrect file path** – `dataDir`가 경로 구분자(`\\` 또는 `/`)로 끝나는지 확인하거나 `Path.Combine`을 사용하세요.
- **Missing license** – 프로덕션 환경에서는 문서를 만들기 전에 Aspose 라이선스를 적용해 평가 워터마크가 표시되지 않도록 하세요.
- **Color visibility** – 사각형이 비어 보이면 브러시나 펜 색상이 페이지 배경과 대비되는지 확인하세요.

## 자주 묻는 질문

**Q:** 사각형의 색상을 사용자 정의할 수 있나요?  
**A:** 물론 가능합니다. `SolidBrush`와 `Pen` 생성자에서 `Color.Orange` 또는 `Color.Red` 값을 원하는 `System.Drawing.Color`로 변경하면 됩니다.

**Q:** Aspose.Page가 다른 문서 형식과 호환되나요?  
**A:** 네. PostScript 외에도 Aspose.Page는 XPS 및 EPS 생성도 지원합니다.

**Q:** 같은 문서에 텍스트를 어떻게 추가할 수 있나요?  
**A:** `TextFragment` 클래스를 사용해 원하는 좌표에 텍스트를 배치한 뒤 `document.Draw(textFragment)`를 호출하면 됩니다.

**Q:** 추가 예제와 전체 API 참조는 어디에서 찾을 수 있나요?  
**A:** 문서 [here](https://reference.aspose.com/page/net/)를 살펴보고 [Aspose.Page forum](https://forum.aspose.com/c/page/39)에서 커뮤니티에 참여하세요.

**Q:** 구매하기 전에 Aspose.Page를 체험할 수 있나요?  
**A:** 예, 무료 체험판을 [here](https://releases.aspose.com/)에서 다운로드하세요. 장기 평가가 필요하면 [temporary license](https://purchase.aspose.com/temporary-license/)를 고려해 보세요.

---

**마지막 업데이트:** 2026-01-18  
**테스트 환경:** Aspose.Page 24.12 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}