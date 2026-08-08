---
date: 2026-04-24
description: Aspose.Page를 사용하여 Java XPS에서 사각형 색상을 설정하고 사각형을 추가하는 방법을 배웁니다. 이 가이드는
  Java에서 사각형 추가와 사각형 스트로크 변경을 다룹니다.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Java XPS에서 사각형 추가
second_title: Aspose.Page Java API
title: Java XPS에서 사각형 색상 설정 및 사각형 추가
url: /ko/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS에서 사각형 색상 설정 및 사각형 추가

## 소개
이 가이드에서는 Aspose.Page 라이브러리를 사용하여 Java XPS에서 **사각형 색상 설정** 및 **사각형 추가** 방법을 배웁니다. 보고서를 위한 간단한 도형을 그리든 복잡한 벡터 그래픽을 만들든, 사각형 스타일링을 마스터하면 XPS 문서를 정밀하게 제어할 수 있습니다.  

## 빠른 답변
- **필요한 라이브러리는 무엇인가요?** Aspose.Page for Java  
- **사각형 스트로크를 변경할 수 있나요?** 예, `setStroke` 및 `setStrokeThickness` 사용  
- **CMYK 색상 프로파일을 지원하나요?** 물론입니다 – 예시와 같이 ICC 프로파일을 로드할 수 있습니다  
- **비평가용이 아닌 경우 라이선스가 필요합니까?** 예, 상업용 라이선스가 필요합니다  
- **구현에 얼마나 걸립니까?** 기본 사각형의 경우 일반적으로 10분 미만 소요  

## **set rectangle color**란?
사각형의 색상을 설정한다는 것은 최종 XPS 문서에 도형이 렌더링될 때 사용할 채우기 색상 또는 스트로크 색상을 정의하는 것을 의미합니다. Aspose.Page를 사용하면 RGB, CMYK 또는 사용자 정의 ICC 색상 프로파일을 활용하여 정확한 색상 매칭을 구현할 수 있습니다.

## Aspose.Page를 사용하여 **add rectangle java** 및 **change rectangle stroke**를 하는 이유?
- **전체 기능 API** – 단색 및 그라디언트를 모두 지원합니다.  
- **크로스 플랫폼** – 네이티브 종속성 없이 모든 Java 런타임에서 작동합니다.  
- **풍부한 기하학 지원** – 복잡한 경로를 만들고, 변환을 적용하며, 스트로크 두께를 쉽게 관리합니다.  

## 사전 요구 사항
시작하기 전에 다음을 확인하십시오:

- Java 프로그래밍에 대한 기본 지식.  
- Aspose.Page 라이브러리가 설치되어 있어야 합니다. 없을 경우 [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)에서 다운로드하십시오.  
- 작동하는 Java 개발 환경(IDE, JDK 등).  

## 패키지 가져오기
시작하려면 Java 프로젝트에 필요한 패키지를 가져오세요. Aspose.Page 라이브러리가 클래스패스에 올바르게 추가되었는지 확인하십시오. 기본 예시는 다음과 같습니다:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

이제 제공된 예제를 여러 단계로 나누어 **사각형 추가** 및 **색상 설정**을 Java XPS에서 수행해 보겠습니다.

## 단계 1: 문서 디렉터리 설정
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
`"Your Document Directory"`를 XPS 파일을 읽고/쓰고자 하는 절대 경로로 교체하십시오.

## 단계 2: 새 XPS 문서 만들기
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
이 코드는 도형을 담을 새로운 XPS 문서를 초기화합니다.

## 단계 3: CMYK 단색 스트로크 사각형 추가
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
이 단계에서는 CMYK 단색으로 **스트로크 사각형**을 추가합니다. `setStroke` 메서드는 사각형의 외곽선 색상을 정의하고, `setStrokeThickness`는 선 두께를 제어합니다—**사각형 스트로크 변경**에 적합합니다.

### 팁:
RGB 색상을 원한다면 `createColor` 호출을 `doc.createColor(0, 0, 255)`로 교체하여 단색 파란색 채우기를 적용하십시오.

## 단계 4: 결과 XPS 문서 저장
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
마지막으로 XPS 문서를 디스크에 저장합니다. 이제 `AddRectangle_out.xps` 파일에 정의한 색상과 스트로크를 가진 사각형이 포함됩니다.

## 일반적인 문제 및 해결책
| 문제 | 원인 | 해결책 |
|-------|-------|----------|
| **사각형이 보이지 않음** | 경로 기하학이 잘못되었거나 스트로크 두께가 0으로 설정됨 | 경로 문자열(`"M 20,10 L 220,10 220,100 20,100 Z"`)을 확인하고 `setStrokeThickness`가 0보다 큰지 확인하십시오. |
| **잘못된 색상** | 원하는 색상 공간과 일치하지 않는 ICC 프로파일을 사용함 | RGB의 경우 `doc.createColor(r, g, b)`를 사용하거나 ICC 파일 경로를 다시 확인하십시오. |
| **파일이 저장되지 않음** | `dataDir`이 존재하지 않는 폴더를 가리키거나 쓰기 권한이 없음 | 폴더를 미리 생성하거나 쓰기 가능한 위치를 선택하십시오. |

## 자주 묻는 질문

**Q:** *단일 XPS 문서에 여러 사각형을 추가할 수 있나요?*  
A: 예. 필요한 각 사각형에 대해 기하학 생성 및 스타일링 단계를 반복하면 됩니다.

**Q:** *스트로크가 아닌 사각형의 채우기 색상을 변경하려면 어떻게 해야 하나요?*  
A: `setStroke`와 유사하게 `path.setFill(...)`를 사용하여 단색 브러시로 채우기 색상을 지정하십시오.

**Q:** *Aspose.Page가 복잡한 XPS 문서 조작에 적합한가요?*  
A: 물론입니다. 이 라이브러리는 그라디언트, 변환, 임베디드 폰트 등 고급 기능을 지원합니다.

**Q:** *추가 예제와 커뮤니티 지원을 어디서 찾을 수 있나요?*  
A: 더 많은 코드 샘플과 동료 지원을 위해 [Aspose.Page forum](https://forum.aspose.com/c/page/39)을 탐색하십시오.

**Q:** *구매 전에 Aspose.Page를 체험해 볼 수 있나요?*  
A: 예, API 기능을 평가할 수 있는 [free trial](https://releases.aspose.com/)을 이용해 보십시오.

---

**마지막 업데이트:** 2026-04-24  
**테스트 환경:** Aspose.Page for Java 24.12  
**작성자:** Aspose

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}