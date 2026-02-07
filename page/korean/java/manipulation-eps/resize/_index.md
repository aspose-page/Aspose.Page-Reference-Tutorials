---
date: 2026-02-07
description: Java에서 EPS 파일 크기를 조정하고 Aspose.Page를 사용하여 EPS 치수를 변경하는 방법을 배워보세요. 이 단계별
  가이드는 포인트, 인치, 밀리미터 또는 백분율로 EPS를 크기 조정하는 방법을 보여줍니다.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Aspose.Page를 사용하여 Java에서 EPS 파일 크기 조정하는 방법
url: /ko/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java와 Aspose.Page를 사용하여 EPS 파일 크기 조정 방법

## 소개
프로그래밍 방식으로 **how to resize EPS** 파일을 신뢰할 수 있게 찾고 있다면, 올바른 곳에 오셨습니다. 이 튜토리얼에서는 Aspose.Page 라이브러리를 사용하여 Java에서 EPS 이미지를 크기 조정하는 과정을 단계별로 안내합니다. 크기를 두 배로 늘리든, 특정 측정값으로 축소하든, 백분율로 작업하든, 아래 단계는 출력 차원을 완벽히 제어할 수 있게 해줍니다. **how to resize eps** 를 이해하는 것은 다양한 인쇄 레이아웃이나 화면 해상도에 맞게 그래픽을 조정해야 할 때 필수적입니다.

## 빠른 답변
- **필요한 라이브러리는 무엇인가요?** Aspose.Page for Java  
- **포인트, 인치, 밀리미터 중 어떤 단위로도 크기 조정이 가능한가요?** Yes – the API supports all three units plus percentages.  
- **개발에 라이선스가 필요한가요?** A free trial works for testing; a license is required for production.  
- **필요한 Java 버전은 무엇인가요?** Java 8 or later.  
- **코드가 스레드 안전한가요?** Each `PsDocument` instance is isolated, so you can process files in parallel.  

## EPS란 무엇이며 왜 크기를 조정해야 할까요?
Encapsulated PostScript (EPS)는 출판 및 인쇄에 사용되는 인기 있는 벡터 그래픽 형식입니다. 때때로 원본 EPS 파일이 목표 출력에 맞지 않는 크기로 만들어집니다 – 예를 들어, 72 pts로 디자인된 로고를 더 큰 브로셔용으로 144 pts가 필요할 수 있습니다. **how to resize eps** 를 알면 벡터 품질을 유지하면서 작업 흐름에 맞게 차원을 조정할 수 있습니다.

## 왜 EPS 크기 조정에 Aspose.Page를 사용해야 할까요?
- **단위에 대한 완전한 제어** – points, inches, millimeters, or percentages.  
- **외부 종속성 없음** – pure Java API, no native libraries.  
- **고성능** – suitable for batch processing on servers.  
- **벡터 정확도 유지** – the output remains scalable without rasterization.

## 전제 조건
코드에 들어가기 전에 다음이 준비되어 있는지 확인하세요:

- Java Development Kit (JDK)가 머신에 설치되어 있어야 합니다.  
- Aspose.Page for Java 라이브러리. **[여기](https://releases.aspose.com/page/java/)**에서 다운로드할 수 있습니다.  
- Java 프로그래밍에 대한 기본적인 이해.

## 패키지 가져오기
Java 프로젝트에서 Aspose.Page 객체와 표준 I/O 스트림을 사용할 수 있도록 필요한 import를 포함하세요.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## 다양한 단위로 EPS 차원 변경 방법
라이브러리를 사용하면 적절한 `Units` 열거형을 선택하여 **change eps dimensions** 를 간단히 수행할 수 있습니다. 아래에서는 포인트, 인치, 밀리미터, 백분율에 대해 동일한 5단계 패턴을 안내합니다. 변경되는 유일한 부분은 `resizeEps`에 전달하는 단위입니다.

## 포인트를 사용하여 EPS 크기 조정 방법
아래는 측정 단위로 포인트를 사용하여 EPS 파일의 크기를 두 배로 늘리는 완전한 단계별 예제입니다.

### Step 1: 입력 스트림 설정
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Step 2: `PsDocument` 객체 초기화
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Step 3: EPS 이미지의 현재 크기 추출
```java
Dimension oldSize = doc.extractEpsSize();
```

### Step 4: 크기 조정된 파일을 위한 출력 스트림 생성
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Step 5: 포인트를 사용하여 EPS 크기 조정 및 저장
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## 인치를 사용하여 EPS 크기 조정 방법
동일한 5단계 패턴을 적용하면 됩니다; `Units.Points`를 `Units.Inches`로 교체하고 원하는 인치 값에 맞게 스케일링 팩터를 조정하세요.

## 밀리미터를 사용하여 EPS 크기 조정 방법
다시 한 번 동일한 단계를 따라가며 단위를 `Units.Millimeters`로 교체합니다. 인쇄 작업 흐름에 메트릭 기반 차원이 필요할 때 유용합니다.

## 백분율을 사용하여 EPS 크기 조정 방법
백분율 기반 스케일링의 경우, 단위를 `Units.Percent`로 유지합니다. 원하는 백분율만큼 원본 너비와 높이를 곱합니다(예: 50 % 감소를 위해 `0.5`).

## 일반적인 함정 및 팁
- **항상 스트림을 닫으세요** – In production code, wrap streams in try‑with‑resources to avoid file locks.  
- **종횡비 유지** – Multiply both width and height by the same factor unless you intentionally want distortion.  
- **DPI 확인** – Resizing does not change the DPI; if you need a different DPI, adjust it separately after resizing.  
- **스레드 안전성** – Create a new `PsDocument` per thread; sharing the same instance can lead to unexpected results.  

## 자주 묻는 질문

**Q: 이 라이브러리를 다른 이미지 형식에 사용할 수 있나요?**  
A: No, Aspose.Page is specialized for PostScript and EPS files only.

**Q: Aspose.Page for Java에 대한 무료 체험판이 있나요?**  
A: Yes, you can explore the free trial **[여기](https://releases.aspose.com/)**.

**Q: 추가 도움 및 토론을 어디서 찾을 수 있나요?**  
A: Visit the **[Aspose.Page 포럼](https://forum.aspose.com/c/page/39)** for community support.

**Q: 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: You can get a temporary license **[여기](https://purchase.aspose.com/temporary-license/)**.

**Q: 예제 프로젝트가 있나요?**  
A: Yes, check the documentation **[여기](https://reference.aspose.com/page/java/)**.

---

**마지막 업데이트:** 2026-02-07  
**테스트 환경:** Aspose.Page for Java 24.12 (latest at time of writing)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}