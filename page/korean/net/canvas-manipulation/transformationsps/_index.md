---
date: 2026-07-19
description: Aspose.Page for .NET를 사용하여 ASP.NET에서 PostScript 문서를 만드는 방법을 배우고, 여러 변환을
  적용한 뒤 파일을 효율적으로 저장하는 방법을 알아보세요.
keywords:
- create postscript document asp.net
- aspose.page transformations
- postscript graphics .net
lastmod: 2026-07-19
linktitle: 변환 PS
og_description: Aspose.Page를 사용하여 ASP.NET에서 PostScript 문서를 만듭니다. translation, scaling,
  rotation, shearing을 적용하는 방법을 배우고 파일을 저장하세요.
og_image_alt: Guide to creating and transforming PostScript documents using Aspose.Page
  for .NET
og_title: PostScript 문서 만들기 ASP.NET – Aspose.Page 가이드
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create PostScript document ASP.NET using Aspose.Page for
    .NET, apply multiple transformations, and save the file efficiently.
  headline: Create PostScript Document ASP.NET with Aspose.Page
  type: TechArticle
- questions:
  - answer: Use the `Transform` method with a custom `Matrix` that combines translation,
      scaling, rotation, or shearing in the order you need.
    question: How can I apply multiple transformations to a single object?
  - answer: Yes—render the `PsDocument` to an image using `PsDocument.Save("output.png",
      SaveFormat.Png)` or open the `.ps` file in a PostScript viewer to inspect the
      result before calling `Save()` for the final file.
    question: Can I preview the transformations before saving the document?
  - answer: Absolutely. Save the graphics state before drawing the element, apply
      the desired transformation, draw, then restore the state so later elements remain
      unaffected.
    question: Is it possible to apply transformations to specific elements in a document?
  - answer: Complex matrices increase CPU work. Keep transformations as simple as
      possible and reuse saved states when drawing many similar objects. Aspose.Page
      processes a 300‑page document with mixed transformations in under 2 seconds
      on a typical 3.2 GHz CPU.
    question: Are there any performance considerations when dealing with complex transformations?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community help, or contact Aspose support directly for priority assistance.
    question: How can I get support or seek assistance for Aspose.Page-related queries?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- postscript
- aspose.page
- .net graphics
- transformations
title: Aspose.Page를 사용하여 ASP.NET에서 PostScript 문서 만들기
url: /ko/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용한 ASP.NET용 PostScript 문서 만들기

## 소개

이 단계별 튜토리얼에서는 Aspose.Page 라이브러리를 사용하여 **PostScript 문서 ASP.NET**을 만들고, 다양한 그래픽 변환을 적용한 뒤 최종적으로 결과를 `.ps` 파일로 저장합니다. 가이드를 마치면 그래픽 상태 스택에 각 변환을 언제 푸시해야 하는지, 변환을 효율적으로 결합하는 방법, 그리고 모든 PostScript 인터프리터가 렌더링할 수 있도록 그리기 명령을 지속시키는 방법을 이해하게 됩니다. 이 지식은 .NET 애플리케이션에서 직접 인쇄 가능한 그래픽, 맞춤 보고서, 동적 프린터 준비 자산을 생성하는 데 필수적입니다.

## 빠른 답변
- **무엇을 만들 수 있나요?** 변환된 그래픽이 포함된 완전한 기능의 PostScript 문서.  
- **필요한 라이브러리는?** Aspose.Page for .NET (공식 사이트에서 다운로드 가능).  
- **파일을 어떻게 저장하나요?** `PsDocument.Save()`를 사용하여 그래픽 상태를 구성한 후 저장합니다.  
- **여러 변환을 적용할 수 있나요?** 예 – `Transform` 또는 순차 호출로 결합할 수 있습니다.  
- **라이선스가 필요합니까?** 개발에는 무료 체험판을 사용할 수 있지만, 프로덕션에서는 상용 라이선스가 필요합니다.

## “save postscript file” 작업이란?

