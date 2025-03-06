---
title: Java를 사용하여 XMP 메타데이터에 배열 항목 추가
linktitle: Java를 사용하여 XMP 메타데이터에 배열 항목 추가
second_title: Aspose.페이지 자바 API
description: Java용 Aspose.Page를 사용하여 EPS 파일을 향상하세요. XMP 메타데이터에 배열 항목을 쉽게 추가하는 방법을 알아보세요. 지금 단계별 가이드를 따르십시오!
weight: 10
url: /ko/java/xmp-metadata-manipulation/add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 XMP 메타데이터에 배열 항목 추가

## 소개
XMP 메타데이터에 배열 항목을 추가하기 위해 Java용 Aspose.Page를 사용하는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. Aspose.Page는 EPS 파일을 포함한 다양한 문서 형식을 조작하고 작업할 수 있는 강력한 Java 라이브러리입니다. 이 튜토리얼에서는 Java를 사용하여 XMP 메타데이터에 배열 항목을 추가하는 특정 작업에 중점을 둘 것입니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 라이브러리용 Aspose.Page가 설치되었습니다.
- Java 프로그래밍에 대한 기본 이해.
- 기존 XMP 메타데이터 또는 PS 메타데이터 설명이 포함된 유효한 EPS 파일입니다.
## 패키지 가져오기
시작하려면 Aspose.Page 작업에 필요한 패키지를 가져와야 합니다. Java 파일 시작 부분에 다음 줄을 포함합니다.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## 1단계: XMP 메타데이터 가져오기
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 입력 EPS 파일 스트림 초기화
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// XMP 메타데이터를 가져옵니다. EPS 파일에 XMP 메타데이터가 포함되어 있지 않으면 PS 메타데이터 주석(%%Creator, %%CreateDate, %%Title 등)의 값으로 채워진 새 파일을 얻습니다.
XmpMetadata xmp = document.getXmpMetadata();
```
이 단계에서는 EPS 파일에서 기존 XMP 메타데이터를 검색합니다. EPS 파일에 아직 XMP 메타데이터가 포함되어 있지 않으면 Aspose.Page는 새 파일을 생성하고 PS 메타데이터 주석의 값으로 채웁니다.
## 2단계: "dc:title" 배열 항목 추가
```java
// "dc:title" 배열 항목을 하나 더 추가하세요.
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
이제 XMP 메타데이터의 "dc:title" 속성에 새 배열 항목을 추가합니다. "NewTitle"을 원하는 제목으로 바꾸십시오.
## 3단계: "dc:creator" 배열 항목 추가
```java
// "dc:creator" 배열 항목을 하나 더 추가하세요.
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
마찬가지로 XMP 메타데이터의 "dc:creator" 속성에 새 배열 항목을 추가합니다. "NewCreator"를 원하는 작성자 정보로 바꾸세요.
## 4단계: 출력 EPS 파일 스트림 초기화
```java
// 출력 EPS 파일 스트림 초기화
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
업데이트된 XMP 메타데이터가 포함된 수정된 문서가 저장될 출력 EPS 파일 스트림을 준비합니다.
## 5단계: 변경된 XMP 메타데이터로 문서 저장
```java
//변경된 XMP 메타데이터로 문서 저장
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
업데이트된 XMP 메타데이터가 포함된 문서를 출력 EPS 파일에 저장합니다.
## 결론
축하해요! Java용 Aspose.Page를 사용하여 XMP 메타데이터에 배열 항목을 추가하는 방법을 성공적으로 배웠습니다. 이 강력한 라이브러리는 EPS 파일 조작 프로세스를 단순화하고 문서 처리를 위한 광범위한 기능을 제공합니다.
## 자주 묻는 질문

### 다른 문서 형식과 함께 Java용 Aspose.Page를 사용할 수 있나요?
예, Aspose.Page는 EPS, PDF, XPS를 포함한 다양한 문서 형식을 지원합니다.
### Aspose.Page for Java에 대한 무료 평가판이 있습니까?
 예, 무료 평가판에 액세스할 수 있습니다[여기](https://releases.aspose.com/).
### Java용 Aspose.Page에 대한 설명서는 어디에서 찾을 수 있나요?
 문서를 사용할 수 있습니다[여기](https://reference.aspose.com/page/java/).
### Java용 Aspose.Page를 어떻게 구매할 수 있나요?
 제품을 구매하실 수 있습니다[여기](https://purchase.aspose.com/buy).
### Aspose.Page for Java에 임시 라이선스를 사용할 수 있나요?
 네, 임시 면허를 취득하실 수 있습니다[여기](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
