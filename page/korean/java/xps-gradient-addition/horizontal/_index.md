---
date: 2026-03-13
description: Aspose.Page를 사용하여 Java에서 XPS 문서에 그라데이션을 추가하는 방법과 눈부신 수평 효과를 위한 그라데이션
  스톱을 맞춤 설정하는 방법을 배워보세요.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Java XPS에서 그라디언트 추가하기 – 수평 그라디언트
url: /ko/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS에서 그라디언트 추가 방법 – 수평 그라디언트

## 소개
Java를 사용하여 XPS 문서에 **그라디언트를 추가하는 방법**에 대한 단계별 가이드에 오신 것을 환영합니다. 이 튜토리얼에서는 수평 그라디언트를 추가하는 방법, 시각적 완성도에 왜 중요한지, 그리고 정밀한 색상 제어를 위해 **그라디언트 스톱을 사용자 정의하는 방법**을 배웁니다. Aspose.Page for Java는 XPS(XML Paper Specification) 문서 작업을 간단하게 만들어 주어, 저수준 파일 처리보다 디자인에 집중할 수 있게 합니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Page for Java  
- **어떤 Java 버전이 작동하나요?** Java 8 이상 런타임이면 모두 가능  
- **라이선스가 필요합니까?** 개발에는 무료 체험판을 사용할 수 있으며, 운영 환경에서는 상용 라이선스가 필요합니다  
- **그라디언트 방향을 변경할 수 있나요?** 예 – 선형 브러시의 시작/끝 점을 수정하면 됩니다  
- **여러 그라디언트를 추가할 수 있나요?** 물론 가능합니다 – 다른 브러시로 경로 생성 단계를 반복하면 됩니다  

## XPS에서 수평 그라디언트란?
수평 그라디언트는 형태 전체를 가로 방향(왼쪽에서 오른쪽)으로 색상이 부드럽게 전환되는 효과입니다. XPS에서는 정의된 **그라디언트 스톱** 사이를 보간하는 선형 그라디언트 브러시로 표현됩니다. 이 시각 효과는 배너, 버튼, 배경 채우기 등에 흔히 사용됩니다.

## 왜 Aspose.Page for Java를 사용해야 할까요?
- **전체 XPS 지원** – 타사 도구 없이 생성, 편집 및 렌더링 가능  
- **간단한 API** – `XpsDocument`, `XpsPath`, `XpsGradientBrush`와 같은 고수준 객체가 XML 복잡성을 숨깁니다  
- **성능** – 대용량 문서 및 배치 처리에 최적화되었습니다  

