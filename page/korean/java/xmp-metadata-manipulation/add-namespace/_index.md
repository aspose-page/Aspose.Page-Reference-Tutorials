---
date: 2026-03-08
description: Aspose.Page for Java를 사용하여 EPS 파일에 XMP 네임스페이스를 추가하는 방법을 배우세요 – XMP와 XMP
  네임스페이스를 추가하는 단계별 자바 튜토리얼 가이드.
linktitle: Add Namespace in XMP using Java
second_title: Aspose.Page Java API
title: Aspose.Page를 사용하여 EPS 파일에 XMP 네임스페이스 추가하는 방법 – Java 튜토리얼
url: /ko/java/xmp-metadata-manipulation/add-namespace/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용하여 EPS 파일에 XMP 네임스페이스 추가 방법 – Java 튜토리얼

## 빠른 답변
- **주된 목표는?** EPS 파일에 사용자 정의 XMP 네임스페이스와 속성을 추가합니다.  
- **필요한 라이브러리는?** Aspose.Page for Java.  
- **테스트에 라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **코드 변경은 몇 번인가요?** 각 단계당 하나씩, 총 다섯 개의 짧은 코드 스니펫만 필요합니다.  
- **다른 네임스페이스에도 재사용할 수 있나요?** 네, `registerNamespaceURI` 호출에서 접두사와 URI만 바꾸면 됩니다.

## XMP 네임스페이스란?

XMP(Extensible Metadata Platform) 네임스페이스는 관련 메타데이터 속성을 공통 URI 아래에 그룹화하는 고유 식별자입니다. 네임스페이스를 등록하면 기존 표준과 충돌하지 않으면서 사용자 정의 데이터(예: 독점 태그)를 저장할 수 있습니다.

## 왜 Aspose.Page를 XMP 조작에 사용하나요?

- **EPS 및 PDF 메타데이터를 Adobe 도구 없이 완전 제어**  
- **XMP 블록이 없을 경우 PS 주석을 기반으로 자동 생성**  
- **크로스‑플랫폼 Java 지원**으로 기존 파이프라인에 손쉽게 통합 가능

## 사전 준비 사항

- Aspose.Page for Java: 라이브러리가 설치되어 있어야 합니다. [여기](https://releases.aspose.com/page/java/)에서 다운로드하세요.  
- Java 개발 환경: 시스템에 Java 환경을 설정합니다.  
- 문서 파일: XMP 메타데이터가 포함된 EPS 파일이 필요합니다. XMP 메타데이터가 없으면 라이브러리가 PS 메타데이터 주석을 기반으로 자동으로 생성합니다.

## 패키지 가져오기

시작하려면 Java 프로젝트에 필요한 패키지를 가져옵니다:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## 단계 1: XMP 메타데이터 가져오기

```java

// The path to the documents directory.
String dataDir = "Your Document Directory";

// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, create a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

### 왜 중요한가요
`XmpMetadata` 객체를 가져오면 문서 메타데이터에 대한 실시간 핸들을 얻어, 저장하기 전에 읽고, 수정하고, 확장할 수 있습니다.

## 단계 2: 새 네임스페이스 등록 *(how to add xmp namespace)*

```java
// Add new XML namespace "http://www.some.org/schema/tmp#" with prefix "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

### 설명
`registerNamespaceURI` 메서드는 짧은 접두사(`tmp`)를 전체 URI에 매핑합니다. XMP 속성은 등록된 네임스페이스와 함께 사용해야 하므로 다음 작업을 위해 필수 단계입니다.

## 단계 3: 새 속성 추가

```java
// Add new property "tmp:newKey" in the new XML namespace
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

### 무슨 일이 일어나나요?
여기서는 `tmp:newKey`라는 사용자 정의 속성을 만들고 값으로 `"NewValue"`를 할당합니다. 비즈니스 로직에 맞게 키와 값을 자유롭게 교체할 수 있습니다.

## 단계 4: 문서 저장

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

### 팁
예외가 발생하더라도 출력 스트림이 닫히도록 `save` 호출을 `try/finally` 블록(또는 try‑with‑resources)으로 감싸는 것이 좋습니다.

## 단계 5: 스트림 닫기

```java
// Close input EPS stream
psStream.close();
```

### 모범 사례
입력 스트림을 닫으면 파일 핸들이 즉시 해제되어 Windows 시스템에서 파일 잠금 문제를 방지합니다.

## 일반적인 문제와 해결책

| 문제 | 가능한 원인 | 해결 방법 |
|------|------------|----------|
| 저장 후 XMP 블록이 나타나지 않음 | 원본 EPS에 XMP가 없고 주석이 충분하지 않음 | EPS에 표준 PS 주석(`%%Creator`, `%%Title` 등)이 포함되어 있는지 확인하거나, 네임스페이스를 등록하기 전에 빈 `XmpMetadata` 객체를 직접 생성합니다. |
| `registerNamespaceURI` 예외 발생 | 접두사가 이미 사용 중 | 고유한 접두사를 선택하거나 `xmp.getRegisteredNamespaces()` 로 기존 네임스페이스를 확인합니다. |
| 저장된 파일이 손상됨 | 출력 스트림이 플러시되지 않음 | `try‑with‑resources` 를 사용하거나 스트림을 닫기 전에 `outPsStream.flush()` 를 명시적으로 호출합니다. |

## 결론

이 **how to add xmp** 튜토리얼을 따라 하면 Aspose.Page for Java를 이용해 EPS 파일에 사용자 정의 네임스페이스와 속성을 추가하는 재사용 가능한 방법을 확보하게 됩니다. 이를 통해 워크플로 식별자, 독점 태그, 하위 시스템을 위한 통합 데이터 등 풍부한 메타데이터 전략을 구현할 수 있습니다.

## 자주 묻는 질문

### Aspose.Page for Java를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
Aspose.Page는 주로 Java를 지원하지만 .NET 등 다른 언어용 버전도 제공됩니다.

### 무료 체험판을 이용할 수 있나요?
네, 무료 체험판은 [여기](https://releases.aspose.com/)에서 확인할 수 있습니다.

### 포괄적인 문서는 어디에서 찾을 수 있나요?
문서는 [여기](https://reference.aspose.com/page/java/)에서 확인하세요.

### 임시 라이선스는 어떻게 얻나요?
임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 발급받을 수 있습니다.

### Aspose.Page 커뮤니티 포럼이 있나요?
네, [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)에서 커뮤니티와 소통할 수 있습니다.

---

**마지막 업데이트:** 2026-03-08  
**테스트 환경:** Aspose.Page for Java 24.10 (최신)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}