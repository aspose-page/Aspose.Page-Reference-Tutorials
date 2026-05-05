---
date: 2026-05-05
description: Aspose.Page for Java를 사용하여 EPS 파일에 XMP 명명된 값을 추가하는 방법을 배우세요 – 단계별 가이드와
  코드 예제.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
linktitle: Java를 사용하여 XMP에 명명된 값 추가
second_title: Aspose.Page Java API
title: Java를 사용하여 EPS 파일에 XMP 명명된 값을 추가하는 방법
url: /ko/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 XMP 메타데이터에 명명된 값 추가

## 소개
현대 Java 개발에서 EPS 파일 내부에 **XMP** 메타데이터를 추가하는 방법을 배우는 것은 문서 출처를 보존하고 검색 가능성을 향상시키는 데 필수적입니다. **asp**(Aspose.Page for Java)를 사용하면 사용자 지정 명명된 값을 XMP 패킷에 손쉽게 삽입할 수 있습니다. 이 튜토리얼은 정확한 단계와 코드 스니펫을 제공하여 오늘 바로 EPS 문서에 XMP 메타데이터를 추가할 수 있도록 안내합니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Page for Java (asp)  
- **대상 파일 유형은?** XMP 메타데이터를 포함하는 EPS 파일  
- **주요 사용 사례?** XMP에 사용자 지정 명명된 값(예: 페이지 크기 제한) 추가  
- **전제 조건?** JDK 8+ 및 Aspose.Page for Java 라이브러리  
- **예상 구현 시간?** 라이브러리를 설정한 후 5–10 분  

## asp란 무엇인가?
*asp*는 **Aspose**의 약칭으로, 문서 처리를 단순화하는 .NET 및 Java API 제품군입니다. Aspose.Page for Java 구성 요소를 사용하면 PostScript 및 EPS 파일을 생성, 편집 및 변환할 수 있으며, XMP를 포함한 메타데이터에 대한 완전한 프로그래밍 액세스를 제공합니다.

## XMP 메타데이터에 명명된 값을 추가하는 이유?
- **검색 엔진 친화성:** 사용자 지정 태그는 검색 가능성을 향상시킵니다.  
- **워크플로 자동화:** 하위 도구가 사용자 지정 값을 읽어 결정을 내릴 수 있습니다.  
- **규정 준수:** 규제 정보를 문서 패키지에 직접 삽입합니다.  

## 이것이 중요한 이유
XMP에 명명된 값을 추가하면 전체 EPS 파일을 파싱하지 않고도 임의의 키‑값 쌍을 저장하고 읽을 수 있습니다. 이 기능은 자동 출판 파이프라인, 디지털 자산 관리 시스템 및 메타데이터가 하위 작업을 주도하는 규정 준수 기반 워크플로에서 특히 유용합니다.

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하십시오:

