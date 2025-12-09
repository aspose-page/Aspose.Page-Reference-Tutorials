---
date: 2025-11-30
description: Aspose.Page를 사용하여 Java에서 EPS 파일을 자르는 방법을 배우세요 – Aspose.Page 라이브러리를 활용한
  EPS 자르기 방법을 단계별로 명확하게 안내하는 튜토리얼입니다.
linktitle: Crop EPS File in Java
second_title: Aspose.Page Java API
title: Java에서 EPS 파일을 자르는 방법 – Aspose.Page 가이드
url: /ko/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java에서 EPS 파일 자르기 – Aspose.Page와 함께하는 단계별 가이드

## 소개
Java 애플리케이션에서 **EPS 파일을 프로그래밍 방식으로 자르는 방법**이 필요하다면, 바로 여기가 정답입니다. 이 튜토리얼에서는 강력한 Aspose.Page for Java 라이브러리를 사용해 EPS 이미지를 자르는 전체 과정을 단계별로 살펴봅니다. 가이드를 마치면 EPS 크롭이 왜 중요한지 이해하고, 필요한 정확한 코드를 확인하며, 자체 프로젝트에 솔루션을 통합할 준비가 됩니다.

## 빠른 답변
- **Java에서 EPS 자르기를 처리하는 라이브러리는 무엇인가요?** Aspose.Page for Java.  
- **기본적인 크롭을 구현하는 데 얼마나 걸리나요?** 약 5‑10분.  
- **개발에 라이선스가 필요합니까?** 평가용 무료 체험판으로 가능하지만, 프로덕션에서는 상용 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** Java 8 이상.  
- **사용자 정의 경계 상자를 정의할 수 있나요?** 예 – 필요한 좌표를 제공하면 됩니다.

## EPS 크롭이란 무엇이며 왜 사용하나요?
Encapsulated PostScript (EPS)는 벡터 이미지를 저장하고, 표시 영역을 정의하는 경계 상자를 포함하는 그래픽 포맷입니다. EPS 파일을 크롭한다는 것은 새로운 경계 상자를 만들어 원하는 영역만 남기는 것을 의미합니다. 이는 흰 여백을 제거하거나 로고를 추출하거나, 원본 파일을 다시 만들지 않고도 그래픽을 더 타이트한 레이아웃에 맞추고 싶을 때 유용합니다.

## 전제 조건
코드를 진행하기 전에 다음이 준비되어 있어야 합니다:

- **Aspose.Page for Java** 라이브러리가 설치되어 있어야 합니다 – 공식 페이지에서 [여기](https://releases.aspose.com/page/java/) 다운로드하세요.  
- **Java Development Kit (JDK)** 8 이상이 머신에 설치되어 있어야 합니다.  
- **입력 EPS(`input.eps`)와 결과물인 크롭된 파일(`output_crop.eps`)을 저장할 폴더**가 필요합니다.

## 패키지 가져오기
먼저 필요한 Java 클래스를 가져옵니다. 이 코드 스니펫은 원본 튜토리얼과 정확히 동일합니다:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

### 단계 1: 문서 디렉터리 및 입력 스트림 설정
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
여기서는 소스 EPS 파일이 들어 있는 폴더를 지정하고, 파일을 읽기 위한 스트림을 엽니다.

### 단계 2: PsDocument 객체 초기화
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
`PsDocument` 클래스는 메모리 내 EPS 문서를 나타내며, 문서의 속성을 조회하고 조작할 수 있게 해줍니다.

### 단계 3: 초기 경계 상자 추출
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
원본 경계 상자를 추출하면 현재 표시 영역의 좌표를 얻을 수 있어, 얼마나 잘라야 할지 판단하는 데 도움이 됩니다.

### 단계 4: 출력 스트림 생성
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
크롭된 EPS를 기록할 스트림을 엽니다.

### 단계 5: 새 경계 상자 정의 및 크롭
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
보존하고 싶은 영역을 정의하는 네 개의 좌표(좌하단 x, 좌하단 y, 우상단 x, 우상단 y)를 제공하세요. `cropEps` 메서드가 실제 크롭을 수행하고 결과를 `output_crop.eps`에 기록합니다.

## 일반적인 문제 및 해결책
- **좌표 오류:** EPS는 포인트(1/72 인치)를 사용합니다. 크롭 결과가 어색하면 단위 변환을 다시 확인하세요.  
- **파일을 찾을 수 없음 오류:** `dataDir`이 올바른 경로 구분자(`/` 또는 `\`)로 끝나는지 확인하세요.  
- **라이선스 예외:** 유효한 라이선스 없이 코드를 실행하면 출력에 워터마크가 추가될 수 있습니다. 프로덕션 사용 전 임시 또는 영구 라이선스를 적용하세요.

## 자주 묻는 질문

**Q: Aspose.Page가 Java 8과 호환되나요?**  
A: 예, Aspose.Page는 Java 8 및 이후 버전에서 작동합니다.

**Q: Aspose.Page를 상업 프로젝트에 사용할 수 있나요?**  
A: 물론입니다. 프로덕션 배포에는 상용 라이선스가 필요합니다. 라이선스는 [여기](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

**Q: 추가 자료와 커뮤니티 지원을 어디서 찾을 수 있나요?**  
A: 공식 [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)에서 토론, 코드 샘플, 문제 해결 팁을 확인하세요.

**Q: 테스트용 무료 체험판이 있나요?**  
A: 예, 릴리스 페이지에서 무료 체험판을 다운로드할 수 있습니다. [여기](https://releases.aspose.com/)에서 확인하세요.

**Q: 단기 평가용 임시 라이선스는 어떻게 받나요?**  
A: 임시 라이선스는 라이선스 포털에서 요청할 수 있습니다. [여기](https://purchase.aspose.com/temporary-license/)에서 신청하세요.

## 결론
이제 Aspose.Page를 사용해 Java에서 **EPS 파일을 어떻게 자르는지** 알게 되었습니다. 사용자 정의 경계 상자를 정의하고 `cropEps`를 호출하면 몇 줄의 코드만으로 원하지 않는 여백을 제거하거나 EPS 그래픽의 특정 부분을 분리할 수 있습니다. 이 스니펫을 문서 처리 파이프라인에 통합하면 EPS 조작을 자동화하고 시각 자산을 깔끔하게 관리할 수 있습니다.

---

**Last Updated:** 2025-11-30  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}