---
date: 2026-03-03
description: Aspose.Page를 사용하여 .NET에서 EPS 이미지를 크기 조정하는 방법을 배워보세요 – 포인트, 인치, 밀리미터 또는
  백분율을 사용해 EPS를 크기 조정하는 단계별 가이드.
linktitle: Resize EPS Images
second_title: Aspose.Page .NET API
title: .NET용 Aspose.Page로 EPS 이미지 크기 조정하는 방법
url: /ko/net/image-manipulation/resize-eps-images/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET을 사용한 EPS 이미지 크기 조정 방법

## 소개

Aspose.Page for .NET을 사용하여 **EPS 이미지를 크기 조정하는 방법**을 찾고 계신가요? 이 튜토리얼은 포인트, 인치, 밀리미터, 퍼센트와 같은 다양한 단위로 EPS 이미지 크기를 손쉽게 조절하는 포괄적인 가이드입니다. Aspose.Page for .NET은 강력한 도구 모음을 제공하며, 이 튜토리얼에서는 단계별로 과정을 안내합니다.

## 빠른 답변
- **EPS 크기 조정을 담당하는 라이브러리는?** Aspose.Page for .NET  
- **지원되는 단위는?** 포인트, 인치, 밀리미터, 퍼센트  
- **프로덕션에 라이선스가 필요합니까?** 예 – 상용 라이선스가 필요합니다  
- **여러 파일을 한 번에 크기 조정할 수 있나요?** 물론입니다 – 파일을 순회하면 됩니다  
- **.NET Core를 지원하나요?** 예, API는 .NET Framework와 .NET Core 모두에서 작동합니다  

## EPS 크기 조정이란?
Encapsulated PostScript (EPS)는 인쇄 및 디자인 워크플로우에서 일반적으로 사용되는 벡터 기반 그래픽 형식입니다. EPS 파일의 크기를 조정하면 아트워크를 래스터화하지 않고 경계 상자를 변경하여 어떤 스케일에서도 선명함을 유지합니다.

## EPS 이미지를 크기 조정해야 하는 이유
- **인쇄 품질 유지:** 벡터 스케일링은 가장자리를 선명하게 유지합니다.  
- **레이아웃 요구사항에 맞춤:** 페이지 또는 캔버스 크기에 맞게 치수를 조정합니다.  
- **배치 작업 자동화:** 수십 개의 파일을 몇 초 만에 프로그래밍 방식으로 크기 조정합니다.  

## 사전 요구 사항

크기 조정 마법에 들어가기 전에 다음 사전 요구 사항이 준비되어 있는지 확인하세요:

