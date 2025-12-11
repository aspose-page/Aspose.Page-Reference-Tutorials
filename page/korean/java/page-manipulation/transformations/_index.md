---
date: 2025-12-07
description: Aspose.Page를 사용하여 Java에서 사각형을 스케일링하고, 도형을 이동하며, 어파인 변환을 적용하여 PostScript
  문서를 만드는 방법을 배웁니다.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Aspose.Page를 사용하여 사각형을 확대하고 변환 적용하기
url: /ko/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용한 사각형 스케일링 및 변환 적용 방법

## 소개
강력한 **Aspose.Page for Java** 기능을 활용하여 다양한 페이지 변환을 수행하는 포괄적인 가이드에 오신 것을 환영합니다. 이 튜토리얼에서는 **how to scale rectangle** 방법, 도형 이동, 객체 회전, **apply affine transform** 기술을 사용해 **PostScript document**를 만드는 방법을 배웁니다. 이러한 기능을 통해 저수준 렌더링 코드를 다루지 않고도 풍부하고 그래픽‑집약적인 Java 애플리케이션을 구축할 수 있습니다.

## 빠른 답변
- **Java에서 Aspose.Page를 사용하여 사각형을 스케일링하려면 어떻게 해야 하나요?** 도형을 그리기 전에 `document.scale()` 메서드를 사용합니다.  
- **다른 그래픽에 영향을 주지 않고 도형을 이동(translate)할 수 있나요?** 예—그래픽 상태를 저장하고 `document.translate(x, y)`를 호출한 뒤 도형을 그린 다음 상태를 복원합니다.  
- **PostScript 파일을 생성하는 클래스는 무엇인가요?** `PsDocument`와 `PsSaveOptions`를 사용합니다.  
- **프로덕션 환경에서 라이선스가 필요합니까?** 상업적 배포를 위해서는 유효한 Aspose.Page 라이선스가 필요합니다.  
- **지원되는 Java 버전은 어느 것인가요?** Aspose.Page는 Java 8 이상을 지원합니다.

## 사전 요구 사항
다음 사전 요구 사항을 충족했는지 확인하십시오:

- Java 프로그래밍에 대한 기본 지식.
- Aspose.Page for Java 라이브러리 설치. [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)에서 다운로드할 수 있습니다.
- 로컬 머신에 Java 통합 개발 환경(IDE)이 설정되어 있어야 합니다.

## 패키지 가져오기
Java 프로젝트에서 Aspose.Page for Java를 사용하기 위해 필요한 패키지를 가져옵니다:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Aspose.Page에서 “how to scale rectangle”란 무엇인가요?
사각형을 스케일링한다는 것은 X축과 Y축을 따라 크기를 변경하면서 형태는 유지하는 것을 의미합니다. Aspose.Page는 현재 그래픽 상태에 **affine transform**을 적용하는 `scale(float sx, float sy)` 메서드를 제공합니다. 이것이 **how to scale rectangle** 키워드의 핵심 기술입니다.

## Aspose.Page를 사용한 도형 이동 방법
이동은 도형의 크기를 변경하지 않고 새로운 위치로 옮기는 작업입니다. 이것이 **how to translate shape**의 본질입니다. 그래픽 상태를 저장하고 `translate(dx, dy)`를 적용한 뒤 도형을 그리며, 마지막에 상태를 복원하면 다른 객체에 영향을 주지 않습니다.

