---
date: 2026-09-09
description: Java PostScript에서 gradient를 만드는 방법과 Aspose.Page를 사용하여 shape에 gradient를
  추가하는 방법을 배웁니다. 코드와 팁이 포함된 단계별 가이드를 따라보세요.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Aspose.Page와 함께하는 Java PostScript Radial Gradient
og_description: Java PostScript에서 gradient를 만드는 방법과 Aspose.Page를 사용하여 shape에 gradient를
  추가하는 방법을 배웁니다. 코드와 팁이 포함된 단계별 가이드를 따라보세요.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Java PostScript에서 radial fill을 사용해 gradient 만드는 방법
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Java PostScript에서 radial fill을 사용해 gradient 만드는 방법
url: /ko/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript에서 방사형 채우기로 그라디언트 만들기

## 소개
이 튜토리얼에서는 Java와 Aspose.Page를 사용하여 PostScript 문서에 **그라디언트 만들기** 그래픽을 만드는 방법을 배웁니다. 프로젝트 설정부터 부드러운 방사형 그라디언트로 채워진 원을 렌더링하는 단계까지 모두 안내하므로 **도형에 그라디언트 추가**를 즉시 수행하고 Java 애플리케이션의 시각적 품질을 향상시킬 수 있습니다.

## 빠른 답변
- **이 튜토리얼은 무엇을 생성합니까?** 방사형 그라디언트로 채워진 원을 포함하는 PostScript 파일(`.ps`).  
- **필요한 라이브러리는?** Java용 Aspose.Page(최신 버전).  
- **구현에 걸리는 시간은?** 작동 예제를 만드는 데 약 10‑15분 정도 소요됩니다.  
- **라이선스가 필요합니까?** 프로덕션 사용을 위해 임시 또는 정식 라이선스가 필요합니다; 개발에는 무료 체험판을 사용할 수 있습니다.  
- **코드를 PDF나 SVG에 재사용할 수 있나요?** 예—Aspose.Page는 최소한의 변경으로 여러 출력 형식을 지원합니다.

## PostScript에서 그라디언트로 도형 채우는 방법
PostScript에서 `PsDocument`를 생성하고 `RadialGradientPaint`를 정의한 뒤 대상 도형에 적용하고 문서를 저장하면 방사형 그라디언트로 도형을 채울 수 있습니다. 이 간결한 워크플로우를 통해 래스터 이미지 없이도 전문가 수준의 벡터 그래픽을 만들 수 있으며, 동일한 코드를 PDF 또는 SVG 출력에도 재사용할 수 있습니다. 이 과정은 직관적이며 지원되는 모든 형식에서 일관되게 작동합니다.

## 방사형 그라디언트란?
방사형 그라디언트는 색상이 중심점에서 바깥쪽으로 전환되어 부드러운 원형 블렌드를 만듭니다. 하이라이트, 버튼 배경 또는 자연스러운 “광택” 효과가 필요한 모든 시각 요소에 이상적입니다. 색상 스톱과 반경을 조절하면 순수 벡터 형태로 조명, 깊이 및 재질 특성을 시뮬레이션할 수 있습니다.

## 방사형 그라디언트에 Aspose.Page를 사용하는 이유
Aspose.Page는 단일 Java API로 디바이스에 독립적인 벡터 그래픽을 생성할 수 있게 해줍니다. PostScript, PDF, SVG 등을 포함한 50개 이상의 입력 및 출력 형식을 지원하며 색상 정확도와 고해상도 출력을 위한 안티앨리어싱을 유지합니다. 또한 라이브러리는 사용하기 쉬운 그라디언트 클래스를 제공하여 복잡한 시각 효과를 간단히 구현할 수 있습니다.

