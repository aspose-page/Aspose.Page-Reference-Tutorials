---
date: 2026-05-25
description: Java와 함께 aspose.page를 사용하여 XMP를 읽는 방법을 배웁니다. 이 단계별 가이드는 XMP 메타데이터, creator
  info, timestamps, thumbnails 등을 추출하는 방법을 보여줍니다.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Java를 사용하여 XMP Metadata 읽는 방법
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Aspose.Page를 사용하여 XMP 읽기 – Java 가이드
url: /ko/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 XMP 메타데이터 가져오기

## Aspose.Page (Java)를 사용하여 XMP를 읽는 방법?

`new Document("file.eps")` 로 EPS 파일을 로드합니다—`Document` 클래스는 로드된 파일을 나타냅니다. `getXmpMetadata()` 를 호출하면 XMP 패킷을 추출하고, 반환된 `XmpMetadata` 객체( XMP 속성을 위한 맵과 유사한 인터페이스)를 조회하여 필요한 키를 가져옵니다. 이것이 Aspose.Page를 사용하여 XMP를 읽는 데 필요한 전부입니다. API는 저수준 파싱을 추상화하므로 두 줄의 코드만으로 사용 가능한 속성 맵을 얻을 수 있습니다.

Java와 Aspose.Page 라이브러리를 사용하여 **XMP 메타데이터를 읽는 방법**을 단계별로 보여주는 튜토리얼에 오신 것을 환영합니다. XMP(Extensible Metadata Platform)는 문서에 풍부한 메타데이터를 삽입하기 위해 널리 채택된 표준입니다. 이 가이드를 끝까지 따라오시면 문서 형식 XMP를 읽고, 제작자 정보, 타임스탬프, 썸네일 등을 추출할 수 있게 되어 보다 스마트한 문서 분석 솔루션을 구축할 수 있습니다.

