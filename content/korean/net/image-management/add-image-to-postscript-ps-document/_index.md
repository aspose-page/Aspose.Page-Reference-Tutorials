---
title: Aspose.Page를 사용하여 PostScript(PS) 문서에 이미지 추가
linktitle: PostScript(PS) 문서에 이미지 추가
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 이미지를 추가하여 PostScript 문서를 향상시키는 방법을 알아보세요. 원활한 경험을 위해 단계별 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/image-management/add-image-to-postscript-ps-document/
---
## 소개

이 튜토리얼에서는 강력한 .NET용 Aspose.Page 라이브러리를 사용하여 PostScript(PS) 문서에 이미지를 추가하는 과정을 살펴보겠습니다. Aspose.Page는 PS 문서 조작을 단순화하여 이미지로 문서를 향상시키는 효율적이고 간단한 방법을 제공합니다. 이 단계별 가이드는 각 개념을 철저하게 이해할 수 있도록 프로세스를 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET용 Aspose.Page 라이브러리: 다음에서 .NET용 Aspose.Page 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/page/net/).
- 문서 디렉터리: 문서와 이미지 파일을 저장할 디렉터리를 시스템에 만듭니다.

## 네임스페이스 가져오기

필요한 네임스페이스를 프로젝트로 가져오는 것부터 시작하세요. 이러한 네임스페이스를 사용하면 .NET 애플리케이션에서 Aspose.Page 기능을 활용할 수 있습니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 1단계: 문서 디렉토리 설정

 문서 전용 디렉터리가 있는지 확인하세요. 바꾸다`"Your Document Directory"` 아래 코드 조각에 문서 디렉터리 경로를 입력하세요.

```csharp
string dataDir = "Your Document Directory";
```

## 2단계: PS 문서용 출력 스트림 생성

PostScript 문서의 출력 스트림을 설정합니다. 이 스트림은 수정된 문서를 저장하는 데 사용됩니다.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddImage_outPS.ps", FileMode.Create))
```

## 3단계: 저장 옵션 생성

페이지 크기 등 원하는 설정을 지정하여 PS 문서에 대한 저장 옵션을 만듭니다.

```csharp
PsSaveOptions options = new PsSaveOptions();
```

## 4단계: PS 문서 만들기

새로운 1페이지 PS 문서를 초기화하고 그래픽 작업을 준비합니다.

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
document.WriteGraphicsSave();
document.Translate(100, 100);
```

## 5단계: 문서에 이미지 추가

이미지 파일에서 Bitmap 객체를 로드하고 변환을 적용합니다. PS 문서에 이미지를 추가합니다.

```csharp
using (Bitmap image = new Bitmap(dataDir + "TestImage Format24bppRgb.jpg"))
{
    System.Drawing.Drawing2D.Matrix transform = new System.Drawing.Drawing2D.Matrix();
    transform.Translate(35, 300);
    transform.Scale(3, 3);
    transform.Rotate(-45);
    
    document.DrawImage(image, transform, Color.Empty);
}
```

## 6단계: 그래픽 작업 마무리

그래픽 작업을 종료하고 현재 페이지를 닫습니다.

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## 7단계: 문서 저장

수정된 PS 문서를 저장합니다.

```csharp
document.Save();
```

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 PostScript 문서에 이미지를 성공적으로 추가했습니다. 이 튜토리얼은 이미지를 PS 문서에 통합하여 문서를 시각적으로 매력적이고 매력적으로 만들기 위한 명확하고 간결한 가이드를 제공합니다.

## FAQ

### Q1: Aspose.Page를 사용하여 단일 PS 문서에 여러 이미지를 추가할 수 있나요?

A1: 네, 가능합니다. 문서 내에서 이미지 추가 단계를 반복하기만 하면 됩니다.

### Q2: Aspose.Page for .NET에서는 어떤 이미지 형식을 지원합니까?

A2: .NET용 Aspose.Page는 JPEG, PNG, BMP 및 GIF를 포함한 다양한 이미지 형식을 지원합니다.

### Q3: 추가할 수 있는 이미지에 크기 제한이 있나요?

A3: 크기 제한은 PS 문서의 사양과 시스템 리소스에 따라 다릅니다. Aspose.Page는 다양한 이미지 크기를 처리합니다.

### Q4: 필터나 오버레이 등의 추가 효과를 이미지에 적용할 수 있나요?

A4: 예, Aspose.Page를 사용하면 이미지를 문서에 추가하기 전에 이미지에 다양한 변형과 효과를 적용할 수 있습니다.

### Q5: PS 문서에서 이미지를 추출하려면 어떻게 해야 합니까?

A5: .NET용 Aspose.Page는 PS 문서에서 이미지를 추출하는 방법을 제공합니다. 자세한 내용은 설명서를 참조하세요.