---
date: 2025-12-21
description: Aspose.Page를 사용하여 Java로 XMP 메타데이터를 읽는 방법을 배워보세요. 이 단계별 가이드는 문서 형식 XMP를
  읽고 주요 속성을 추출하는 방법을 보여줍니다.
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: Java를 사용하여 XMP 메타데이터 읽는 방법 – Aspose.Page 가이드
url: /ko/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 XMP 메타데이터 가져오기

## Java를 사용하여 XMP 메타데이터 읽는 방법

Java와 Aspose.Page 라이브러리를 사용하여 **XMP를 읽는 방법**을 단계별로 안내하는 튜토리얼에 오신 것을 환영합니다. XMP(Extensible Metadata Platform)는 문서에 풍부한 메타데이터를 삽입하기 위해 널리 채택된 표준입니다. 이 가이드를 마치면 문서 형식 XMP를 읽고, 작성자 정보, 타임스탬프, 썸네일 등을 추출할 수 있게 되어 보다 스마트한 문서 분석 솔루션을 구축할 수 있습니다.

## 빠른 답변
- **“how to read xmp”가 무엇을 의미하나요?** 파일에서 프로그래밍 방식으로 XMP 메타데이터를 추출하는 것을 의미합니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Page for Java (Aspose 다운로드 페이지에서 제공).  
- **라이선스가 필요합니까?** 프로덕션 사용을 위해 임시 또는 정식 라이선스가 필요하며, 무료 체험판을 이용할 수 있습니다.  
- **지원되는 Java 버전은?** Java 8 이상.  
- **다른 형식에서도 XMP를 읽을 수 있나요?** 예, Aspose.Page는 EPS, PDF 및 XMP를 포함하는 여러 이미지 형식을 처리할 수 있습니다.

## 사전 요구 사항
코드에 들어가기 전에 다음이 준비되어 있는지 확인하세요:

- **Java Development Kit (JDK)** – 머신에 Java 8 이상이 설치되고 구성되어 있어야 합니다.  
- **Aspose.Page for Java** – 공식 사이트에서 라이브러리를 다운로드하세요 [here](https://releases.aspose.com/page/java/).  
- XMP 메타데이터를 포함하는 EPS 파일(`xmp1.eps` 등).

## 패키지 가져오기
Java 프로젝트에서 필요한 패키지를 가져옵니다:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## 단계 1: 입력 EPS 파일 스트림 초기화
문서 디렉터리 경로를 설정하고 입력 EPS 파일 스트림을 초기화합니다.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## 단계 2: XMP 메타데이터 가져오기
EPS 파일에서 XMP 메타데이터를 가져옵니다. 파일에 XMP 메타데이터가 없으면 PS 메타데이터 주석에서 값을 가져와 새 메타데이터가 생성됩니다.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## 단계 3: CreatorTool 정보 추출
XMP 메타데이터에서 "CreatorTool" 값을 확인하고 출력합니다.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## 단계 4: CreateDate 정보 추출
XMP 메타데이터에서 "CreateDate" 값을 확인하고 출력합니다.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## 단계 5: 썸네일 너비 가져오기
썸네일이 존재하면 첫 번째 썸네일의 너비를 추출하여 출력합니다.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## 단계 6: 포맷 정보 추출
XMP 메타데이터에서 "format" 값을 확인하고 출력합니다.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## 단계 7: DocumentID 가져오기
XMP 메타데이터에서 "DocumentID" 값을 확인하고 출력합니다.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## 왜 중요한가
XMP 메타데이터를 읽으면 뷰어를 열지 않고도 문서의 출처, 생성 날짜 및 기타 필수 속성을 프로그래밍 방식으로 파악할 수 있습니다. 이는 메타데이터가 인덱싱 및 검색을 주도하는 배치 처리, 콘텐츠 관리 시스템, 디지털 자산 파이프라인에 특히 유용합니다.

## 일반적인 함정 및 팁
- **Missing XMP:** 일부 EPS 파일에는 XMP가 포함되지 않을 수 있습니다. `getXmpMetadata()` 호출은 기존 PS 주석을 기반으로 최소한의 메타데이터를 합성하지만, 임베드되지 않은 경우 전체 메타데이터를 얻을 수 없습니다.  
- **Thumbnail Arrays:** `xmp:Thumbnails` 키는 여러 항목을 가질 수 있습니다. 예제는 첫 번째 항목만 추출하므로, 모든 썸네일이 필요하면 배열을 반복하세요.  
- **Namespace Awareness:** XMP 키는 네임스페이스(`xmp:`, `dc:` 등)를 사용합니다. 정확한 키 이름을 참조해야 하며, 그렇지 않으면 `containsKey`가 false를 반환합니다.

## 자주 묻는 질문
### Aspose.Page for Java를 다른 프로그래밍 언어와 함께 사용할 수 있나요?
예, Aspose.Page는 Java, .NET 등 여러 언어를 지원합니다. 자세한 내용은 [documentation](https://reference.aspose.com/page/java/)을 확인하세요.

### Aspose.Page for Java의 무료 체험판을 이용할 수 있나요?
예, 무료 체험판은 [here](https://releases.aspose.com/)에서 이용할 수 있습니다.

### Aspose.Page for Java 지원은 어디에서 찾을 수 있나요?
커뮤니티 지원은 [Aspose.Page forum](https://forum.aspose.com/c/page/39)에서 확인하세요.

### Aspose.Page for Java 임시 라이선스는 어떻게 얻나요?
임시 라이선스는 [here](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

### Aspose.Page for Java에 대한 추가 리소스가 있나요?
전체 [documentation](https://reference.aspose.com/page/java/)을 살펴보고 라이브러리는 [here](https://releases.aspose.com/page/java/)에서 다운로드하세요.

## 추가 FAQ
**Q: 이 방법이 XMP를 포함한 PDF 파일에서도 작동하나요?**  
A: 예, Aspose.Page는 PDF, EPS 및 여러 이미지 형식에서 XMP를 읽을 수 있습니다.

**Q: 읽은 후 XMP 메타데이터를 수정할 수 있나요?**  
A: 물론입니다. `XmpMetadata` 객체는 변경 가능하며, 키를 추가·수정·삭제한 뒤 문서를 저장할 수 있습니다.

**Q: 썸네일 이미지 전체를 추출할 수 있는 방법이 있나요? (크기만이 아니라)**  
A: 각 썸네일 항목의 `xmpGImg:data` 속성에서 바이너리 데이터를 가져와 파일로 저장하면 됩니다.

## 결론
이제 Java와 Aspose.Page를 사용하여 **XMP를 읽는 방법**을 마스터했습니다. 이 단계들을 따라 하면 작성자 도구, 타임스탬프, 썸네일, 포맷 정보 및 문서 ID를 추출할 수 있어 EPS 파일에 포함된 메타데이터를 완전히 파악할 수 있습니다. 추가 XMP 네임스페이스를 실험하여 애플리케이션에 더 풍부한 데이터를 가져오세요.

---

**Last Updated:** 2025-12-21  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