## 빠른 답변
- **“XMP 읽기”가 무엇을 의미하나요?** 파일 내부에 메타데이터를 저장하는 XMP 패킷을 프로그래밍 방식으로 추출하는 것을 의미합니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Page for Java (공식 페이지 [here](https://releases.aspose.com/page/java/)에서 다운로드).  
- **라이선스가 필요한가요?** 프로덕션에서는 임시 또는 정식 라이선스가 필요합니다; 평가용으로는 무료 체험판을 사용할 수 있습니다.  
- **지원되는 Java 버전은?** Java 8 이상.  
- **다른 형식에서도 XMP를 읽을 수 있나요?** 예 — Aspose.Page는 EPS, PDF, JPEG, PNG 및 20가지 이상의 다른 형식에서 XMP를 추출합니다.

## 사전 요구 사항
코드를 살펴보기 전에 다음이 준비되어 있는지 확인하십시오:

- **Java Development Kit (JDK)** – Java 8+가 설치되고 머신에 구성되어 있음.  
- **Aspose.Page for Java** – 공식 사이트 [here](https://releases.aspose.com/page/java/)에서 라이브러리를 다운로드하십시오.  
- XMP 메타데이터를 포함하고 있는 EPS 파일(e.g., `xmp1.eps`).  

## 패키지 가져오기
`XmpMetadata` 클래스는 `com.aspose.page.xmp` 네임스페이스에, `Document` 클래스는 `com.aspose.page`에 있습니다. 두 클래스를 모두 가져와 EPS 파일과 메타데이터를 작업할 수 있도록 합니다.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 단계 1: 입력 EPS 파일 스트림 초기화
먼저 문서 디렉터리 경로를 설정하고 입력 EPS 파일 스트림을 초기화합니다.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## 단계 2: XMP 메타데이터 가져오기
`XmpMetadata`는 문서에서 추출된 XMP 패킷을 보관하는 Aspose.Page 객체입니다. `document.getXmpMetadata()` 로 가져옵니다. 파일에 XMP가 없을 경우, API는 기존 PostScript 주석을 기반으로 최소 패킷을 합성합니다.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## 단계 3: CreatorTool 정보 추출
`CreatorTool` 키는 `xmp` 네임스페이스에 있으며 파일을 생성한 애플리케이션을 기록합니다. 존재 여부를 확인하고 값을 출력합니다.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## 단계 4: CreateDate 정보 추출
`CreateDate`는 문서가 원래 **생성**된 시점을 저장합니다. 동일한 `containsKey`/`get` 패턴을 사용하여 읽습니다.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## 단계 5: 썸네일 너비 가져오기
썸네일이 존재하면 `xmp:Thumbnails` 배열에 하나 이상의 항목이 들어 있습니다. 각 항목은 `width`, `height`, 그리고 바이너리 데이터를 포함합니다. **예제**는 **첫 번째** 썸네일의 **width**를 추출합니다.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## 단계 6: 포맷 정보 추출
`format` 키는 원본 파일 형식(e.g., “application/postscript”)을 알려줍니다. 이는 소스 유형을 기록하거나 검증할 때 유용합니다.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## 단계 7: DocumentID 가져오기
`DocumentID`는 제작 애플리케이션이 할당한 고유 식별자입니다. 대규모 자산 라이브러리에서 중복 제거에 사용할 수 있습니다.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## 이것이 중요한 이유
Aspose.Page는 **20개 이상의** 파일 형식에서 XMP를 읽을 수 있으며, 전체 파일을 메모리에 로드하지 않고 **500 MB**까지의 문서를 처리하여 필수 메타데이터에 빠르고 낮은 오버헤드로 접근할 수 있습니다. 이 기능은 배치 처리 파이프라인, 디지털 자산 관리 시스템 및 검색 가능하고 기계가 읽을 수 있는 문서 속성에 의존하는 모든 솔루션에 필수적입니다.

## 일반적인 함정 및 팁
- **Missing XMP:** 일부 EPS 파일에는 XMP가 포함되지 않을 수 있습니다. `getXmpMetadata()` 호출은 기존 PS 주석을 기반으로 최소 세트를 합성하지만, 임베드되지 않은 경우 전체 메타데이터를 얻을 수 없습니다.  
- **Thumbnail Arrays:** `xmp:Thumbnails` 키는 여러 항목을 가질 수 있습니다. 예제는 첫 번째 항목만 추출합니다; 모든 썸네일이 필요하면 배열을 반복하세요.  
- **Namespace Awareness:** XMP 키는 네임스페이스(e.g., `xmp:`, `dc:`)를 사용합니다. 정확한 키 이름을 참조해야 하며, 그렇지 않으면 `containsKey`가 false를 반환합니다.  

## 자주 묻는 질문
### Aspose.Page for Java를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
예, Aspose.Page는 Java, .NET 및 여러 다른 언어를 지원합니다. 전체 목록은 [documentation](https://reference.aspose.com/page/java/)에서 확인하세요.

### Aspose.Page for Java에 대한 무료 체험판이 있나요?
예, 무료 체험판은 [here](https://releases.aspose.com/)에서 이용할 수 있습니다.

### Aspose.Page for Java 지원을 어디서 찾을 수 있나요?
커뮤니티 도움과 공식 지원을 위해 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 을 방문하세요.

### Aspose.Page for Java에 대한 임시 라이선스를 어떻게 얻나요?
임시 라이선스는 [here](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

### Aspose.Page for Java에 대한 추가 리소스가 있나요?
전체 [documentation](https://reference.aspose.com/page/java/)을 살펴보고 라이브러리를 [here](https://releases.aspose.com/page/java/)에서 다운로드하세요.

## 추가 FAQ
**Q: 이 방법이 XMP를 포함한 PDF 파일에서도 작동하나요?**  
A: 예, Aspose.Page는 PDF, EPS 및 여러 이미지 형식에서 XMP를 읽을 수 있습니다.

**Q: 읽은 후 XMP 메타데이터를 수정할 수 있나요?**  
A: 물론입니다. `XmpMetadata` 객체는 변경 가능하며, 키를 추가, 업데이트 또는 제거한 뒤 문서를 저장할 수 있습니다.

**Q: 차원만이 아니라 모든 썸네일 이미지를 추출할 방법이 있나요?**  
A: 각 썸네일 항목의 `xmpGImg:data` 속성에서 바이너리 데이터를 가져와 파일로 저장할 수 있습니다.

## 결론
이제 Java와 Aspose.Page를 사용하여 **XMP 메타데이터를 읽는 방법**을 마스터했습니다. 이 단계들을 따라하면 제작 도구, 타임스탬프, 썸네일, 포맷 정보 및 DocumentID를 추출할 수 있어 EPS 파일에 포함된 메타데이터를 완전히 파악할 수 있습니다. 추가 XMP 네임스페이스를 실험하여 애플리케이션에 더 풍부한 데이터를 가져오세요.

---

**마지막 업데이트:** 2026-05-25  
**테스트 대상:** Aspose.Page for Java 24.12 (latest)  
**작성자:** Aspose

## 관련 튜토리얼

- [Aspose Page Java 튜토리얼 – EPS 파일에 XMP 메타데이터 추가](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page XMP 튜토리얼 – Java를 사용하여 XMP에 네임스페이스 추가](/page/java/xmp-metadata-manipulation/add-namespace/)
- [aspose page XMP 튜토리얼 – Java를 사용하여 XMP의 명명된 값 변경](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}