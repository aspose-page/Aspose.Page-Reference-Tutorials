---
date: 2026-06-30
description: Aspose.Page for .NET를 사용하여 postscript 문서 .NET을 만들고 사각형을 추가하는 방법을 배웁니다.
  코드 샘플이 포함된 단계별 가이드.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: PostScript (PS)에 사각형 추가
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: PostScript 문서 .NET 만들기 – 사각형 추가 Aspose.Page
url: /ko/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PostScript (PS)에 사각형 추가하기 (Aspose.Page for .NET 사용)

## 소개

Aspose.Page for .NET은 PostScript, EPS 및 XPS 파일을 프로그래밍 방식으로 생성하고 조작할 수 있게 해주는 라이브러리입니다. **postscript 문서를 .net에서 생성**하려는 경우, 이 튜토리얼은 Aspose.Page를 사용해 PostScript 문서에 사각형을 추가하는 방법을 단계별로 안내하여 보다 풍부한 그래픽 생성의 기초를 제공합니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Page for .NET.  
- **처음부터 PostScript 문서를 만들 수 있나요?** 예 – API를 사용해 PS 파일을 프로그래밍 방식으로 구축할 수 있습니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **개발에 라이선스가 필요합니까?** 테스트용 무료 체험판을 사용할 수 있으며, 프로덕션에서는 라이선스가 필요합니다.  
- **구현 소요 시간은?** 기본 도형의 경우 일반적으로 10분 미만입니다.

## postscript 문서를 .net에서 생성한다는 것은 무엇인가요?
.NET에서 PostScript 문서를 생성한다는 것은 Aspose.Page API를 사용해 페이지 내용(텍스트, 그래픽, 도형)을 설명하는 `.ps` 파일을 프로그래밍 방식으로 만들어 내는 것을 의미합니다. 이 접근 방식은 서버‑사이드 그래픽 생성, 자동 보고서 작성, 또는 출력 형식에 대한 정밀 제어가 필요한 모든 시나리오에 이상적입니다.

## 왜 Aspose.Page for .NET을 사용하나요?
Aspose.Page는 **30개 이상의 그래픽 프리미티브**를 지원하며 전체 문서를 메모리에 로드하지 않고도 **500 MB**까지 파일을 생성할 수 있어 Windows, Linux, macOS에서 고성능 렌더링을 제공합니다. 저수준 PostScript 코드를 작성할 필요 없이 도형, 색상 및 스트로크를 완벽히 제어할 수 있습니다.

- **그래픽에 대한 완전한 제어** – 저수준 PS 구문을 다루지 않고도 도형을 그리고 색상을 설정하며 스트로크를 적용합니다.  
- **크로스‑플랫폼** – Windows, Linux, macOS 런타임에서 동작합니다.  
- **외부 종속성 없음** – 라이브러리 자체가 모든 PS 생성을 내부에서 처리합니다.  
- **풍부한 문서 및 예제** – 빠르게 시작할 수 있습니다.

## 전제 조건

