---
title: Java를 사용하여 XMP에서 명명된 값 변경
linktitle: Java를 사용하여 XMP에서 명명된 값 변경
second_title: Aspose.페이지 자바 API
description: Java용 Aspose.Page를 살펴보세요 - 간소화된 문서 처리를 위한 단계별 가이드를 통해 EPS 파일의 XMP 메타데이터를 쉽게 변경할 수 있습니다.
weight: 16
url: /ko/java/xmp-metadata-manipulation/change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java를 사용하여 XMP에서 명명된 값 변경

문서 조작 영역에서 Java용 Aspose.Page는 개발자가 EPS 파일의 XMP 메타데이터로 원활하게 작업할 수 있도록 지원하는 강력한 도구로 돋보입니다. 이 단계별 가이드는 Aspose.Page for Java를 사용하여 XMP에서 명명된 값을 변경하는 과정을 안내합니다. 자세한 내용을 살펴보기 전에 먼저 소개를 통해 상황을 살펴보겠습니다.
## 소개
Aspose.Page for Java는 EPS 파일의 조작 및 처리를 용이하게 하는 강력한 Java 라이브러리입니다. 이러한 파일 내에서 XMP 메타데이터를 처리할 때 Aspose.Page는 개발자에게 포괄적인 기능 세트를 제공합니다. 이 튜토리얼에서는 XMP에서 명명된 값을 변경하는 방법에 중점을 두고 문서 처리 기능을 향상시키려는 개발자에게 명확하고 간결한 가이드를 제공합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
1. Java 개발 환경: 컴퓨터에 Java 개발 환경이 설정되어 있는지 확인하십시오.
2.  Aspose.Page for Java 라이브러리: Aspose.Page for Java 라이브러리를 다운로드하여 프로젝트에 통합하세요. 라이브러리와 자세한 문서를 찾을 수 있습니다[여기](https://reference.aspose.com/page/java/).
3. 샘플 EPS 파일: 실험을 위해 샘플 EPS 파일을 준비합니다. 없는 경우 제공된 "xmp4.eps"라는 예제 파일을 사용할 수 있습니다.
## 패키지 가져오기
프로세스를 시작하려면 Java 코드에 필요한 패키지를 가져옵니다. 이러한 패키지는 Java용 Aspose.Page와 상호 작용하는 데 필수적입니다. Java 파일 시작 부분에 다음 줄을 포함합니다.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
이제 Aspose.Page for Java를 사용하여 XMP에서 명명된 값을 변경하는 프로세스를 여러 단계로 나누어 보겠습니다.
## 1단계: 입력 EPS 파일 스트림 초기화
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
        
// 입력 EPS 파일 스트림 초기화
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```
## 2단계: PsDocument 초기화
```java
PsDocument document = new PsDocument(psStream);
```
## 3단계: XMP 메타데이터 가져오기
```java
// XMP 메타데이터를 가져옵니다. EPS 파일에 XMP 메타데이터가 포함되어 있지 않으면 PS 메타데이터 주석(%%Creator, %%CreateDate, %%Title 등)의 값으로 채워진 새 파일을 얻습니다.
XmpMetadata xmp = document.getXmpMetadata();
```
## 4단계: XMP에서 새 값 설정
```java
// "xmpTPg:MaxPageSize" 구조의 명명된 값 "stDim:unit"에 대해 새 문자열 값 "Inches"를 설정합니다.
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```
## 5단계: 출력 EPS 파일 스트림 초기화
```java
// 출력 EPS 파일 스트림 초기화
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```
## 6단계: 변경된 XMP 메타데이터로 문서 저장
```java
//변경된 XMP 메타데이터로 문서 저장
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 7단계: 입력 EPS 스트림 닫기
```java
// 입력 EPS 스트림 닫기
psStream.close();
```
이 단계별 가이드는 Aspose.Page for Java를 사용하여 XMP에서 명명된 값을 변경하는 체계적인 접근 방식을 보장합니다. 다음 단계를 수행하면 이 기능을 Java 애플리케이션에 원활하게 통합할 수 있습니다.
## 결론
결론적으로 Java용 Aspose.Page는 EPS 파일의 XMP 메타데이터 작업 프로세스를 단순화합니다. 이 튜토리얼은 XMP에서 명명된 값을 효율적으로 변경하여 문서 처리 기능을 향상시키는 지식을 제공합니다.
## 자주 묻는 질문
### 다른 프로그래밍 언어와 함께 Java용 Aspose.Page를 사용할 수 있나요?
Aspose.Page는 주로 Java를 지원하지만 Aspose는 다양한 프로그래밍 언어에 대해 유사한 라이브러리를 제공합니다.
### Aspose.Page for Java에 대한 무료 평가판이 있습니까?
 예, Aspose.Page for Java의 무료 평가판을 탐색할 수 있습니다.[여기](https://releases.aspose.com/).
### Aspose.Page for Java에 대한 추가 지원과 토론은 어디서 찾을 수 있나요?
 방문하다[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 커뮤니티 지원 및 토론을 위해.
### Aspose.Page for Java의 임시 라이선스를 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### Java용 Aspose.Page를 어디서 구입할 수 있나요?
 Java용 Aspose.Page를 구입하려면 다음을 방문하세요.[구매 페이지](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
