---
date: 2026-01-12
description: Aspose.Page for .NET를 사용하여 PostScript 파일을 저장하고 PostScript 문서를 만드는 방법을
  배우고, 동적 그래픽을 위해 여러 변환을 적용하십시오.
linktitle: Transformations PS
second_title: Aspose.Page .NET API
title: Aspose.Page 변환(.NET)으로 PostScript 파일 저장
url: /ko/net/canvas-manipulation/transformationsps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page 변환(.NET)으로 PostScript 파일 저장

## 소개

이 튜토리얼에서는 Aspose.Page for .NET을 사용하면서 **PostScript 파일을 저장**하는 방법을 알아봅니다. PostScript 문서를 생성하고, 이동, 스케일링, 회전 및 전단과 같은 여러 변환을 적용한 뒤 최종적으로 저장하는 과정을 단계별로 진행합니다. 튜토리얼을 마치면 프로그래밍으로 동적 그래픽을 만들고, 그래픽 상태에서 각 변환을 어디에 배치해야 하는지 정확히 이해하게 됩니다.

## 빠른 답변
- **What can I create?** 변환된 그래픽이 포함된 완전한 PostScript 문서를 만들 수 있습니다.  
- **Which library is required?** Aspose.Page for .NET(공식 사이트에서 다운로드 가능).  
- **How do I save the file?** 그래픽 상태를 구성한 후 `PsDocument.Save()`를 사용합니다.  
- **Can I apply multiple transformations?** 예 – `Transform` 또는 순차 호출로 결합할 수 있습니다.  
- **Is a license needed?** 개발에는 무료 체험판을 사용할 수 있으며, 제품에서는 상용 라이선스가 필요합니다.

## “PostScript 파일 저장” 작업이란 무엇인가요?

PostScript 파일을 저장한다는 것은 메모리에서 만든 그리기 명령을 디스크의 `.ps` 파일로 영구 저장하는 것을 의미합니다. 저장된 파일은 어떤 PostScript 인터프리터, 프린터 또는 뷰어에서도 렌더링할 수 있습니다.

## 왜 Aspose.Page for .NET을 사용해 PostScript 문서를 만들까요?

Aspose.Page는 저수준 PostScript 구문을 추상화하는 고수준, 장치 독립 API를 제공합니다. 다음과 같은 이점을 얻을 수 있습니다.

- 경로, 브러시 및 변환을 위한 강력한 C# 객체.  
- 그래픽 상태 스택(저장/복원)의 자동 처리.  
- 수동 계산 없이 복잡한 변환 행렬을 완벽히 지원.  

## 전제 조건

시작하기 전에 다음이 준비되어 있는지 확인하세요.

- **Aspose.Page for .NET** 라이브러리를 프로젝트에 통합합니다. [download link](https://releases.aspose.com/page/net/)에서 다운로드하세요.  
- 생성된 `.ps` 파일이 저장될 쓰기 가능한 폴더. 코드의 자리표시자 경로를 실제 디렉터리로 교체하세요.

## 네임스페이스 가져오기

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

이제 각 변환을 단계별로 살펴보겠습니다.

## 변환 없음

### 1단계: 출력 스트림 생성

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

이 스니펫은 단일 주황색 사각형이 포함된 **PostScript 문서**를 생성하고, 변환을 적용하지 않은 채 **PostScript 파일을 저장**합니다.

## 이동(Translation)

### 1단계: 그래픽 상태 저장

```csharp
// Save graphics state to return back to this state after transformation
document.WriteGraphicsSave();
```

그래픽 상태를 저장하면 객체를 이동한 후 원래 상태로 되돌릴 수 있습니다.

### 2단계: 그래픽 상태 이동

```csharp
// Displace current graphics state 250 to the right
document.Translate(250, 0);
```

이 호출 이후에 그려지는 모든 것이 오른쪽으로 250 단위 이동합니다.

### 3단계: 이동 변환으로 사각형 채우기

```csharp
// Set paint in the current graphics state
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// Fill the second rectangle in the current graphics state (has translation transformation)
document.Fill(path);
```

이제 파란 사각형이 주황색 사각형 오른쪽으로 250 포인트에 나타납니다.

### 4단계: 그래픽 상태 복원

```csharp
// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

복원하면 좌표계가 원래 위치로 돌아가므로 이후 그리기는 이동의 영향을 받지 않습니다.

## 스케일링

> *같은 패턴을 따를 수 있습니다—상태 저장, `Scale` 적용, 그리기, 복원.*  
> **Pro tip:** 한 방향으로만 객체를 늘리려면 비균등 스케일링(`Scale(sx, sy)`)을 사용하세요.

## 회전

> *`Rotate(angle)`을 사용해 원점이나 사용자 지정 기준점 주위로 회전합니다.*  
> **Pro tip:** 회전 전에 `Translate`를 결합하면 특정 점을 중심으로 회전할 수 있습니다.

## 전단(Shearing)

> *전단 변환(`Shear(shx, shy)`)은 형태를 기울여 이탤릭 효과 등에 유용합니다.*

## 복합 변환

> *고급 시나리오에서는 사용자 정의 `Matrix`를 구축하고 `Transform(matrix)`에 전달합니다.*  
> 여기서 **여러 변환을 한 단계에 적용**합니다.

## 결론

Aspose.Page for .NET을 사용해 **PostScript 파일 저장**, **PostScript 문서 생성**, **여러 변환 적용** 방법을 배웠습니다. 다양한 변환 순서를 실험하고 결합하여 그래픽이 어떻게 변하는지 확인해 보세요.

## 자주 묻는 질문

**Q: 단일 객체에 여러 변환을 적용하려면 어떻게 해야 하나요?**  
A: 필요한 순서대로 변환, 스케일링, 회전 또는 전단을 결합한 사용자 정의 `Matrix`와 함께 `Transform` 메서드를 사용합니다.

**Q: 문서를 저장하기 전에 변환을 미리 볼 수 있나요?**  
A: 예—`PsDocument`를 이미지로 렌더링하거나 PostScript 뷰어를 사용해 `Save()` 호출 전에 출력물을 검사할 수 있습니다.

**Q: 문서의 특정 요소에 변환을 적용할 수 있나요?**  
A: 물론입니다. 요소를 그리기 전에 그래픽 상태를 저장하고, 원하는 변환을 적용한 뒤 그리기, 마지막에 상태를 복원합니다.

**Q: 복잡한 변환을 다룰 때 성능상의 고려사항이 있나요?**  
A: 복잡한 행렬은 CPU 작업을 증가시킵니다. 가능한 한 변환을 단순하게 유지하고, 많은 유사 객체를 그릴 때는 저장된 상태를 재사용하세요.

**Q: Aspose.Page 관련 문의에 대한 지원이나 도움을 어떻게 받을 수 있나요?**  
A: 커뮤니티 도움을 위해 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 를 방문하거나 Aspose 지원팀에 직접 연락하세요.

---  

**마지막 업데이트:** 2026-01-12  
**테스트 환경:** Aspose.Page 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}