---
date: 2026-05-20
description: Aspose.Page for Java를 사용하여 EPS 파일에 XMP 메타데이터를 추가하는 방법을 배웁니다. 간단한 XMP
  속성을 프로그래밍 방식으로 삽입하는 단계별 가이드.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Java를 사용하여 XMP에 간단한 속성 추가
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Java를 사용하여 EPS 파일에 XMP 메타데이터 추가
url: /ko/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 EPS 파일에 XMP 메타데이터 추가

## 소개
현대 그래픽 파이프라인에서 EPS 파일에 **XMP 메타데이터 추가**를 프로그래밍 방식으로 수행하면 일러스트레이션이 어떻게 설명되고, 검색되고, 보관되는지를 완전히 제어할 수 있습니다. Aspose.Page for Java를 사용하면 Java 환경을 떠나지 않고 EPS 문서 내부의 XMP 패킷을 읽고, 수정하고, 쓸 수 있습니다. 이 튜토리얼에서는 EPS 파일에 간단한 XMP 속성을 추가하는 정확한 단계들을 안내하여, 사용자 정의 메타데이터로 그래픽을 빠르고 신뢰성 있게 풍부하게 만들 수 있도록 도와드립니다.

## 빠른 답변
- **“add XMP metadata to EPS”가 무엇을 의미합니까?** EPS 파일 내부에 XMP 패킷(XML 기반 메타데이터)을 삽입하는 것입니다.  
- **필요한 라이브러리는 무엇입니까?** Aspose.Page for Java (Aspose 사이트에서 다운로드 가능).  
- **테스트에 라이선스가 필요합니까?** 개발에는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **코드 라인은 몇 줄입니까?** Java 코드 30줄 미만에 몇 개의 import 문만 추가하면 됩니다.  
- **다른 데이터 유형을 추가할 수 있습니까?** 예 — 날짜, 정수, 실수(double), 문자열, 그리고 배열까지 지원됩니다.

## Java를 사용하여 EPS 파일에 XMP 메타데이터를 추가하는 방법?
`new PsDocument("input.eps")` 로 EPS 파일을 로드하고, XMP 패킷을 가져오거나 생성한 뒤 원하는 속성을 삽입하고, 문서를 디스크에 저장합니다 — 모두 Java 코드 10줄 이하로 가능합니다. 이 방법을 사용하면 EPS 소스를 수동으로 편집하지 않고도 검색 가능하고 표준을 준수하는 메타데이터를 삽입할 수 있습니다.

## EPS에서 XMP 메타데이터란 무엇입니까?
EPS의 XMP 메타데이터는 EPS 파일 내부에 존재하는 XML 패킷으로, 작성자, 생성 날짜, 사용자 정의 태그와 같은 정보를 저장합니다. 이 패킷을 삽입하면 별도의 사이드카 파일 없이도 하위 도구가 데이터를 읽고 활용할 수 있습니다.

## 왜 EPS 파일에 XMP 메타데이터를 추가합니까?
XMP 메타데이터를 삽입하면 EPS 자산을 즉시 검색 가능하게 만들고, 파일 내부에 라이선스 정보를 저장하여 규정 준수를 보장하며, 삽입된 태그를 기반으로 자동 파이프라인이 결정을 내릴 수 있게 하고, 메타데이터가 모든 플랫폼에서 그래픽과 함께 이동하도록 보장합니다. Aspose.Page는 전체 문서를 메모리에 로드하지 않고도 최대 500 MB 파일을 처리할 수 있어 대규모 작업에 빠른 성능을 제공합니다.

## 사전 요구 사항
시작하기 전에 다음을 확인하십시오:

