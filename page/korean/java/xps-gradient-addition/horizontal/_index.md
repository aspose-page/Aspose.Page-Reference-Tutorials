---
date: 2025-12-25
description: Aspose.Page를 사용하여 Java에서 XPS 문서에 그라디언트를 추가하는 방법과 눈부신 수평 효과를 위한 그라디언트
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

# Java XPS에서 그라디언트 추가 – 수평 그라디언트

## 소개
이 가이드에 접속하는 것을 환영합니다. **그라디언트를 추가하는 방법**을 Java를 사용하여 XPS 문서에 적용하는 방법을 안내합니다. 이 튜토리얼에서는 수평 그라디언트를 추가하는 방법, 완벽도를 나타내는 이유, 정밀한 색상 제어를 위해 **그라디언트 스톱을 커스터마이즈**하는 방법을 배웁니다. Aspose.Page for Java는 XPS(XML Paper Spec) 문서 작업을 해보도록 하고, 저수준 파일 처리보다 디자인에 집중할 수 있게 해 줍니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Page for Java
- **어떤 Java 버전이 작동할까요?** Java8 이상이라면 모두 사용 가능합니다.
- **라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하며, 운영 환경에서는 인스턴스가 필요합니다.
- **그라디언트 방향을 반대할 수 없습니까?** 예 – 인도인 브러시의 시작/끝나기를 수정하면
- **여러용 그라디언트를 추가할 수 있습니까?** 물론 – 다른 브러시를 실행하는 동안 생성 단계를 반복하면 됩니다.

## XPS의 수평 그라데이션이란 무엇입니까?
수평 방향은 도형을 가로 방향(왼쪽에서 오른쪽)으로 색상이 부드럽게 전환되는 효과입니다. XPS에서는 정의된 **그라디언트 스톱** 사이를 보간하는 공룡 그라디언트 브러시로 표현되었습니다. 이 효과는 배너, 버튼, 백그라운드에서 자주 사용됩니다.

## Java용 Aspose.Page를 사용하는 이유는 무엇입니까?
- **XPS 전체 지원** – 외부 도구 없이 생성, 편집, 전송이 가능합니다.
- **간단한 API** – `XpsDocument`, `XpsPath`, `XpsGradientBrush`와 같은 모양이 되어 XML 수축을 확장합니다.
- **성능** – 주최자 문서와 배치 처리에 최적화되어 있습니다.

## 전제 조건
시작하기 전에 다음을 준비하십시오:

1. **Java 개발 환경** – 최신 JDK를 [java.com](https://www.java.com)에서 설치하세요.
2. **Aspose.Page for Java Library** – [Aspose.Page for Java document](https://reference.aspose.com/page/java/)에서 JAR 파일을 다운로드하세요.

## 패키지 가져오기
필요한 클래스를 가져옵니다. 이 임포트문을 통해 문서 생성, 그라디언트 처리 및 기본 기하학 기능에 접근할 수 있습니다.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## 1단계: XPS 문서 초기화
새 `XpsDocument` 인스턴스를 만들고 결과를 저장할 폴더를 지정합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## 2단계: 가로 그라디언트 생성
색상과 위치를 제어하는 **그라디언트 스톱** 목록을 정의합니다. 아래 예시는 활기찬 무지개 색상의 그라디언트를 생성합니다.

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

### 그라디언트 정지점 사용자 지정 방법
- **Color** – `doc.createColor(alpha, red, green, blue)`를 사용해任意의 ARGB 값을 설정합니다.  
- **Position** – 두 번째 인자(`float` 0~1 사이)는 그라디언트 라인 상에서 스톱이 나타나는 위치를 정의합니다. 이 값을 조정해 색상을 왼쪽이나 오른쪽으로 이동시킬 수 있습니다.

## 3단계: 그라디언트가 포함된 패스 추가
사각형 경로를 만들고 필요하면 변환을 적용한 뒤, 선형 그라디언트 브러시로 채웁니다. 브러시는 두 점(`(10,0)` → `(228,0)`)을 사용해 수평 효과를 만듭니다.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Pro tip:** 동일한 `stops` 리스트를 여러 경로에 재사용하면 성능이 향상되지만, 새로운 스톱을 추가하기 전에 `clear()` 호출을 잊지 마세요.

## 4단계: 문서 저장
XPS 파일을 디스크에 저장합니다. 이제 XPS 뷰어에서 열어 수평 그라디언트가 적용된 모습을 확인할 수 있습니다.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## 일반적인 문제 및 해결 방법
| 문제 | 원인 | 해결 방법 |

|-------|--------|-----|

| 그라디언트가 단색으로 나타남 | 그라디언트 정지점이 추가되지 않았거나 브러시가 설정되지 않음 | `path.setFill(...)`에서 `LinearGradientBrush`를 사용하고 `getGradientStops().addAll(stops)`를 통해 정지점이 추가되었는지 확인하십시오. |

| 색상이 흐릿하게 보임 | 알파 값(첫 번째 매개변수)이 잘못됨 | 투명도가 필요한 경우가 아니면 완전히 불투명한 색상을 위해 `255`를 사용하십시오. |

| 경로 크기가 잘못됨 | 변환 행렬 값이 잘못됨 | 행렬 매개변수(`scaleX, skewY, skewX, scaleY, translateX, translateY`)를 조정하십시오. |

## 자주 묻는 질문

**질문: 하나의 XPS 문서에 여러 개의 그라디언트를 적용할 수 있습니까?**
답변: 예, 각각 고유한 그라디언트 브러시를 가진 여러 개의 경로를 추가하여 복잡한 레이어 디자인을 만들 수 있습니다.

**질문: Aspose.Page는 최신 Java 버전과 호환되나요?**
답변: Aspose.Page for Java는 정기적으로 업데이트되며 Java 8 이상 버전에서 작동합니다.

**질문: Aspose.Page에서 사용할 수 있는 다른 그라디언트 유형이 있나요?**
답변: Aspose.Page는 선형 그라디언트 외에도 원형 색상 전환을 위한 방사형 그라디언트를 지원합니다.

**질문: 그라디언트 정지점의 색상과 위치를 사용자 지정할 수 있나요?**
답변: 네, 가능합니다! 각 정지점의 ARGB 색상과 상대적 위치(0~1 범위)를 완벽하게 제어할 수 있습니다.

**질문: Aspose.Page 관련 도움을 받을 수 있는 커뮤니티 포럼이 있나요?**
답변: 네, [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)을 방문하여 커뮤니티와 소통하고 도움을 받을 수 있습니다.

---

**최종 업데이트:** 2025년 12월 25일
**테스트 환경:** Aspose.Page for Java 24.11
**개발자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}