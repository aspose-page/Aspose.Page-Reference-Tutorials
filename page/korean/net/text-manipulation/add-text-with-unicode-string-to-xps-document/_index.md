---
date: 2026-03-21
description: Aspose.Page for .NET를 사용하여 XPS 문서에 유니코드 텍스트를 추가하는 방법을 배웁니다. 이 가이드는 C#으로
  XPS 문서를 생성하고 Aspose.Page를 사용해 유니코드 문자열로 텍스트를 추가하는 방법을 보여줍니다.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Aspose.Page를 사용하여 XPS 문서에 유니코드 텍스트 추가하는 방법
url: /ko/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page로 XPS 문서에 유니코드 텍스트 추가하는 방법

## 소개

XPS 파일에 **유니코드 텍스트를 추가하는 방법**이 필요하다면, 여기서 정확한 절차를 확인할 수 있습니다. 이 튜토리얼에서는 Aspose.Page for .NET을 사용해 **C# 스타일로 XPS 문서 만들기**와 유니코드 문자열을 이용한 **aspose page add text** 기능을 단계별로 살펴봅니다. 마지막에는 오른쪽‑왼쪽(RTL) 유니코드 텍스트가 올바르게 표시되는 완전한 XPS 문서를 얻을 수 있습니다.

## 빠른 답변
- **이 튜토리얼은 무엇을 다루나요?** Aspose.Page for .NET을 이용해 XPS 문서에 유니코드 텍스트를 추가하는 방법.  
- **사용 언어는?** C# (.NET Framework 및 .NET Core와 호환).  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 가능하지만, 제품 환경에서는 상용 라이선스가 필요합니다.  
- **폰트나 크기를 변경할 수 있나요?** 예 – 예제에서는 Arial 20 pt를 사용했지만, 설치된 모든 폰트를 사용할 수 있습니다.  
- **RTL 지원이 포함되어 있나요?** `BidiLevel = 1`을 설정하면 유니코드 문자열에 대해 오른쪽‑왼쪽 렌더링이 활성화됩니다.

## XPS에서 “유니코드 텍스트 추가”란?

유니코드 텍스트 추가란 아랍어, 히브리어, 중국어 등 모든 언어의 문자를 XPS 문서에 삽입하는 것을 의미합니다. Aspose.Page의 `XpsGlyphs` 클래스가 저수준 글리프 배치를 담당하고, `BidiLevel` 속성이 RTL 스크립트의 텍스트 방향을 제어합니다.

## Aspose.Page로 텍스트를 추가하는 이유

- **전체 .NET 통합** – .NET Framework, .NET Core, .NET 5/6+와 함께 작동합니다.  
- **외부 종속성 없음** – 순수 관리 코드이며 COM 인터옵이 필요 없습니다.  
- **풍부한 타이포그래피 지원** – 폰트, 스타일, 색상 및 양방향 텍스트 지원.  
- **고성능** – XPS 파일을 빠르게 생성·저장하므로 서버‑사이드 생성에 적합합니다.

## 사전 요구 사항

- C# 및 .NET 개발에 대한 기본 지식.  
- Visual Studio(최근 버전).  
- Aspose.Page for .NET 라이브러리 – [여기](https://releases.aspose.com/page/net/)에서 다운로드.

## 네임스페이스 가져오기

XPS 모델 및 그리기 유틸리티에 접근할 수 있도록 네임스페이스를 가져옵니다.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## 1단계: 문서 설정 – XPS 문서 만들기 (C#)

유니코드 텍스트를 담을 새로운 XPS 문서를 생성합니다.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## 2단계: 유니코드 텍스트 추가 – aspose page add text

이제 실제 유니코드 문자열을 추가합니다. 예제에서는 Arial 폰트, 크기 20, 위치 (400 f, 200 f)를 사용합니다. `BidiLevel`을 1로 설정하면 렌더러가 문자열을 오른쪽‑왼쪽으로 처리합니다.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## 3단계: 문서 저장

마지막으로 XPS 파일을 디스크에 저장합니다.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

축하합니다! Aspose.Page for .NET을 사용해 XPS 문서에 **유니코드 텍스트를 추가하는 방법**을 성공적으로 구현했습니다.

## 일반적인 문제와 해결책

| 문제 | 원인 | 해결 방법 |
|------|------|-----------|
| 텍스트가 깨져 보임 | 폰트가 해당 유니코드 범위를 지원하지 않음 | 필요한 글리프가 포함된 폰트(예: Arial Unicode MS)를 사용합니다. |
| RTL 텍스트가 여전히 왼쪽‑오른쪽 | `BidiLevel`이 설정되지 않았거나 0으로 설정됨 | RTL 스크립트에는 `glyphs.BidiLevel = 1;`을 반드시 설정합니다. |
| 파일이 저장되지 않음 | `dataDir` 경로가 잘못됨 | 디렉터리가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인합니다. |

## 자주 묻는 질문

**Q: Aspose.Page가 최신 .NET 프레임워크와 호환되나요?**  
A: 네, Aspose.Page는 .NET Framework, .NET Core 및 .NET 5/6+를 지원하도록 정기적으로 업데이트됩니다.

**Q: 텍스트를 추가할 때 폰트 스타일과 크기를 커스터마이즈할 수 있나요?**  
A: 물론입니다! `AddGlyphs` 메서드를 사용하면 원하는 폰트 패밀리, 크기 및 `FontStyle`을 지정할 수 있습니다.

**Q: Aspose.Page에 대한 추가 문서는 어디서 찾을 수 있나요?**  
A: 포괄적인 API 세부 정보는 [여기](https://reference.aspose.com/page/net/)에서 확인할 수 있습니다.

**Q: Aspose.Page를 시작하기 위한 무료 리소스가 있나요?**  
A: 네, [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)에서 팁, 예제 및 커뮤니티 지원을 받을 수 있습니다.

**Q: 구매 전에 체험판 버전을 사용할 수 있나요?**  
A: 물론입니다! 라이브러리를 평가하려면 [여기](https://releases.aspose.com/)에서 무료 체험판을 다운로드하십시오.

---

**마지막 업데이트:** 2026-03-21  
**테스트 환경:** Aspose.Page 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}