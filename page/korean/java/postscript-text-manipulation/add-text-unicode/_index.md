---
date: 2025-12-17
description: Aspose.Page를 사용하여 Java PostScript에 유니코드 텍스트를 추가하는 방법을 배우세요 – 유니코드 문자열을
  손쉽게 추가하는 단계별 가이드.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page를 사용한 Java PostScript에서 유니코드 텍스트 추가 방법
url: /ko/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript에서 Aspose.Page를 사용하여 유니코드 텍스트 추가하는 방법

## Introduction
Java 기반 PostScript(또는 XPS) 워크플로우에 **유니코드** 문자를 추가하는 방법이 궁금하시다면, 바로 여기가 정답입니다. 이 튜토리얼에서는 Aspose.Page 라이브러리를 사용해 Java에서 유니코드 문자열을 삽입하는 정확한 단계를 차근차근 안내합니다. 가이드를 마치면 아랍어, 중국어, 이모지 등 원하는 모든 언어의 텍스트를 PostScript 출력에 직접 삽입할 수 있게 됩니다.

## Quick Answers
- **필요한 라이브러리는?** Aspose.Page for Java  
- **우측에서 좌측으로 쓰는 스크립트를 추가할 수 있나요?** 예, 코드에 표시된 대로 Bidi 레벨을 설정하면 됩니다  
- **개발용 라이선스가 필요한가요?** 테스트용 무료 체험판을 사용할 수 있으며, 실제 운영 환경에서는 상용 라이선스가 필요합니다  
- **어떤 IDE가 가장 좋나요?** 모든 Java IDE(IntelliJ IDEA, Eclipse, NetBeans 등)에서 사용 가능  
- **코드가 크로스‑플랫폼인가요?** 네—Windows, macOS, Linux 어디서든 실행할 수 있습니다

## What is “how to add Unicode” in the context of PostScript?
유니코드를 추가한다는 것은 기본 ASCII 범위를 넘어서는 코드 포인트를 가진 문자를 삽입한다는 의미입니다. Aspose.Page는 저수준 인코딩 작업을 추상화하여 텍스트 내용과 시각적 배치에만 집중할 수 있게 해줍니다.

## Why use Aspose.Page for Unicode text?
- **Full Unicode support** – 복잡한 스크립트, 합자, 우측‑좌측 언어까지 모두 처리합니다.  
- **No external dependencies** – 폰트 파일을 직접 관리할 필요 없이 시스템 폰트를 자동으로 사용합니다.  
- **Straight‑forward API** – 몇 번의 메서드 호출만으로 다국어 텍스트를 렌더링할 수 있습니다.

## Prerequisites
시작하기 전에 아래 항목들을 준비하세요:

1. **Java Development Kit (JDK)** – 최신 버전(8 이상)  
2. **Aspose.Page for Java** – [download link](https://releases.aspose.com/page/java/)에서 라이브러리를 다운로드하고 설치합니다.  
3. **IDE of your choice** – IntelliJ IDEA, Eclipse 또는 선호하는 다른 Java IDE

## Import Packages
Java 소스 파일에 필요한 Aspose.Page 클래스를 추가합니다:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Step 1: Set Up Your Project
새 Java 프로젝트를 만들고, Aspose.Page JAR 파일을 프로젝트 빌드 경로에 추가한 뒤, 생성된 XPS 파일을 저장할 폴더를 만듭니다. 이 폴더는 이후 `dataDir` 로 참조됩니다.

## Step 2: Initialize XPS Document
콘텐츠를 담을 빈 XPS 문서를 생성합니다:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Step 3: Add Unicode Text
이제 실제로 유니코드 문자열을 추가합니다. 아래 예제는 ASCII 문자만 포함된 뒤집힌 문구 “AVAJ rof SPX.esopsA”를 작성하지만, 원하는 유니코드 텍스트(예: 아랍어 “مرحبا” 또는 중국어 “你好”)로 교체하면 됩니다.

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Pro tip:** 우측‑좌측 언어를 올바르게 렌더링하려면 `glyphs.setBidiLevel(1);`을 설정하세요. 좌측‑우측 스크립트의 경우 이 줄을 생략해도 됩니다.

## Step 4: Save the Document
XPS 파일을 디스크에 저장합니다:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

프로그램을 실행한 후, 생성된 `AddEncodingText_out.xps` 파일을 XPS 뷰어로 열어 지정된 좌표에 유니코드 텍스트가 올바르게 표시되는지 확인합니다.

## Common Issues and Solutions
| Issue | Reason | Fix |
|-------|--------|-----|
| 텍스트가 사각형으로 표시됨 | 폰트를 찾을 수 없거나 해당 문자를 지원하지 않음 | 필요한 글리프가 포함된 폰트(예: “Arial Unicode MS”)를 사용 |
| 우측‑좌측 텍스트가 좌측‑우측으로 표시됨 | Bidi 레벨이 설정되지 않음 | `glyphs.setBidiLevel(1);` 호출 |
| 파일이 저장되지 않음 | `dataDir` 경로가 잘못되었거나 쓰기 권한이 없음 | 디렉터리가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인 |

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other programming languages?
Aspose.Page는 주로 Java용으로 설계되었지만, Aspose는 다양한 프로그래밍 언어용 라이브러리도 제공합니다.

### Is there a free trial available?
네, Aspose.Page 무료 체험판은 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.

### Where can I find support and discussions about Aspose.Page?
지원 및 토론은 [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)에서 확인하세요.

### How can I obtain a temporary license for Aspose.Page?
임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

### What are the available font styles in Aspose.Page?
Aspose.Page는 Regular, Bold, Italic, BoldItalic 등 다양한 폰트 스타일을 지원합니다.

## Conclusion
이제 **Java PostScript (XPS) 문서에 유니코드 텍스트를 추가하는 방법**을 완전히 익히셨습니다. 이 기능을 활용하면 다국어 보고서, 국제화된 청구서 등 비‑ASCII 문자가 필요한 모든 시나리오를 구현할 수 있습니다. 텍스트 회전, 클리핑 경로, 사용자 정의 폰트 삽입 등 추가 기능도 자유롭게 탐색해 보세요—자세한 내용은 공식 [documentation](https://reference.aspose.com/page/java/)을 참고하시기 바랍니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2025-12-17  
**Tested With:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Author:** Aspose  

---