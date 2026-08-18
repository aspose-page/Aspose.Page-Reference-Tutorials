---
date: 2026-02-15
description: Aspose.Page Java를 사용하여 Java PostScript 파일에 해치 패턴을 추가하는 방법을 배웁니다. 이 단계별
  가이드는 전체 코드와 팁을 보여줍니다.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: Aspose.Page를 사용한 Java PostScript에서 해치 패턴 추가 방법
url: /ko/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PostScript에서 Hatch 패턴 추가하기

## 소개
**Aspose.Page Java**를 사용하고 있으며 PostScript 출력에 **hatch pattern을 추가하는 방법**을 궁금해한다면, hatch 패턴은 빠르고 유연한 솔루션입니다. 이 튜토리얼에서는 PostScript 문서에 **hatch 디자인을 추가하는 방법**을 단계별로 살펴보고, 왜 유용한지 설명하며, 바로 실행할 수 있는 완전한 코드 예제를 제공합니다. 끝까지 읽으면 몇 줄의 Java 코드만으로 시각적으로 매력적인 hatch‑채워진 도형과 텍스트를 만들 수 있게 됩니다.

## 빠른 답변
- **어떤 라이브러리가 필요합니까?** Aspose.Page for Java (“aspose page java” SDK).  
- **어떤 시각 효과를 추가합니까?** Hatch 패턴 (예: 대각선 라인, 교차 해치).  
- **샘플을 실행하려면 라이선스가 필요합니까?** 개발 단계에서는 무료 체험판으로 충분하지만, 운영 환경에서는 라이선스가 필요합니다.  
- **코드 라인은 몇 줄입니까?** 약 70줄이며, 명확한 단계로 구분됩니다.  
- **PDF에도 같은 접근 방식을 사용할 수 있나요?** 예—Aspose.Page는 PDF를 포함한 여러 출력 형식을 지원합니다.

## Hatch 패턴 추가 방법 – 개요
Hatch 패턴은 벡터 기반 텍스처로, 어떤 해상도에서도 깨끗하게 렌더링되며 흑백 프린터에서도 잘 작동합니다. Aspose.Page Java를 사용하면 저수준 PostScript 명령을 직접 다루지 않고도 도형, 경로, 텍스트에 이러한 패턴을 적용할 수 있습니다.

## 전제 조건
시작하기 전에 다음을 준비하세요:

