---
date: 2025-12-28
description: Aspose.Page를 사용해 Java에서 XPS 문서를 만드는 방법과 타일 이미지를 손쉽게 추가하는 방법을 단계별 가이드로
  배워보세요.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Java에서 타일 이미지가 포함된 XPS 문서 만드는 방법
url: /ko/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS 문서 만들기 및 Java에서 타일 이미지 추가

## 소개
현대 Java 개발에서 **XPS 문서** 파일을 프로그래밍 방식으로 **생성**하는 능력은 특히 타일 이미지와 같은 그래픽을 풍부하게 넣어야 할 때 귀중한 기술입니다. Aspose.Page for Java는 이 과정을 간단하게 만들어 주어, 저수준 파일 처리를 신경 쓰지 않고 시각적 디자인에 집중할 수 있게 합니다. 이 튜토리얼에서는 XPS 문서를 만드는 방법, **타일 이미지 추가** 방법, 그리고 결과를 저장하는 방법을 명확한 단계별 코드 예제로 배웁니다.

## 빠른 답변
- **Aspose.Page는 무엇을 하나요?** Java에서 XPS 문서를 생성하고 조작할 수 있는 고수준 API를 제공합니다.  
- **이미지를 타일링할 수 있나요?** 예 – `XpsImageBrush`와 `XpsTileMode.Tile`을 사용합니다.  
- **라이선스가 필요합니까?** 운영 환경에서는 임시 또는 상업용 라이선스가 필요합니다.  
- **지원되는 Java 버전은?** JDK 8 이상이면 모두 호환됩니다.  
- **구현에 걸리는 시간은?** 기본 타일 이미지 시나리오의 경우 대략 10~15분 정도 소요됩니다.

## “XPS 문서 만들기”란?
XPS(XML Paper Specification) 파일은 PDF와 유사한 고정 레이아웃 문서 형식입니다. 프로그래밍 방식으로 XPS 문서를 만들면 Java 코드에서 직접 인쇄 가능하고 장치에 독립적인 파일을 생성할 수 있습니다.

## 왜 타일 이미지를 추가하나요?
이미지를 타일링하면 그래픽이 정의된 영역 전체에 반복되어 배경, 워터마크 또는 패턴 채우기에 이상적입니다. Aspose.Page의 `XpsTileMode.Tile`을 사용하면 몇 줄의 코드만으로 이를 구현할 수 있습니다.

## 사전 준비
시작하기 전에 다음을 준비하세요:

1. **Java Development Kit (JDK)** – JDK 8 이상이 설치되어 있어야 합니다.  
2. **Aspose.Page for Java** – [웹사이트](https://releases.aspose.com/page/java/)에서 다운로드합니다.  
3. **쓰기 가능한 디렉터리** – 생성된 XPS 파일을 저장할 위치입니다.

## 패키지 가져오기
Java 프로젝트에서 필요한 클래스를 가져옵니다:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## 단계별 가이드

### 단계 1: 프로젝트 설정
Aspose.Page JAR 파일을 프로젝트 클래스패스에 추가하고 import 문이 오류 없이 컴파일되는지 확인합니다.

### 단계 2: XPS 문서 만들기
새 `XpsDocument` 객체를 인스턴스화합니다. 이 객체가 모든 페이지, 경로 및 리소스를 담는 핵심 컨테이너가 됩니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### 단계 3: 타일 이미지 경로 정의
타일링하려는 이미지(예: `R08LN_NN.jpg`)를 `dataDir`이 가리키는 디렉터리에 넣습니다. 이 이미지는 브러시 패턴으로 사용됩니다.

### 단계 4: 타일 이미지 추가
사각형 경로를 만들고 `XpsImageBrush`로 채웁니다. 타일 모드를 `Tile`로 설정하면 이미지가 사각형 전체에 반복됩니다.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### 단계 5: 문서 저장
XPS 파일을 디스크에 저장합니다. 출력 파일에는 방금 정의한 타일 이미지가 포함됩니다.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

다른 페이지나 동일 XPS 문서 내의 다른 도형에 **타일 이미지 추가**가 필요할 때마다 이 단계를 반복하면 됩니다.

## 일반적인 문제와 해결책
| 문제 | 해결책 |
|------|--------|
| 이미지가 표시되지 않음 | 파일 경로(`dataDir + "R08LN_NN.jpg"`)가 정확하고 이미지에 접근 가능한지 확인합니다. |
| 타일 패턴이 늘어남 | 타일 크기를 제어하려면 `Rectangle2D`의 원본 및 대상 값을 조정합니다. |
| 불투명도가 적용되지 않음 | 브러시의 불투명도 설정을 타일 모드 구성 **후**에 수행했는지 확인합니다. |

## 자주 묻는 질문

### Aspose.Page는 모든 Java 버전과 호환되나요?
Aspose.Page는 다양한 Java 버전에서 작동하도록 설계되었습니다. 호환성 여부는 [여기](https://reference.aspose.com/page/java/)의 문서를 확인하세요.

### 상업 프로젝트에 Aspose.Page를 사용할 수 있나요?
예, Aspose.Page는 상업용 라이선스를 제공합니다. 라이선스 구매는 [여기](https://purchase.aspose.com/buy)에서 가능합니다.

### 무료 체험판이 있나요?
예, 무료 체험판은 [여기](https://releases.aspose.com/)에서 확인할 수 있습니다.

### 커뮤니티 지원 및 토론은 어디서 찾을 수 있나요?
Aspose.Page 커뮤니티는 [포럼](https://forum.aspose.com/c/page/39)에서 활동하고 있습니다.

### Aspose.Page 임시 라이선스는 어떻게 얻나요?
임시 라이선스는 [여기](https://purchase.aspose.com/temporary-license/)에서 획득할 수 있습니다.

---

**마지막 업데이트:** 2025-12-28  
**테스트 환경:** Aspose.Page for Java 24.12 (최신)  
**작성자:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
