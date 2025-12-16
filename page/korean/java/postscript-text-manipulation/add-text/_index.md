---
date: 2025-12-14
description: Aspose.Page for Java를 사용하여 Java에서 텍스트 색상을 설정하고, PostScript에 텍스트를 추가하며,
  풍부한 문서 스타일링을 위해 스트로크 텍스트를 적용하는 방법을 배워보세요.
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

## 소개
Aspose.Page for Java를 사용하여 PostScript 파일을 다룰 때 **set text color java**에 대한 단계별 가이드에 오신 것을 환영합니다. Aspose.Page for Java는 개발자가 **postscript file** 문서를 생성하고, 폰트를 조작하며, 텍스트 스타일을 정밀하게 지정할 수 있게 해주는 강력한 라이브러리입니다. 이 튜토리얼에서는 텍스트를 추가하고 색상을 변경하며 크기를 조정하고, 깔끔한 효과를 위해 **apply stroke text**까지 적용하는 방법을 배웁니다.

## 빠른 답변
- **Java에서 텍스트 색상을 설정할 수 있는 라이브러리는?** Aspose.Page for Java.  
- **시스템 폰트와 커스텀 폰트를 모두 사용할 수 있나요?** 예, 모두 지원됩니다.  
- **텍스트 크기를 어떻게 변경하나요?** `Font` 또는 `DrFont`를 생성할 때 폰트 크기를 지정하면 됩니다.  
- **텍스트를 동시에 외곽선과 채우기로 표시할 수 있나요?** 물론입니다 – `fillAndStrokeText`를 사용하세요.  
- **이 튜토리얼이 생성하는 출력 형식은?** PostScript (`.ps`) 문서입니다.

## “set text color java”란?
Java에서 텍스트 색상을 설정한다는 것은 렌더링 엔진(여기서는 Aspose.Page)이 페이지에 문자를 그릴 때 사용할 `Color` 객체를 정의하는 것을 의미합니다. 이 작업은 **postscript documents**를 프로그래밍 방식으로 생성할 때 시각적으로 구분되는 문서를 만들기 위해 필수적입니다.

## Aspose.Page for Java를 사용하는 이유
- **PostScript 생성에 대한 완전한 제어**를 제공하며 별도의 네이티브 PostScript 인터프리터가 필요 없습니다.  
- **시스템 폰트와 외부 폰트 모두 지원**하여 필요한 모든 타이포그래피를 임베드할 수 있습니다.  
- **텍스트 채우기, 외곽선, 채우기·외곽선**을 손쉽게 할 수 있는 **Easy API**를 제공해 스타일링 유연성을 높입니다.  
- **크로스‑플랫폼** 호환성 – Java가 실행되는 어디서든 한 번 작성해 여러 환경에서 실행할 수 있습니다.

## 사전 준비
시작하기 전에 다음을 확인하세요:

- Java 프로그래밍에 대한 기본 지식.  
- Aspose.Page for Java 라이브러리 설치. [Aspose.Page for Java 다운로드 페이지](https://releases.aspose.com/page/java/)에서 받을 수 있습니다.  
- 지정된 폴더에 필요한 폰트가 존재하는지 확인. 자세한 내용은 [Aspose.Page for Java 문서](https://reference.aspose.com/page/java/)를 참고하세요.

## 패키지 가져오기
Java 프로젝트에서 Aspose.Page for Java에 필요한 패키지를 가져옵니다:

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

## 단계 1: 문서 설정
먼저 **PostScript 문서**를 새로 만들고 출력 옵션을 구성합니다.

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

## 시스템 폰트를 사용하여 텍스트 색상 설정하기
이제 시스템 기본 폰트를 이용해 **set text color java**를 시연합니다.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **팁:** `fillText` 메서드는 `Color` 인자를 전달하지 않으면 현재 색상을 자동으로 사용하며, 기본값은 검정색입니다.

## 커스텀 폰트와 텍스트 크기 변경
커스텀 폰트를 사용하고 텍스트 크기를 **change text size**하는 방법도 보여드립니다.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## 텍스트 외곽선(Stroke) 적용 – Apply Stroke Text
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

## 커스텀 폰트로 텍스트 외곽선 적용
같은 기법을 커스텀 폰트에도 적용할 수 있습니다.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## 단계 6: 문서 저장
마지막으로 페이지를 닫고 파일을 디스크에 기록합니다.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## 일반적인 문제 및 해결책
| Issue | Solution |
|-------|----------|
| **Font not found** | 폰트 파일이 `necessary_fonts` 폴더에 위치하고 `options.setAdditionalFontsFolders`를 통해 폴더 경로가 올바르게 추가되었는지 확인하세요. |
| **Color not applied** | `Color` 인자를 포함하는 `fillText` 또는 `outlineText` 오버로드를 호출했는지 확인하세요. |
| **Stroke appears too thin** | `BasicStroke` 너비를 늘리세요(예: `new BasicStroke(3)`). |
| **Document not opening** | 생성된 `.ps` 파일이 올바른 확장자로 저장되었는지, 사용 중인 뷰어가 PostScript를 지원하는지 확인하세요. |

## 자주 묻는 질문

**Q:** Aspose.Page for Java에서 내 커스텀 폰트를 사용할 수 있나요?  
**A:** 예, `DrFont` 클래스에 폰트 이름과 크기를 지정하면 커스텀 폰트를 사용할 수 있습니다.

**Q:** 텍스트 색상을 어떻게 변경하나요?  
**A:** 텍스트를 채우거나 외곽선을 그릴 때 `Color` 클래스를 사용해 원하는 색상을 지정하면 됩니다.

**Q:** PostScript 문서에 여러 페이지를 추가할 수 있나요?  
**A:** 물론입니다! 문서 생성 및 저장 단계를 반복하면 여러 페이지를 만들 수 있습니다.

**Q:** `ExternalFontCache` 클래스의 용도는 무엇인가요?  
**A:** `ExternalFontCache`는 커스텀 폰트를 가져와 텍스트 조작에 사용할 수 있도록 보장합니다.

**Q:** 외곽선 텍스트에 다양한 스트로크를 적용할 수 있나요?  
**A:** 예, `Stroke` 클래스와 `Color` 클래스를 이용해 스트로크의 두께와 색상을 자유롭게 커스터마이즈할 수 있습니다.

## 결론
축하합니다! 이제 **set text color java**를 사용해 폰트 크기를 조정하고, **apply stroke text**를 적용하며, Aspose.Page for Java를 이용해 **postscript document** 파일을 생성하는 방법을 알게 되었습니다. 다양한 폰트, 색상, 외곽선 스타일을 실험해 전문적인 PostScript 출력물을 만들어 보세요.

---

**Last Updated:** 2025-12-14  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}