## 예제 1: 변환 없음
첫 번째 예제는 변환을 적용하지 않은 간단한 사각형을 그립니다. 이는 이후 예제와 비교하기 위한 기준점 역할을 합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## 예제 2: 이동
여기서는 두 번째 사각형을 그리기 전에 그래픽 컨텍스트를 오른쪽으로 250 단위 이동시켜 **how to translate shape**를 시연합니다.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## 예제 3: 스케일링
이 예제는 주요 질문인 **how to scale rectangle**에 대한 답을 제공합니다. 사각형을 원래 너비의 50 %와 높이의 75 %로 축소합니다.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Java에서 도형 회전 방법 (rotate shape java)
회전은 또 다른 일반적인 affine 연산입니다. 회전에 대한 코드 스니펫은 간결함을 위해 생략했지만 패턴은 동일합니다: 그래픽 상태를 저장하고 `document.rotate(angle)`를 호출한 뒤 도형을 그리며, 마지막에 상태를 복원합니다. 이는 **rotate shape java**와 **how to rotate rectangle**를 실제로 보여줍니다.

## 이러한 변환에 Aspose.Page를 사용하는 이유
- **디바이스 독립적**: 한 번 작성하면 플랫폼‑특정 코딩 없이 PostScript 또는 XPS를 생성합니다.  
- **세밀한 제어**: 그래픽 상태에 직접 접근하여 이동, 스케일링, 전단, 회전을 자유롭게 조합할 수 있습니다.  
- **성능**: 대용량 문서의 배치 처리에 적합한 저오버헤드 API입니다.  

## 일반적인 사용 사례
- 동적 바코드와 로고가 포함된 인쇄용 청구서 생성.  
- 정밀한 스케일링 및 위치 지정이 필요한 기술 다이어그램 제작.  
- PostScript 형식의 다중 페이지 보고서를 자동으로 생성.  

## 결론
이 튜토리얼에서는 Aspose.Page for Java를 사용한 Java 페이지 조작에서 다양한 변환을 살펴보았으며, 특히 **how to scale rectangle**, **how to translate shape**, 그리고 기타 affine 연산에 중점을 두었습니다. 예제를 따라 하면 Java 애플리케이션에 고급 페이지 조작 기능을 추가하고 **create PostScript document** 출력을 통해 전문적인 출판 기준을 충족할 수 있습니다.

## FAQ
### Aspose.Page for Java를 다른 문서 형식에도 사용할 수 있나요?
Aspose.Page는 주로 PostScript 및 XPS 형식의 페이지 조작에 중점을 두고 있습니다.

### Aspose.Page for Java에 대한 더 많은 예제와 문서는 어디서 찾을 수 있나요?
포괄적인 정보는 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)을 방문하십시오.

### Aspose.Page for Java의 무료 체험판이 있나요?
예, 무료 체험판은 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.

### Aspose.Page for Java에 대한 임시 라이선스를 어떻게 받을 수 있나요?
임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 얻을 수 있습니다.

### Aspose.Page for Java에 대한 커뮤니티 지원이나 질문은 어디서 할 수 있나요?
커뮤니티 토론은 [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)에서 확인하십시오.

## Frequently Asked Questions

**Q: `translate`와 `scale`의 차이점은 무엇인가요?**  
A: `translate`는 좌표계의 원점을 이동시키고, `scale`은 X 및/또는 Y 축을 따라 그려진 객체의 크기를 변경합니다.

**Q: 하나의 그래픽 상태에서 여러 변환을 결합할 수 있나요?**  
A: 예—그리기 전에 `translate`, `scale`, `rotate`, `shear` 등을 순차적으로 호출하면 결합된 affine 변환을 만들 수 있습니다.

**Q: 도형을 그린 후 변환을 어떻게 초기화하나요?**  
A: `document.writeGraphicsRestore()`를 사용해 이전에 저장한 그래픽 상태로 복원합니다.

**Q: 사각형을 중심을 기준으로 회전시킬 수 있나요?**  
A: 물론 가능합니다. 사각형을 원점으로 이동한 뒤 `rotate(angle)`를 적용하고, 다시 원래 위치로 이동한 후 그립니다.

**Q: Aspose.Page가 부드러운 그래픽을 위한 안티앨리어싱을 지원하나요?**  
A: 예—`PsSaveOptions`에서 적절한 렌더링 옵션을 설정하면 안티앨리어싱을 활성화할 수 있습니다.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}