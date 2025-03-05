---
title: Aspose.Page를 사용하여 PostScript(PS) 문서에 텍스트 추가
linktitle: PostScript(PS) 문서에 텍스트 추가
second_title: Aspose.페이지 .NET API
description: Aspose.Page를 사용하여 PostScript(PS) 문서에 텍스트를 추가하는 방법을 배워 .NET 개발 기술을 향상하세요. 단계별 예제를 살펴보고 문서 조작의 힘을 활용해 보세요.
type: docs
weight: 10
url: /ko/net/text-manipulation/add-text-to-postscript-ps-document/
---
## 소개

.NET 개발의 역동적인 세계에서 PostScript(PS) 문서를 조작하고 향상시키는 것은 일반적인 요구 사항입니다. .NET용 Aspose.Page는 PS 문서에 텍스트를 쉽게 추가할 수 있는 강력한 도구 세트를 제공합니다. 이 튜토리얼에서는 이 기능을 프로젝트에 원활하게 통합할 수 있도록 프로세스를 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET용 Aspose.Page: Aspose.Page 라이브러리가 .NET 프로젝트에 통합되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[Aspose.Page .NET 문서](https://reference.aspose.com/page/net/).

- 문서 디렉터리: 문서가 저장될 디렉터리를 설정합니다. 예제에서는 이를 "문서 디렉터리"라고 합니다.

- 글꼴 폴더: 예제에서는 "문서 디렉터리"라고 하는 사용자 정의 글꼴을 저장할 폴더를 만듭니다.

## 네임스페이스 가져오기

시작하기 전에 프로젝트에 필요한 네임스페이스를 포함했는지 확인하세요.

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

이제 예제를 여러 단계로 나누어 보겠습니다.

## 1단계: PS 문서용 출력 스트림 생성

```csharp
string dataDir = "Your Document Directory";
string FONTS_FOLDER = "Your Document Directory";

using (Stream outPsStream = new FileStream(dataDir + "AddText_outPS.ps", FileMode.Create))
{
    PsSaveOptions options = new PsSaveOptions();
    options.AdditionalFontsFolders = new string[] { FONTS_FOLDER };
    string str = "ABCDEFGHIJKLMNO";
    int fontSize = 48;
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## 2단계: 시스템 글꼴로 텍스트 채우기

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

## 3단계: 사용자 정의 글꼴로 텍스트 채우기

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

## 4단계: 시스템 글꼴을 사용한 윤곽선 텍스트

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

## 5단계: 사용자 정의 글꼴을 사용한 텍스트 윤곽선

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

## 6단계: 닫기 및 저장

```csharp
document.ClosePage();
document.Save();
}
```

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 PostScript(PS) 문서에 텍스트를 추가하는 방법을 성공적으로 배웠습니다. 자유롭게 더 많은 기능을 살펴보고 문서 조작 기능을 향상해 보세요.

## FAQ

### Q1: Aspose.Page를 다른 .NET 라이브러리와 함께 사용할 수 있나요?

A1: 예, Aspose.Page는 다른 .NET 라이브러리와 완벽하게 통합되어 문서 조작을 위한 다양한 환경을 제공합니다.

### Q2: 이 프로세스에 사용자 정의 글꼴이 필수적입니까?

A2: 시스템 글꼴을 사용할 수도 있지만 사용자 정의 글꼴을 통합하면 더 큰 유연성과 디자인 선택이 가능해집니다.

### Q3: Aspose.Page는 대규모 문서 처리에 적합한가요?

A3: 물론이죠! Aspose.Page는 대규모 문서 처리를 효율적이고 안정적으로 처리하도록 설계되었습니다.

### Q4: PS 문서에서 텍스트 위치를 수정할 수 있습니까?

A4: 물론이죠! 추가된 텍스트의 위치를 변경하려면 제공된 예제의 좌표를 조정하세요.

### Q5: Aspose.Page 관련 문의에 대한 도움은 어디서 구할 수 있나요?

 A5: 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지역사회와 연결하고 전문가의 조언을 구합니다.