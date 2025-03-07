---
title: .NET용 Aspose.Page를 사용한 변환 PS
linktitle: 변환 PS
second_title: Aspose.페이지 .NET API
description: PostScript 변환에 대한 포괄적인 가이드를 통해 Aspose.Page for .NET의 잠재력을 활용해 보세요. 역동적인 그래픽을 쉽게 만들어 보세요.
weight: 12
url: /ko/net/canvas-manipulation/transformationsps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Page를 사용한 변환 PS

## 소개

PostScript 문서에서 변환의 힘을 발휘할 수 있는 .NET용 Aspose.Page의 세계에 오신 것을 환영합니다. 이 튜토리얼은 시각적으로 놀랍고 역동적인 그래픽을 만들 수 있도록 변환, 크기 조정, 회전, 기울이기 및 복잡한 변환과 같은 다양한 변환을 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET 라이브러리용 Aspose.Page: 프로젝트에 .NET용 Aspose.Page 라이브러리가 통합되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[다운로드 링크](https://releases.aspose.com/page/net/).

- 문서 디렉터리: 문서 디렉터리를 설정하고 코드의 자리 표시자를 실제 경로로 바꿉니다.

## 네임스페이스 가져오기

.NET 프로젝트에서 Aspose.Page 작업에 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

이제 단계별 가이드 형식으로 각 예를 여러 단계로 나누어 보겠습니다.


## 변환 없음

### 1단계: 출력 스트림 생성

```csharp
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";

// PostScript 문서의 출력 스트림 생성
using (Stream outPsStream = new FileStream(dataDir + "Transformations_outPS.ps", FileMode.Create))
{
    // 기본값으로 저장 옵션 생성
    PsSaveOptions options = new PsSaveOptions();

    // 새로운 1페이지 PS 문서 만들기
    PsDocument document = new PsDocument(outPsStream, options, false);

    document.Translate(100, 100);

    // 직사각형에서 그래픽 경로 만들기
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(0, 0, 150, 100));

    // 상위 수준의 그래픽 상태에서 페인트 설정
    document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

    // 상위 레벨 그래픽 상태에 있고 변환 없이 첫 번째 직사각형을 채웁니다.
    document.Fill(path);

    // 현재 페이지 닫기
    document.ClosePage();

    // 문서 저장
    document.Save();
}
```

이 코드는 변환 없이 직사각형을 주황색으로 채우는 PostScript 문서를 만듭니다.

## 번역

### 1단계: 그래픽 상태 저장

```csharp
// 변환 후 이 상태로 돌아가려면 그래픽 상태를 저장하세요.
document.WriteGraphicsSave();
```

이 단계는 현재 그래픽 상태를 저장하므로 변환 후 해당 상태로 돌아갈 수 있습니다.

### 2단계: 그래픽 상태 변환

```csharp
// 현재 그래픽 상태 250을 오른쪽으로 변위
document.Translate(250, 0);
```

변환 구성 요소를 추가하여 현재 그래픽 상태를 변환한 다음 현재 그래픽 상태의 페인트를 파란색으로 설정합니다.

### 3단계: 변환 변환으로 직사각형 채우기

```csharp
// 현재 그래픽 상태에서 페인트 설정
document.SetPaint(new System.Drawing.SolidBrush(Color.Blue));

// 현재 그래픽 상태에서 두 번째 직사각형을 채웁니다(변환 변환 있음).
document.Fill(path);
```

이 단계는 현재 그래픽 상태의 두 번째 직사각형을 채우며 이제 변환 변환을 포함합니다.

### 4단계: 그래픽 상태 복원

```csharp
// 그래픽 상태를 이전(상위) 수준으로 복원
document.WriteGraphicsRestore();
```

직사각형을 채운 후 그래픽 상태를 이전 수준으로 복원합니다.

크기 조정, 회전, 전단 및 복합 변환을 포함한 각 변환 유형에 대해 이 단계별 가이드를 계속 진행하세요.

## 결론

축하해요! .NET용 Aspose.Page의 혁신적인 기능을 성공적으로 탐색했습니다. 이제 다양한 조합을 실험하고 PostScript 문서 변환에서 창의력을 발휘해 보세요.

## FAQ

### Q1: 단일 개체에 여러 변형을 적용하려면 어떻게 해야 합니까?

A1: 여러 변환을 적용하려면`Transform` 사용자 정의 변환 행렬을 사용하는 방법입니다.

### Q2: 문서를 저장하기 전에 변환을 미리 볼 수 있습니까?

A2: 예, 문서를 렌더링하고 적절한 뷰어에서 미리 보면 변형을 시각화할 수 있습니다.

### Q3: 문서의 특정 요소에 변형을 적용할 수 있습니까?

A3: 예, 문서 내의 특정 그래픽 요소에 대한 변환을 분리할 수 있습니다.

### Q4: 복잡한 변환을 처리할 때 성능 고려 사항이 있습니까?

A4: 복잡한 변환은 성능에 영향을 미칠 수 있으므로 효율성을 위해 코드를 최적화하세요.

### Q5: Aspose.Page 관련 쿼리에 대해 어떻게 지원을 받거나 도움을 구할 수 있나요?

 A5: 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 커뮤니티 지원 및 토론을 위해.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
