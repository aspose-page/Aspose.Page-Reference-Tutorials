---
date: 2025-12-08
description: Aspose.Page를 사용하여 Java PostScript에서 방사형 그라디언트를 추가하는 방법을 배워보세요. 이 단계별
  가이드는 문서에 놀라운 그라디언트 효과를 만드는 방법을 보여줍니다.
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: Aspose.Page를 사용하여 Java PostScript에 방사형 그라데이션 추가하는 방법
url: /ko/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript에서 Aspose.Page를 사용하여 방사형 그라디언트 추가하는 방법

## 소개
PostScript 출력에 부드럽고 눈에 띄는 색상 전환을 적용해야 할 때가 있다면, **방사형 그라디언트 추가 방법**을 배우는 것이 시작하기에 완벽합니다. 이 튜토리얼에서는 **Aspose.Page for Java** 라이브러리를 사용하여 아름다운 방사형 그라디언트를 포함한 PostScript 파일을 생성하는 데 필요한 모든 단계를 차례대로 안내합니다. 끝까지 진행하면 API를 이해하고, 실행 가능한 전체 예제를 확인하며, 색상, 위치 및 반경을 원하는 디자인에 맞게 조정하는 방법을 알게 됩니다.

## 빠른 답변
- **PostScript에서 방사형 그라디언트를 생성하는 라이브러리는?** Aspose.Page for Java.  
- **구현에 소요되는 시간은?** 기본 예제의 경우 약 10‑15분 정도 걸립니다.  
- **코드를 실행하려면 라이선스가 필요합니까?** 개발에는 무료 체험판으로 충분하지만, 운영 환경에서는 상용 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** Java 8 이상.  
- **그라디언트 형태를 변경할 수 있나요?** 예 – `RadialGradientPaint` 생성자에서 반경과 중심점을 조정하면 됩니다.

## 방사형 그라디언트란?
방사형 그라디언트는 중앙 지점에서 바깥쪽으로 색상이 방사형으로 퍼지면서 점차 가장자리로 블렌딩되는 방식입니다. 선형 그라디언트와 달리 색상 전환이 원형(또는 타원형) 패턴을 따라 진행되므로 하이라이트, 스포트라이트 또는 부드러운 배경 채우기에 이상적입니다.

## 왜 Aspose.Page를 방사형 그라디언트에 사용하나요?
- **PostScript 출력에 대한 완전한 제어** – 저수준 PS 명령을 직접 작성할 필요가 없습니다.  
- **크로스‑플랫폼** – Java가 실행되는 모든 OS에서 작동합니다.  
- **풍부한 색상 관리** – 다중 색상 스톱, 다양한 색상 공간 및 사이클 방식을 지원합니다.  
- **통합 준비 완료** – 텍스트, 이미지 및 벡터 도형과 같은 Aspose.Page의 다른 기능과 결합할 수 있습니다.

## 전제 조건
코드에 들어가기 전에 다음 항목을 준비하십시오:

- **Java Development Kit (JDK) 8+** – `java -version`으로 확인합니다.  
- **Aspose.Page for Java** – 공식 [Aspose.Page 다운로드 페이지](https://releases.aspose.com/page/java/)에서 최신 JAR를 다운로드합니다.  
- **선택한 IDE** – Eclipse, IntelliJ IDEA 또는 Java 확장이 포함된 VS Code.  
- **쓰기 가능한 폴더** – 생성된 `.ps` 파일이 저장될 위치입니다.

## 패키지 가져오기
먼저 필요한 클래스를 가져옵니다. `java.awt` 패키지는 그라디언트 페인트 객체를 제공하고, `com.aspose.eps`는 PostScript 문서 처리 클래스를 포함합니다.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 단계별 가이드

### 1단계: 사각형 생성 및 PS 문서 열기
먼저 출력 스트림을 생성하고, 페이지 크기(A4 기본)를 설정한 뒤, 그라디언트를 표시할 사각형을 정의합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **팁:** 사각형 좌표(`200, 100, 200, 200`)를 조정하여 페이지 내 원하는 위치에 그라디언트를 배치할 수 있습니다.

### 2단계: 색상 및 비율 정의
방사형 그라디언트는 *색상 스톱*(색상)과 *비율*(각 스톱의 상대 위치)으로 구성됩니다. 여기서는 6가지 색상과 해당 비율을 배열로 생성합니다.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **왜 중요한가:** `fractions`를 조정하면 색상이 전환되는 속도를 제어할 수 있어 미묘하거나 극적인 효과를 만들 수 있습니다.

### 3단계: 방사형 그라디언트 페인트 생성
이제 `RadialGradientPaint` 객체를 생성합니다. 생성자는 그라디언트 중심점, 반경, 초점점, 비율, 색상, 사이클 방식, 색상 공간 및 선택적 변환을 매개변수로 받습니다.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **참고:** 추가적인 스케일링이나 회전이 필요하지 않다면 `transform`을 `null`로 설정할 수 있습니다. 기울어진 그라디언트를 위해 `AffineTransform`을 실험해 보세요.

### 4단계: 페인트 설정 및 사각형 채우기
페인트가 준비되면 `PsDocument`에 이를 사용하도록 지정하고, 앞서 정의한 사각형을 채웁니다.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

이 시점에서 PostScript 페이지에는 설정한 방사형 그라디언트가 부드럽게 채워진 사각형이 포함됩니다.

### 5단계: 문서 닫기 및 저장
마지막으로 현재 페이지를 닫고 파일을 디스크에 기록합니다.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

`RadialGradient1_outPS.ps` 파일을任意의 PostScript 뷰어(예: Ghostscript)에서 열면 정의한 대로 그라디언트가 정확히 렌더링된 것을 확인할 수 있습니다.

## 일반적인 문제 및 해결책

| 증상 | 가능한 원인 | 해결 방법 |
|---------|--------------|-----|
| 그라디언트가 단색으로 표시됨 | `fractions` 배열이 `0.0f`로 시작하거나 `1.0f`로 끝나지 않음 | 첫 번째 fraction이 `0.0f`이고 마지막이 `1.0f`인지 확인하십시오. |
| 색상이 흐릿하게 보임 | 잘못된 `ColorSpaceType` 사용 | 더 선명한 출력을 위해 `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB`로 전환하십시오. |
| 출력 파일이 생성되지 않음 | `FileOutputStream` 경로가 잘못되었거나 쓰기 권한이 없음 | `dataDir`가 존재하고 애플리케이션에 쓰기 권한이 있는지 확인하십시오. |

## 자주 묻는 질문

**Q: Aspose.Page for Java를 상업 프로젝트에 사용할 수 있나요?**  
A: 예. 운영 환경에서는 상용 라이선스가 필요합니다. [Aspose 라이선스 페이지](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

**Q: 공식 API 레퍼런스는 어디에서 찾을 수 있나요?**  
A: 전체 문서는 [여기](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

**Q: 테스트용 무료 체험판을 사용할 수 있나요?**  
A: 물론입니다. [Aspose.Page 릴리스 페이지](https://releases.aspose.com/)에서 체험판을 다운로드하십시오.

**Q: 평가용 임시 라이선스는 어떻게 얻나요?**  
A: [여기](https://purchase.aspose.com/temporary-license/)에서 요청할 수 있습니다.

**Q: 커뮤니티 지원은 어디서 받을 수 있나요?**  
A: [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39)에서 Aspose.Page 커뮤니티 포럼에 참여하십시오.

## 결론
이제 Aspose.Page를 사용하여 Java PostScript 문서에 **방사형 그라디언트를 추가하는 방법**을 알게 되었습니다. 사각형 크기, 색상 스톱 및 그라디언트 반경을 조정하면 미묘한 배경 채우기부터 대담한 스포트라이트 그래픽까지 무수히 많은 시각 효과를 만들 수 있습니다. 다양한 `AffineTransform` 값을 실험해 그라디언트를 회전하거나 기울여 보세요. 또한 이 기법을 텍스트와 이미지와 결합하면 PDF 또는 EPS 출력이 더욱 풍부해집니다.

---

**마지막 업데이트:** 2025-12-08  
**테스트 환경:** Aspose.Page for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}