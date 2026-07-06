---
date: 2026-02-13
description: Aspose.Page를 사용하여 Java PostScript에서 그라디언트로 도형을 채우고 원을 그리는 방법을 배워보세요.
  코드와 팁이 포함된 단계별 가이드.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: '그라디언트로 도형 채우기: Java PostScript 방사형 예제'
url: /ko/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 그라디언트로 도형 채우기: Java PostScript 방사형 예제

## 소개
이 튜토리얼에서는 Aspose.Page for Java를 사용하여 PostScript 문서에 방사형 그라디언트를 적용하는 예제를 만들면서 **그라디언트로 도형 채우기** 방법을 배웁니다. 프로젝트 설정부터 부드러운 방사형 그라디언트가 적용된 원을 렌더링하는 단계까지 모두 안내하므로, Java 애플리케이션에 눈에 띄는 그래픽을 즉시 추가할 수 있습니다.

## 빠른 답변
- **이 튜토리얼이 만드는 것은?** 방사형 그라디언트가 적용된 원을 포함하는 PostScript 파일(`.ps`)입니다.  
- **필요한 라이브러리는?** Aspose.Page for Java(최신 버전).  
- **구현 시간은?** 작업 가능한 예제를 만드는 데 약 10‑15분 정도 소요됩니다.  
- **라이선스가 필요한가요?** 프로덕션 사용을 위해서는 임시 또는 정식 라이선스가 필요합니다; 개발 단계에서는 무료 체험판을 사용할 수 있습니다.  
- **코드를 PDF나 SVG에 재사용할 수 있나요?** 예, Aspose.Page는 최소한의 변경으로 여러 출력 형식을 지원합니다.

## PostScript에서 그라디언트로 도형 채우는 방법
코드에 들어가기 전에 “그라디언트로 도형 채우기”가 왜 중요한지 살펴보겠습니다. 그라디언트를 사용하면 래스터 이미지 없이도 그래픽에 전문적이고 입체적인 느낌을 부여할 수 있습니다. Aspose.Page를 이용하면 원, 사각형, 사용자 정의 경로 등 모든 벡터 도형에 동일한 그라디언트 로직을 적용할 수 있으며, 지원되는 모든 출력 형식(PostScript, PDF, SVG)에서 동일하게 동작합니다.

## 방사형 그라디언트란?
방사형 그라디언트는 중앙점에서 바깥쪽으로 색상이 전환되어 부드러운 원형 블렌드를 만듭니다. 하이라이트, 버튼 배경, 자연스러운 “광원” 효과가 필요한 시각 요소에 이상적입니다.

## Aspose.Page를 사용해 방사형 그라디언트를 적용하는 이유
- **디바이스 독립적 렌더링** – PostScript, PDF, SVG 등에서 동일하게 동작합니다.  
- **완전한 Java 통합** – 네이티브 코드 없이 순수 Java API만 사용합니다.  
- **고품질 출력** – 안티앨리어싱 및 색상 공간 제어를 지원합니다.

## 사전 요구 사항
시작하기 전에 다음을 준비하세요:

