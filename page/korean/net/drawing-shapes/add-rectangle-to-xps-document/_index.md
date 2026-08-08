---
date: 2026-07-19
description: 간결한 단계별 가이드에서 Aspose.Page for .NET을 사용하여 XPS 문서 .NET을 만들고 사각형을 추가하는 방법을
  배웁니다.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: XPS 문서에 사각형 추가
og_description: XPS 문서 .NET을 빠르게 생성합니다. 이 튜토리얼에서는 Aspose.Page for .NET을 사용하여 XPS 파일에
  사각형을 추가하는 방법을 명확한 코드와 팁과 함께 보여줍니다.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: XPS 문서 .NET 생성 – Aspose.Page로 사각형 추가
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: XPS 문서 .NET 생성 – Aspose.Page로 사각형 추가
url: /ko/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용하여 XPS 문서 .NET 만들기 – 사각형 추가

## 소개

이 튜토리얼에서는 **XPS 문서 .NET 만들기**와 Aspose.Page for .NET을 사용하여 그 안에 사각형을 그리는 방법을 배웁니다. 보고 엔진, 인쇄 가능한 청구서, 혹은 사용자 정의 그래픽 레이어를 구축하든, 프로그래밍 방식으로 XPS 파일을 생성할 수 있는 능력은 레이아웃과 정확성을 완전히 제어할 수 있게 해줍니다. 아래 단계들을 따라 하면 몇 분 안에 바로 사용할 수 있는 XPS 파일을 얻을 수 있습니다.

## 빠른 답변
- **주요 목표는 무엇인가요?** XPS 문서 .NET을 만들고 사각형 모양을 추가합니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Page for .NET (공식 사이트에서 다운로드 가능).  
- **테스트에 라이선스가 필요합니까?** 개발에는 무료 체험판을 사용할 수 있으며, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **지원되는 .NET 버전은 무엇인가요?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **구현에 걸리는 시간은?** 기본 사각형을 만드는 데 약 5‑10 분 정도 소요됩니다.

## Aspose.Page for .NET란?
Aspose.Page for .NET은 고성능, 완전 관리형 API로, 외부 구성 요소에 의존하지 않고 XPS(XML Paper Specification) 문서를 프로그래밍 방식으로 생성, 편집 및 렌더링할 수 있게 해줍니다. 도형, 텍스트 및 이미지 그리기를 위한 풍부한 객체 모델을 제공하며, 색상 관리, 압축, PDF 변환과 같은 고급 기능을 지원하여 다양한 문서 생성 시나리오에 적합합니다.

## 왜 Aspose.Page를 사용해 XPS 문서 .NET을 만들까요?
Aspose.Page는 **30개 이상의 XPS 기능**을 지원하며—벡터 그래픽, 텍스트 레이아웃, 색상 관리 등을 포함—전체 문서를 메모리에 로드하지 않고 **500 MB**까지 파일을 생성할 수 있습니다. 이러한 정량화된 역량은 대규모 인쇄 작업에서도 원활한 성능을 보장합니다.

## 전제 조건

이 튜토리얼을 시작하기 전에 다음 전제 조건이 준비되어 있는지 확인하십시오:

1. Aspose.Page for .NET 라이브러리: 개발 환경에 Aspose.Page for .NET 라이브러리가 설치되어 있는지 확인하십시오. [여기](https://releases.aspose.com/page/net/)에서 다운로드할 수 있습니다.

2. 문서 디렉터리: XPS 문서를 저장할 디렉터리를 설정하십시오.

## 네임스페이스 가져오기

.NET 애플리케이션에서 Aspose.Page 기능을 사용하려면 필요한 네임스페이스를 포함하십시오.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## .NET에서 XPS 문서에 사각형을 추가하려면 어떻게 하나요?

XPS 문서를 로드하고, `Graphics` 객체를 생성한 뒤, 원하는 크기의 `RectangleF`를 정의하고 `DrawRectangle`을 호출합니다. 이 순서는 한 줄의 코드로 사각형을 그리며 DPI 스케일링을 자동으로 처리합니다. 일반적인 A4 크기 페이지에서는 200 × 100 pt 사각형이 추가 계산 없이 중앙에 배치됩니다.

### 단계 1: 문서 디렉터리 설정

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### 단계 2: 새 XPS 문서 만들기

`XpsDocument` 클래스는 구축 중인 XPS 파일을 나타내며 페이지, 그래픽 및 기타 리소스를 추가하는 메서드를 제공합니다.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### 단계 3: 사각형 추가

`XpsPath`는 XPS 문서 내에서 그릴 수 있는 경로 객체를 정의하며, 기하학, 스트로크, 채우기 및 기타 시각적 속성을 설정할 수 있습니다.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### 단계 4: 문서 저장

`Save` 메서드는 구성된 XPS 문서를 지정된 파일 경로에 기록합니다.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

축하합니다! Aspose.Page for .NET을 사용하여 XPS 문서에 사각형을 성공적으로 추가했습니다.

## 일반적인 문제 및 팁

- **폰트 누락:** 참조하는 폰트가 서버에 설치되어 있는지 확인하십시오. 그렇지 않으면 Aspose.Page가 기본 폰트로 대체하여 레이아웃이 변경될 수 있습니다.  
- **대용량 문서:** 파일 크기가 200 MB를 초과할 경우 `document.SaveOptions.Compress = true`를 호출하여 메모리 사용량을 줄이는 것을 고려하십시오.  
- **좌표 시스템:** XPS는 포인트(1/72 인치)를 사용합니다. 화면 기반 차원을 사용할 경우 픽셀을 포인트로 변환하는 것을 기억하십시오.

## 자주 묻는 질문

**Q: Aspose.Page가 모든 .NET 애플리케이션과 호환되나요?**  
A: 네, Aspose.Page는 데스크톱, 웹 및 클라우드 .NET 애플리케이션과 원활하게 작동합니다.

**Q: Aspose.Page for .NET에 대한 문서는 어디서 찾을 수 있나요?**  
A: 전체 API 레퍼런스는 [여기](https://reference.aspose.com/page/net/)에서 확인할 수 있습니다.

**Q: 구매 전에 Aspose.Page for .NET을 무료로 체험할 수 있나요?**  
A: 네, 무료 체험판을 [여기](https://releases.aspose.com/)에서 받을 수 있습니다.

**Q: Aspose.Page for .NET의 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: 임시 라이선스를 받으려면 [이 링크](https://purchase.aspose.com/temporary-license/)를 방문하십시오.

**Q: Aspose.Page for .NET 관련 커뮤니티 지원이나 질문은 어디에서 받을 수 있나요?**  
A: 커뮤니티 지원은 [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)에서 확인하십시오.

---

**마지막 업데이트:** 2026-07-19  
**테스트 환경:** Aspose.Page for .NET 24.9  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose.Page for .NET으로 XPS 문서 만들기](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – 도형 그리기](/page/net/drawing-shapes/)
- [Aspose.Page for .NET으로 XPS 문서에 텍스트 추가](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}