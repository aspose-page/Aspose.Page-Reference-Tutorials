---
title: .NET용 Aspose.Page를 사용하여 XPS 문서에 이미지 추가
linktitle: XPS 문서에 이미지 추가
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 XPS 문서에 이미지를 완벽하게 통합하는 방법을 살펴보세요. 원활한 개발 경험을 위해 단계별 가이드를 따르세요.
weight: 11
url: /ko/net/image-management/add-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Page를 사용하여 XPS 문서에 이미지 추가

## 소개

.NET 개발 세계에서는 XPS 문서에 이미지를 통합하는 것이 일반적인 요구 사항입니다. .NET용 Aspose.Page는 XPS 문서를 손쉽게 조작하고 향상시킬 수 있는 강력한 툴킷을 제공하여 이 프로세스를 단순화합니다. 이 튜토리얼은 .NET용 Aspose.Page를 사용하여 XPS 문서에 이미지를 추가하는 단계를 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  .NET 라이브러리용 Aspose.Page: 다음에서 라이브러리를 다운로드하고 설치하세요.[Aspose.Page .NET 문서](https://reference.aspose.com/page/net/).

2. 개발 환경: Visual Studio와 같은 .NET 개발 환경을 설정합니다.

3. 샘플 이미지: XPS 문서에 추가할 샘플 이미지 파일(예: "QL_logo_color.tif")이 있습니다.

## 네임스페이스 가져오기

필요한 네임스페이스를 .NET 프로젝트로 가져오는 것부터 시작하세요. 이러한 네임스페이스는 Aspose.Page for .NET에서 제공하는 기능을 활용하는 데 필수적입니다.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1단계: 문서 디렉터리 설정

문서 디렉토리의 경로를 지정하여 시작하십시오. 이 단계를 통해 프로젝트는 파일을 찾고 저장할 위치를 알 수 있습니다.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
// 연장:1
```

## 2단계: XPS 문서 만들기

.NET용 Aspose.Page를 사용하여 새 XPS 문서를 만듭니다.

```csharp
// ExStart:1
XpsDocument doc = new XpsDocument();
// 연장:1
```

## 3단계: XPS 문서에 이미지 추가

이제 XPS 문서에 이미지를 추가해 보겠습니다. 이 예에서는 "QL_logo_color.tif"라는 샘플 이미지를 사용합니다.

```csharp
// ExStart:1
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.RenderTransform = doc.CreateMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f);
path.Fill = doc.CreateImageBrush(dataDir + "QL_logo_color.tif", new RectangleF(0f, 0f, 258.24f, 56.64f), new RectangleF(50f, 20f, 193.68f, 42.48f));
// 연장:1
```

## 4단계: 결과 XPS 문서 저장

추가된 이미지가 포함된 XPS 문서를 저장합니다.

```csharp
// ExStart:1
doc.Save(dataDir + "AddImage_outXPS.xps");
// 연장:1
```

이제 .NET용 Aspose.Page를 사용하여 XPS 문서에 이미지를 성공적으로 추가했습니다!

## 결론

이 튜토리얼에서는 .NET용 Aspose.Page를 활용하여 이미지를 XPS 문서에 원활하게 통합하는 방법을 살펴보았습니다. 이 단계별 가이드는 원활한 통합 프로세스를 보장하여 .NET 개발 기능을 향상시킵니다.

## FAQ

### Q1: Aspose.Page for .NET은 최신 .NET 프레임워크 버전과 호환됩니까?

 A1: Aspose.Page for .NET은 최신 릴리스를 포함하여 광범위한 .NET 프레임워크 버전과 호환되도록 설계되었습니다. 다음을 참조하세요.[선적 서류 비치](https://reference.aspose.com/page/net/) 자세한 내용은

### Q2: Windows와 Linux 환경 모두에서 Aspose.Page for .NET을 사용할 수 있나요?

A2: 예, .NET용 Aspose.Page는 플랫폼 독립적이므로 Windows 및 Linux 환경 모두에서 사용하기에 적합합니다.

### Q3: .NET용 Aspose.Page에 대한 라이선스 옵션이 있습니까?

 A3: 예, 라이선스 옵션을 살펴보고 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy).

### Q4: Aspose.Page for .NET에 대한 무료 평가판이 있습니까?

 A4: 예, 다음 사이트에 액세스하여 .NET용 Aspose.Page를 무료로 사용해 볼 수 있습니다.[무료 시험판](https://releases.aspose.com/).

### Q5: Aspose.Page for .NET에 대한 도움을 구하거나 커뮤니티에 참여할 수 있는 곳은 어디입니까?

 A5: 다음을 방문하세요.[.NET 포럼용 Aspose.Page](https://forum.aspose.com/c/page/39) 커뮤니티와 연결하고 지원을 받으세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
