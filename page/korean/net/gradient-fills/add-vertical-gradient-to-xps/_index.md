---
date: 2026-02-25
description: Aspose.Page for .NET를 사용하여 XPS 문서를 만들고 선형 그라디언트를 적용하는 방법을 배워보세요. XPS
  파일을 저장하는 단계별 가이드를 따라하세요.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Aspose.Page를 사용하여 수직 그라디언트가 적용된 XPS 문서 만들기
url: /ko/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS에 수직 그라디언트 추가 - Aspose.Page for .NET 사용

## 소개

이 튜토리얼에서는 **수직 그라디언트가 적용된 XPS 문서**를 **생성**합니다. 그라디언트를 추가하면 XPS 파일을 보다 전문적으로 보이게 할 수 있어 보고서, 브로셔 또는 인쇄용 그래픽에 적합합니다. 프로젝트 설정부터 최종 XPS 파일 저장까지 모든 단계를 자세히 안내하므로, 언제든지 경로에 선형 그라디언트를 빠르게 적용할 수 있습니다.

## 빠른 답변
- **이 튜토리얼은 무엇을 다루나요?** XPS 문서의 경로에 수직 선형 그라디언트를 추가합니다.  
- **필요한 라이브러리는?** Aspose.Page for .NET.  
- **라이선스가 필요합니까?** 개발에는 무료 체험판을 사용할 수 있으며, 상용 환경에서는 상업용 라이선스가 필요합니다.  
- **구현 시간은 얼마나 걸리나요?** 기본 예제는 약 10‑15분 정도 소요됩니다.  
- **결과를 XPS 파일로 저장할 수 있나요?** 예, `Save` 메서드가 파일을 디스크에 기록합니다.

## XPS에서 수직 그라디언트란?

수직 그라디언트는 형태의 위쪽에서 아래쪽으로 색상이 변하는 전환을 의미합니다. XPS에서는 **선형 그라디언트 브러시**를 사용해 시작점과 끝점을 정의하고, 특정 위치에서 색상을 지정하는 그라디언트 스톱 컬렉션을 함께 지정함으로써 구현합니다.

## 왜 Aspose.Page를 사용해 그라디언트가 포함된 XPS 문서를 만들까요?

- **전체 .NET 통합** – .NET Framework, .NET Core, .NET 5/6+와 함께 작동합니다.  
- **외부 종속성 없음** – 모든 렌더링이 라이브러리에서 처리됩니다.  
- **고충실도** – 그라디언트가 정의된 대로 정확히 렌더링되어 XPS 사양과 일치합니다.  
- **유지보수 용이** – 경로, 브러시, 색상에 대한 명확한 객체 모델을 제공합니다.

## 필수 조건

- Aspose.Page for .NET 라이브러리: 개발 환경에 Aspose.Page for .NET 라이브러리가 설치되어 있는지 확인하십시오. [여기](https://releases.aspose.com/page/net/)에서 다운로드할 수 있습니다.  
- 개발 환경: Visual Studio와 같은 선호하는 IDE를 사용해 .NET 개발 환경을 설정하십시오.

이제 준비가 모두 끝났으니, 코드로 들어가 보겠습니다.

## 네임스페이스 가져오기

.NET 애플리케이션에서 Aspose.Page 클래스와 메서드에 접근하기 위해 필요한 네임스페이스를 포함합니다.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## 1단계: 문서 디렉터리 설정

생성된 XPS 파일이 저장될 폴더를 정의합니다.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## 2단계: 새 XPS 문서 만들기

나중에 그라디언트가 채워진 경로를 추가할 새 XPS 문서를 인스턴스화합니다.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## 3단계: 그라디언트 스톱 정의

그라디언트 스톱은 색상과 그라디언트 라인상의 위치를 결정합니다. 여기서는 부드러운 수직 전환을 만들기 위해 다섯 개의 스톱을 생성합니다.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## 4단계: 그라디언트가 적용된 경로 만들기

사각형 형태의 경로를 그린 뒤, 점 (10, 110)에서 점 (10, 200)까지 수직으로 흐르는 **선형 그라디언트 브러시**를 적용합니다. 브러시는 앞서 정의한 그라디언트 스톱을 받습니다.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## 5단계: 결과 XPS 문서 저장

마지막으로 XPS 문서를 디스크에 기록합니다. 이 **XPS 파일 저장** 단계는 지정한 폴더에 `AddVerticalGradient_outXPS.xps` 파일을 생성합니다.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**팁:** Windows XPS Viewer 또는 기타 뷰어에서 XPS 파일을 열어 그라디언트가 정상적으로 표시되는지 확인하십시오.

## 일반적인 문제 및 해결 방법

| 증상 | 가능한 원인 | 해결 방법 |
|---------|--------------|-----|
| 그라디언트가 단색으로 표시됨 | 그라디언트 스톱이 브러시에 추가되지 않음 | `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);`가 실행되었는지 확인하십시오. |
| 저장 시 파일을 찾을 수 없음 | `dataDir`이 존재하지 않는 폴더를 가리킴 | 먼저 디렉터리를 생성하거나 절대 경로를 사용하십시오. |
| 색상이 다르게 보임 | 색상 값이 ARGB 순서로 지정됨; 채널 순서를 확인하십시오 | `CreateColor(alpha, red, green, blue)`를 올바르게 사용하십시오. |

## 자주 묻는 질문

**Q: Aspose.Page가 Visual Studio 2019와 호환되나요?**  
A: 예, Aspose.Page는 Visual Studio 2019와 호환됩니다. 올바른 버전의 라이브러리가 설치되어 있는지 확인하십시오.

**Q: Aspose.Page를 상업 프로젝트에 사용할 수 있나요?**  
A: 예, Aspose.Page는 상업 프로젝트에 사용할 수 있습니다. 라이선스 옵션을 확인하려면 [여기](https://purchase.aspose.com/buy)를 방문하십시오.

**Q: 무료 체험판을 이용할 수 있나요?**  
A: 예, Aspose.Page 무료 체험판을 [여기](https://releases.aspose.com/)에서 받을 수 있습니다.

**Q: Aspose.Page 문서는 어디에서 찾을 수 있나요?**  
A: 문서는 [여기](https://reference.aspose.com/page/net/)에서 확인할 수 있습니다.

**Q: 지원을 받거나 질문을 할 수 있는 방법은?**  
A: 커뮤니티 지원을 위해 [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)을 방문하십시오.

## 결론

이제 Aspose.Page for .NET을 사용해 **XPS 문서를 생성**, **선형 그라디언트를 적용**, 그리고 **XPS 파일을 저장**하는 방법을 알게 되었습니다. 이 접근 방식은 XPS 출력물의 시각적 스타일을 완전히 제어할 수 있게 해 주어 인쇄용 문서를 돋보이게 합니다.

---  

**마지막 업데이트:** 2026-02-25  
**테스트 환경:** Aspose.Page for .NET 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}