- **Aspose.Page for .NET Library** – [여기](https://releases.aspose.com/page/net/)에서 다운로드하고 설치합니다.  
- **개발 환경** – Visual Studio, VS Code 또는 .NET 호환 IDE.

## 네임스페이스 가져오기

`Aspose.Page` 네임스페이스는 `Document`, `Page`, `SolidBrush`, `Pen` 등 필요한 핵심 클래스를 제공합니다. 코딩을 시작하기 전에 해당 네임스페이스를 가져오세요.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

이제 예제를 명확한 번호 단계로 나누어 살펴보겠습니다.

## 1단계: 문서 디렉터리 설정

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

`"Your Document Directory"`를 결과 PS 파일을 저장하고자 하는 폴더 경로로 교체합니다.

## 2단계: PostScript 문서를 위한 출력 스트림 만들기

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

이 스트림은 **AddRectangle_outPS.ps**를 가리킵니다. 필요에 따라 파일명을 바꾸거나 위치를 변경해도 됩니다.

## 3단계: 저장 옵션 설정 및 PS 문서 만들기

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

여기서는 Aspose.Page에 A4 페이지 크기를 사용하고 단일 페이지 문서를 만들도록 지정합니다.

## 4단계: 채워진 사각형 추가

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

(250, 100) 위치에 너비 150, 높이 100인 사각형을 정의하고 주황색 브러시를 설정해 도형을 채웁니다.

## 5단계: 외곽선 사각형 추가

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

두 번째 사각형은 페이지 아래쪽에 생성되며, 이번에는 빨간색 3포인트 스트로크를 사용합니다.

## 6단계: 페이지 닫고 문서 저장

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

페이지를 닫으면 그리기가 완료되고 `Save()` 메서드가 PS 파일을 디스크에 기록합니다.

## postscript 문서를 .net에서 만드는 방법은?
`Document`는 Aspose.Page에서 PostScript 파일을 나타내는 주요 클래스입니다. `SaveOptions`는 페이지 크기 및 출력 형식과 같은 설정을 지정합니다. `Document` 객체를 로드하고 A4 페이지용 `SaveOptions`를 구성한 뒤 `SolidBrush` 또는 `Pen`으로 도형을 그린 다음 `document.Save()`를 호출하면 됩니다—전체 워크플로는 몇 줄의 코드로 끝나며 지원되는 모든 .NET 런타임에서 실행됩니다. 이 패턴을 사용하면 원시 PS 구문을 직접 다루지 않고도 완전한 PostScript 파일을 생성할 수 있습니다.

## postscript 파일 생성 방법
Aspose.Page의 `SaveOptions` 클래스를 사용해 출력 형식을 PostScript(`SaveFormat.PS`)로 지정합니다. 라이브러리는 콘텐츠를 파일 또는 메모리 스트림으로 직접 스트리밍하므로 대용량 문서를 메모리 과다 사용 없이 효율적으로 생성할 수 있습니다.

## 일반적인 문제 및 팁

- **잘못된 파일 경로** – `dataDir`이 경로 구분자(`\\` 또는 `/`)로 끝나는지 확인하거나 `Path.Combine`을 사용하세요.  
- **라이선스 누락** – 프로덕션 환경에서는 문서를 만들기 전에 Aspose 라이선스를 적용해 평가 워터마크가 표시되지 않도록 합니다.  
- **색상 가시성** – 사각형이 비어 보이면 브러시 또는 펜 색상이 페이지 배경과 대비되는지 확인하세요.

## 자주 묻는 질문

**Q:** 사각형 색상을 커스터마이즈할 수 있나요?  
**A:** 물론 가능합니다. `SolidBrush`와 `Pen` 생성자에서 `Color.Orange` 또는 `Color.Red` 값을 원하는 `System.Drawing.Color`로 변경하면 됩니다.

**Q:** Aspose.Page가 다른 문서 형식도 지원하나요?  
**A:** 예. PostScript 외에도 XPS 및 EPS 생성도 지원합니다.

**Q:** 같은 문서에 텍스트를 추가하려면 어떻게 하나요?  
**A:** `TextFragment` 클래스를 사용해 원하는 좌표에 텍스트를 배치한 뒤 `document.Draw(textFragment)`를 호출하면 됩니다.

**Q:** 추가 예제와 전체 API 레퍼런스는 어디서 찾을 수 있나요?  
**A:** 문서 [여기](https://reference.aspose.com/page/net/)에서 확인하고, [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)에서 커뮤니티에 참여하세요.

**Q:** 구매 전에 Aspose.Page를 체험해볼 수 있나요?  
**A:** 예, 무료 체험판을 [여기](https://releases.aspose.com/)에서 다운로드하세요. 장기 평가가 필요하면 [임시 라이선스](https://purchase.aspose.com/temporary-license/)를 고려해 보세요.

---

**마지막 업데이트:** 2026-06-30  
**테스트 환경:** Aspose.Page 24.12 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [How to Create PostScript Document with Aspose.Page for .NET](/page/net/document-creation/create-postscript-document/)
- [Add Image to PostScript (PS) Document with Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Add Text to PostScript (PS) Document with Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}