---
date: 2026-03-21
description: Aspose.Page for .NET을 사용하여 PS 문서에 텍스트를 채우고 추가하는 방법을 배웁니다. 코드 예제가 포함된
  단계별 가이드.
linktitle: Add Text to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Aspose.Page를 사용하여 PostScript(PS) 문서에 텍스트 채우기
url: /ko/net/text-manipulation/add-text-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용한 PostScript (PS) 문서에 텍스트 채우기

## 소개

PostScript (PS) 파일 안에 **텍스트를 채우는 방법**이 필요하다면, Aspose.Page for .NET을 사용하면 간단합니다. 보고서, 청구서, 맞춤 그래픽을 생성하든 텍스트를 추가하고 스타일링하는 것은 핵심 요구 사항입니다. 이 튜토리얼에서는 환경 설정부터 최종 PS 문서 저장까지 전체 과정을 단계별로 안내하므로 .NET 애플리케이션에서 PS 파일에 텍스트를 자신 있게 추가할 수 있습니다.

## 빠른 답변
- **“텍스트 채우기”가 의미하는 것은?** 문자를 솔리드 브러시로 렌더링하여 글리프를 페이지에 직접 그립니다.  
- **커스텀 폰트를 사용할 수 있나요?** 예—Aspose.Page는 `add custom font ps` 기능을 통해 커스텀 폰트를 지원합니다.  
- **PS 문서를 어떻게 저장하나요?** 페이지를 닫은 후 `document.Save()`를 호출하면 파일이 디스크에 기록됩니다 (`save ps document`).  
- **“fill and stroke text”가 지원되나요?** 물론입니다; `FillAndStrokeText`를 사용해 채우기와 외곽선을 동시에 적용합니다.  
- **필요한 .NET 버전은?** .NET Framework 4.5 이상 또는 .NET Core/5/6 이상 런타임이면 모두 사용 가능합니다.

## PS 문서에서 “텍스트 채우기”란?

텍스트를 채운다는 것은 외곽선 없이 솔리드 컬러(또는 브러시)로 문자를 그리는 것을 의미합니다. PostScript에서는 `fill` 연산자와 동일합니다. Aspose.Page는 `FillText` 및 `FillAndStrokeText`와 같은 사용하기 쉬운 메서드로 이를 추상화합니다.

## 커스텀 폰트 ps를 추가할 때 Aspose.Page를 사용하는 이유

- **전체 폰트 지원** – 시스템 폰트와 외부 TrueType/OpenType 폰트를 바로 사용할 수 있습니다.  
- **정밀한 위치 지정** – X/Y 좌표, 크기, 스타일을 직접 제어합니다.  
- **다채로운 스타일링** – 채우기, 스트로크, 펜을 조합해 “fill and stroke text”와 같은 효과를 구현합니다.  
- **크로스‑플랫폼** – 동일한 API로 Windows, Linux, macOS에서 동작합니다.

## 사전 요구 사항

시작하기 전에 다음을 준비하세요:

- **Aspose.Page for .NET** – [Aspose.Page .NET documentation](https://reference.aspose.com/page/net/)에서 라이브러리를 다운로드합니다.  
- **Document Directory** – 소스 및 출력 PS 파일이 위치할 로컬 폴더(*Your Document Directory* 라고 코드에 명시됨).  
- **Fonts Folder** – 사용하려는 커스텀 폰트가 들어 있는 하위 폴더.

## 네임스페이스 가져오기

컴파일러가 사용할 클래스를 찾을 수 있도록 필요한 네임스페이스를 먼저 가져옵니다:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.Font;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 단계별 가이드

### 단계 1: PS 문서를 위한 출력 스트림 만들기  

생성된 PS 파일을 담을 `FileStream`을 열고, `PsSaveOptions`를 커스텀 폰트 폴더로 지정한 뒤 `PsDocument`를 인스턴스화합니다.

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

> **팁:** `using` 블록을 유지하면 스트림이 자동으로 닫히고 PS 파일도 최종화됩니다 (`save ps document`).

### 단계 2: 시스템 폰트로 텍스트 채우기  

내장 *Times New Roman* 폰트를 사용해 기본 **텍스트 채우기** 작업을 보여줍니다.

```csharp
System.Drawing.Font font = new System.Drawing.Font("Times New Roman", fontSize, FontStyle.Bold);
document.FillText(str, font, 50, 100);
document.FillText(str, font, 50, 150, new SolidBrush(Color.Blue));
```

### 단계 3: 커스텀 폰트로 텍스트 채우기  

특정 디자인이 필요하면 `ExternalFontCache.FetchDrFont`를 이용해 폰트 폴더에서 커스텀 폰트를 로드합니다. 이는 **add custom font ps** 요구 사항을 충족합니다.

```csharp
DrFont drFont = ExternalFontCache.FetchDrFont("Palatino Linotype", fontSize, FontStyle.Regular);
document.FillText(str, drFont, 50, 200);
document.FillText(str, drFont, 50, 250, new SolidBrush(Color.Blue));
```

### 단계 4: 시스템 폰트로 텍스트 외곽선(스트로크)  

외곽선은 글리프의 윤곽을 그립니다. 이를 채우기와 결합하면 “fill and stroke” 효과를 얻을 수 있습니다.

```csharp
document.OutlineText(str, font, 50, 300);
document.OutlineText(str, font, 50, 350, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, font, 50, 400, new SolidBrush(Color.Yellow), new Pen(new SolidBrush(Color.BlueViolet), 2));
```

> **왜 중요한가:** `FillAndStrokeText` 호출은 한 번에 **fill and stroke text**를 적용하는 방법을 보여 주어 타이포그래피 제어를 강화합니다.

### 단계 5: 커스텀 폰트로 텍스트 외곽선  

로드한 커스텀 폰트에서도 동일한 외곽선 기법을 사용할 수 있습니다.

```csharp
document.OutlineText(str, drFont, 50, 450);
document.OutlineText(str, drFont, 50, 500, new Pen(new SolidBrush(Color.BlueViolet), 2));
document.FillAndStrokeText(str, drFont, 50, 550, new SolidBrush(Color.Orange), new Pen(new SolidBrush(Color.Blue), 2));
```

### 단계 6: 페이지 닫고 문서 저장  

마무리는 간단합니다: 현재 페이지를 닫고 `Save()`를 호출해 PS 파일을 디스크에 기록합니다.

```csharp
document.ClosePage();
document.Save();
}
```

> **결과:** *Your Document Directory*에 `AddText_outPS.ps` 파일이 생성되며, 시스템 폰트와 커스텀 폰트로 채우고 외곽선을 적용한 텍스트가 포함됩니다.

## 일반적인 문제와 해결책

| Issue | Solution |
|-------|----------|
| **Custom font not found** | `AdditionalFontsFolders`에 지정된 폴더에 폰트 파일(.ttf/.otf)이 존재하는지 확인하세요. |
| **Text appears at wrong position** | `FillText`/`OutlineText`에 전달하는 X/Y 좌표를 조정하세요. PostScript는 포인트(1/72 인치)를 사용합니다. |
| **Colors look different** | 올바른 `Color` 값을 가진 `SolidBrush` 또는 `Pen`을 사용하고 있는지 확인하세요. |
| **Document not saving** | `using` 블록이 예외 없이 종료되는지, 대상 폴더에 쓰기 권한이 있는지 확인하세요. |

## 자주 묻는 질문

**Q: Aspose.Page를 다른 .NET 라이브러리와 함께 사용할 수 있나요?**  
A: 예, Aspose.Page는 다른 .NET 구성 요소와 원활히 통합되어 PDF, 이미지, 차트 라이브러리를 같은 솔루션에서 결합할 수 있습니다.

**Q: 이 과정에 커스텀 폰트가 필수인가요?**  
A: 시스템 폰트만으로도 동작하지만, 커스텀 폰트를 사용하면 디자인 자유도가 높아지고 브랜드 전용 타이포그래피에 유용합니다.

**Q: Aspose.Page가 대규모 문서 처리에 적합한가요?**  
A: 물론입니다. 라이브러리는 고처리량 시나리오에 최적화돼 수천 개의 PS 파일을 효율적으로 처리할 수 있습니다.

**Q: PS 문서에서 텍스트 위치를 수정할 수 있나요?**  
A: 네—`FillText` 또는 `OutlineText` 호출에 사용되는 숫자 X/Y 값을 변경하면 됩니다.

**Q: Aspose.Page 관련 문의는 어디에 하면 되나요?**  
A: [Aspose.Page Forum](https://forum.aspose.com/c/page/39)에서 커뮤니티와 전문가에게 도움을 받을 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-21  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose