---
title: Aspose.Page Java 텍스트 조작
linktitle: Java PostScript에 텍스트 추가
second_title: Aspose.페이지 자바 API
description: PostScript 문서에 텍스트를 추가하는 방법에 대한 튜토리얼에서 Java용 Aspose.Page의 강력한 기능을 살펴보세요. 시스템 및 사용자 정의 글꼴을 쉽게 사용하는 방법을 알아보세요.
type: docs
weight: 10
url: /ko/java/postscript-text-manipulation/add-text/
---
## 소개
Java용 Aspose.Page를 사용하여 Java PostScript에 텍스트를 추가하는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. Aspose.Page for Java는 개발자가 PostScript 문서를 쉽게 조작할 수 있게 해주는 강력한 라이브러리입니다. 이 튜토리얼에서는 텍스트 추가, 시스템 및 사용자 정의 글꼴 사용, 텍스트 윤곽선 지정, 시각적으로 매력적인 결과를 위한 획 통합 과정을 안내합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제조건이 충족되었는지 확인하십시오.
- Java 프로그래밍에 대한 기본 지식.
-  Java 라이브러리용 Aspose.Page가 설치되었습니다. 다음에서 다운로드할 수 있습니다.[Aspose.Page for Java 다운로드 페이지](https://releases.aspose.com/page/java/).
-  지정된 폴더에서 사용할 수 있는 필수 글꼴입니다. 추가 정보는 다음에서 확인할 수 있습니다.[Java 문서용 Aspose.Page](https://reference.aspose.com/page/java/).
## 패키지 가져오기
Java 프로젝트에서 Aspose.Page for Java에 필요한 패키지를 가져옵니다.
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
## 1단계: 문서 설정
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// PostScript 문서의 출력 스트림 생성
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// A4 크기로 저장 옵션 만들기
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// PS 파일에 쓸 텍스트
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// 새로운 1페이지 PS 문서 만들기
PsDocument document = new PsDocument(outPsStream, options, false);
```
## 2단계: 텍스트 채우기에 시스템 글꼴 사용
```java
// 텍스트 채우기에 시스템 글꼴 사용
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// 기본 색상 또는 이미 정의된 색상(검은색)으로 텍스트 채우기
document.fillText(str, font, 50, 100);
// 파란색으로 텍스트 채우기
document.fillText(str, font, 50, 150, Color.BLUE);
```
## 3단계: 텍스트 채우기에 사용자 정의 글꼴 사용
```java
// 텍스트 채우기에 사용자 정의 글꼴 사용
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// 기본 색상 또는 이미 정의된 색상(검은색)으로 텍스트 채우기
document.fillText(str, drFont, 50, 200);
// 파란색으로 텍스트 채우기
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## 4단계: 시스템 글꼴을 사용하여 텍스트 개요 지정
```java
// 텍스트 개요에 시스템 글꼴 사용
document.outlineText(str, font, 50, 300);
// 파란색-보라색 2포인트 너비 펜을 사용하여 텍스트 윤곽선 그리기
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// 텍스트를 주황색으로 채우고 파란색 2포인트 너비 펜으로 획을 그립니다.
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## 5단계: 사용자 정의 글꼴을 사용하여 텍스트 개요 지정
```java
// 텍스트 개요에 사용자 정의 글꼴 사용
document.outlineText(str, drFont, 50, 450);
// 파란색-보라색 2포인트 너비 펜을 사용하여 텍스트 윤곽선 그리기
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// 텍스트를 주황색으로 채우고 파란색 2포인트 너비 펜으로 획을 그립니다.
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## 6단계: 문서 저장
```java
// 현재 페이지 닫기
document.closePage();
// 문서 저장
document.save();
```
## 결론
축하해요! Java용 Aspose.Page를 사용하여 Java PostScript에 텍스트를 추가하는 방법을 성공적으로 배웠습니다. 다양한 글꼴, 색상, 개요 옵션을 실험하여 문서를 더욱 향상시켜 보세요.
## 자주 묻는 질문
### Java용 Aspose.Page에서 나만의 사용자 정의 글꼴을 사용할 수 있나요?
 예, 글꼴 이름과 크기를 지정하여 사용자 정의 글꼴을 사용할 수 있습니다.`DrFont` 수업.
### 텍스트 색상을 어떻게 변경할 수 있나요?
 다음을 사용하여 원하는 색상을 설정할 수 있습니다.`Color` 텍스트를 채우거나 개요를 설명할 때 수업을 진행하세요.
### PostScript 문서에 여러 페이지를 추가할 수 있습니까?
전적으로! 문서 생성 및 저장 단계를 반복하여 여러 페이지를 만들 수 있습니다.
###  의 목적은 무엇입니까?`ExternalFontCache` class?
`ExternalFontCache` 사용자 정의 글꼴을 가져와 텍스트 조작에 사용할 수 있도록 하는 데 사용됩니다.
### 윤곽선이 있는 텍스트에 다른 획을 적용할 수 있나요?
 예, 다음을 사용하여 획의 너비와 색상을 사용자 정의할 수 있습니다.`Stroke` 수업과`Color` 수업은 각각.