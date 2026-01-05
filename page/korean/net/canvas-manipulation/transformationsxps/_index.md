---
date: 2026-01-05
description: Aspose.Page for .NET를 사용하여 XPS 문서를 손쉽게 변환하는 방법을 배워보세요. 원활한 변환을 위한 단계별
  가이드를 따라가세요.
linktitle: Transformations XPS
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET를 사용하여 XPS 변환하는 방법
url: /ko/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET으로 XPS 변환하기

## 소개

Aspose.Page for .NET의 세계에 오신 것을 환영합니다. 이 강력한 라이브러리를 사용하면 XPS 문서를 손쉽게 다양한 방식으로 변환할 수 있습니다. **이 튜토리얼에서는 Aspose.Page for .NET을 사용해 XPS 문서를 변환하는 방법을 알아봅니다**. 숙련된 개발자든 이제 시작하는 개발자든 관계없이 단계별로 진행하면서 각 변환의 이유를 설명하고 실제 프로젝트에 적용할 수 있는 실용적인 팁을 제공합니다.

## 빠른 답변
- **무엇을 할 수 있나요?** XPS 캔버스 요소를 프로그래밍 방식으로 생성, 이동, 확대/축소, 회전할 수 있습니다.  
- **필요한 라이브러리는?** Aspose.Page for .NET (최신 버전).  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **지원 플랫폼?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **구현 소요 시간?** 여기서 보여주는 기본 변환은 약 10‑15분 정도 걸립니다.

## “how to transform xps”란?
*how to transform xps* 라는 표현은 XPS(XML Paper Specification) 문서 내부 요소의 레이아웃, 크기, 방향을 프로그래밍 방식으로 수정하는 것을 의미합니다. Aspose.Page를 사용하면 매트릭스 기반 변환을 캔버스에 적용하여 위치 지정, 스케일링, 회전을 세밀하게 제어할 수 있으며, XPS XML을 직접 편집할 필요가 없습니다.

## XPS 변환에 Aspose.Page를 사용하는 이유
- **완전한 .NET 통합** – Visual Studio, Rider 등 주요 IDE와 원활히 작동합니다.  
- **외부 종속성 없음** – API가 모든 저수준 XPS 처리를 대신합니다.  
- **다양한 변환 지원** – 이동, 확대/축소, 회전 및 여러 변환을 한 번에 결합할 수 있습니다.  
- **성능 최적화** – 실시간으로 보고서, 청구서 또는 인쇄용 그래픽을 생성하는 데 적합합니다.

## 사전 준비

시작하기 전에 다음을 준비하세요:

- **Aspose.Page for .NET 라이브러리** – 공식 문서에서 다운로드 및 설치: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).  
- **개발 환경** – Visual Studio, Visual Studio Code 또는 기타 .NET 호환 IDE.  
- **문서 디렉터리** – XPS 파일을 읽고 쓸 폴더. 코드에 있는 플레이스홀더를 실제 경로로 교체하세요.

준비가 끝났다면 코드로 들어가 보겠습니다.

## 네임스페이스 가져오기

Aspose.Page 클래스에 접근하기 위해 필요한 네임스페이스를 먼저 가져옵니다:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## XPS 변환 – 단계별 가이드

### 단계 1: 새 XPS 문서 만들기

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*설명*: 소스와 출력 파일이 위치한 폴더를 정의하고, 빈 `XpsDocument`를 인스턴스화합니다. 이 객체가 이후 모든 변환의 캔버스 역할을 합니다.

### 단계 2: 메인 캔버스 만들기

```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*왜 중요한가*: 메인 캔버스는 다른 모든 캔버스의 컨테이너 역할을 합니다. 작은 오프셋을 적용해 페이지 가장자리에서 내용이 잘리지 않도록 합니다.

### 단계 3: 사각형 경로 기하학 만들기

```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*팁*: 경로 문자열은 표준 XPS 경로 구문(`M` 이동, `L` 선, `Z` 닫기)을 따릅니다. 좌표를 조정해 사각형 크기를 변경할 수 있습니다.

### 단계 4: 사각형 채우기 추가

```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*전문가 팁*: `CreateColor`에 RGB 값을 지정해 브랜드 색상 팔레트를 적용하세요.

### 단계 5: 변환 없이 새 캔버스 추가

```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

여기서는 추가 변환 없이 사각형을 페이지에 배치합니다—기준 요소로 활용하기 좋습니다.

### 단계 6: 이동 변환이 적용된 새 캔버스 추가

```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*무슨 일이 일어나나요?* 첫 번째 매트릭스는 사각형을 아래로 200 단위 이동시킵니다. 이어지는 `Translate` 호출은 오른쪽으로 500 단위 이동시켜, 여러 이동을 체인처럼 연결하는 방법을 보여줍니다.

### 단계 7: 두 배 확대 변환이 적용된 새 캔버스 추가

```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*왜 확대하나요?* 스케일을 2배로 지정하면 사각형의 가로·세로가 두 배가 되어, 기하학을 다시 정의하지 않고도 큰 그래픽을 만들 수 있습니다.

### 단계 8: 특정 지점을 기준으로 회전 변환이 적용된 새 캔버스 추가

```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*핵심 인사이트*: `RotateAround`는 캔버스를 사용자 정의 기준점(여기서는 (100, 50))을 중심으로 회전시켜, 회전 앵커를 세밀하게 제어할 수 있게 합니다.

### 단계 9: 결과 XPS 문서 저장

```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

모든 변환이 적용된 후 문서는 `output1.xps`에 저장됩니다. XPS 뷰어에서 파일을 열어 각각의 이동, 확대/축소, 회전이 적용된 사각형이 겹쳐진 모습을 확인하세요.

## 일반적인 문제 및 해결 방법

| 증상 | 가능 원인 | 해결 방법 |
|------|-----------|-----------|
| 출력 파일이 비어 있음 | `dataDir`가 존재하지 않는 폴더를 가리킴 | 디렉터리가 존재하는지 확인하거나 절대 경로를 사용 |
| 사각형 위치가 예상과 다름 | 매트릭스 값 오류 | `Translate`, `Scale`, `RotateAround` 호출 순서를 다시 확인 |
| 색상이 잘못 표시됨 | RGB 값이 0‑255 범위를 벗어남 | 각 채널에 유효한 바이트 값을 사용 |

## 자주 묻는 질문

**Q: Aspose.Page for .NET은 모든 .NET 개발 환경과 호환되나요?**  
A: 네, Visual Studio, Visual Studio Code, Rider 등 .NET을 지원하는 모든 IDE와 원활히 작동합니다.

**Q: 추가 예제와 상세 API 문서는 어디서 찾을 수 있나요?**  
A: 공식 문서에서 확인할 수 있습니다: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

**Q: 라이선스를 구매하기 전에 Aspose.Page를 체험해볼 수 있나요?**  
A: 물론입니다. 무료 체험판은 여기에서 제공됩니다: [Aspose.Page Free Trial](https://releases.aspose.com/).

**Q: 테스트용 임시 라이선스는 어떻게 얻나요?**  
A: 임시 라이선스 페이지에서 요청할 수 있습니다: [Temporary License](https://purchase.aspose.com/temporary-license/).

**Q: 정식 라이선스는 어디서 구매하나요?**  
A: Aspose 스토어에서 직접 구매하세요: [Aspose.Page Buy](https://purchase.aspose.com/buy).

---

**마지막 업데이트:** 2026-01-05  
**테스트 환경:** Aspose.Page 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}