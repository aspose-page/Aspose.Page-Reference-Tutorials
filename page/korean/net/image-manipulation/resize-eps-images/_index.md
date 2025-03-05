---
title: .NET용 Aspose.Page를 사용하여 EPS 이미지 크기 조정
linktitle: EPS 이미지 크기 조정
second_title: Aspose.페이지 .NET API
description: Aspose.Page를 사용하여 .NET에서 EPS 이미지 크기를 조정하는 원활한 프로세스를 살펴보세요. 포인트, 인치, 밀리미터, 백분율 단위의 정밀도를 쉽게 달성할 수 있습니다.
type: docs
weight: 11
url: /ko/net/image-manipulation/resize-eps-images/
---
## 소개

.NET용 Aspose.Page를 사용하여 EPS 이미지 크기를 원활하게 조정하고 싶으십니까? 이 튜토리얼은 포인트, 인치, 밀리미터 및 백분율과 같은 다양한 단위로 EPS 이미지의 크기를 손쉽게 조작하기 위한 포괄적인 가이드입니다. .NET용 Aspose.Page는 강력한 도구 세트를 제공하며, 이 튜토리얼에서는 프로세스를 단계별로 안내합니다.

## 전제 조건

크기 조정 마법을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET 라이브러리용 Aspose.Page: .NET 라이브러리용 Aspose.Page가 설치되어 있는지 확인하세요. 다음에서 다운로드할 수 있습니다.[여기](https://releases.aspose.com/page/net/).

- 문서 디렉터리: 입력 EPS 파일과 크기가 조정된 출력 파일을 저장할 디렉터리를 만듭니다.

이제 모든 설정이 완료되었으므로 필요한 네임스페이스를 가져오고 단계별 가이드를 살펴보겠습니다.

## 네임스페이스 가져오기

.NET 프로젝트에서 Aspose.Page 작업에 필요한 네임스페이스를 가져오는 것부터 시작하세요. 파일 시작 부분에 다음 코드를 추가합니다.

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

## 1단계: 포인트 크기 조정

EPS 이미지의 크기를 포인트 단위로 조정하는 것부터 시작해 보겠습니다. 포인트는 인쇄 업계의 표준 측정 단위입니다.

```csharp
public static void ResizeInPoints()
{
    // 귀하의 문서 디렉토리
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

## 2단계: 인치 단위로 크기 조정

이제 그래픽 디자인에서 흔히 사용되는 단위인 인치 단위로 EPS 이미지의 크기를 조정해 보겠습니다.

```csharp
public static void ResizeInInches()
{
    // 귀하의 문서 디렉토리
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

## 3단계: 밀리미터 단위로 크기 조정

이제 디자인과 인쇄에 널리 사용되는 또 다른 단위인 EPS 이미지의 크기를 밀리미터 단위로 조정해 보겠습니다.

```csharp
public static void ResizeInMillimeters()
{
    // 귀하의 문서 디렉토리
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

## 4단계: 백분율로 크기 조정

마지막으로 백분율을 사용하여 EPS 이미지의 크기를 조정하여 이미지 크기를 조정하는 유연한 접근 방식을 제공하겠습니다.

```csharp
public static void ResizeInPercents()
{
    // 귀하의 문서 디렉토리
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

이러한 방법을 프로젝트에 자유롭게 통합하면 EPS 이미지의 크기를 쉽게 조정할 수 있습니다. 원하는 크기를 얻기 위해 다양한 단위를 실험해 보세요.

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 EPS 이미지 크기를 조정하는 기술을 마스터했습니다. 이 강력한 라이브러리는 벡터 그래픽을 조작할 수 있는 가능성의 세계를 열어줍니다. 인쇄용이든 디지털 미디어용이든 Aspose.Page를 사용하면 정확하고 맞춤화된 결과를 얻을 수 있습니다.

## FAQ

### Q1: 여러 EPS 이미지의 크기를 동시에 조정할 수 있나요?

A1: 예, 그에 따라 크기 조정 방법을 적용하여 EPS 파일 모음을 반복할 수 있습니다.

### Q2: Aspose.Page는 다른 이미지 형식과 호환됩니까?

A2: Aspose.Page는 주로 PostScript 및 EPS 형식에 중점을 둡니다. 다른 이미지 형식의 경우 Aspose.Imaging 사용을 고려하세요.

### Q3: 상업 프로젝트에 대한 라이센스 고려 사항이 있습니까?

 A3: 네, 유효한 라이센스가 있는지 확인하세요. 방문하다[여기](https://purchase.aspose.com/buy) 라이선스 세부정보를 확인하세요.

### Q4: 구매하기 전에 Aspose.Page를 사용해 볼 수 있나요?

 A4: 물론이죠! 무료 평가판을 받을 수 있습니다.[여기](https://releases.aspose.com/).

### Q5: 추가 도움을 구하거나 문제를 논의할 수 있는 곳은 어디입니까?

 A5: 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 지역사회와 연결하고 도움을 받으려면