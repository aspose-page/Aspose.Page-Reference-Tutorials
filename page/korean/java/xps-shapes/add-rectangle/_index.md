---
date: 2025-12-30
description: Aspose.Page를 사용하여 사각형을 추가함으로써 Java에서 XPS 문서를 만드는 방법을 배워보세요. 원활한 XPS 문서
  조작을 위한 단계별 가이드를 따라가세요.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: XPS 문서 만들기 Java – Aspose.Page로 사각형 추가
url: /ko/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS Document Java 만들기 – 사각형 추가

## 소개
이 포괄적인 튜토리얼에서는 **XPS document Java** 파일을 만들고 Aspose.Page 라이브러리를 사용하여 사각형을 추가하는 방법을 배웁니다. 보고서, 청구서 또는 맞춤형 그래픽을 만들든, 사각형 생성 기술을 마스터하면 XPS 레이아웃을 정밀하게 제어할 수 있습니다. 각 단계를 차근차근 진행하면서 코드 한 줄 한 줄의 이유를 설명하고, 색상 및 스트로크를 맞춤 설정하여 전문적인 결과를 얻는 방법을 보여드립니다.

## 빠른 답변
- **추천 라이브러리는?** Aspose.Page for Java  
- **구현 시간은?** 기본 사각형 하나는 약 10 분 정도  
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 가능하지만, 운영 환경에서는 상용 라이선스가 필요합니다  
- **지원되는 Java 버전은?** Java 8 이상  
- **여러 도형을 추가할 수 있나요?** 예 – 각 도형마다 동일한 절차를 반복하면 됩니다

## 전제 조건
시작하기 전에 다음이 준비되어 있는지 확인하세요:

- Java 프로그래밍 언어에 대한 기본 지식  
- Aspose.Page 라이브러리 설치. 설치가 안 되어 있다면 [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)에서 다운로드할 수 있습니다.  
- 작업 가능한 Java 개발 환경(IDE, JDK, Maven/Gradle 등)

## 패키지 가져오기
프로젝트에 필요한 패키지를 가져옵니다. Aspose.Page 라이브러리가 클래스패스에 올바르게 추가되어 있는지 확인하세요. 기본 예시는 다음과 같습니다:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

이제 예제를 여러 단계로 나누어 Java XPS에서 사각형을 추가하는 방법을 살펴보겠습니다.

## 1단계: 문서 디렉터리 설정
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

`"Your Document Directory"`를 XPS 파일을 저장하고자 하는 폴더 경로로 교체합니다.

## 2단계: 새 XPS 문서 만들기
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

이 코드는 **새로운** XPS 문서를 생성합니다. 이후 도형, 텍스트 또는 이미지를 채워 넣을 수 있습니다.

## 3단계: CMYK 고체 색상 스트로크 사각형 추가
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

이 단계에서는 CMYK 고체 색상으로 스트로크된 사각형을 추가합니다. `geometry` 문자열(`"M 20,10 L 220,10 220,100 20,100 Z"`)을 변경하면 크기와 위치를 조정할 수 있고, `createColor`의 색상 값을 바꾸어 디자인에 맞게 색상을 지정할 수 있습니다.

## 4단계: 결과 XPS 문서 저장
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

마지막으로, 앞서 지정한 디렉터리에 사각형이 추가된 XPS 문서를 저장합니다.

## 일반적인 사용 사례
- **보고서 헤더** – 제목 배경 블록으로 사각형 사용  
- **청구서 표** – 셀이나 구역을 색상 테두리로 강조  
- **맞춤 그래픽** – 여러 사각형을 결합해 복합 도형 생성

## 문제 해결 팁
- **파일을 찾을 수 없음 오류:** `dataDir`이 실제 존재하는 폴더를 가리키는지, ICC 프로파일(`uswebuncoated.icc`)이 존재하는지 확인하세요.  
- **색상이 올바르지 않음:** 사용하려는 색상 공간(CMYK vs. RGB)에 맞는 ICC 프로파일인지 확인합니다.  
- **예상치 못한 크기:** 좌표가 정확히 반영되도록 `geometry` 문자열을 조정합니다.

## 결론
축하합니다! 이제 **XPS document Java** 파일을 만들고 Aspose.Page를 사용해 사각형을 추가하는 방법을 익혔습니다. 이 기반을 바탕으로 더 풍부한 XPS 문서를 제작하고, 그래픽을 맞춤화하며, 도형을 다양한 워크플로에 통합할 수 있습니다.

## 자주 묻는 질문

### 단일 XPS 문서에 여러 사각형을 추가할 수 있나요?
예, 튜토리얼에 설명된 단계를 반복하면 원하는 만큼 사각형을 추가할 수 있습니다.

### 사각형 색상을 어떻게 변경하나요?
`createColor` 메서드의 색상 값을 수정하면 원하는 색상으로 변경할 수 있습니다.

### Aspose.Page가 복잡한 XPS 문서 조작에 적합한가요?
물론입니다! Aspose.Page는 다양한 XPS 문서 작업을 처리할 수 있는 강력한 기능을 제공합니다.

### 추가 예제와 지원을 어디서 찾을 수 있나요?
더 많은 예제는 [Aspose.Page forum](https://forum.aspose.com/c/page/39)에서 확인하고, 커뮤니티에 도움을 요청하세요.

### 구매 전에 Aspose.Page를 체험해볼 수 있나요?
예, [free trial](https://releases.aspose.com/)을 통해 Aspose.Page의 기능을 직접 체험해볼 수 있습니다.

## Frequently Asked Questions

**Q: Does this approach work with Java 11 or newer?**  
A: Yes, the Aspose.Page library is compatible with Java 8 and later, including Java 11, 17, and beyond.

**Q: Can I embed images inside the rectangle area?**  
A: You can add an `XpsImage` element and position it over or inside the rectangle using the same geometry coordinates.

**Q: How do I set a fill color instead of just a stroke?**  
A: Call `path.setFill(...)` with a solid color brush created via `doc.createSolidColorBrush(...)`.

**Q: Is it possible to rotate the rectangle?**  
A: Apply a transformation matrix to the path using `path.setTransform(...)` to achieve rotation or scaling.

**Q: What licensing is required for production use?**  
A: A commercial Aspose.Page license is required for deployment; the free trial is limited to evaluation and development.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**마지막 업데이트:** 2025-12-30  
**테스트 환경:** Aspose.Page for Java 24.12 (latest)  
**작성자:** Aspose  

---