- Aspose.Page for .NET 라이브러리: Aspose.Page for .NET 라이브러리가 설치되어 있는지 확인하십시오. [여기](https://releases.aspose.com/page/net/)에서 다운로드할 수 있습니다.

- 문서 디렉터리: 입력 EPS 파일과 출력 크기 조정 파일을 저장할 디렉터리를 생성합니다.

모든 준비가 끝났다면 필요한 네임스페이스를 가져오고 단계별 가이드를 진행해 보겠습니다.

## 네임스페이스 가져오기

.NET 프로젝트에서 Aspose.Page와 작업하기 위해 필요한 네임스페이스를 가져옵니다. 파일 시작 부분에 다음 코드를 추가하세요:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## 포인트 단위로 EPS 크기 조정하기

포인트는 인쇄 산업에서 표준 측정 단위입니다. 아래 예제는 원본 너비와 높이를 두 배로 늘립니다.

```csharp
public static void ResizeInPoints()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_points.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(oldSize.Width * 2, oldSize.Height * 2), Units.Points);
        }
    }
}
```

## 인치 단위로 EPS 크기 조정하기

인치는 그래픽 디자이너가 인쇄용 자산을 준비할 때 자주 사용하는 단위입니다.

```csharp
public static void ResizeInInches()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_inches.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
        }
    }
}
```

## 밀리미터 단위로 EPS 크기 조정하기

밀리미터는 미터법을 사용하는 지역에서 일반적인 단위입니다.

```csharp
public static void ResizeInMillimeters()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_mms.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
        }
    }
}
```

## 퍼센트 단위로 EPS 크기 조정하기

퍼센트 기반 크기 조정은 원본 크기에 대한 비율로 이미지를 스케일링할 수 있게 해줍니다.

```csharp
public static void ResizeInPercents()
{
    // Your Document Directory
    string dataDir = "Your Document Directory";

    using (Stream inputEpsStream = new FileStream(dataDir + "input.eps", FileMode.Open, FileAccess.Read))
    {
        PsDocument doc = new PsDocument(inputEpsStream);

        Size oldSize = doc.ExtractEpsSize();

        using (Stream outputEpsStream = new FileStream(dataDir + "output_resize_percents.eps", FileMode.Create, FileAccess.Write))
        {
            doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
        }
    }
}
```

이 방법들을 프로젝트에 자유롭게 통합하면 EPS 이미지를 손쉽게 크기 조정할 수 있습니다. 원하는 치수를 얻기 위해 다양한 단위를 실험해 보세요.

## 일반적인 문제와 해결 방법
- **파일을 찾을 수 없음:** `dataDir`이 올바른 폴더를 가리키고 `input.eps`가 존재하는지 확인하세요.  
- **예상치 못한 크기:** `Units.Percents`는 150과 같이 150 %를 의미하는 값을 기대합니다.  
- **라이선스 예외:** 라이선스 오류가 발생하면 `PsDocument`를 생성하기 전에 유효한 Aspose.Page 라이선스 파일을 로드했는지 확인하세요.

## 결론

축하합니다! Aspose.Page for .NET을 사용하여 **EPS 이미지를 크기 조정하는 방법**을 마스터했습니다. 이 강력한 라이브러리는 벡터 그래픽을 조작할 수 있는 다양한 가능성을 열어줍니다. 인쇄든 디지털 미디어든, Aspose.Page를 통해 정밀하고 맞춤화된 결과를 얻을 수 있습니다.

## FAQ's

### Q1: 여러 EPS 이미지를 동시에 크기 조정할 수 있나요?

A1: 예, EPS 파일 컬렉션을 순회하면서 크기 조정 메서드를 적용하면 됩니다.

### Q2: Aspose.Page가 다른 이미지 형식과 호환되나요?

A2: Aspose.Page는 주로 PostScript와 EPS 형식에 초점을 맞춥니다. 다른 이미지 형식의 경우 Aspose.Imaging을 고려해 보세요.

### Q3: 상업 프로젝트에 대한 라이선스 고려 사항이 있나요?

A3: 예, 유효한 라이선스를 보유해야 합니다. 라이선스 상세 정보는 [여기](https://purchase.aspose.com/buy)에서 확인하세요.

### Q4: 구매 전에 Aspose.Page를 체험해 볼 수 있나요?

A4: 물론입니다! 무료 체험은 [여기](https://releases.aspose.com/)에서 받을 수 있습니다.

### Q5: 추가 도움을 받거나 이슈를 논의할 수 있는 곳은 어디인가요?

A5: 커뮤니티와 소통하고 지원을 받으려면 [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)을 방문하세요.

## Frequently Asked Questions

**Q: 이 코드는 .NET Core 6에서도 작동하나요?**  
A: 예. API는 .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, .NET 6+와 호환됩니다.

**Q: 원본 색상 프로파일을 유지하려면 어떻게 해야 하나요?**  
A: `ResizeEps` 메서드는 색상 데이터를 변경하지 않으며, 경계 상자만 변경합니다.

**Q: 전체 파일을 메모리에 로드하지 않고 EPS를 크기 조정할 수 있나요?**  
A: 예시와 같이 스트림을 사용하면 메모리 사용량을 낮게 유지하면서 문서를 실시간으로 처리합니다.

**Q: 여러 크기 조정 작업을 연속으로 적용할 수 있나요?**  
A: 물론입니다. 동일 `PsDocument` 인스턴스에서 `ResizeEps`를 순차적으로 호출하면 됩니다.

**Q: EPS 내부에 포함된 이미지들은 어떻게 처리되나요?**  
A: 벡터 콘텐츠와 비례하여 스케일링되며, 품질이 유지됩니다.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}