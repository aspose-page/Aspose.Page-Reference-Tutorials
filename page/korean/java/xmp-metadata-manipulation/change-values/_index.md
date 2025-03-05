---
title: Java를 사용하여 XMP에서 값 변경
linktitle: Java를 사용하여 XMP에서 값 변경
second_title: Aspose.페이지 자바 API
description: Java용 Aspose.Page를 사용하여 EPS 문서를 향상하세요. 맞춤형 전문 콘텐츠를 위해 XMP 메타데이터를 손쉽게 수정할 수 있습니다. #자바개발
type: docs
weight: 17
url: /ko/java/xmp-metadata-manipulation/change-values/
---
## 소개
문서 처리 및 조작 영역에서 Java용 Aspose.Page는 강력한 도구로 돋보입니다. 이 튜토리얼에서는 Aspose.Page 라이브러리와 함께 Java를 사용하여 EPS(Encapsulated PostScript) 문서에서 XMP(Extensible Metadata Platform) 값을 변경하는 프로세스를 살펴봅니다. 제공된 단계별 가이드를 따르면 메타데이터를 쉽게 수정하여 문서를 특정 요구 사항에 맞게 조정하는 방법을 배울 수 있습니다.
## 전제 조건
이 튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. Java 개발 환경: 컴퓨터에 Java 개발 환경이 작동하는지 확인하세요.
2.  Aspose.Page for Java 라이브러리: Aspose.Page for Java 라이브러리를 다운로드하고 설치하세요. 필요한 패키지를 찾을 수 있습니다[여기](https://releases.aspose.com/page/java/).
## 패키지 가져오기
필요한 패키지를 Java 프로젝트로 가져오는 것부터 시작하세요. 이러한 패키지는 EPS 문서와 상호 작용하고 조작하는 데 필수적입니다.
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
EPS 문서에서 XMP 메타데이터를 검색합니다. EPS 파일에 XMP 메타데이터가 포함되어 있지 않으면 %%Creator, %%CreateDate 및 %%Title과 같은 PS 메타데이터 주석의 값을 사용하여 새 파일이 생성됩니다.
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
// 입력 EPS 파일 스트림 초기화
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// XMP 메타데이터를 가져옵니다. EPS 파일에 XMP 메타데이터가 포함되어 있지 않으면 PS 메타데이터 주석의 값으로 새 파일이 생성됩니다.
XmpMetadata xmp = document.getXmpMetadata();
```
## 2단계: "ModifyDate" 값 변경
원하는 날짜를 반영하도록 XMP 메타데이터에서 "ModifyDate" 값을 수정합니다.
```java
// "ModifyDate" 값 변경
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## 3단계: "Creator" 값 변경
문서 작성자를 지정하려면 XMP 메타데이터에서 "Creator" 값을 업데이트하세요.
```java
// "작성자" 값 변경
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## 4단계: "제목" 값 변경
XMP 메타데이터에서 "제목" 값을 수정하여 문서에 적절한 제목을 설정합니다.
```java
//"제목" 값 변경
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## 5단계: 변경된 XMP 메타데이터로 문서 저장
업데이트된 XMP 메타데이터가 포함된 문서를 새 EPS 파일에 저장합니다.
```java
// 출력 EPS 파일 스트림 초기화
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//변경된 XMP 메타데이터로 문서 저장
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 결론
축하해요! Aspose.Page for Java를 사용하여 EPS 문서에서 XMP 값을 변경하는 프로세스를 성공적으로 탐색했습니다. 이 튜토리얼에서는 메타데이터를 수정하여 문서가 특정 요구 사항에 원활하게 부합하도록 하는 지식을 제공합니다.
## 자주 묻는 질문
### Q: XMP 값을 수정할 때 시간대 고려 사항을 어떻게 처리할 수 있습니까?
 활용`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` 시간대 설정의 일관성을 보장합니다.
### Q: 단일 작업으로 여러 XMP 값을 변경할 수 있습니까?
 예,`put` 원하는 각 값에 대한 방법을 사용하면 여러 XMP 값을 동시에 수정할 수 있습니다.
### Q: Aspose.Page for Java에 대한 추가 문서는 어디서 찾을 수 있나요?
 포괄적인 문서 살펴보기[여기](https://reference.aspose.com/page/java/).
### Q: Aspose.Page for Java에 대한 무료 평가판이 있습니까?
 예, 무료 평가판에 액세스할 수 있습니다[여기](https://releases.aspose.com/).
### Q: Aspose.Page for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시 라이센스 취득[여기](https://purchase.aspose.com/temporary-license/).