---
date: 2025-12-11
description: Aspose.Page를 사용하여 Java PostScript 문서에 사용자 정의 페이지 크기를 설정하고 페이지를 추가하는 방법을
  배워보세요. 원활한 문서 조작을 위한 단계별 가이드를 따라보세요.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Aspose.Page Java 튜토리얼 – PostScript에 페이지를 추가할 때 사용자 정의 페이지 크기 설정
url: /ko/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Java 튜토리얼 – PostScript에 페이지 추가 시 사용자 정의 페이지 크기 설정

## 소개
현대 Java 애플리케이션에서는 **PostScript 출력에 사용자 정의 페이지 크기**를 설정해야 하는 경우가 많습니다—예를 들어 청구서, 티켓, 맞춤형 그래픽을 생성할 때와 같습니다. Aspose.Page for Java를 사용하면 이 작업이 간단합니다. 이 튜토리얼에서는 PostScript 문서에 페이지를 추가하고 사용자 정의 페이지 크기를 설정하는 방법을 단계별로 배워, 매번 정확한 레이아웃을 만들 수 있게 됩니다.

## 빠른 답변
- **각 페이지마다 다른 페이지 크기를 설정할 수 있나요?** 예, `document.openPage(width, height)`를 사용해 사용자 정의 치수로 페이지를 열 수 있습니다.  
- **프로덕션 환경에서 라이선스가 필요합니까?** 평가용이 아닌 배포에서는 유효한 Aspose.Page 라이선스가 필요합니다.  
- **지원되는 Java 버전은 무엇인가요?** Java 8 이상에서 동작합니다.  
- **API가 스레드‑안전한가요?** `PsDocument` 인스턴스는 스레드‑안전하지 않으므로, 스레드당 별도의 인스턴스를 생성하세요.  
- **PostScript 파일 크기에 제한이 있나요?** Aspose.Page는 멀티메가바이트 파일을 효율적으로 처리합니다; 메모리 사용량은 페이지 수가 아니라 내용에 비례합니다.

## 사전 요구 사항
시작하기 전에 다음을 준비하세요:

- Java 프로그래밍에 대한 기본 이해  
- 프로젝트에 Aspose.Page for Java 추가 (Maven/Gradle 또는 수동 JAR)  
- Java 개발 환경 (IDE, JDK 8 이상)

## 패키지 가져오기
먼저 Aspose.Page 라이브러리에서 필요한 클래스를 가져옵니다.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 1단계: 다중 페이지 PostScript 문서 만들기
새 `PsDocument`를 생성하고 다중 페이지용으로 구성합니다. 이렇게 하면 출력 스트림이 설정되고, 라이브러리에게 다중 페이지 파일을 다룰 것임을 알립니다.

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

## 2단계: 첫 번째 페이지에 내용 추가
문서가 준비되면 첫 번째 페이지에 필요한 내용을 추가합니다. 작업이 끝나면 페이지를 닫아 내용을 고정합니다.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## 사용자 정의 페이지 크기 설정 방법
기본 페이지 크기가 필요에 맞지 않을 경우, 새 페이지를 열 때 **사용자 정의 페이지 크기**를 설정할 수 있습니다. 영수증, 라벨 또는 비표준 레이아웃에 유용합니다.

## 3단계: 다른 크기의 두 번째 페이지 추가
아래 예시에서는 두 번째 페이지를 열고 폭과 높이(포인트 단위)를 명시적으로 지정합니다. 이를 통해 개별 페이지에 사용자 정의 페이지 크기를 적용하는 방법을 보여줍니다.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## 4단계: 문서 저장
마지막으로 문서를 저장하여 변경 사항을 영구화합니다. 사용자 정의 크기를 가진 페이지를 포함한 모든 페이지가 출력 파일에 기록됩니다.

```java
// Save the document
document.save();
```

이 단계들을 따르면 Aspose.Page를 사용해 Java PostScript 문서에서 페이지를 손쉽게 추가하고 **사용자 정의 페이지 크기**를 설정할 수 있어, 각 페이지 레이아웃을 완벽히 제어할 수 있습니다.

## 결론
Aspose.Page for Java는 PostScript 문서를 다루기 위한 견고하고 개발자 친화적인 API를 제공합니다. 이제 다중 페이지 추가, 사용자 정의 치수 적용, 저장까지 전체 흐름을 익혔으므로, Java 기반 솔루션에서 정확히 포맷된 출력을 생성할 수 있습니다.

## 자주 묻는 질문
### 단일 PostScript 문서에 서로 다른 크기의 페이지를 추가할 수 있나요?
예, 이 튜토리얼에서 보여준 대로 다중 페이지 PostScript 문서에 크기가 다른 페이지를 추가할 수 있습니다.  
### 추가할 수 있는 페이지 수에 제한이 있나요?
Aspose.Page는 사실상 무제한에 가까운 페이지 수를 지원합니다.  
### 페이지에 이미지나 그래픽 같은 사용자 정의 콘텐츠를 추가할 수 있나요?
물론입니다! Aspose.Page를 사용하면 텍스트, 이미지 및 기타 그래픽 요소 등 다양한 콘텐츠를 페이지에 삽입할 수 있습니다.  
### 대용량 문서를 처리하기에 적합한가요?
예, Aspose.Page는 작은 문서든 큰 문서든 효율적으로 처리하도록 설계되었습니다.  
### Aspose.Page에 대한 추가 자료와 지원은 어디서 찾을 수 있나요?
[Aspose.Page 문서](https://reference.aspose.com/page/java/)를 확인하거나, 커뮤니티 지원을 위해 [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)을 방문하세요.  

**추가 Q&A**

**Q:** *PostScript 페이지에 그림을 그릴 때 지원되는 이미지 형식은 무엇인가요?*  
**A:** PNG, JPEG, BMP, GIF 이미지를 그리기 API를 통해 직접 삽입할 수 있습니다.  

**Q:** *문서의 기본 DPI를 어떻게 변경하나요?*  
**A:** `PsDocument`를 생성하기 전에 `PsSaveOptions.setResolution(int dpi)`를 설정하면 됩니다.  

**Q:** *PostScript 파일에 비밀번호를 설정해 암호화할 수 있나요?*  
**A:** PostScript 자체는 암호화를 지원하지 않지만, 필요하다면 출력을 PDF로 래핑하고 보안 설정을 적용할 수 있습니다.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2025-12-11  
**테스트 환경:** Aspose.Page for Java 24.10  
**작성자:** Aspose  

---