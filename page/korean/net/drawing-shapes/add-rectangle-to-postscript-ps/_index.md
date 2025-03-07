---
title: .NET용 Aspose.Page를 사용하여 PostScript(PS)에 직사각형 추가
linktitle: PostScript에 직사각형 추가(PS)
second_title: Aspose.페이지 .NET API
description: Aspose.Page를 사용하여 .NET에서 문서 생성을 향상하세요. PostScript(PS) 파일에 직사각형을 추가하는 방법을 단계별로 알아보세요.
weight: 12
url: /ko/net/drawing-shapes/add-rectangle-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Page를 사용하여 PostScript(PS)에 직사각형 추가

## 소개

.NET에서 문서 생성 기능을 향상시키려는 경우 Aspose.Page는 PostScript 문서 처리를 위한 강력한 솔루션을 제공합니다. 이 튜토리얼에서는 Aspose.Page for .NET을 사용하여 PostScript 문서에 직사각형을 추가하는 과정을 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET용 Aspose.Page 라이브러리: 다음에서 .NET용 Aspose.Page 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/page/net/).

- 개발 환경: 컴퓨터에 .NET 개발 환경이 설정되어 있는지 확인하세요.

## 네임스페이스 가져오기

코딩을 시작하기 전에 필요한 클래스와 메서드에 액세스하려면 필요한 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

이제 예제를 여러 단계로 나누어 보겠습니다.

## 1단계: 문서 디렉터리 설정

```csharp
// ExStart:1
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
```

이 단계에서는 "문서 디렉토리"를 PostScript 문서를 저장하려는 경로로 바꾸십시오.

## 2단계: PostScript 문서에 대한 출력 스트림 생성

```csharp
//PostScript 문서의 출력 스트림 생성
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

여기서는 PostScript 문서에 대한 출력 스트림을 생성하고 파일 이름("AddRectangle_outPS.ps")을 지정합니다. 원하는 대로 파일 이름과 위치를 조정하세요.

## 3단계: 저장 옵션 설정 및 PS 문서 만들기

```csharp
//A4 크기로 저장 옵션 만들기
PsSaveOptions options = new PsSaveOptions();

// 새로운 1페이지 PS 문서 만들기
PsDocument document = new PsDocument(outPsStream, options, false);
```

원하는 페이지 크기(이 경우 A4)를 지정하여 저장 옵션을 설정합니다. 그런 다음 새로운 단일 페이지 PostScript 문서를 만듭니다.

## 4단계: 직사각형 추가 및 채우기

```csharp
//첫 번째 직사각형에서 그래픽 경로 만들기
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//페인트 세트
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//직사각형을 채우세요
document.Fill(path);
```

여기서는 첫 번째 직사각형을 나타내는 그래픽 경로를 만들고 페인트 색상(이 경우 주황색)을 설정한 후 직사각형을 채웁니다.

## 5단계: 다른 직사각형과 획 추가

```csharp
//두 번째 직사각형에서 그래픽 경로 만들기
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//스트로크 설정
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//직사각형을 획(윤곽선)으로 그립니다.
document.Draw(path);
```

이전 단계와 마찬가지로 두 번째 직사각형에 대한 그래픽 경로를 만들고 획 색상(두께 3의 빨간색)을 설정한 다음 직사각형의 윤곽을 그립니다.

## 6단계: 페이지를 닫고 문서 저장

```csharp
//현재 페이지 닫기
document.ClosePage();

//문서 저장
document.Save();
```

마지막으로 현재 페이지를 닫고 전체 문서를 저장합니다.

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 PostScript 문서에 직사각형을 성공적으로 추가했습니다. 이 튜토리얼에서는 개발 환경 설정부터 최종 문서 저장까지 필수 단계를 다루었습니다.

## FAQ

### Q1: 직사각형의 색상을 사용자 정의할 수 있나요?

A1: 예, 매개변수를 조정하여 색상을 사용자 정의할 수 있습니다.`SolidBrush` 그리고`Pen` 클래스.

### Q2: Aspose.Page는 다른 문서 형식과 호환됩니까?

A2: 예, Aspose.Page는 XPS 및 PostScript를 포함한 다양한 문서 형식을 지원합니다.

### Q3: 문서에 텍스트를 어떻게 추가할 수 있나요?

 A3: 다음을 사용할 수 있습니다.`TextFragment` 문서에 텍스트를 추가하려면 Aspose.Page의 클래스를 사용하세요.

### Q4: 추가 예제와 문서는 어디에서 찾을 수 있습니까?

 A4: 문서 살펴보기[여기](https://reference.aspose.com/page/net/) 그리고 방문하세요[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지역 사회 지원을 위해.

### Q5: 구매하기 전에 Aspose.Page를 사용해 볼 수 있나요?

 A5: 예, 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/) , 확장된 사용을 위해서는 다음을 고려하십시오.[임시 면허증](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
