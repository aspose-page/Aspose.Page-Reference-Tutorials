---
title: Aspose.Page를 사용하여 Java에서 EPS 파일 크기 조정
linktitle: Java에서 EPS 파일 크기 조정
second_title: Aspose.페이지 자바 API
description: Java용 Aspose.Page를 사용하여 Java에서 EPS 파일 크기를 쉽게 조정하는 방법을 알아보세요. 단계별 지침은 당사의 종합 가이드를 따르세요.
weight: 11
url: /ko/java/manipulation-eps/resize/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용하여 Java에서 EPS 파일 크기 조정

## 소개
강력한 Aspose.Page 라이브러리를 사용하여 Java에서 EPS 파일 크기를 조정하는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. EPS 이미지의 크기를 프로그래밍 방식으로 조정해야 한다면 잘 찾아오셨습니다. 이 튜토리얼에서는 포인트, 인치, 밀리미터 및 백분율을 포함한 다양한 크기 조정 옵션을 탐색하여 특정 요구 사항에 필요한 유연성을 제공합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 사항이 있는지 확인하세요.
- 컴퓨터에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Java 라이브러리용 Aspose.Page. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/page/java/).
- Java 프로그래밍에 대한 기본적인 이해.
## 패키지 가져오기
Java 프로젝트에서 Aspose.Page 기능을 사용하는 데 필요한 가져오기가 있는지 확인하세요. 예는 다음과 같습니다.
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
이제 각 크기 조정 옵션에 대해 튜토리얼을 여러 단계로 나누어 보겠습니다.
## 포인트를 사용하여 EPS 크기 조정
### 1단계: 입력 스트림 설정
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### 2단계: PsDocument 개체 초기화
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### 3단계: EPS 이미지의 현재 크기 추출
```java
Dimension oldSize = doc.extractEpsSize();
```
### 4단계: 출력 스트림 생성
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### 5단계: 크기 조정 및 포인트 단위로 저장
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## 인치를 사용하여 EPS 크기 조정
예제 1과 유사한 단계를 수행하여 "포인트"를 "인치"로 바꾸고 그에 따라 새 크기를 조정합니다.
## 밀리미터를 사용하여 EPS 크기 조정
예제 1과 유사한 단계를 수행하여 "포인트"를 "밀리미터"로 바꾸고 이에 따라 새 크기를 조정합니다.
## 백분율을 사용하여 EPS 크기 조정
예제 1과 유사한 단계를 수행하여 "포인트"를 "백분율"로 바꾸고 이에 따라 새 크기를 조정합니다.
## 결론
축하해요! Aspose.Page를 사용하여 Java에서 EPS 파일 크기를 조정하는 방법을 성공적으로 배웠습니다. 이 가이드는 다양한 옵션을 제공하므로 특정 요구 사항에 맞게 크기 조정 프로세스를 맞춤화할 수 있습니다.

## 자주 묻는 질문
### 이 라이브러리를 다른 이미지 형식에 사용할 수 있나요?
아니요, Aspose.Page는 PostScript 및 EPS 파일을 처리하기 위해 특별히 설계되었습니다.
### Aspose.Page for Java에 대한 무료 평가판이 있습니까?
예, 무료 평가판을 살펴볼 수 있습니다[여기](https://releases.aspose.com/).
### 추가 도움말과 토론은 어디에서 찾을 수 있나요?
 방문하다[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지역 사회 지원을 위해.
### 임시 라이센스는 어떻게 얻을 수 있나요?
 임시면허를 취득할 수 있습니다.[여기](https://purchase.aspose.com/temporary-license/).
### 사용 가능한 예시 프로젝트가 있나요?
 예, 문서를 확인하세요[여기](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