## 사전 요구 사항
1. **Java 개발 환경** – 최신 JDK를 [java.com](https://www.java.com)에서 설치합니다.  
2. **Aspose.Page for Java 라이브러리** – [Aspose.Page for Java 문서](https://reference.aspose.com/page/java/)에서 JAR 파일을 다운로드합니다.  

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다. 이러한 import는 문서 생성, 그라디언트 처리 및 기본 기하학에 접근할 수 있게 해줍니다.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## 단계 1: XPS 문서 초기화
`XpsDocument` 인스턴스를 새로 생성하고 결과를 저장할 폴더를 지정합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## 단계 2: 수평 그라디언트 만들기
**그라디언트 스톱** 목록을 정의하여 각 전환 지점의 색상과 위치를 제어합니다. 아래 예제는 활기찬 무지개와 같은 그라디언트를 생성합니다.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### 그라디언트 스톱 사용자 정의 방법
- **색상** – `doc.createColor(alpha, red, green, blue)`를 사용하여 任意 ARGB 값을 설정합니다.  
- **위치** – 두 번째 인수(`0`과 `1` 사이의 `float`)는 그라디언트 라인에서 스톱이 나타나는 위치를 정의합니다. 이 값을 조정하여 색상을 왼쪽이나 오른쪽으로 이동시킬 수 있습니다.

## 단계 3: 그라디언트가 적용된 경로 추가
사각형 경로를 만들고 필요하면 변환을 적용한 뒤, 선형 그라디언트 브러시로 채웁니다. 브러시는 두 점(`(10,0)`에서 `(228,0)`)을 사용해 수평 효과를 만듭니다. Y 좌표가 동일하기 때문에 이 브러시는 **수평 그라디언트 브러시** 역할을 합니다.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**팁:** 여러 경로에 동일한 `stops` 리스트를 재사용하면 성능이 향상될 수 있지만, 새 스톱을 추가하기 전에 `clear()` 하는 것을 잊지 마세요.

## 단계 4: 문서 저장
XPS 파일을 디스크에 저장합니다. 이제 모든 XPS 뷰어에서 열어 수평 그라디언트가 적용된 모습을 확인할 수 있습니다.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## 여러 그라디언트 적용 방법
같은 XPS 문서 내에서 **여러 그라디언트를 적용**하려면, 각 새로운 형태에 대해 “수평 그라디언트 만들기”와 “그라디언트가 적용된 경로 추가” 단계를 반복하면 됩니다. 새로운 `XpsGradientStop` 객체 리스트를 사용하거나 기존 리스트를 `clear()`하고, 자체 시작/끝 점을 가진 새로운 `LinearGradientBrush`를 할당합니다. 이 방법을 통해 그라디언트를 겹치거나 복잡한 배경을 만들거나 단일 페이지에서 다양한 UI 요소를 강조할 수 있습니다.

## 왜 이것이 중요한가 – 수평 그라디언트 브러시의 장점
- **시각적 깊이:** 수평 그라디언트 브러시는 추가 이미지 없이도 미묘한 3차원 느낌을 제공합니다.  
- **파일 크기 효율성:** 그라디언트는 벡터 정의로 저장되어 XPS 파일을 가볍게 유지합니다.  
- **확장성:** 그라디언트가 벡터 기반이므로 고해상도 디스플레이에서도 깨끗하게 확대됩니다.  

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결 방법 |
|------|------|-----------|
| 그라디언트가 단색으로 표시됨 | 그라디언트 스톱이 추가되지 않았거나 브러시가 설정되지 않음 | `path.setFill(...)`에 `LinearGradientBrush`가 사용되고 `getGradientStops().addAll(stops)`를 통해 스톱이 추가되었는지 확인하세요. |
| 색상이 흐릿하게 보임 | 알파 값(첫 번째 매개변수)이 잘못됨 | 투명도가 필요하지 않다면 `255`를 사용하여 완전 불투명 색상을 지정하세요. |
| 경로 크기가 잘못됨 | 변환 행렬 값이 잘못됨 | 행렬 매개변수(`scaleX, skewY, skewX, scaleY, translateX, translateY`)를 조정하세요. |

## 자주 묻는 질문

**Q: 하나의 XPS 문서에 여러 그라디언트를 적용할 수 있나요?**  
A: 예, 각기 다른 그라디언트 브러시를 가진 여러 경로를 추가하여 복잡한 레이어 디자인을 만들 수 있습니다.

**Q: Aspose.Page가 최신 Java 버전과 호환되나요?**  
A: Aspose.Page for Java는 정기적으로 업데이트되며 Java 8 및 이후 버전에서 작동합니다.

**Q: Aspose.Page에서 다른 그라디언트 유형도 제공하나요?**  
A: 선형 그라디언트 외에도 Aspose.Page는 원형 색상 전환을 위한 방사형 그라디언트를 지원합니다.

**Q: 그라디언트 스톱의 색상과 위치를 사용자 정의할 수 있나요?**  
A: 물론입니다! 각 스톱의 ARGB 색상과 상대 위치(0‑1 범위)를 완전히 제어할 수 있습니다.

**Q: Aspose.Page에 대한 커뮤니티 포럼이 있나요?**  
A: 예, [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)에서 커뮤니티와 연결하고 도움을 받을 수 있습니다.

---

**마지막 업데이트:** 2026-03-13  
**테스트 환경:** Aspose.Page for Java 24.11  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}