## 전제 조건
- Java 프로그래밍에 대한 기본적인 이해.  
- JDK 8 이상이 설치되어 있어야 합니다.  
- Aspose.Page for Java 라이브러리([Aspose.Page Java 문서](https://reference.aspose.com/page/java/)에서 다운로드).

## 패키지 가져오기
먼저, 필요한 클래스를 가져옵니다. 여기에는 표준 AWT 그래픽 타입과 Aspose.Page API가 포함됩니다.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 1단계: 문서 디렉터리 설정
생성된 PostScript 파일이 저장될 폴더를 정의합니다. 플레이스홀더를 시스템에 실제 경로로 교체하십시오.

```java
String dataDir = "Your Document Directory";
```

## 2단계: 출력 스트림 생성
FileOutputStream은 원시 바이트를 파일에 기록하여 바이너리 데이터를 저장할 수 있게 합니다. `.ps` 파일을 대상으로 열면 Aspose.Page가 생성된 PostScript 데이터를 직접 디스크에 스트리밍합니다.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## 3단계: 저장 옵션 생성
PsSaveOptions는 페이지 크기와 압축 등 PostScript 파일 저장 방식을 구성합니다. 설정을 사용자 정의할 수 있지만, 이 예제에서는 기본값으로 충분합니다.

```java
PsSaveOptions options = new PsSaveOptions();
```

## 4단계: ps 문서 생성
PsDocument는 메모리 내에서 PostScript 문서를 나타내며 페이지와 그래픽을 추가하는 메서드를 제공합니다.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 5단계: 원 만들기
`Ellipse2D.Float`는 타원 형태를 설명합니다; 너비와 높이가 같으면 완벽한 원이 됩니다. 이 객체는 그라디언트 채우기의 캔버스로 사용됩니다.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## 그라디언트로 원 그리기
방사형 그라디언트로 원을 그리려면 `RadialGradientPaint`를 그래픽 컨텍스트에 로드한 뒤 앞서 정의한 타원을 채웁니다. 이 한 번의 작업으로 도형을 중심에서 바깥쪽으로 부드럽게 색상이 전환되는 형태로 채워 시각적으로 매력적인 효과를 만듭니다.

## 6단계: 그라디언트 색 정의
두 개의 배열을 준비합니다: 그라디언트에 사용할 색상 배열과 해당 색상의 위치(분수) 배열(0 = 중심, 1 = 가장자리).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## 7단계: AffineTransform 생성
AffineTransform은 그래픽 객체를 이동, 회전, 스케일 또는 전단할 수 있는 행렬입니다. 여기서는 그라디언트를 스케일하고 이동시켜 원 안에 정확히 맞추도록 합니다.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## 8단계: 방사형 그라디언트 페인트 생성
RadialGradientPaint는 중심점, 반경 및 색상 스톱을 기반으로 방사형 색상 그라디언트를 생성합니다.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## 9단계: 페인트 설정 및 원 채우기
그라디언트 페인트를 문서에 적용하고 앞서 정의한 원을 채웁니다. 이것이 우리의 **방사형 그라디언트 예제**의 핵심이며 **도형에 그라디언트 채우기** 방법을 보여줍니다.

```java
document.setPaint(paint);
document.fill(circle);
```

## 10단계: 페이지 닫고 문서 저장
페이지를 마무리하고 내용을 디스크에 기록한 뒤 스트림을 닫습니다. 이제 PostScript 파일을 모든 PS 뷰어로 열어볼 수 있습니다.

```java
document.closePage();
document.save();
```

축하합니다! Aspose.Page를 사용하여 Java PostScript에서 방사형 그라디언트 예제를 성공적으로 만들었습니다. 이제 **도형에 그라디언트 채우기**를 위한 재사용 가능한 패턴을 갖게 되었으며, 이를 다른 도형 및 출력 형식에 적용할 수 있습니다.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|---------|----------|
| **FileNotFoundException** 발생 시 출력 스트림 열기 | `dataDir`이 존재하는 폴더를 가리키고 쓰기 권한이 있는지 확인하십시오. |
| 그라디언트가 평평하거나 누락됨 | `fractions` 배열이 `colors` 배열 길이와 일치하고 `AffineTransform`이 올바르게 스케일되는지 확인하십시오. |
| 색상이 반대로 표시됨 | `colors` 배열의 색상 순서를 바꾸거나 `focus` 점 좌표를 조정하십시오. |

## 자주 묻는 질문

**Q: Aspose.Page for Java 문서는 어디에서 찾을 수 있나요?**  
A: 전체 API 참조는 [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

**Q: Aspose.Page for Java를 어떻게 다운로드하나요?**  
A: 최신 JAR 파일은 [releases page](https://releases.aspose.com/page/java/)에서 가져오세요.

**Q: 무료 체험판을 이용할 수 있나요?**  
A: 예—[Aspose free trial download page](https://releases.aspose.com/)에서 체험판을 다운로드하세요.

**Q: 테스트용 임시 라이선스를 받을 수 있나요?**  
A: 물론입니다, [temporary license page](https://purchase.aspose.com/temporary-license/)에서 요청하세요.

**Q: 커뮤니티 지원은 어디서 받을 수 있나요?**  
A: [Aspose.Page forum](https://forum.aspose.com/c/page/39)에서 토론에 참여하세요.

## 결론
이 가이드에서는 Aspose.Page for Java를 사용하여 PostScript 문서에 완전한 **방사형 그라디언트 예제**를 구축했습니다. 단계별로 따라 하면 이제 **도형에 그라디언트 채우기**를 위한 재사용 가능한 패턴을 갖게 되었으며, 이를 PDF, SVG 또는 Aspose.Page가 지원하는 다른 형식에 적용할 수 있습니다. 다양한 색상, 반경 및 도형을 실험하여 Java 그래픽 프로젝트를 풍부하게 만들어 보세요.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## 관련 튜토리얼

- [Java에서 PostScript 그라디언트 만들기 – 수직 그라디언트 추가](/page/java/postscript-gradient-addition/vertical/)
- [Aspose.Page for Java를 사용한 PostScript 텍스처 패턴 만들기](/page/java/postscript-texture-patterns/)
- [Aspose.Page 투명도 튜토리얼 – Java PostScript에 투명도 추가](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}