- **Java Development Kit (JDK):** 최신 JDK(8 이상)가 머신에 설치되어 있어야 합니다.  
- **Aspose.Page for Java 라이브러리:** 공식 [download link](https://releases.aspose.com/page/java/)에서 다운로드하십시오. JAR 파일을 프로젝트의 클래스패스에 추가합니다.  
- **EPS 파일**은 이미 XMP 메타데이터를 포함하고 있거나 자동으로 생성될 것입니다.

## 패키지 가져오기
필요한 Java 패키지를 가져오는 것으로 시작합니다. 이러한 import는 파일 스트림, EPS 문서 모델 및 XMP 처리 클래스를 사용할 수 있게 해줍니다.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Java를 사용하여 EPS 파일에 XMP 명명된 값 추가
다음은 EPS 문서에 **XMP** 명명된 값을 정확히 추가하는 방법을 단계별로 보여주는 간결한 안내입니다.

### 단계 1: 입력 EPS 파일 스트림 초기화
소스 EPS 파일을 `FileInputStream`에 로드합니다. 이 스트림은 문서를 Aspose API에 전달합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **팁:** `dataDir` 변수를 구성 가능하게 유지하여 동일한 코드가 다양한 환경에서 작동하도록 합니다.

### 단계 2: XMP 메타데이터 가져오기
기존 XMP 패킷을 가져옵니다. EPS 파일에 XMP가 없으면 Aspose가 PS 주석에서 정보를 추출하여 새로운 XMP 객체를 생성합니다.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### 단계 3: 명명된 값 추가
XMP 구조에 사용자 지정 명명된 값을 삽입합니다. 이 예제에서는 `xmpTPg:MaxPageSize` 네임스페이스 아래에 새 키를 추가합니다.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **왜 중요한가:** 명명된 값은 전체 문서를 파싱하지 않고도 하위 애플리케이션이 읽을 수 있는 임의의 키‑값 쌍을 저장할 수 있게 합니다.

### 단계 4: 출력 EPS 파일 스트림 초기화
수정된 EPS를 저장할 `FileOutputStream`을 준비합니다.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### 단계 5: 문서 저장
변경 사항을 영구히 저장합니다. `save` 호출은 업데이트된 XMP 패킷을 EPS 파일에 다시 기록합니다.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### 단계 6: 입력 EPS 스트림 닫기
리소스 누수를 방지하기 위해 원본 파일 핸들을 해제합니다.

```java
psStream.close();
```

이 여섯 단계를 따라 하면 **asp**(Aspose.Page for Java)를 사용하여 **XMP 메타데이터에 명명된 값을 성공적으로 추가**한 것입니다.

## 일반적인 문제 및 해결책
| 문제 | 원인 | 해결책 |
|-------|-------|-----|
| `xmp`에서 NullPointerException | EPS 파일에 XMP가 없고 Aspose가 생성하지 못함 | EPS에 최소 하나의 PS 주석이 포함되어 있는지 확인하거나 새 `XmpMetadata` 인스턴스를 수동으로 생성하십시오. |
| 출력 파일이 비어 있음 | 출력 스트림이 플러시/닫히지 않음 | `outPsStream.close()`가 `finally` 블록에서 호출되는지 확인하십시오(예시 참조). |
| 키 중복 오류 | 같은 명명된 값을 두 번 추가함 | 추가하기 전에 `xmp.containsNamedValue(...)`로 키 존재 여부를 확인하십시오. |

## 자주 묻는 질문

**Q: Aspose.Page for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?**  
A: 예, Aspose.Page for Java는 다른 Java 라이브러리와 원활하게 작동하도록 설계되어 개발 환경에 유연성을 제공합니다.

**Q: Aspose.Page for Java의 무료 체험판을 이용할 수 있나요?**  
A: 예, Aspose.Page for Java의 무료 체험판은 [here](https://releases.aspose.com/)에서 이용할 수 있습니다.

**Q: Aspose.Page for Java의 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: Aspose.Page for Java의 임시 라이선스를 받으려면 [this link](https://purchase.aspose.com/temporary-license/)를 방문하십시오.

**Q: Aspose.Page for Java에 대한 더 많은 튜토리얼과 예제를 어디서 찾을 수 있나요?**  
A: 포괄적인 튜토리얼과 예제를 보려면 [documentation](https://reference.aspose.com/page/java/)을 탐색하십시오.

**Q: Aspose.Page for Java가 대규모 프로젝트에 적합한가요?**  
A: 물론입니다. Aspose.Page for Java는 대규모 프로젝트를 효율적으로 처리하도록 설계되어 강력한 문서 조작 기능을 제공합니다.

## 결론
이 가이드에서는 **asp**(Aspose.Page for Java)를 사용하여 EPS 파일 내 **XMP 메타데이터에 명명된 값을 추가**하는 방법을 간단히 보여주었습니다. 위 단계들을 통해 문서에 사용자 지정 메타데이터를 추가하고, 검색 가능성을 향상시키며, 보다 스마트한 하위 처리 기능을 구현할 수 있습니다.

---

**Last Updated:** 2026-05-05  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}