- Java 프로그래밍에 대한 기본 지식.  
- JDK 8 이상 설치.  
- Aspose.Page for Java 라이브러리([Aspose.Page Java 문서](https://reference.aspose.com/page/java/)에서 다운로드).

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다. 여기에는 표준 AWT 그래픽 타입과 Aspose.Page API가 포함됩니다.

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
생성된 PostScript 파일이 저장될 폴더를 정의합니다. 플레이스홀더를 실제 경로로 교체하세요.

```java
String dataDir = "Your Document Directory";
```

## 2단계: 출력 스트림 생성
대상 `.ps` 파일을 가리키는 `FileOutputStream`을 엽니다. 이 스트림은 Aspose.Page가 만든 바이너리 데이터를 전달합니다.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## 3단계: 저장 옵션 만들기
`PsSaveOptions`를 인스턴스화합니다. 페이지 크기, 압축 등은 기본값으로 두어도 예제에 충분합니다.

```java
PsSaveOptions options = new PsSaveOptions();
```

## 4단계: PS 문서 생성
출력 스트림과 저장 옵션을 전달하여 `PsDocument` 객체를 생성합니다. `false` 플래그는 Aspose.Page가 자동으로 페이지를 열지 않도록 하며, 우리가 직접 페이지를 열게 됩니다.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 5단계: 원 만들기
`Ellipse2D.Float`를 사용해 원을 그립니다. 매개변수는 `(x, y, width, height)`이며, width = height이면 완벽한 원이 됩니다.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## 원에 그라디언트 그리기
이제 도형이 준비되었으니 **그라디언트로 원 그리기** 단계로 넘어갑니다. `RadialGradientPaint`를 원에 적용하면 채우기 작업이 자동으로 정의한 그라디언트를 사용합니다.

## 6단계: 그라디언트 색상 정의
두 개의 배열을 준비합니다: 그라디언트에 사용할 색상 배열과 해당 색상의 비율(0 = 중심, 1 = 가장자리) 배열입니다.

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## 7단계: AffineTransform 생성
`AffineTransform`은 그라디언트를 원에 맞게 스케일 및 이동시킵니다. 행렬 `(scaleX, 0, 0, scaleY, translateX, translateY)`이 그 역할을 합니다.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## 8단계: RadialGradientPaint 생성
이제 `RadialGradientPaint` 객체를 만듭니다. 중심점, 반지름, 포커스점, 색상 비율, 색상 배열, 사이클 메서드, 색상 공간, 그리고 방금 정의한 변환을 전달합니다.

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
그라디언트 페인트를 문서에 적용하고 앞서 정의한 원을 채웁니다. 이것이 **방사형 그라디언트 예제**의 핵심이며 **그라디언트로 도형 채우기**를 보여줍니다.

```java
document.setPaint(paint);
document.fill(circle);
```

## 10단계: 페이지 닫기 및 문서 저장
페이지를 마무리하고 내용을 디스크에 기록한 뒤 스트림을 닫습니다. 이제 PostScript 파일을 어떤 PS 뷰어에서도 열어볼 수 있습니다.

```java
document.closePage();
document.save();
```

축하합니다! Aspose.Page를 사용해 Java PostScript에서 방사형 그라디언트 예제를 성공적으로 만들었습니다. 이제 **그라디언트로 도형 채우기** 패턴을 다른 도형이나 출력 형식에 재사용할 수 있습니다.

## 일반적인 문제와 해결책
| 문제 | 해결책 |
|---------|----------|
| 출력 스트림을 열 때 **FileNotFoundException** 발생 | `dataDir`이 존재하는 폴더를 가리키는지, 쓰기 권한이 있는지 확인합니다. |
| 그라디언트가 평평하거나 보이지 않음 | `fractions` 배열 길이가 `colors` 배열 길이와 일치하는지, `AffineTransform`이 올바르게 스케일되는지 확인합니다. |
| 색상이 뒤바뀜 | `colors` 배열의 순서를 바꾸거나 `focus` 점 좌표를 조정합니다. |

## 자주 묻는 질문

**Q: Aspose.Page for Java 문서는 어디서 찾을 수 있나요?**  
A: 전체 API 레퍼런스는 [여기](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

**Q: Aspose.Page for Java를 어떻게 다운로드하나요?**  
A: 최신 JAR 파일은 [릴리스 페이지](https://releases.aspose.com/page/java/)에서 받으세요.

**Q: 무료 체험판이 있나요?**  
A: 네—체험판은 [여기](https://releases.aspose.com/)에서 다운로드할 수 있습니다.

**Q: 테스트용 임시 라이선스를 받을 수 있나요?**  
A: 물론입니다. [임시 라이선스 페이지](https://purchase.aspose.com/temporary-license/)에서 요청하세요.

**Q: 커뮤니티 지원은 어디서 받을 수 있나요?**  
A: [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)에서 토론에 참여하세요.

## 결론
이 가이드에서는 Aspose.Page for Java를 활용해 PostScript 문서에 완전한 **방사형 그라디언트 예제**를 구축했습니다. 단계별로 진행하면서 이제 **그라디언트로 도형 채우기** 패턴을 PDF, SVG 등 Aspose.Page가 지원하는 다른 형식에도 적용할 수 있게 되었습니다. 다양한 색상, 반지름, 도형을 실험해 보며 Java 그래픽 프로젝트를 풍부하게 만들어 보세요.

---

**마지막 업데이트:** 2026-02-13  
**테스트 환경:** Aspose.Page for Java 24.11 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}