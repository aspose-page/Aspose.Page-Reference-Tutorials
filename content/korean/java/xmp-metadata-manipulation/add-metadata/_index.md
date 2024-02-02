---
title: Java를 사용하여 XMP에 메타데이터 추가
linktitle: Java를 사용하여 XMP에 메타데이터 추가
second_title: Aspose.페이지 자바 API
description: Aspose.Page for Java의 원활한 통합을 살펴보고 EPS 파일에 XMP 메타데이터를 손쉽게 추가하는 방법을 알아보세요. 지금 귀하의 문서 관리 게임을 한 단계 더 발전시키세요!
type: docs
weight: 11
url: /ko/java/xmp-metadata-manipulation/add-metadata/
---
## 소개
Java를 사용하여 XMP 정보를 추가하여 문서의 메타데이터를 향상시키고 싶으십니까? 더 이상 보지 마세요! 이 단계별 가이드는 Aspose.Page for Java 라이브러리를 사용하여 EPS 파일에 메타데이터를 추가하는 과정을 안내합니다. Aspose.Page는 Java 애플리케이션에서 문서 조작 작업을 단순화하는 강력한 도구입니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
-  Java 라이브러리용 Aspose.Page가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/page/java/).
- 수정하려는 EPS 파일입니다.
## 패키지 가져오기
먼저 필요한 패키지를 Java 프로그램으로 가져옵니다.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## 1단계: XMP 메타데이터 가져오기
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 입력 EPS 파일 스트림 초기화
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// XMP 메타데이터를 가져옵니다. EPS 파일에 XMP 메타데이터가 포함되어 있지 않으면 PS 메타데이터 주석(%%Creator, %%CreateDate, %%Title 등)의 값을 사용하여 새 파일이 생성됩니다.
XmpMetadata xmp = document.getXmpMetadata();
```
"문서 디렉토리"를 문서가 저장된 실제 경로로 바꾸십시오.

## 2단계: CreatorTool 값 검색
```java
// "CreatorTool" 값 가져오기
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## 3단계: CreateDate 값 검색
```java
// "CreateDate" 값 가져오기
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## 4단계: 제목 값 검색
```java
// "제목" 값 가져오기
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## 5단계: 형식 값 검색
```java
//"형식" 값 가져오기
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## 6단계: 창조자 가치 검색
```java
// "창조자" 가치 얻기
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## 7단계: MetadataDate 값 검색
```java
// "MetadataDate" 값 가져오기
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## 8단계: 새 XMP 메타데이터로 문서 저장
```java
// 출력 EPS 파일 스트림 초기화
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// 새로운 XMP 메타데이터로 문서 저장
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
마지막으로 입력 EPS 스트림을 닫는 것을 잊지 마십시오.
```java
// 입력 EPS 스트림 닫기
psStream.close();
```
이제 Java용 Aspose.Page를 사용하여 EPS 파일에 메타데이터를 성공적으로 추가했습니다!
## 결론
이 튜토리얼에서는 Aspose.Page for Java 라이브러리를 사용하여 EPS 파일에 XMP 메타데이터를 추가하는 프로세스를 살펴보았습니다. 이 강력한 도구를 사용하면 문서를 원활하게 조작하여 전반적인 문서 관리 경험을 향상시킬 수 있습니다.
## 자주 묻는 질문
### Q: Java용 Aspose.Page는 무료로 사용할 수 있나요?
 A: Aspose.Page for Java는 상용 제품입니다. 무료 평가판을 통해 기능을 탐색할 수 있습니다.[여기](https://releases.aspose.com/).
### Q: Java용 Aspose.Page에 대한 설명서는 어디서 찾을 수 있나요?
 A: 문서를 사용할 수 있습니다.[여기](https://reference.aspose.com/page/java/).
### Q: Aspose.Page for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 A: 임시 면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Q: Aspose.Page for Java는 어떤 파일 형식을 지원합니까?
A: Aspose.Page for Java는 EPS, PDF, XPS 등 다양한 형식을 지원합니다.
### Q: Java용 Aspose.Page를 구입할 수 있나요?
 A: 예, Java용 Aspose.Page를 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy).