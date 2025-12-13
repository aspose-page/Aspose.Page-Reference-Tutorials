---
date: 2025-12-13
description: Java에서 ASP 페이지에 텍스트를 추가하고, Java에서 글꼴 스타일을 설정하며, Aspose.Page를 사용해 유니코드
  텍스트를 추가하는 방법을 배워보세요. 단계별 가이드를 따라가세요.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: asp 페이지에 텍스트 추가 – Java PostScript의 유니코드
url: /ko/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – Java PostScript에서 Unicode

## Introduction
Java PostScript 워크플로우에서 **asp page add text** 를 수행하면서 Unicode 문자를 보존해야 한다면, 바로 여기입니다. 이 튜토리얼에서는 Unicode 텍스트 추가, 폰트 스타일 설정, 그리고 **Aspose.Page for Java** 를 사용해 결과를 저장하는 과정을 단계별로 안내합니다. 끝까지 읽으면 **font style java** 를 설정하고 프로젝트에서 Unicode 텍스트를 효율적으로 추가하는 방법을 이해하게 됩니다.

## Quick Answers
- **What library can add Unicode text in Java PostScript?** Aspose.Page for Java.  
- **Which primary method adds text?** `doc.addGlyphs(...)` with a `XpsGlyphs` object.  
- **Do I need a special font for Unicode?** Any TrueType/OpenType font that supports the required code points (e.g., Arial).  
- **Can I change the font style?** Yes, using `XpsFontStyle` (Regular, Bold, Italic, etc.).  
- **Is a license required for production?** Yes, a valid Aspose.Page license is needed for non‑trial use.

## What is asp page add text?
`asp page add text`는 Aspose.Page API를 사용하여 PostScript 또는 XPS 문서에 텍스트 문자열을 삽입하는 과정을 의미합니다. 이 API는 저수준 PostScript 명령을 추상화하여 `XpsGlyphs`와 같은 고수준 객체로 작업할 수 있게 해줍니다.

## Why use Aspose.Page to set font style java and add Unicode text?
- **Full Unicode support** – 오른쪽에서 왼쪽으로 쓰는 스크립트와 복잡한 글리프를 처리합니다.  
- **Simple API** – 텍스트 추가와 스타일 적용을 한 줄 호출로 수행합니다.  
- **Cross‑platform** – 모든 Java 호환 환경에서 작동합니다.  
- **No external dependencies** – 추가 렌더링 엔진이 필요 없습니다.

## Prerequisites
튜토리얼을 시작하기 전에 다음 사전 조건을 확인하세요:

1. **Java Development Kit (JDK)** – 머신에 Java가 설치되어 있는지 확인합니다.  
2. **Aspose.Page for Java** – [download link](https://releases.aspose.com/page/java/)에서 Aspose.Page 라이브러리를 다운로드하고 설치합니다.  
3. **Integrated Development Environment (IDE)** – IntelliJ IDEA, Eclipse 등 선호하는 Java IDE를 선택합니다.

## Import Packages
Java 프로젝트에서 Aspose.Page에 필요한 패키지를 임포트합니다. 코드에 다음 라인을 추가하세요:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Step 1: Set Up Your Project
IDE에서 새 Java 프로젝트를 생성하고 프로젝트 구조를 설정합니다. 프로젝트 의존성에 Aspose.Page 라이브러리를 포함시키는 것을 잊지 마세요.

## Step 2: Initialize XPS Document
프로젝트 내에서 새로운 XPS 문서를 초기화합니다:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Step 3: Add Unicode Text
Aspose.Page 라이브러리를 사용해 XPS 문서에 Unicode 텍스트를 추가합니다. 아래 코드 스니펫을 활용하세요:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

이 코드는 Unicode 텍스트 **"AVAJ rof SPX.esopsA"** 를 좌표 (400, 200) 에 지정된 폰트와 스타일로 XPS 문서에 삽입합니다. `setBidiLevel(1)` 호출이 오른쪽‑왼쪽 렌더링을 활성화하여 올바른 Unicode 표시를 가능하게 하는 점에 주목하세요.

## Step 4: Save the Document
아래 코드를 사용해 최종 XPS 문서를 저장합니다:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## Conclusion
축하합니다! Aspose.Page를 활용해 Java PostScript 시나리오에서 **asp page add text** 를 성공적으로 수행하고 폰트 스타일을 설정했습니다. 이 방법은 Unicode 렌더링과 스타일링에 대한 세밀한 제어를 제공하므로 국제화된 보고서, 인보이스, 그래픽 등에 이상적입니다.

더 많은 기능과 활용법은 [documentation](https://reference.aspose.com/page/java/)을 참고하세요.

## Frequently Asked Questions

**Q:** Can I use Aspose.Page for Java with other programming languages?  
**A:** Aspose.Page is primarily designed for Java, but Aspose provides libraries for various programming languages.

**Q:** Is there a free trial available?  
**A:** Yes, you can access a free trial of Aspose.Page [here](https://releases.aspose.com/).

**Q:** Where can I find support and discussions about Aspose.Page?  
**A:** Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for support and discussions.

**Q:** How can I obtain a temporary license for Aspose.Page?  
**A:** You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).

**Q:** What are the available font styles in Aspose.Page?  
**A:** Aspose.Page supports font styles such as Regular, Bold, Italic, and BoldItalic.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-13  
**Tested With:** Aspose.Page for Java (latest)  
**Author:** Aspose  

---