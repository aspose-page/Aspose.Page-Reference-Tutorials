---
date: 2026-04-30
description: Aspose.Page Java를 사용하여 Java에서 XPS 문서를 생성하고 불투명도 마스크를 추가하는 방법을 배워보세요.
  코드 예제가 포함된 단계별 가이드.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Java XPS에서 불투명도 마스크 설정
second_title: Aspose.Page Java API
title: Java로 XPS 문서 만들기 – Aspose.Page를 사용한 불투명도 마스크 설정
url: /ko/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java XPS에서 Aspose.Page Java를 사용하여 불투명도 마스크 설정

## 소개
이 튜토리얼에서는 **Java XPS 문서** 파일을 **생성**하고 그래픽에 세련되고 반투명한 효과를 주는 불투명도 마스크를 적용하는 방법을 배웁니다. XPS 문서 초기화, 캔버스 추가, 사각형 그리기, 이미지 기반 불투명도 마스크 연결까지 직관적인 Aspose.Page Java API를 사용해 전체 과정을 단계별로 안내합니다. 끝까지 따라 하면 프로페셔널한 XPS 파일을 프로그래밍으로 생성하고 필요에 따라 마스크를 어떤 도형에도 재사용할 수 있게 됩니다.

## 빠른 답변
- **불투명도 마스크는 무엇을 하나요?** 도형에 대해 투명도 수준을 다양하게 정의하여 아래 콘텐츠가 비쳐 보이게 합니다.  
- **필요한 라이브러리는 무엇인가요?** Aspose.Page for Java (aspose page java).  
- **라이선스가 필요합니까?** 테스트용 임시 라이선스로도 동작하지만, 실제 운영을 위해서는 정식 라이선스가 필요합니다.  
- **코드 라인은 몇 줄인가요?** Java 코드 약 20줄에 몇 개의 설정 문장이 추가됩니다.  
- **여러 도형에 마스크를 재사용할 수 있나요?** 예, 동일한 `ImageBrush`를 여러 경로에 할당할 수 있습니다.

## XPS에서 불투명도 마스크란 무엇인가요?
불투명도 마스크는 비트맵 또는 벡터 형태로 도형의 각 픽셀 알파(투명도)를 제어합니다. 사각형에 적용하면 사각형의 일부는 완전히 불투명하고, 일부는 부분 투명, 일부는 완전 투명해져 추가적인 그리기 레이어 없이도 복잡한 시각 효과를 만들 수 있습니다.

## 왜 Aspose.Page Java를 사용하여 **XPS 문서(java)를 생성**합니까?
- **Pure Java API** – 네이티브 종속성이 없으므로 동일한 코드가 Windows, Linux, macOS에서 실행됩니다.  
- **전체 XPS 사양 준수** – 마스크가 XPS 표준에 정의된 대로 정확히 렌더링됩니다.  
- **객체 지향 설계** – .NET과 유사하여 다른 언어에서 Aspose를 사용한 경험이 있다면 쉽게 익힐 수 있습니다.  
- **고성능** – 대용량 문서 및 배치 처리에 최적화되었습니다.

## 일반적인 사용 사례
- **워터마크** – 페이지 전체에 반투명 로고 적용.  
- **동적 테마** – 생성된 보고서의 UI 요소 시각 스타일 변경.  
- **인쇄 준비 미리보기** – 프린터에 보내기 전에 다양한 불투명도로 디자인이 어떻게 보이는지 표시.

## 전제 조건
시작하기 전에 다음을 준비하세요:
- Java 프로그래밍에 대한 기본 이해.  
- Aspose.Page for Java 라이브러리를 설치합니다. **[여기](https://releases.aspose.com/page/java/)**에서 다운로드할 수 있습니다.  
- 유효한 Aspose.Page 라이선스. 없으신 경우 **[여기](https://purchase.aspose.com/temporary-license/)**에서 임시 라이선스를 얻으세요.  
- Java 애플리케이션을 컴파일하고 실행할 수 있는 개발 환경(예: IntelliJ IDEA, Eclipse, VS Code).

## 패키지 가져오기
먼저 Aspose.Page 라이브러리에서 필요한 클래스를 가져옵니다. 이렇게 하면 API를 프로젝트에서 사용할 수 있습니다.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## 단계별 가이드

### 1단계: 새 XPS 문서 만들기
먼저, 모든 그래픽을 담을 새로운 XPS 문서를 인스턴스화합니다.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### 2단계: 캔버스 추가
캔버스는 XPS 페이지 내부의 그리기 표면 역할을 합니다.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### 3단계: 사각형 추가 및 단색 채우기 적용
여기서는 사각형 경로를 만들고 단색 빨간색 채우기를 적용합니다. 이 사각형은 나중에 불투명도 마스크를 받게 됩니다.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### 4단계: ImageBrush를 사용하여 불투명도 마스크 추가
TIFF 이미지를 로드하고, 소스 및 대상 사각형을 정의한 뒤, 필요에 따라 마스크가 반복되도록 브러시를 타일 모드로 설정합니다.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### 5단계: 결과 XPS 문서 저장
마지막으로 문서를 디스크에 저장합니다. 출력 파일에는 적용된 불투명도 마스크가 있는 사각형이 포함됩니다.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

이 단계를 주의 깊게 따라 Aspose.Page를 사용하여 Java XPS 문서에 **불투명도 마스크 추가** 기능을 통합하세요.

## 일반적인 문제 및 해결 방법
- **이미지를 찾을 수 없음** – `dataDir`가 올바른 폴더를 가리키고 `R08SY_NN.tif`가 존재하는지 확인하세요.  
- **마스크가 단색으로 보임** – 소스 이미지에 실제로 다양한 알파 값이 포함되어 있는지 확인하세요; 완전 불투명 이미지에서는 투명도가 표시되지 않습니다.  
- **타일 모드가 적용되지 않음** – 타일링이 눈에 띄려면 대상 사각형이 소스 사각형보다 작아야 합니다.

## 자주 묻는 질문

**Q: Aspose.Page가 모든 Java 개발 환경과 호환되나요?**  
A: 네, Aspose.Page는 다양한 Java IDE와 빌드 도구와 원활하게 작동하도록 설계되었습니다.

**Q: 라이선스 없이 Aspose.Page를 사용할 수 있나요?**  
A: 임시 라이선스로 라이브러리를 평가할 수는 있지만, 실제 사용을 위해서는 정식 라이선스가 필요합니다.

**Q: 체험 버전에 제한이 있나요?**  
A: 체험판은 크기 또는 기능 제한이 있을 수 있으니, 자세한 내용은 공식 문서를 참고하세요.

**Q: Aspose.Page 지원을 어떻게 받을 수 있나요?**  
A: 커뮤니티 지원을 위해 **[Aspose.Page 포럼](https://forum.aspose.com/c/page/39)**을 방문하거나 프리미엄 지원을 위해 라이선스를 구매하세요.

**Q: Aspose.Page에 대한 환불 보장이 있나요?**  
A: 환불 정책에 대한 정보는 **[구매 페이지](https://purchase.aspose.com/buy)**를 참고하세요.

---

**마지막 업데이트:** 2026-04-30  
**테스트 환경:** Aspose.Page Java 24.11 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}