- Java 프로그래밍에 대한 기본 지식.  
- Aspose.Page for Java 라이브러리가 설치되어 있어야 합니다. **[여기](https://releases.aspose.com/page/java/)**에서 다운로드할 수 있습니다.  
- 메타데이터가 포함된 샘플 EPS 파일. 파일이 없으면 제공된 **`xmp3.eps`** 파일을 사용하십시오.

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다. import 구문은 원본 예제와 정확히 동일하게 유지됩니다:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## 단계 1: EPS 문서를 로드하고 XMP 메타데이터 가져오기
`PsDocument` 클래스는 EPS 파일을 나타내며 해당 내용 및 메타데이터에 접근하는 메서드를 제공합니다.  
`XmpMetadata` 객체는 문서와 연결된 XMP 패킷을 보유합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 단계 2: Date 속성 추가
`Date` 클래스는 밀리초 정밀도로 특정 순간을 나타냅니다.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## 단계 3: Integer 속성 추가
`Integer` 클래스는 기본형 `int` 값을 객체로 감싸줍니다.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## 단계 4: Double 속성 추가
`Double` 클래스는 기본형 `double` 값을 객체로 감싸줍니다.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## 단계 5: String 속성 추가
`String` 클래스는 문자 시퀀스를 나타냅니다.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## 단계 6: 업데이트된 EPS 파일 저장
`save` 메서드는 수정된 문서를 디스크에 다시 기록하여 EPS 구조를 유지합니다.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 단계 7: 리소스 정리
파일 핸들 누수를 방지하고 모든 버퍼가 플러시되도록 스트림을 항상 닫아야 합니다.

```java
// Close input EPS stream
psStream.close();
```

## 일반적인 문제 및 해결책
| 문제 | 원인 | 해결 방법 |
|-------|--------|-----|
| **Null XMP 메타데이터** | EPS 파일에 XMP 패킷이 없었으며 라이브러리가 PS 주석을 추론할 수 없었습니다. | `%%Creator`와 같은 PS 주석이 최소 하나 포함되어 있는지 확인하십시오. 라이브러리가 자동으로 최소한의 XMP 패킷을 생성합니다. |
| **시간대 불일치** | 다른 애플리케이션에서 열었을 때 날짜가 이동된 것처럼 보입니다. | `Date` 객체를 만들기 전에 `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` 를 설정하십시오(단계 2 참고). |
| **라이선스 예외** | 런타임에서 `LicenseException`이 발생합니다. | API를 사용하기 전에 유효한 Aspose.Page 라이선스를 적용하거나 평가용으로 체험 모드로 실행하십시오. |

## 자주 묻는 질문
**Q: Aspose.Page for Java를 다른 프로그래밍 언어와 함께 사용할 수 있나요?**  
A: Aspose.Page는 주로 Java를 지원하지만, .NET, C++, Python용 동등한 라이브러리도 제공됩니다.

**Q: Aspose.Page for Java에 대한 무료 체험판이 제공되나요?**  
A: 예, **[여기](https://releases.aspose.com/)**에서 무료 체험판을 받아 Aspose.Page의 기능을 살펴볼 수 있습니다.

**Q: Aspose.Page for Java에 대한 자세한 문서는 어디에서 찾을 수 있나요?**  
A: 문서는 **[여기](https://reference.aspose.com/page/java/)**에서 확인할 수 있습니다.

**Q: Aspose.Page for Java에 대한 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: 임시 라이선스는 **[여기](https://purchase.aspose.com/temporary-license/)**에서 획득할 수 있습니다.

**Q: Aspose.Page for Java를 어디에서 구매할 수 있나요?**  
A: 제품은 **[여기](https://purchase.aspose.com/buy)**에서 구매할 수 있습니다.

**마지막 업데이트:** 2026-05-20  
**테스트 환경:** Aspose.Page for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 관련 튜토리얼

- [Java를 사용하여 XMP 메타데이터 읽는 방법 – Aspose.Page 가이드](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page XMP 튜토리얼 – Java를 사용하여 XMP에 네임스페이스 추가](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Java를 사용하여 XMP 메타데이터에 배열 항목 추가](/page/java/xmp-metadata-manipulation/add-array-items/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}