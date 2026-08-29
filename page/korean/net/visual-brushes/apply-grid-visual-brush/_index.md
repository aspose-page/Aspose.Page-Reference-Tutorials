---
date: 2026-04-03
description: Aspose.Page를 사용하여 .NET에서 투명 사각형을 추가하고 Grid Visual Brush를 적용하는 방법을 배워
  멋진 XPS 문서를 만들세요.
keywords:
- add transparent rectangle
- grid visual brush
- Aspose.Page .NET
linktitle: 그리드 비주얼 브러시 적용
second_title: Aspose.Page .NET API
title: 그리드 비주얼 브러시(.NET)를 사용해 투명 사각형 추가
url: /ko/net/visual-brushes/apply-grid-visual-brush/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 그리드 비주얼 브러시(.NET)를 사용하여 투명 사각형 추가

## 소개

XPS 문서에 **투명 사각형**을 추가하고 스타일리시한 그리드 비주얼 브러시를 적용하고 싶다면, 바로 이곳이 정답입니다. 이 튜토리얼에서는 Aspose.Page for .NET을 사용해 필요한 정확한 단계를 차근차근 안내하므로, 시각적으로 풍부한 문서를 손쉽게 만들 수 있습니다. 끝까지 따라오면 두 기술을 하나의 간단한 워크플로우로 구현한 완전한 실행 예제를 얻을 수 있습니다.

## 빠른 답변
- **투명 사각형은 무엇을 하나요?** 배경 콘텐츠가 비쳐 보이도록 반투명 오버레이를 추가합니다.  
- **어떤 API가 브러시를 생성하나요?** `XpsDocument.CreateVisualBrush`가 그리드 비주얼 브러시를 만듭니다.  
- **라이선스가 필요합니까?** 테스트용 무료 체험판을 사용할 수 있으며, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5 이상, .NET Core 3.1 이상, .NET 5/6 이상.  
- **구현에 걸리는 시간은?** 기본 예제는 약 10‑15분 정도 소요됩니다.

## XPS에서 투명 사각형이란?
투명 사각형은 채우기 색상의 알파 값이 1.0보다 작은 형태로, 배경 그래픽이 부분적으로 보이게 합니다. 배경을 완전히 가리지 않으면서 섹션을 강조하는 데 이상적입니다.

## 그리드 비주얼 브러시를 사용하는 이유는?
그리드 비주얼 브러시는 작은 벡터 그래픽을 넓은 영역에 타일링하여 격자, 해치 또는 사용자 정의 텍스처와 같은 패턴을 만들 수 있게 해줍니다. 이를 투명 사각형과 결합하면 가볍고 해상도에 독립적인 레이어드 시각 효과를 얻을 수 있습니다.

## 전제 조건

코드를 진행하기 전에 다음을 준비하세요:

- **Aspose.Page for .NET** – [여기](https://releases.aspose.com/page/net/)에서 다운로드할 수 있습니다.  
- .NET 개발 환경 (Visual Studio, VS Code 또는 선호하는 IDE).  
- 생성된 XPS 파일을 저장할 폴더.

## 네임스페이스 가져오기

C# 파일에서 필요한 네임스페이스를 가져옵니다:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

이제 솔루션을 명확한 번호 단계로 나누어 보겠습니다.

## 1단계: XpsDocument 초기화

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

`XpsDocument` 인스턴스를 생성하여 이후 모든 그리기 작업을 수행할 수 있게 합니다.

## 2단계: 마젠타 그리드 기하학 생성

```csharp
// ExStart:4
XpsPathGeometry pathGeometry = doc.CreatePathGeometry();
pathGeometry.AddSegment(doc.CreatePolyLineSegment(
    new PointF[] { new PointF(240f, 5f), new PointF(240f, 310f), new PointF(0f, 310f) }));
pathGeometry[0].StartPoint = new PointF(0f, 5f);
// ExEnd:4
```

이 기하학은 비주얼 브러시가 채울 그리드의 외곽선을 정의합니다.

## 3단계: 마젠타 그리드 VisualBrush 디자인

```csharp
// ExStart:5
XpsCanvas visualCanvas = doc.CreateCanvas();
XpsPath visualPath = visualCanvas.AddPath(
    doc.CreatePathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1f, .61f, 0.1f, 0.61f));
// ExEnd:5
```

작은 마젠타 타일을 그려서 그리드 전체에 반복하도록 합니다.

## 4단계: 그리드에 VisualBrush 적용

```csharp
// ExStart:6
XpsPath gridPath = doc.CreatePath(pathGeometry);
gridPath.Fill = doc.CreateVisualBrush(visualCanvas,
    new RectangleF(0f, 0f, 10f, 10f), new RectangleF(0f, 0f, 10f, 10f));
((XpsVisualBrush)gridPath.Fill).TileMode = XpsTileMode.Tile;
// ExEnd:6
```

`CreateVisualBrush` 호출을 통해 마젠타 타일을 그리드 기하학에 연결하고 타일링을 활성화합니다.

## 5단계: 캔버스에 그리드 추가

```csharp
// ExStart:7
XpsCanvas canvas = doc.AddCanvas();
canvas.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 268f, 70f);
canvas.AddPath(pathGeometry);
// ExEnd:7
```

타일링된 그리드를 캔버스에 배치하고 원하는 위치에 나타나도록 변환을 적용합니다.

## 6단계: 투명 사각형 추가

```csharp
// ExStart:8
XpsPath path = canvas.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = canvas.AddPath(doc.CreatePathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.Fill = doc.CreateSolidColorBrush(doc.CreateColor(1.0f, 0.0f, 0.0f));
path.Opacity = 0.7f; // This opacity makes the rectangle transparent
// ExEnd:8
```

이 단계에서는 **투명 사각형**(예: `Opacity = 0.7f`인 빨간 도형)을 추가합니다. `Opacity` 값을 조정해 사각형의 투명도를 제어하세요.

## 7단계: 문서 저장

```csharp
// ExStart:9
doc.Save(dataDir + "AddGrid_out.xps");
// ExEnd:9
```

지정한 폴더에 XPS 파일이 기록됩니다.

## 일반 사용 사례

- **보고서 강조:** 차트나 표를 강조하기 위해 반투명 사각형을 오버레이합니다.  
- **워터마크 효과:** 타일형 그리드와 투명 오버레이를 결합해 은은한 브랜드 표시를 만듭니다.  
- **인터랙티브 PDF/XPS:** 패턴을 폼 필드 배경으로 사용하면서 UI 가독성을 유지합니다.

## 문제 해결 팁

- **불투명도가 보이지 않나요?** 뷰어가 XPS 투명성을 지원하는지 확인하세요; 일부 오래된 뷰어는 `Opacity` 속성을 무시할 수 있습니다.  
- **타일 크기가 잘못되었나요?** 소스 사각형(`new RectangleF(0f, 0f, 10f, 10f)`)이 벡터 타일의 차원과 일치하는지 확인하세요.  
- **파일이 저장되지 않나요?** `dataDir`이 존재하고 쓰기 가능한 디렉터리를 가리키는지 다시 확인하세요.

## 자주 묻는 질문

**Q: Aspose.Page for .NET을 웹과 데스크톱 애플리케이션 모두에서 사용할 수 있나요?**  
A: 예, 이 라이브러리는 모든 .NET 애플리케이션 유형에서 작동합니다.

**Q: 구매 전에 체험판 버전을 사용할 수 있나요?**  
A: 물론입니다. 무료 체험판은 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.

**Q: 추가 지원이나 커뮤니티 토론을 어디서 찾을 수 있나요?**  
A: 커뮤니티와 Aspose 엔지니어의 도움을 받으려면 [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)을 방문하세요.

**Q: 평가용 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: 임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 획득할 수 있습니다.

**Q: Aspose.Page for .NET에 대한 다른 문서는 어디서 확인할 수 있나요?**  
A: 포괄적인 문서는 [여기](https://reference.aspose.com/page/net/)에서 확인하세요.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}