---
date: 2025-12-20
description: Aspose.Page for Java를 사용하여 EPS 파일에 XMP 메타데이터를 생성하는 방법을 배웁니다. 간단한 XMP
  속성을 프로그래밍 방식으로 추가하는 단계별 가이드.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Java로 XMP 메타데이터 EPS 만드는 방법
url: /ko/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 XMP에 간단한 속성 추가

## 소개
현대 문서 워크플로우에서 **XMP 메타데이터 EPS** 파일을 프로그래밍 방식으로 생성할 수 있으면 그래픽이 어떻게 설명되고, 검색되며, 보관되는지를 완전히 제어할 수 있습니다. Aspose.Page for Java를 사용하면 Java 환경을 떠나지 않고 EPS 문서 내부의 XMP 패킷을 읽고, 수정하고, 쓸 수 있습니다. 이 튜토리얼에서는 EPS 파일에 간단한 XMP 속성을 추가하는 정확한 단계를 안내하므로, 맞춤형 메타데이터를 빠르고 안정적으로 그래픽에 풍부하게 적용할 수 있습니다.

## 빠른 답변
- **“create xmp metadata eps”는 무엇을 의미하나요?** XMP 패킷(XML 기반 메타데이터)을 EPS 파일에 추가하는 것입니다.  
- **필요한 라이브러리는?** Aspose.Page for Java (Aspose 사이트에서 다운로드 가능).  
- **테스트에 라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분합니다; 프로덕션에서는 상용 라이선스가 필요합니다.  
- **코드 라인 수는?** import 문 몇 줄을 제외하고 30줄 미만의 Java 코드.  
- **다른 데이터 타입도 추가할 수 있나요?** 예 — 날짜, 정수, 실수, 문자열 및 배열까지 지원됩니다.

## “create xmp metadata eps”란?
XMP(Extensible Metadata Platform)는 파일 내부에 풍부한 메타데이터를 삽입하기 위한 표준입니다. **XMP 메타데이터 EPS**를 **생성**한다는 것은 XML 패킷을 EPS(Encapsulated PostScript) 문서에 삽입하여, 다운스트림 애플리케이션이 작성자, 생성 날짜, 사용자 정의 태그 등을 읽을 수 있게 하는 것을 의미합니다.

## EPS 파일에 XMP 메타데이터를 추가하는 이유
- **검색 가능성:** DAM 시스템이 자동으로 색인할 수 있습니다.  
- **규정 준수:** 법적 또는 라이선스 정보를 파일에 직접 저장합니다.  
- **자동화:** 파이프라인이 삽입된 데이터를 기반으로 의사결정을 할 수 있습니다.  
- **이식성:** 메타데이터가 EPS와 함께 이동하므로 플랫폼 간 일관성을 보장합니다.

## 사전 준비
시작하기 전에 다음이 준비되어 있는지 확인하세요:

- Java 프로그래밍에 대한 기본 지식.  
- Aspose.Page for Java 라이브러리 설치. **[여기](https://releases.aspose.com/page/java/)**에서 다운로드할 수 있습니다.  
- 메타데이터가 포함된 샘플 EPS 파일. 없으시다면 제공된 **`xmp3.eps`** 파일을 사용하세요.

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다. import 구문은 원본 예제와 동일하게 유지됩니다:

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

## 1단계: EPS 문서를 로드하고 XMP 메타데이터 가져오기
EPS 파일을 열고 `PsDocument` 인스턴스를 만든 뒤 XMP 패킷을 가져오거나 생성합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## 2단계: 날짜 속성 추가
날짜를 추가하는 것은 `Date` 객체를 생성하고 XMP 맵에 넣는 것만큼 간단합니다.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## 3단계: 정수 속성 추가
정수 값을 사용해 식별자나 버전 번호 등을 저장할 수 있습니다.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## 4단계: 실수(Double) 속성 추가
부동소수점 숫자는 측정값이나 평점 등에 유용합니다.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## 5단계: 문자열 속성 추가
프로젝트 코드와 같은 사용자 정의 텍스트 태그는 문자열로 저장됩니다.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## 6단계: 업데이트된 EPS 파일 저장
모든 속성을 추가한 뒤 문서를 디스크에 다시 씁니다.

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

## 7단계: 리소스 정리
파일 핸들 누수를 방지하기 위해 입력 스트림을 반드시 닫아야 합니다.

```java
// Close input EPS stream
psStream.close();
```

## 일반적인 문제와 해결 방법
| 문제 | 원인 | 해결 방법 |
|------|------|-----------|
| **Null XMP 메타데이터** | EPS 파일에 XMP 패킷이 없고 라이브러리가 PS 주석을 추론하지 못함 | 최소 하나의 PS 주석(예: `%%Creator`)이 포함된 EPS를 사용하세요. 라이브러리가 자동으로 최소 XMP 패킷을 생성합니다. |
| **시간대 불일치** | 다른 애플리케이션에서 열었을 때 날짜가 이동됨 | 2단계에서 보여준 것처럼 `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`를 설정한 뒤 `Date` 객체를 생성하세요. |
| **라이선스 예외** | 실행 시 `LicenseException` 발생 | API 사용 전에 유효한 Aspose.Page 라이선스를 적용하거나 평가용 트라이얼 모드로 실행하세요. |

## 결론
이 단계들을 따라 하면 Aspose.Page for Java를 사용해 **XMP 메타데이터 EPS** 파일을 생성하는 방법을 알게 됩니다. 날짜, 정수, 실수, 문자열과 같은 간단한 속성을 추가하는 것은 매우 직관적이며, 결과 EPS 파일은 풍부하고 검색 가능한 메타데이터를 포함해 모든 다운스트림 워크플로우에 가치를 더합니다.

## 자주 묻는 질문
### Aspose.Page for Java를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
Aspose.Page는 주로 Java를 지원하지만 .NET 등 다른 언어용 버전도 제공됩니다.

### Aspose.Page for Java의 무료 체험판이 있나요?
예, 무료 체험판은 **[여기](https://releases.aspose.com/)**에서 받을 수 있습니다.

### Aspose.Page for Java에 대한 자세한 문서는 어디서 찾을 수 있나요?
문서는 **[여기](https://reference.aspose.com/page/java/)**에서 확인할 수 있습니다.

### Aspose.Page for Java의 임시 라이선스는 어떻게 얻나요?
임시 라이선스는 **[여기](https://purchase.aspose.com/temporary-license/)**에서 신청할 수 있습니다.

### Aspose.Page for Java를 구매하려면 어디로 가야 하나요?
구매는 **[여기](https://purchase.aspose.com/buy)**에서 진행합니다.

---

**마지막 업데이트:** 2025-12-20  
**테스트 환경:** Aspose.Page for Java 24.11 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}