---
date: 2026-02-20
description: Aspose.Page for Java를 사용하여 텍스트 색상을 설정하고, 글꼴 크기를 변경하고, 포스트스크립트 파일을 생성하며,
  텍스트를 채우고 스트로크하고, 포스트스크립트 문서를 만들 때 사용자 정의 글꼴을 사용하는 방법을 배워보세요.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page를 사용한 Java 텍스트 색상 설정 – 텍스트 조작 가이드
url: /ko/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page와 함께하는 Java 텍스트 색상 설정 – 텍스트 조작 가이드

## Introduction
Aspose.Page for Java을 사용하여 PostScript 파일을 다루면서 **set text color java**에 대한 단계별 가이드에 오신 것을 환영합니다. Aspose.Page for Java은 개발자가 **create postscript document** 파일을 만들고, 글꼴을 조작하며, 텍스트 스타일을 정밀하게 지정할 수 있게 해주는 강력한 라이브러리입니다. 이 튜토리얼에서는 텍스트를 추가하고, 색상을 변경하며, **change font size java**와 **apply fill and stroke text**까지 배워서 깔끔한 결과물을 만들 수 있습니다.

## Quick Answers
- **Java에서 텍스트 색상을 설정할 수 있는 라이브러리는?** Aspose.Page for Java.  
- **시스템 글꼴과 사용자 정의 글꼴을 사용할 수 있나요?** 예, 두 가지 모두 지원되며, **use custom fonts java**를 쉽게 사용할 수 있습니다.  
- **텍스트 크기를 어떻게 변경하나요?** `Font` 또는 `DrFont`를 생성할 때 글꼴 크기를 지정하면 됩니다.  
- **텍스트를 동시에 외곽선과 채우기로 적용할 수 있나요?** 물론입니다 – `fillAndStrokeText`를 사용하세요.  
- **이 튜토리얼이 생성하는 출력 형식은?** PostScript(`.ps`) 문서이며, 프로그래밍으로 **generate postscript file**할 수 있습니다.

## What is “set text color java”?
Java에서 텍스트 색상을 설정한다는 것은 페이지에 문자를 그릴 때 렌더링 엔진(여기서는 Aspose.Page)이 사용하는 `Color` 객체를 정의하는 것을 의미합니다. 이 작업은 시각적으로 구분되는 문서를 만들 때 필수적이며, 특히 **generate postscript file**을 프로그래밍으로 생성해야 할 때 중요합니다.

## Why use Aspose.Page for Java?
- **Full control**: 네이티브 인터프리터 없이 PostScript 생성에 대한 완전한 제어를 제공합니다.  
- **Support for both system and external fonts**: 시스템 및 외부 글꼴을 모두 지원하여 필요한 모든 타이포그래피를 임베드할 수 있습니다.  
- **Easy API**: 텍스트를 채우고, 외곽선을 그리고, **fill and stroke text**를 적용할 수 있는 쉬운 API를 제공하여 스타일링에 유연성을 줍니다.  
- **Cross‑platform** 호환성 – 한 번 작성하면 Java가 실행되는 모든 환경에서 동작합니다.  

## Prerequisites
시작하기 전에 다음을 준비하세요:

- Java 프로그래밍에 대한 기본 지식.  
- Aspose.Page for Java 라이브러리 설치. [Aspose.Page for Java download page](https://releases.aspose.com/page/java/)에서 다운로드할 수 있습니다.  
- 지정된 폴더에 필요한 글꼴이 있어야 합니다. 자세한 내용은 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)을 참고하세요.  

## Import Packages
Java 프로젝트에서 Aspose.Page for Java에 필요한 패키지를 import합니다:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```

## Step 1: Set Up the Document
먼저, 새로운 **PostScript document**를 생성하고 출력 옵션을 구성합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## How to Set Text Color Java Using System Font
이제 시스템 제공 글꼴을 사용한 **set text color java** 예제를 보여드립니다.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Tip:** `fillText` 메서드는 `Color` 인수를 전달하지 않으면 현재 색상을 자동으로 사용하며, 기본값은 검정색입니다.

## Using Custom Font and Changing Text Size
또한 **change font size java**를 적용하고, 폰트 폴더에 저장된 사용자 정의 글꼴을 사용할 수 있습니다.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Outlining (Stroke) Text – Apply Stroke Text
텍스트에 외곽선을 적용하면 선명한 가장자리를 얻을 수 있습니다. 여기서는 `BasicStroke`를 사용해 **apply stroke text**를 수행합니다.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Outlining Text with Custom Font
같은 방법을 사용자 정의 글꼴에도 적용할 수 있습니다.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Step 6: Save the Document
마지막으로 페이지를 닫고 파일을 디스크에 저장합니다.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Why This Matters
**set text color java**를 수행하고 채우기와 외곽선을 결합하면 최종 PostScript 출력물에 대한 완전한 디자인 제어가 가능합니다. 청구서, 증명서, 맞춤형 그래픽을 생성하든, 정밀한 스타일링으로 **create postscript document** 파일을 만들 수 있어 그래픽 편집기에서의 후처리 필요성이 줄어듭니다.

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Font not found** | `necessary_fonts`에 글꼴 파일이 위치하고 있는지, `options.setAdditionalFontsFolders`를 통해 폴더 경로가 올바르게 추가되었는지 확인하세요. |
| **Color not applied** | `Color` 인수를 포함하는 `fillText` 또는 `outlineText` 오버로드를 호출했는지 확인하세요. |
| **Stroke appears too thin** | `BasicStroke` 너비를 늘리세요(예: `new BasicStroke(3)`). |
| **Document not opening** | 생성된 `.ps` 파일이 올바른 확장자로 저장되었는지, 사용 중인 뷰어가 PostScript를 지원하는지 확인하세요. |

## Frequently Asked Questions

**Q:** Aspose.Page for Java에서 내 사용자 정의 글꼴을 사용할 수 있나요?  
**A:** 예, `DrFont` 클래스에서 글꼴 이름과 크기를 지정하여 **use custom fonts java**를 사용할 수 있습니다.

**Q:** 텍스트 색상을 어떻게 변경하나요?  
**A:** 텍스트를 채우거나 외곽선을 그릴 때 `Color` 클래스를 사용해 원하는 색상을 설정하면 됩니다.

**Q:** PostScript 문서에 여러 페이지를 추가할 수 있나요?  
**A:** 물론입니다! 문서 생성 및 저장 단계를 반복하면 여러 페이지를 만들 수 있습니다.

**Q:** `ExternalFontCache` 클래스의 목적은 무엇인가요?  
**A:** `ExternalFontCache`는 사용자 정의 글꼴을 가져오는 데 사용되며, 텍스트 조작에 사용할 수 있도록 합니다.

**Q:** 외곽선 텍스트에 다른 스트로크를 적용할 수 있나요?  
**A:** 예, `Stroke` 클래스와 `Color` 클래스를 사용해 스트로크의 너비와 색상을 각각 맞춤 설정할 수 있습니다.

## Conclusion
축하합니다! 이제 Aspose.Page for Java를 사용해 **set text color java**, **change font size java**, **apply fill and stroke text**, 그리고 **create postscript document** 파일을 만드는 방법을 알게 되었습니다. 다양한 글꼴, 색상, 외곽선 스타일을 실험하여 전문가 수준의 PostScript 출력물을 만들어 보세요.

---

**마지막 업데이트:** 2026-02-20  
**테스트 환경:** Aspose.Page for Java 23.12 (latest)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}