- **Java 개발 환경** – JDK 8 이상 및 원하는 IDE.  
- **Aspose.Page for Java 라이브러리** – 공식 사이트 [here](https://releases.aspose.com/page/java/)에서 최신 JAR을 다운로드합니다.  
- **쓰기 권한** – 생성된 PostScript 파일이 저장될 폴더에 대한 쓰기 접근 권한.

## 패키지 가져오기
먼저 프로젝트에 필요한 클래스를 가져옵니다. 이러한 import 구문을 통해 그리기 기본 요소, 색상 처리 및 Aspose.Page API에 접근할 수 있습니다.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## 단계 1: 초기 매개변수 설정
출력 스트림을 생성하고 페이지 크기(A4)를 구성한 뒤, 각 hatch‑채워진 사각형을 그릴 때 재사용할 레이아웃 변수를 정의합니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## 단계 2: 그래픽 상태 저장 및 변환
그래픽 상태를 저장하면 나중에 원래 좌표계로 복귀할 수 있고, `translate`를 사용해 시작점을 편리한 위치로 이동합니다.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## 단계 3: 각 패턴에 대한 사각형 만들기
각 hatch‑채워진 셀을 나타낼 재사용 가능한 사각형을 정의합니다.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## 단계 4: 패턴 사각형 외곽선용 펜 설정
2 포인트 두께의 `BasicStroke`가 각 사각형 주변에 선명한 외곽선을 제공합니다.

```java
BasicStroke stroke = new BasicStroke(2);
```

## 단계 5: Hatch 패턴 순회
`HatchStyle` 열거형의 모든 값을 순회하면서 각 사각형을 해당 텍스처로 채우고 외곽선을 그립니다. 이것이 **hatch pattern을 추가**하는 핵심 기능입니다.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## 단계 6: 그래픽 상태 복원
사각형 그리기 그리드를 완료한 후 원래 좌표계로 복귀합니다.

```java
document.writeGraphicsRestore();
```

## 단계 7: 텍스트를 Hatch 패턴으로 채우기
여기서는 대각선‑교차 패턴으로 단어 “ABC”를 채우는 예제를 보여줍니다.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## 단계 8: 텍스트를 Hatch 패턴으로 외곽선 그리기
이번에는 70 % hatch 스타일과 더 두꺼운 스트로크를 사용해 동일한 텍스트에 외곽선을 그립니다.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## 단계 9: 문서 닫기 및 저장
페이지를 마무리하고 파일을 디스크에 기록한 뒤 리소스를 해제합니다.

```java
document.closePage();
document.save();
```

이 단계를 따라 하면 **aspose page java**가 구동하는 완전한 hatch 패턴 세트를 도형과 텍스트 모두에 적용한 PostScript 파일을 얻을 수 있습니다.

## Aspose.Page Java와 함께 Hatch 패턴을 사용하는 이유
- **시각적 구분** – 프린터가 흑백 출력만 지원해도 Hatch 채우기가 작동합니다.  
- **성능** – 텍스처가 실시간으로 생성되어 큰 이미지 파일을 피할 수 있습니다.  
- **다중 포맷 지원** – 동일한 코드를 최소한의 수정으로 PDF, EPS, SVG 등에 적용할 수 있습니다.

## 일반적인 함정 및 팁
- **파일 경로 오류** – `dataDir`이 적절한 파일 구분자(`/` 또는 `\`)로 끝나는지 확인하세요.  
- **지원되지 않는 색상** – 일부 오래된 PostScript 인터프리터는 특정 색상 공간을 처리하지 못할 수 있습니다; 최대 호환성을 위해 기본 RGB를 사용하세요.  
- **라이선스 경고** – 유효한 라이선스 없이 샘플을 실행하면 출력에 워터마크가 삽입됩니다.

## 결론
Hatch 패턴을 도입하면 기술 도면, 지도 또는 Java로 생성된 모든 그래픽의 가독성과 미관을 크게 향상시킬 수 있습니다. **Aspose.Page Java**를 사용하면 저수준 PostScript 명령을 추상화하는 간결한 API를 제공하므로 파일 포맷의 복잡성보다 디자인에 집중할 수 있습니다. 이제 **PostScript 문서에 hatch pattern을 추가하는 방법**을 알게 되었으니, 다양한 `HatchStyle` 값을 실험해 원하는 모습을 구현해 보세요.

## 자주 묻는 질문

**Q: Aspose.Page Java를 다른 Java 프레임워크와 함께 사용할 수 있나요?**  
A: 예, 이 라이브러리는 프레임워크에 구애받지 않으며 Spring, Jakarta EE, Android(제한적), 순수 Java SE와 모두 호환됩니다.

**Q: Aspose.Page Java의 체험판이 제공되나요?**  
A: 물론입니다. 무료 30일 체험판을 [here](https://releases.aspose.com/)에서 다운로드하세요.

**Q: 개발용 임시 라이선스는 어떻게 얻나요?**  
A: 임시 라이선스를 [here](https://purchase.aspose.com/temporary-license/)에서 요청하세요. 평가용 워터마크가 제거됩니다.

**Q: 더 많은 튜토리얼과 커뮤니티 지원은 어디서 찾을 수 있나요?**  
A: 공식 포럼 [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)에서 추가 예제와 Q&A를 확인하세요.

**Q: 모든 클래스와 메서드에 대한 포괄적인 문서는 있나요?**  
A: 예, 전체 API 레퍼런스는 [here](https://reference.aspose.com/page/java/)에서 확인할 수 있습니다.

**Q: PostScript 대신 PDF에 동일한 hatch 패턴을 렌더링할 수 있나요?**  
A: 물론입니다. `PsSaveOptions`를 `PdfSaveOptions`(또는 동등한 옵션)로 변경하면 나머지 코드는 그대로 사용할 수 있습니다.

**Q: 생성된 파일이 비어 있으면 어떻게 해야 하나요?**  
A: 출력 스트림이 쓰기 가능한 디렉터리를 가리키는지, 그리고 모든 그리기 작업 후 `document.save()`가 호출되는지 확인하세요.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}