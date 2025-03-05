---
title: Java를 사용하여 XMP에 단순 속성 추가
linktitle: Java를 사용하여 XMP에 단순 속성 추가
second_title: Aspose.페이지 자바 API
description: EPS 파일의 XMP 메타데이터에 속성을 추가하는 방법에 대한 가이드를 통해 Aspose.Page에서 Java의 잠재력을 알아보세요. 손쉽게 문서 처리 수준을 높이세요!
type: docs
weight: 14
url: /ko/java/xmp-metadata-manipulation/add-simple-properties/
---
## 소개
끊임없이 진화하는 문서 처리 환경에서는 메타데이터를 효율적으로 관리하는 것이 중요합니다. Aspose.Page for Java는 개발자가 XMP(Extensible Metadata Platform) 데이터를 원활하게 조작할 수 있도록 지원합니다. 이 튜토리얼에서는 Java를 사용하여 XMP에 간단한 속성을 추가하는 과정을 살펴보고 포괄적인 단계별 가이드를 제공합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- Java 프로그래밍에 대한 기본 지식.
-  Java 라이브러리용 Aspose.Page가 설치되었습니다. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/page/java/).
- 메타데이터가 포함된 샘플 EPS 파일입니다. 없으면 제공된 "xmp3.eps" 파일을 사용하세요.
## 패키지 가져오기
프로젝트를 시작하려면 필요한 패키지를 가져와야 합니다.
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
## 2단계: 날짜 속성 추가
```java
// 날짜 속성 "xmp:Date1" 값 추가
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## 3단계: 정수 속성 추가
```java
// 정수 속성 "xmp:Intg1" 값 추가
xmp.put("xmp:Intg1", new XmpValue(111));
```
## 4단계: 이중 속성 추가
```java
// 이중 속성 "xmp:Double1" 값 추가
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## 5단계: 문자열 속성 추가
```java
// 문자열 속성 "xmp:String1" 값 추가
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## 6단계: 문서 저장
```java
// 출력 EPS 파일 스트림 초기화
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//변경된 XMP 메타데이터로 문서 저장
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 7단계: 스트림 닫기
```java
// 입력 EPS 스트림 닫기
psStream.close();
```
## 결론
Aspose.Page for Java는 EPS 파일에서 XMP 메타데이터를 조작하는 프로세스를 단순화합니다. 이 단계별 가이드를 따르면 간단한 속성을 쉽게 추가하여 문서의 메타데이터를 향상할 수 있습니다.
## 자주 묻는 질문
### 다른 프로그래밍 언어와 함께 Java용 Aspose.Page를 사용할 수 있나요?
Aspose.Page는 주로 Java를 지원하지만 .NET과 같은 다른 언어에도 사용할 수 있는 버전이 있습니다.
### Aspose.Page for Java에 대한 무료 평가판을 사용할 수 있습니까?
 예, 무료 평가판을 통해 Aspose.Page의 기능을 탐색할 수 있습니다[여기](https://releases.aspose.com/).
### Aspose.Page for Java에 대한 자세한 문서는 어디서 찾을 수 있나요?
 문서를 사용할 수 있습니다[여기](https://reference.aspose.com/page/java/).
### Aspose.Page for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허 취득 가능[여기](https://purchase.aspose.com/temporary-license/).
### Java용 Aspose.Page를 어디서 구입할 수 있나요?
 해당 상품을 구매하실 수 있습니다[여기](https://purchase.aspose.com/buy).