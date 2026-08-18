---
date: 2026-02-18
description: Aspose.Page를 사용하여 Java PostScript 문서에 사용자 정의 페이지 크기를 설정하고 페이지를 추가하는 방법을
  배우세요. 원활한 문서 조작을 위해 단계별 가이드를 따라보세요.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java 튜토리얼 – PostScript에서 페이지를 추가하면서 사용자 정의 페이지 크기 설정
url: /ko/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java 튜토리얼 – PostScript에 페이지를 추가하면서 사용자 정의 페이지 크기 설정

## Introduction
현대 Java 애플리케이션에서는 **사용자 정의 페이지 크기**를 PostScript 출력에 설정해야 하는 경우가 많습니다—예를 들어 청구서, 티켓, 맞춤형 그래픽을 생성할 때 말이죠. 이 튜토리얼에서는 **사용자 정의 페이지 크기**를 각 페이지마다 설정하고, 여러 페이지를 추가한 뒤, 정확한 레이아웃 요구에 맞는 **PostScript 파일**을 생성하는 방법을 배웁니다. 코드를 단계별로 살펴보면서 여러분의 프로젝트에 바로 적용할 수 있도록 안내합니다.

## Quick Answers
- **각 페이지마다 다른 페이지 크기를 설정할 수 있나요?** 예, `document.openPage(width, height)`를 사용하여 사용자 정의 치수로 페이지를 열 수 있습니다.  
- **프로덕션 사용에 라이선스가 필요합니까?** 평가판이 아닌 배포에서는 유효한 Aspose.Page 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇입니까?** 라이브러리는 Java 8 이상에서 작동합니다.  
- **API가 스레드‑안전합니까?** `Document` 인스턴스는 스레드‑안전하지 않으므로, 스레드당 별도의 `PsDocument`를 생성하세요.  
- **PostScript 파일 크기의 제한은 어떻게 됩니까?** Aspose.Page는 멀티 메가바이트 파일을 효율적으로 처리하며, 메모리 사용량은 페이지 수가 아니라 내용에 비례합니다.  
- **openPage(width, height) 오버로드를 사용할 수 있나요?** 물론입니다—`openPage(double width, double height)`를 사용하면 포인트 단위로 원하는 모든 치수를 지정할 수 있습니다.  

## Prerequisites
시작하기 전에 다음을 준비하세요:

- Java 프로그래밍에 대한 기본 이해.  
- 프로젝트에 Aspose.Page for Java가 추가되어 있어야 합니다 (Maven/Gradle 또는 수동 JAR).  
- Java 개발 환경 (IDE, JDK 8 이상).  

## Import Packages
먼저 Aspose.Page 라이브러리에서 필요한 클래스를 가져옵니다.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Create a Multipaged PostScript Document
새로운 `PsDocument`를 생성하고 다중 페이지용으로 구성합니다. 이는 출력 스트림을 설정하고 라이브러리에게 멀티 페이지 파일을 작업할 것임을 알리는 단계입니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Step 2: Add Content to the First Page
문서가 준비되면 첫 번째 페이지에 필요한 콘텐츠를 추가할 수 있습니다. 작업이 끝나면 페이지를 닫아 내용이 고정되도록 합니다.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## How to set custom page size
기본 페이지 크기가 필요에 맞지 않을 경우, 새 페이지를 열 때 **사용자 정의 페이지 크기**를 설정할 수 있습니다. 영수증, 라벨 또는 비표준 레이아웃에 유용합니다.

## Step 3: Add a Second Page with Different Size
아래 예시에서는 두 번째 페이지를 열고 사용자 정의 너비와 높이(포인트 단위)를 명시적으로 제공합니다. 이는 개별 페이지마다 **다른 페이지 크기**를 설정하는 방법을 보여줍니다.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Step 4: Save the Document
마지막으로 문서를 저장하여 변경 사항을 영구화합니다. 사용자 정의 크기를 가진 모든 페이지가 출력 파일에 기록됩니다.

```java
// Save the document
document.save();
```

이 단계들을 따라 하면 Aspose.Page를 사용해 Java PostScript 문서에서 페이지를 자유롭게 추가하고 **사용자 정의 페이지 크기**를 설정할 수 있어 각 페이지 레이아웃을 완벽히 제어할 수 있습니다.

## Why use Aspose.Page to set custom page size?
- **정밀도:** 치수가 포인트 단위로 정의되므로 페이지 너비와 높이를 정확히 제어할 수 있습니다.  
- **유연성:** 하나의 PostScript 파일 안에서 **다양한 페이지 크기**를 혼합하여 사용할 수 있습니다.  
- **성능:** 라이브러리는 콘텐츠를 직접 출력 파일로 스트리밍하므로 대규모 **PostScript 파일 생성** 시에도 적합합니다.  
- **풍부한 API:** 그래픽 그리기, 이미지 삽입, 텍스트 추가 등을 지원하며, 설정한 사용자 정의 치수를 그대로 반영합니다.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **페이지 치수가 뒤바뀌어 보입니다** | `openPage(width, height)`는 먼저 너비, 그 다음 높이를 기대합니다(둘 다 포인트 단위). |
| **콘텐츠가 페이지를 넘칩니다** | `PsGraphics` 좌표계를 사용해 사용자 정의 경계 내에 요소를 배치하거나, 그림을 스케일링하세요. |
| **대용량 문서에서 메모리 부족 오류가 발생합니다** | 예시와 같이 `FileOutputStream`에 직접 스트리밍하고, 큰 이미지를 한 번에 메모리로 로드하지 않도록 합니다. |

## Frequently Asked Questions
### 단일 PostScript 문서에 서로 다른 크기의 페이지를 추가할 수 있나요?
예, 이 튜토리얼에서 보여준 대로 멀티 페이지 PostScript 문서에 다양한 크기의 페이지를 추가할 수 있습니다.  

### 추가할 수 있는 페이지 수에 제한이 있나요?
Aspose.Page는 사실상 무제한에 가까운 페이지 수를 지원합니다.  

### 페이지에 이미지나 그래픽 같은 사용자 정의 콘텐츠를 추가할 수 있나요?
물론입니다! Aspose.Page를 사용하면 텍스트, 이미지, 기타 그래픽 요소 등 다양한 콘텐츠를 페이지에 삽입할 수 있습니다.  

### 대용량 문서를 처리하기에 Aspose.Page가 적합한가요?
예, Aspose.Page는 크고 작은 문서를 모두 효율적으로 처리하도록 설계되었습니다.  

### Aspose.Page에 대한 추가 자료와 지원은 어디서 찾을 수 있나요?
[Aspose.Page documentation](https://reference.aspose.com/page/java/)을 확인하거나, 커뮤니티 지원을 위해 [Aspose.Page forum](https://forum.aspose.com/c/page/39)에서 질문해 보세요.  

**Additional Q&A**

**Q:** *PostScript 페이지에 그림을 그릴 때 지원되는 이미지 포맷은 무엇인가요?*  
**A:** PNG, JPEG, BMP, GIF 이미지를 그리기 API를 통해 직접 삽입할 수 있습니다.  

**Q:** *문서의 기본 DPI를 변경하려면 어떻게 해야 하나요?*  
**A:** `PsDocument`를 만들기 전에 `PsSaveOptions.setResolution(int dpi)`를 설정하면 됩니다.  

**Q:** *PostScript 파일에 비밀번호를 걸어 암호화할 수 있나요?*  
**A:** PostScript 자체는 암호화를 지원하지 않지만, 필요하다면 출력을 PDF로 래핑하고 PDF 보안 설정을 적용할 수 있습니다.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.10  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}