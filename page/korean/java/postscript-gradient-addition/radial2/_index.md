---
date: 2025-12-08
description: Aspose.Page를 사용하여 Java PostScript에서 방사형 그라디언트 예제를 만드는 방법을 배웁니다. 전체 코드와
  문제 해결이 포함된 단계별 가이드.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: '방사형 그라디언트 예제: Aspose.Page를 사용한 Java PostScript'
url: /ko/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 방사형 그라디언트 예제: Aspose.Page를 사용한 Java PostScript

## 소개
이 튜토리얼에서는 Aspose.Page for Java를 사용하여 PostScript 문서에 대한 **방사형 그라디언트 예제**를 만들게 됩니다. 프로젝트 설정부터 부드러운 방사형 그라디언트가 채워진 원을 렌더링하는 단계까지 모두 안내하므로 Java 애플리케이션에 즉시 눈에 띄는 그래픽을 추가할 수 있습니다.

## 빠른 답변
- **이 튜토리얼이 만드는 것은?** 방사형 그라디언트가 채워진 원을 포함하는 PostScript 파일(`.ps`).  
- **필요한 라이브러리는?** Aspose.Page for Java(최신 버전).  
- **구현에 걸리는 시간은?** 작동 예제를 만들기 위해 약 10‑15분 정도 소요됩니다.  
- **라이선스가 필요한가요?** 프로덕션 사용에는 임시 또는 정식 라이선스가 필요하며, 개발 단계에서는 무료 체험판을 사용할 수 있습니다.  
- **코드를 PDF나 SVG에 재사용할 수 있나요?** 예—Aspose.Page는 최소한의 변경으로 여러 출력 형식을 지원합니다.

## 방사형 그라디언트란?
방사형 그라디언트는 색상이 중심점에서 바깥쪽으로 전환되어 부드러운 원형 블렌드를 만듭니다. 하이라이트, 버튼 배경 또는 자연스러운 ‘광채’ 효과가 필요한 모든 시각 요소에 이상적입니다.

## 왜 Aspose.Page를 방사형 그라디언트에 사용하나요?
- **디바이스 독립적 렌더링** – PostScript, PDF, SVG 등에서 동일하게 동작합니다.  
- **완전한 Java 통합** – 네이티브 코드 없이 순수 Java API만 사용합니다.  
- **고품질 출력** – 안티앨리어싱 및 색상 공간 제어를 지원합니다.

## 사전 요구 사항
- Java 프로그래밍에 대한 기본 지식.  
- JDK 8 이상이 설치되어 있어야 합니다.  
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

## 단계 1: 문서 디렉터리 설정
생성된 PostScript 파일이 저장될 폴더를 정의합니다. 플레이스홀더를 시스템에 실제 존재하는 경로로 교체하십시오.

```java
String dataDir = "Your Document Directory";
```

## 단계 2: 출력 스트림 생성
`FileOutputStream`을 열어 대상 `.ps` 파일을 지정합니다. 이 스트림은 Aspose.Page가 생성한 바이너리 데이터를 전달합니다.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## 단계 3: 저장 옵션 생성
`PsSaveOptions`를 인스턴스화합니다. 페이지 크기, 압축 등을 사용자 정의할 수 있지만, 이 예제에서는 기본값으로 충분합니다.

```java
PsSaveOptions options = new PsSaveOptions();
```

## 단계 4: PS 문서 생성
`PsDocument` 객체를 생성하고 출력 스트림과 저장 옵션을 전달합니다. `false` 플래그는 Aspose.Page가 자동으로 페이지를 열지 않도록 지정하며(우리는 수동으로 엽니다).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 단계 5: 원 만들기
`Ellipse2D.Float`을 사용해 원을 그립니다. 매개변수는 `(x, y, width, height)`이며, width = height 로 설정하면 완벽한 원이 됩니다.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## 단계 6: 그라디언트 색상 정의
두 개의 배열을 준비합니다: 그라디언트에 사용할 색상 배열과 해당 색상의 위치 비율 배열(0 = 중심, 1 = 가장자리).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## 단계 7: AffineTransform 생성
`AffineTransform`은 그라디언트를 스케일 및 이동시켜 원에 맞춥니다. 행렬 `(scaleX, 0, 0, scaleY, translateX, translateY)`이 이를 수행합니다.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## 단계 8: Radial Gradient Paint 생성
이제 `RadialGradientPaint` 객체를 만듭니다. 중심점, 반경, 포커스 포인트, 색상 비율, 색상 배열, 사이클 메서드, 색상 공간 및 방금 정의한 변환을 인자로 받습니다.

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

## 단계 9: 페인트 설정 및 원 채우기
문서에 그라디언트 페인트를 적용하고 앞서 정의한 원을 채웁니다. 이것이 우리의 **방사형 그라디언트 예제**의 핵심입니다.

```java
document.setPaint(paint);
document.fill(circle);
```

## 단계 10: 페이지 닫기 및 문서 저장
페이지를 마무리하고 내용을 디스크에 기록한 뒤 스트림을 닫습니다. 이제 PostScript 파일을 어떤 PS 뷰어에서도 열어볼 수 있습니다.

```java
document.closePage();
document.save();
```

축하합니다! Aspose.Page를 사용하여 Java PostScript에서 방사형 그라디언트 예제를 성공적으로 만들었습니다.

## 일반적인 문제 및 해결책
| 문제 | 해결책 |
|------|--------|
| **FileNotFoundException** 발생 시 출력 스트림 열기 | `dataDir`가 존재하는 폴더를 가리키고 쓰기 권한이 있는지 확인하십시오. |
| 그라디언트가 평평하거나 보이지 않음 | `fractions` 배열이 `colors` 배열 길이와 일치하고 `AffineTransform`이 올바르게 스케일되는지 확인하십시오. |
| 색상이 반전되어 표시됨 | `colors` 배열의 순서를 바꾸거나 `focus` 포인트 좌표를 조정하십시오. |

## 자주 묻는 질문

**Q: Aspose.Page for Java 문서는 어디에서 찾을 수 있나요?**  
A: 전체 API 레퍼런스는 [여기](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

**Q: Aspose.Page for Java를 어떻게 다운로드하나요?**  
A: 최신 JAR 파일은 [릴리즈 페이지](https://releases.aspose.com/page/java/)에서 다운로드하십시오.

**Q: 무료 체험판이 있나요?**  
A: 예—체험판은 [여기](https://releases.aspose.com/)에서 다운로드하십시오.

**Q: 테스트용 임시 라이선스를 받을 수 있나요?**  
A: 물론입니다. [임시 라이선스 페이지](https://purchase.aspose.com/temporary-license/)에서 요청하십시오.

**Q: 커뮤니티 지원은 어디서 받을 수 있나요?**  
A: [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)에서 토론에 참여하십시오.

## 결론
이 가이드에서는 Aspose.Page for Java를 사용하여 PostScript 문서에 대한 완전한 **방사형 그라디언트 예제**를 구축했습니다. 단계별로 진행함으로써 이제 복잡한 그라디언트를 만들기 위한 재사용 가능한 패턴을 확보했으며, 이를 PDF, SVG 또는 기타 지원 형식에 맞게 적용할 수 있습니다. 다양한 색상, 반경 및 형태를 실험하여 Java 그래픽 프로젝트를 풍부하게 만들어 보세요.

---

**마지막 업데이트:** 2025-12-08  
**테스트 환경:** Aspose.Page for Java 24.11 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}