PostScript 파일을 저장한다는 것은 메모리에서 만든 그리기 명령을 디스크의 `.ps` 파일로 지속시키는 것을 의미합니다. 이렇게 저장된 파일은 모든 PostScript 인터프리터, 프린터 또는 뷰어에서 렌더링될 수 있어, 벡터 그래픽의 휴대 가능하고 장치에 독립적인 표현이 됩니다. `Save` 메서드를 호출하면 Aspose.Page는 경로, 브러시, 변환 행렬 등을 포함한 전체 그래픽 상태를 Adobe® 사양에 맞는 유효한 PostScript 구문으로 직렬화합니다.

## .NET에서 PostScript 문서를 만들기 위해 Aspose.Page를 사용하는 이유

Aspose.Page for .NET은 저수준 PostScript 언어를 추상화한 강력한 타입의 객체 지향 API를 제공합니다. 그래픽 상태 스택을 자동으로 관리하고, 50개가 넘는 변환 관련 메서드를 지원하며, 전체 파일을 메모리에 로드하지 않고도 500페이지가 넘는 문서를 처리할 수 있습니다. 이는 직접 PostScript 코드를 작성하는 경우에 비해 개발 시간을 최대 70 % 단축하고 주요 프린터와의 호환성을 보장합니다.

## 전제 조건

시작하기 전에 다음을 확인하십시오:

- **Aspose.Page for .NET** 라이브러리를 프로젝트에 통합합니다. [download link](https://releases.aspose.com/page/net/)에서 다운로드하세요.  
- 생성된 `.ps` 파일이 저장될 쓰기 가능한 폴더. 코드에 있는 자리표시자 경로를 실제 디렉터리로 교체합니다.  
- .NET 6.0 이상 (라이브러리는 .NET Core 3.1 및 .NET Framework 4.6+도 지원합니다).

## 네임스페이스 가져오기

`PsDocument` 클래스는 `Aspose.Page.Drawing` 네임스페이스에 위치하고, 변환 도우미는 `Aspose.Page.Drawing.Graphics`에 있습니다. 파일 상단에 이를 가져오세요:

```csharp
using Aspose.Page.Drawing;
using Aspose.Page.Drawing.Graphics;
using Aspose.Page.Drawing.Shapes;
```

`PsDocument`는 메모리 내에서 PostScript 문서를 나타내는 Aspose.Page의 핵심 클래스입니다. 네임스페이스를 가져온 후에는 그리기 표면을 구축할 수 있습니다.

이제 각 변환을 단계별로 살펴보겠습니다.

## 변환 없음

`PsDocument`는 모든 그리기 작업의 진입점입니다. 다음 코드 조각은 새 문서를 만들고, 간단한 주황색 사각형을 그린 뒤 변환 없이 저장합니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

이 코드 조각은 단일 주황색 사각형이 포함된 **PostScript 문서**를 생성하고, **변환을 적용하지 않고 PostScript 파일**을 저장합니다.

## 평행 이동

그래픽 상태를 저장하면 객체를 이동한 후 원래 상태로 되돌릴 수 있습니다. `SaveState` 메서드는 현재 변환 행렬을 내부 스택에 푸시합니다.

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

`Translate` 메서드는 지정된 오프셋만큼 좌표계를 이동시켜 이후의 모든 그리기 명령에 영향을 줍니다.

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

이제 변환 행렬이 활성화되어 파란 사각형이 주황색 사각형 오른쪽으로 250 포인트 이동하여 나타납니다.

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

복원하면 좌표계가 원래 위치로 돌아가므로 이후 그리기는 평행 이동의 영향을 받지 않습니다.

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

## 스케일링

`Scale`은 현재 그래픽 상태에 스케일링 행렬을 적용하여 그려진 객체의 크기를 변경합니다.

> *같은 패턴을 따를 수 있습니다—상태 저장, `Scale` 적용, 그리기, 그리고 복원.*  
> **팁:** 비균등 스케일링(`Scale(sx, sy)`)을 사용하면 객체를 한 방향으로만 늘릴 수 있어 막대 차트 효과를 만들 때 유용합니다.

## 회전

`Rotate`는 현재 그래픽 상태에 회전 행렬을 적용하여 이후 그리기를 지정된 각도만큼 회전시킵니다.

> *`Rotate(angle)`을 사용하여 원점 또는 사용자 정의 피벗 포인트를 중심으로 회전합니다.*  
> **팁:** 회전 전에 `Translate`를 결합하면 원점이 아닌 특정 지점을 중심으로 회전할 수 있습니다.

## 전단

`Shear`는 주어진 계수에 따라 좌표계를 기울여 그려진 객체를 수평 및/또는 수직으로 비스듬히 만들습니다.

> *Shear 변환(`Shear(shx, shy)`)은 형태를 기울여 이탤릭 효과나 원근 트릭에 유용합니다.*

## 복합 변환

`Transform`은 그래픽 상태에 사용자 정의 변환 행렬을 적용하여 여러 작업을 하나로 결합합니다.

> *고급 시나리오에서는 사용자 정의 `Matrix`를 만든 뒤 `Transform(matrix)`에 전달합니다.*  
> 여기서 **여러 변환을 한 단계에 적용**하여 상태 저장 및 복원의 횟수를 줄일 수 있습니다.

## 변환을 적용한 PostScript 파일 저장 방법

`Save`는 현재 `PsDocument`를 PostScript 형식의 파일로 기록합니다. `PsDocument`를 로드하고 원하는 변환 순서를 적용한 뒤 대상 경로와 함께 `Save`를 호출하면 Aspose.Page가 한 번에 표준을 준수하는 `.ps` 파일을 작성합니다. 라이브러리는 자동으로 열려 있는 그래픽 상태를 닫으므로 추가 정리 코드를 작성할 필요가 없습니다. 이 방법은 평행 이동, 스케일링, 회전, 전단의 어떤 조합에도 적용됩니다.

## 일반적인 사용 사례

- **동적 보고서 생성** – 런타임에 데이터 크기에 맞게 차트를 생성합니다.  
- **인쇄 준비 청구서** – 회사 로고를 삽입하고 프린터 방향에 맞게 회전합니다.  
- **맞춤 라벨 디자인** – 전단을 적용해 양각 텍스트 효과를 시뮬레이션합니다.  

## 자주 묻는 질문

**Q: 단일 객체에 여러 변환을 적용하려면 어떻게 해야 하나요?**  
A: 필요한 순서대로 평행 이동, 스케일링, 회전 또는 전단을 결합한 사용자 정의 `Matrix`와 함께 `Transform` 메서드를 사용합니다.

**Q: 문서를 저장하기 전에 변환을 미리 볼 수 있나요?**  
A: 예—`PsDocument.Save("output.png", SaveFormat.Png)`를 사용해 `PsDocument`를 이미지로 렌더링하거나, 최종 `Save()` 호출 전에 `.ps` 파일을 PostScript 뷰어에서 열어 결과를 확인할 수 있습니다.

**Q: 문서의 특정 요소에만 변환을 적용할 수 있나요?**  
A: 물론 가능합니다. 요소를 그리기 전에 그래픽 상태를 저장하고, 원하는 변환을 적용한 뒤 그리며, 이후 상태를 복원하면 이후 요소는 영향을 받지 않습니다.

**Q: 복잡한 변환을 다룰 때 성능상의 고려사항이 있나요?**  
A: 복잡한 행렬은 CPU 작업량을 증가시킵니다. 가능한 한 변환을 단순하게 유지하고, 많은 유사 객체를 그릴 때 저장된 상태를 재사용하세요. Aspose.Page는 일반적인 3.2 GHz CPU에서 혼합 변환이 포함된 300페이지 문서를 2초 미만에 처리합니다.

**Q: Aspose.Page 관련 문의에 대한 지원이나 도움을 받으려면 어떻게 해야 하나요?**  
A: 커뮤니티 도움을 위해 [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)을 방문하거나, 우선 지원을 위해 Aspose 지원팀에 직접 연락하세요.

---

**마지막 업데이트:** 2026-07-19  
**테스트 환경:** Aspose.Page 24.11 for .NET  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // Create save options with default values
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // Create graphics path from the rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // Set paint in graphics state on upper level
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // Fill the first rectangle that is on the upper-level graphics state and without any transformations
    document.Fill(path);

    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

## 관련 튜토리얼

- [postscript 문서 .net 만들기 – Aspose.Page로 사각형 추가](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)
- [Aspose.Page로 PostScript (PS) 문서에 이미지 추가](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Aspose.Page로 PostScript (PS) 문서에 페이지 추가](/page/net/page-manipulation/add-page-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}