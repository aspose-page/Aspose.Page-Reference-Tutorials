---
title: .NET용 Aspose.Page를 사용하여 측정 라이선스 적용
linktitle: 계량 라이센스 적용
second_title: Aspose.페이지 .NET API
description: 계량 라이선스 적용에 대한 단계별 가이드를 통해 .NET용 Aspose.Page의 원활한 통합을 살펴보세요. 문서 처리를 손쉽게 최적화하세요.
weight: 10
url: /ko/net/getting-started/apply-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .NET용 Aspose.Page를 사용하여 측정 라이선스 적용

## 소개

계량 라이선스를 적용하여 .NET용 Aspose.Page의 잠재력을 최대한 활용하세요. 이 튜토리얼에서는 이 강력한 .NET 라이브러리를 원활하고 최적화하여 사용할 수 있도록 계량 라이센스를 설정하고 적용하는 과정을 안내합니다.

## 전제 조건

단계를 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

-  .NET 라이센스에 대한 유효한 Aspose.Page: 다음에서 얻을 수 있습니다.[buy.aspose.com](https://purchase.aspose.com/buy).
-  Aspose.Page 라이브러리 설치:[선적 서류 비치](https://reference.aspose.com/page/net/) 설치 지침을 확인하세요.
- .NET 개발 환경: 컴퓨터에 작동하는 .NET 환경이 설정되어 있는지 확인하세요.

## 네임스페이스 가져오기

.NET 프로젝트에서 Aspose.Page 기능에 액세스하는 데 필요한 네임스페이스를 가져옵니다.

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## 1단계: 측정된 공개 및 개인 키 설정

 초기화`Aspose.Page.Metered` 클래스를 선택하고 측정된 공개 키와 개인 키를 설정합니다. 바꾸다`<type public key here>` 그리고`<type private key here>` 실제 키로.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## 2단계: EPS 파일 로드 및 문서 만들기

 EPS 파일의 경로를 지정하고 해당 콘텐츠를 읽을 스트림을 만듭니다. 그런 다음`PsDocument` 스트림의 클래스입니다.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## 3단계: EPS를 PNG 이미지로 변환

 만들기`ImageDevice` EPS 파일을 PNG 이미지로 변환하는 방법입니다. 다음을 사용하여 EPS 파일을 이미지로 저장합니다.`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## 4단계: 이미지 바이트 검색

각 바이트 배열이 한 페이지를 나타내는 이미지 바이트를 가져옵니다. 이 경우에는 한 페이지가 있습니다.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## 5단계: 이미지 바이트를 파일에 저장

EPS에서 PNG로의 성공적인 변환을 보장하기 위해 이미지 바이트를 파일에 저장합니다.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## 6단계: 측정 라이선스 확인

계량 라이센스가 성공적으로 적용되었는지 눈으로 확인하세요. 결과 이미지에 빨간색 평가 메시지가 포함되어 있지 않으면 계량 라이선스가 문제 없이 적용되었음을 나타냅니다.

이제 측정된 라이선스를 통해 Aspose.Page for .NET의 모든 기능을 활용할 준비가 되었습니다!

## 결론

이 단계별 가이드는 Aspose.Page for .NET을 사용하여 계량 라이선스를 원활하게 적용하는 방법에 대한 지식을 제공합니다. 문서 처리 기능을 강화하고 이 강력한 라이브러리가 제공하는 다양한 기능을 탐색해 보세요.

## FAQ

### Q1: .NET용 Aspose.Page에 대한 계량 라이선스를 어떻게 얻나요?

 A1: 방문[buy.aspose.com](https://purchase.aspose.com/buy) 유효한 라이센스를 취득하기 위해.

### Q2: .NET용 Aspose.Page에 대한 설명서는 어디서 찾을 수 있나요?

 A2: 참조[Aspose.페이지 .NET](https://reference.aspose.com/page/net/) 포괄적인 문서화를 위해.

### Q3: Aspose.Page 토론 및 지원을 위한 포럼이 있습니까?

 A3: 그렇습니다, 방문하십시오[법정](https://forum.aspose.com/c/page/39) 지역사회에 참여하고 도움을 구합니다.

### Q4: 구매하기 전에 Aspose.Page for .NET을 사용해 볼 수 있나요?

 A4: 물론이죠! 다음에서 무료 평가판에 액세스하세요.[여기](https://releases.aspose.com/).

### Q5: Aspose.Page for .NET의 임시 라이선스를 어떻게 얻을 수 있나요?

 A5: 방문[임시면허/](https://purchase.aspose.com/temporary-license/) 임시면허를 취득하기 위해
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
