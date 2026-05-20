---
date: 2026-04-24
description: Java에서 방사형 그라디언트 타원을 사용하여 XPS 문서를 만드는 방법을 배워보세요. 이 단계별 가이드는 Aspose.Page를
  사용하여 스트로크 두께를 설정하고 경로 기하학을 정의하는 방법을 보여줍니다.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Java XPS에 타원 추가
second_title: Aspose.Page Java API
title: XPS 문서 생성 Java – 방사형 그라디언트 타원 추가
url: /ko/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용한 방사형 그라디언트 타원 추가

## 소개
이 튜토리얼에서는 Aspose.Page for Java를 사용하여 아름다운 방사형 그라디언트 스트로크 타원을 포함한 **create XPS document Java**를 만드는 방법을 배웁니다. Aspose.Page는 저수준 XPS 세부 정보를 추상화하는 강력한 라이브러리로, 파일 형식의 복잡성보다 디자인에 집중할 수 있게 해줍니다. 이 가이드를 마치면 보고서, 청구서 또는 기타 문서 생성 워크플로에 삽입할 수 있는 사용 준비가 된 XPS 파일을 얻게 됩니다.

## 빠른 답변
- **이 코드가 생성하는 것은 무엇입니까?** 다중 색상의 방사형 그라디언트 스트로크가 적용된 타원을 포함하는 단일 페이지 XPS 파일.  
- **주요 API는 무엇입니까?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, 등).  
- **샘플을 실행하려면 라이선스가 필요합니까?** 임시 라이선스는 평가에 사용할 수 있으며, 프로덕션에는 정식 라이선스가 필요합니다.  
- **설정하는 주요 속성은 무엇입니까?** 스트로크 브러시(방사형 그라디언트), 스프레드 메서드, 그라디언트 스톱 및 스트로크 두께.  
- **타원 크기를 변경할 수 있나요?** 예 – 경로 기하 문자열이나 그라디언트 브러시 좌표를 수정하면 됩니다.

## “create XPS document Java”란?
Java에서 XPS 문서를 생성한다는 것은 XML Paper Specification (XPS) 파일—PDF와 유사한 고정 레이아웃 문서 형식—을 Java 코드에서 직접 프로그래밍 방식으로 생성하는 것을 의미합니다. Aspose.Page는 XML 마크업을 추상화하는 고수준 객체 모델(`XpsDocument`, `XpsCanvas` 등)을 제공하여, 표준 Java 객체를 다루는 것만큼 간단하게 작업할 수 있게 합니다.

## 방사형 그라디언트 타원을 사용하는 이유
방사형 그라디언트는 3차원적인 느낌을 제공하여 시각적 강조, 로고 또는 보고서의 장식 요소에 적합합니다. 단색 스트로크와 비교할 때, 그라디언트는 파일 크기를 크게 늘리지 않으면서 깊이를 추가하고, XPS 형식은 어떤 확대/축소에도 벡터 품질을 유지합니다.

## 사전 요구 사항
- 머신에 Java Development Kit (JDK)이 설치되어 있어야 합니다.
- Aspose.Page for Java 라이브러리를 다운로드합니다. [here](https://releases.aspose.com/page/java/)에서 받을 수 있습니다.
- 선호하는 코드 편집기(Eclipse, IntelliJ 등)를 사용하여 Java 코드를 작성하고 실행합니다.

## 패키지 가져오기
Java 프로젝트에 Aspose.Page를 사용하기 위해 필요한 패키지가 가져와졌는지 확인하십시오. 다음 import 문을 Java 파일 상단에 추가합니다:

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## 단계 1: 문서 디렉터리 설정
XPS 문서를 저장할 문서 디렉터리 경로를 정의합니다:

```java
String dataDir = "Your Document Directory";
```

## 단계 2: XPS 문서 생성
다음 코드를 사용하여 새 XPS 문서를 초기화합니다:

```java
XpsDocument doc = new XpsDocument();
```

## 단계 3: 방사형 그라디언트 스톱 정의
방사형 그라디언트 스트로크 타원을 위한 그라디언트 스톱 목록을 생성합니다:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## 단계 4: 경로 기하학 생성
경로 기하학을 사용하여 방사형 그라디언트 스트로크 타원을 정의합니다:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## 단계 5: 캔버스 및 경로 추가
문서에 새 캔버스를 추가하고 정의된 기하학으로 경로를 추가합니다:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## 단계 6: 스트로크 및 그라디언트 설정
경로의 스트로크를 방사형 그라디언트 브러시로 설정합니다:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## 단계 7: 스트로크 두께 설정
경로의 **스트로크 두께 설정**을 지정합니다:

```java
path.setStrokeThickness(12f);
```

## 단계 8: 문서 저장
결과 XPS 문서를 저장합니다:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

축하합니다! Aspose.Page를 사용하여 **creating an XPS document Java**를 수행하면서 방사형 그라디언트 스트로크 타원을 성공적으로 추가했습니다.

## 일반적인 문제 및 해결책
| 문제 | 발생 원인 | 해결 방법 |
|-------|----------------|-----|
| **타원이 평면적으로 보임** | `Reflect` 대신 `XpsSpreadMethod.Pad`를 사용했기 때문입니다. | Step 6에 표시된 대로 스프레드 메서드를 `XpsSpreadMethod.Reflect`로 변경하십시오. |
| **출력 파일 없음** | `dataDir`이 존재하지 않는 폴더를 가리키고 있습니다. | 디렉터리가 존재하는지 확인하거나 절대 경로를 사용하십시오. |
| **그라디언트 색상이 이상함** | 그라디언트 스톱 순서가 잘못되었습니다. | `offset` 값(0 → 1)이 단조롭게 증가하는지 확인하십시오. |
| **컴파일 오류** | 클래스패스에 Aspose.Page JAR가 누락되었습니다. | 프로젝트 의존성에 `aspose-page-xx.jar`를 추가하십시오. |

## 자주 묻는 질문

**Q: Aspose.Page for Java를 다른 Java 라이브러리와 함께 사용할 수 있나요?**  
A: 예, Aspose.Page for Java는 다른 Java 라이브러리와 원활하게 통합될 수 있습니다.

**Q: Aspose.Page가 대규모 문서 처리에 적합한가요?**  
A: 물론입니다! Aspose.Page는 대규모 문서 처리를 효율적으로 수행하도록 설계되었습니다.

**Q: Aspose.Page for Java에 대한 더 많은 튜토리얼 및 예제를 어디서 찾을 수 있나요?**  
A: 포괄적인 튜토리얼 및 예제를 보려면 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)을 방문하십시오.

**Q: Aspose.Page for Java의 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: [here](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 받을 수 있습니다.

**Q: Aspose.Page 토론을 위한 커뮤니티 포럼이 있나요?**  
A: 예, 다른 개발자와 교류하고 도움을 받으려면 [Aspose.Page community forum](https://forum.aspose.com/c/page/39)에 참여하십시오.

---

**마지막 업데이트:** 2026-04-24  
**테스트 환경:** Aspose.Page for Java 24.11 (latest at time of writing)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}