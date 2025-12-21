---
date: 2025-12-21
description: Java를 사용하여 EPS 문서에서 XMP를 수정하는 방법을 배우세요. Aspose.Page for Java로 메타데이터를
  빠르게 향상시키세요.
linktitle: Change Values in XMP using Java
second_title: Aspose.Page Java API
title: aspose.page XMP 수정 – Java를 사용하여 XMP 값 변경
url: /ko/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 XMP 값 변경

## 소개
EPS 파일 내부의 **aspose.page modify xmp** 데이터를 수정해야 한다면, 올바른 곳에 오셨습니다. 이 튜토리얼에서는 Aspose.Page Java 라이브러리를 사용하여 XMP(Extensible Metadata Platform) 값을 읽고, 업데이트하고, 저장하는 정확한 단계들을 안내합니다. 끝까지 진행하면 문서 메타데이터(예: creator, title, modify date)를 프로젝트 요구사항에 맞게 조정할 수 있게 됩니다.

## 빠른 답변
- **“aspose.page modify xmp”는 무엇을 하나요?** Aspose.Page Java API를 통해 EPS 파일의 XMP 메타데이터를 읽고 쓸 수 있게 해줍니다.  
- **필요한 라이브러리 버전은?** 최신 Aspose.Page for Java 릴리스라면 어느 것이든 사용 가능하며(API는 버전 간에 안정적입니다).  
- **샘플을 실행하려면 라이선스가 필요합니까?** 평가용으로는 무료 체험판으로 충분하고, 실제 운영에서는 상용 라이선스가 필요합니다.  
- **한 번에 여러 XMP 필드를 변경할 수 있나요?** 예—문서를 저장하기 전에 각 필드에 대해 `put`을 호출하면 됩니다.  
- **시간대 처리가 필요합니까?** 기본 시간대(예: UTC)를 설정하면 일관된 날짜 값을 보장합니다.

## XMP란 무엇이며 왜 수정해야 하나요?
XMP(Extensible Metadata Platform)는 EPS, PDF, 이미지와 같은 파일에 풍부한 메타데이터를 직접 삽입하는 표준화된 방식입니다. XMP를 업데이트하면 문서가 색인되고, 표시되며, 검색되는 방식을 제어할 수 있어 브랜드 관리, 규정 준수, 워크플로 자동화에 필수적입니다.

## 왜 Aspose.Page for Java를 사용하나요?
- **Full‑featured API** – 외부 도구가 필요 없으며 모든 작업이 프로세스 내에서 처리됩니다.  
- **Cross‑platform** – Java를 지원하는 모든 OS에서 동작합니다.  
- **No native dependencies** – 순수 Java 구현으로 배포가 간편합니다.  
- **Robust support** – 기존 XMP 블록을 처리하고, 없을 경우 PS 주석에서 새 블록을 생성합니다.

## 사전 요구 사항
이 튜토리얼을 시작하기 전에 다음 사전 요구 사항을 확인하세요:
1. **Java 개발 환경** – JDK(8 이상)와 원하는 IDE 또는 빌드 도구.  
2. **Aspose.Page for Java 라이브러리** – Aspose.Page for Java 라이브러리를 다운로드하고 설치합니다. 필요한 패키지는 [here](https://releases.aspose.com/page/java/)에서 찾을 수 있습니다.

## 패키지 가져오기
Java 프로젝트에 필요한 패키지를 가져오는 것으로 시작합니다. 이 패키지들은 문서와 상호 작용하고 조작하는 데 필수적입니다.

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

## 단계 1: XMP 메타데이터 가져오기
EPS 문서에서 XMP 메타데이터를 가져옵니다. EPS 파일에 XMP 메타데이터가 없으면, %%Creator, %%CreateDate, %%Title과 같은 PS 메타데이터 주석에서 값을 가져와 새 메타데이터가 생성됩니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## 단계 2: "ModifyDate" 값 변경
```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## 단계 3: "Creator" 값 변경
```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## 단계 4: "Title" 값 변경
```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## 단계 5: 변경된 XMP 메타데이터와 함께 문서 저장
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## 일반적인 문제 및 해결책
- **Missing XMP block** – API가 PS 주석에서 자동으로 생성하지만, 필요하면 `XmpMetadata`를 수동으로 인스턴스화할 수도 있습니다.  
- **Timezone mismatches** – 예상치 못한 오프셋을 방지하려면 `Date` 객체를 만들기 전에 항상 `TimeZone.setDefault`를 설정하세요.  
- **File access errors** – 입력 및 출력 경로가 올바른지, 애플리케이션에 읽기/쓰기 권한이 있는지 확인하세요.

## 자주 묻는 질문

**Q: XMP 값을 수정할 때 시간대 고려사항을 어떻게 처리할 수 있나요?**  
A: `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`를 사용하여 시간대 설정의 일관성을 보장합니다.

**Q: 한 번에 여러 XMP 값을 변경할 수 있나요?**  
A: 예, 원하는 각 값에 대해 `put` 메서드를 사용하면 여러 XMP 값을 동시에 수정할 수 있습니다.

**Q: Aspose.Page for Java에 대한 추가 문서는 어디서 찾을 수 있나요?**  
A: 포괄적인 문서는 [here](https://reference.aspose.com/page/java/)에서 확인하세요.

**Q: Aspose.Page for Java의 무료 체험판이 있나요?**  
A: 예, 무료 체험판은 [here](https://releases.aspose.com/)에서 이용할 수 있습니다.

**Q: Aspose.Page for Java 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: 임시 라이선스는 [here](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

**Q: XMP를 수정하면 EPS의 시각적 내용에 영향을 줍니까?**  
A: 아니요. XMP 변경은 메타데이터만 수정하며 EPS 파일의 그래픽 요소는 변경되지 않습니다.

**Q: 프로그램matically 업데이트된 값을 다시 읽어 변경을 확인할 수 있나요?**  
A: 물론입니다—저장 후 문서를 닫기 전에 `xmp.get("dc:creator")`(또는 해당 키)를 호출하면 됩니다.

## 결론
축하합니다! Aspose.Page for Java를 사용하여 EPS 문서에서 **aspose.page modify xmp** 값을 성공적으로 수정했습니다. 이 튜토리얼을 통해 메타데이터를 수정하는 방법을 익혀 문서가 특정 요구사항에 원활히 맞도록 할 수 있게 되었습니다.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**마지막 업데이트:** 2025-12-21  
**테스트 환경:** Aspose.Page for Java (latest release)  
**작성자:** Aspose