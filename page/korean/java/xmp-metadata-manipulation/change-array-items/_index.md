---
title: Java를 사용하여 XMP에서 배열 항목 변경
linktitle: Java를 사용하여 XMP에서 배열 항목 변경
second_title: Aspose.페이지 자바 API
description: Java용 Aspose.Page를 사용하여 XMP에서 배열 항목을 변경하는 방법을 알아보세요. 단계별 가이드를 통해 손쉽게 메타데이터를 수정하세요. 지금 EPS 문서를 강화하세요!
type: docs
weight: 15
url: /ko/java/xmp-metadata-manipulation/change-array-items/
---
## 소개
Java용 Aspose.Page를 사용하여 XMP에서 배열 항목을 변경하는 방법에 대한 포괄적인 가이드에 오신 것을 환영합니다! Aspose.Page는 EPS 파일의 XMP 메타데이터를 원활하게 사용할 수 있는 강력한 Java 라이브러리입니다. 이 튜토리얼에서는 XMP 메타데이터 내의 배열 항목을 수정하는 과정을 안내하여 EPS 문서를 향상하고 사용자 정의하는 데 도움을 드립니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- 시스템에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Java용 Aspose.Page 라이브러리. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/page/java/).
## 패키지 가져오기
시작하려면 Java 프로젝트에 필요한 패키지를 가져오세요. 프로젝트에 Aspose.Page 라이브러리가 포함되어 있는지 확인하세요.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;

```
## 1단계: XMP 메타데이터 가져오기
먼저 EPS 파일에서 XMP 메타데이터를 검색합니다. EPS 파일에 아직 XMP 메타데이터가 포함되어 있지 않은 경우 %%Creator, %%CreateDate, %%Title 등과 같은 PS 메타데이터 주석의 값을 사용하여 새 EPS 파일이 생성됩니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 입력 EPS 파일 스트림 초기화
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// XMP 메타데이터를 가져옵니다. EPS 파일에 XMP 메타데이터가 포함되어 있지 않으면 PS 메타데이터 주석의 값으로 새 파일이 채워집니다.
XmpMetadata xmp = document.getXmpMetadata();
```
## 2단계: "dc:title" 배열 항목 설정
이제 인덱스 0에 "dc:title" 배열 항목을 새 값으로 설정해 보겠습니다.
```java
// 인덱스 0으로 "dc:title" 배열 항목 설정
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```
## 3단계: "dc:creator" 배열 항목 설정
마찬가지로, 새 작성자 값을 사용하여 인덱스 0에 "dc:creator" 배열 항목을 설정합니다.
```java
// "dc:creator" 배열 항목을 인덱스 0으로 설정
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```
## 4단계: 출력 EPS 파일 스트림 초기화
수정된 문서가 저장될 출력 EPS 파일 스트림을 준비합니다.
```java
// 출력 EPS 파일 스트림 초기화
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
## 5단계: 변경된 XMP 메타데이터로 문서 저장
업데이트된 XMP 메타데이터로 문서를 저장합니다.
```java
//변경된 XMP 메타데이터로 문서 저장
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 결론
축하해요! Java용 Aspose.Page를 사용하여 XMP에서 배열 항목을 변경하는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 단계별 지침을 제공하여 사용자 정의된 메타데이터로 EPS 문서를 쉽게 향상시킬 수 있습니다.

## 자주 묻는 질문
### 다른 프로그래밍 언어와 함께 Java용 Aspose.Page를 사용할 수 있나요?
Aspose.Page는 주로 Java용으로 설계되었지만 Aspose는 다른 언어에도 유사한 라이브러리를 제공합니다.
### Aspose.Page for Java에 대한 자세한 문서는 어디서 찾을 수 있나요?
 문서를 사용할 수 있습니다[여기](https://reference.aspose.com/page/java/).
### Aspose.Page for Java에 대한 무료 평가판이 있습니까?
 예, 무료 평가판을 받을 수 있습니다[여기](https://releases.aspose.com/).
### Aspose.Page for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Java용 Aspose.Page 정식 버전은 어디서 구입할 수 있나요?
 정식 버전을 구매하실 수 있습니다[여기](https://purchase.aspose.com/buy).