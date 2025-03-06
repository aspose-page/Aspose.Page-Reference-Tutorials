---
title: .NET용 Aspose.Page를 사용하여 XPS 문서에 타일 이미지 추가
linktitle: XPS 문서에 타일식 이미지 추가
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 XPS 문서에 타일 이미지를 손쉽게 추가해 보세요. 시각적 매력을 강화하고 멋진 문서를 만들어보세요.
weight: 12
url: /ko/net/image-management/add-tiled-image-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Page를 사용하여 XPS 문서에 타일 이미지 추가

## 소개

시각적으로 매력적인 타일 이미지를 추가하여 XPS 문서를 향상시키고 싶으십니까? .NET용 Aspose.Page는 개발자가 이를 원활하게 달성할 수 있도록 지원합니다. 이 단계별 가이드에서는 .NET용 Aspose.Page를 사용하여 XPS 문서에 타일 이미지를 추가하는 과정을 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET용 Aspose.Page: Aspose.Page 라이브러리가 설치되어 있는지 확인하세요. 자세한 문서를 찾고 라이브러리를 다운로드할 수 있습니다.[여기](https://reference.aspose.com/page/net/).
- 개발 환경: Visual Studio와 같은 선호하는 .NET 개발 환경을 설정합니다.

## 네임스페이스 가져오기

시작하려면 필요한 네임스페이스를 프로젝트로 가져옵니다. 이렇게 하면 Aspose.Page 작업에 필요한 클래스와 메서드에 액세스할 수 있습니다. 코드 시작 부분에 다음 네임스페이스를 추가합니다.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

이제 예제를 여러 단계로 나누어 보겠습니다.

## 1단계: 문서 디렉터리 정의

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
```

"문서 디렉터리"를 XPS 문서를 저장하려는 실제 경로로 바꾸십시오.

## 2단계: 새 XPS 문서 만들기

```csharp
// 새 XPS 문서 만들기
XpsDocument doc = new XpsDocument();
```

 다음을 사용하여 새 XPS 문서를 인스턴스화합니다.`XpsDocument` 수업.

## 3단계: 타일식 이미지 추가

```csharp
// 타일 이미지
// 아래 오른쪽 상단에 있는 ImageBrush로 채워진 직사각형
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

이 단계에서는 XPS 문서에 타일식 이미지를 추가합니다. 요구 사항에 따라 좌표와 이미지 파일 경로를 조정합니다.

## 4단계: 결과 XPS 문서 저장

```csharp
// 결과 XPS 문서 저장
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

수정된 XPS 문서를 지정된 디렉터리에 저장합니다.

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 XPS 문서에 타일 이미지를 추가하는 방법을 성공적으로 배웠습니다. 이 간단하면서도 강력한 기능을 사용하면 문서의 시각적 매력을 쉽게 향상시킬 수 있습니다.

## FAQ

### Q1: Aspose.Page는 모든 .NET 개발 환경과 호환됩니까?

A1: 예, Aspose.Page는 Visual Studio를 포함한 다양한 .NET 개발 환경과 원활하게 작동하도록 설계되었습니다.

### Q2: 타일링된 이미지의 불투명도를 조정할 수 있나요?

대답 2: 물론, 예에서 설명한 것처럼 다음을 사용하여 채워진 직사각형의 불투명도를 설정할 수 있습니다.`Opacity` 재산.

### Q3: .NET용 Aspose.Page에서 사용할 수 있는 다른 타일 모드가 있습니까?

 A3: 예, Aspose.Page는 다양한 타일 모드를 제공합니다. 이 튜토리얼에서는 다음을 사용했습니다.`XpsTileMode.Tile`, 그러나 문서에서 다른 옵션을 탐색할 수 있습니다.

### Q4: Aspose.Page의 임시 라이선스를 어떻게 처리하나요?

 A4: 다음을 참조하세요.[임시 면허증](https://purchase.aspose.com/temporary-license/) 임시 라이센스 획득 및 구현에 대한 지침은 Aspose 웹사이트의 페이지에서 확인하세요.

### Q5: 어디서 도움을 구하거나 Aspose.Page 커뮤니티에 연결할 수 있나요?

 A5: 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 커뮤니티에 참여하고, 질문하고, 해결책을 찾으세요.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
