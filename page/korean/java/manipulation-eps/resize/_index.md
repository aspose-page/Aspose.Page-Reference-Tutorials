---
date: 2025-12-02
description: Aspose.Page를 사용하여 Java에서 EPS 파일을 손쉽게 크기 조정하는 방법을 배워보세요. 이 단계별 가이드는 포인트,
  인치, 밀리미터 또는 백분율을 사용하여 EPS를 크기 조정하는 방법을 보여줍니다.
language: ko
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Aspose.Page를 사용하여 Java에서 EPS 파일 크기 조정하는 방법
url: /java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java와 Aspose.Page를 사용하여 EPS 파일 크기 조정 방법

## 소개
프로그래밍 방식으로 **EPS 파일 크기 조정** 방법을 찾고 있다면, 바로 여기가 정답입니다. 이 튜토리얼에서는 Aspose.Page 라이브러리를 사용해 Java에서 EPS 이미지를 크기 조정하는 과정을 단계별로 안내합니다. 크기를 두 배로 늘리든, 특정 치수로 축소하든, 혹은 백분율로 조정하든, 아래 단계들을 통해 출력 크기를 완벽히 제어할 수 있습니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Page for Java  
- **포인트, 인치, 밀리미터 중 어느 단위로도 크기 조정이 가능한가요?** 예 – API가 세 가지 단위와 백분율을 모두 지원합니다.  
- **개발용 라이선스가 필요한가요?** 테스트용 무료 체험판을 사용할 수 있으며, 실제 운영 환경에서는 라이선스가 필요합니다.  
- **필요한 Java 버전은?** Java 8 이상  
- **코드가 스레드‑안전한가요?** 각 `PsDocument` 인스턴스가 독립적이므로 파일을 병렬 처리할 수 있습니다.

## 사전 준비
코드 작성을 시작하기 전에 다음 항목을 준비하세요:

- 머신에 설치된 Java Development Kit (JDK)  
- Aspose.Page for Java 라이브러리. **[여기](https://releases.aspose.com/page/java/)**에서 다운로드할 수 있습니다.  
- Java 프로그래밍에 대한 기본 이해  

## 패키지 가져오기
Java 프로젝트에 Aspose.Page 객체와 표준 I/O 스트림을 사용할 수 있도록 필요한 import 구문을 포함합니다.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## 포인트 단위로 EPS 크기 조정하기
아래 예제는 포인트 단위를 사용해 EPS 파일의 크기를 두 배로 늘리는 전체 단계별 코드입니다.

### 단계 1: 입력 스트림 설정
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### 단계 2: `PsDocument` 객체 초기화
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### 단계 3: EPS 이미지의 현재 크기 추출
```java
Dimension oldSize = doc.extractEpsSize();
```

### 단계 4: 크기 조정된 파일을 위한 출력 스트림 생성
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### 단계 5: 포인트 단위로 EPS 크기 조정 및 저장
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## 인치 단위로 EPS 크기 조정하기
동일한 5단계 패턴을 사용하되 `Units.Points`를 `Units.Inches`로 교체하고, 필요에 따라 스케일링 팩터를 조정하면 됩니다.

## 밀리미터 단위로 EPS 크기 조정하기
같은 절차를 따르면서 단위를 `Units.Millimeters`로 바꾸면 됩니다. 인쇄 워크플로우에서 메트릭 기반 치수가 필요할 때 유용합니다.

## 백분율 단위로 EPS 크기 조정하기
백분율 기반 스케일링을 위해서는 단위를 `Units.Percent`로 유지하고, 원본 너비와 높이에 원하는 백분율을 곱합니다(예: 50 % 감소는 `0.5`).

## 흔히 발생하는 문제와 팁
- **스트림은 항상 닫아야 합니다** – 실제 코드에서는 try‑with‑resources 구문을 사용해 파일 잠금을 방지하세요.  
- **종횡비 유지** – 왜곡을 원하지 않는 한, 너비와 높이에 동일한 팩터를 곱합니다.  
- **DPI 확인** – 크기 조정만으로 DPI가 바뀌지는 않으니, 필요하다면 크기 조정 후 별도로 DPI를 조정하세요.

## 결론
이제 Java와 Aspose.Page를 사용해 포인트, 인치, 밀리미터, 백분율 중 원하는 단위로 **EPS 파일 크기 조정** 방법을 알게 되었습니다. 이 유연성을 활용해 자동화 파이프라인, 데스크톱 유틸리티, 서버‑사이드 서비스 등에 EPS 조작 기능을 손쉽게 통합할 수 있습니다.

## 자주 묻는 질문

**Q: 이 라이브러리를 다른 이미지 포맷에도 사용할 수 있나요?**  
A: 아니요, Aspose.Page는 PostScript와 EPS 파일 전용입니다.

**Q: Aspose.Page for Java의 무료 체험판을 이용할 수 있나요?**  
A: 예, **[여기](https://releases.aspose.com/)**에서 무료 체험판을 확인할 수 있습니다.

**Q: 추가 도움말 및 토론을 어디서 찾을 수 있나요?**  
A: 커뮤니티 지원을 위해 **[Aspose.Page 포럼](https://forum.aspose.com/c/page/39)**을 방문하세요.

**Q: 임시 라이선스를 어떻게 얻을 수 있나요?**  
A: **[여기](https://purchase.aspose.com/temporary-license/)**에서 임시 라이선스를 발급받을 수 있습니다.

**Q: 예제 프로젝트가 있나요?**  
A: 예, 문서는 **[여기](https://reference.aspose.com/page/java/)**에서 확인할 수 있습니다.

---

**마지막 업데이트:** 2025-12-02  
**테스트 환경:** Aspose.Page for Java 24.12 (작성 시 최신 버전)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}