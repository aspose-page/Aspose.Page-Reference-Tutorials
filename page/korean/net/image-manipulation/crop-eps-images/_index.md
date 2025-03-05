---
title: .NET용 Aspose.Page를 사용하여 EPS 이미지 자르기
linktitle: EPS 이미지 자르기
second_title: Aspose.페이지 .NET API
description: Aspose.Page를 사용하여 .NET에서 EPS 이미지 조작의 원활한 세계를 탐색해 보세요. 놀라운 결과를 얻으려면 이미지를 쉽게 자르고 크기를 조정하세요.
type: docs
weight: 10
url: /ko/net/image-manipulation/crop-eps-images/
---
## 소개

.NET 애플리케이션에서 EPS 이미지를 조작하는 데 어려움을 겪고 계십니까? 더 이상 보지 마세요! 이 튜토리얼에서는 강력한 .NET용 Aspose.Page 라이브러리를 사용하여 EPS 이미지를 자르는 과정을 안내합니다. 숙련된 개발자이든 이제 막 시작하는 개발자이든 이 단계별 가이드는 이미지를 쉽게 자르는 데 도움이 될 것입니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

- .NET 개발에 대한 실무 지식.
-  .NET 라이브러리용 Aspose.Page가 설치되었습니다. 그렇지 않은 경우 다운로드할 수 있습니다.[여기](https://releases.aspose.com/page/net/).
- 샘플 EPS 이미지(코드의 "input.eps"를 실제 파일로 대체)

## 네임스페이스 가져오기

코드가 원활하게 실행되는 데 필요한 네임스페이스를 가져오는 것부터 시작하겠습니다. 

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

이제 튜토리얼을 여러 단계로 나누어 보겠습니다.

## 1단계: PsDocument 초기화

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

 초기화`PsDocument` 입력 EPS 스트림이 있는 객체입니다.

## 2단계: 경계 상자 추출

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

EPS 이미지의 초기 경계 상자를 검색합니다.

## 3단계: 출력 스트림 생성

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

자른 EPS 이미지에 대한 출력 스트림을 만듭니다.

## 4단계: 새 경계 상자 정의

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

자르기를 위한 새 경계 상자를 정의합니다. 새 값이 초기 경계 상자 내에 있는지 확인하십시오.

## 5단계: 자르기 및 저장

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

새로운 경계 상자를 사용하여 EPS 이미지를 자르고 출력 스트림에 저장합니다.

다양한 크기 조정 시나리오에 대해 이 단계를 반복합니다.

## EPS 이미지 크기 조정

### 인치 단위로 크기 조정

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

EPS 이미지의 크기를 조정하고 지정된 치수(인치)로 저장합니다.

### 밀리미터 단위로 크기 조정

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

EPS 이미지의 크기를 조정하고 지정된 치수(밀리미터)로 저장합니다.

### 백분율로 크기 조정

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

EPS 이미지의 크기를 조정하고 지정된 치수(%)로 저장합니다.

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 EPS 이미지를 자르고 크기를 조정하는 방법을 성공적으로 배웠습니다. 이제 이미지 조작 기능을 강화하고 .NET 애플리케이션을 한 단계 더 발전시키십시오.

## 자주 묻는 질문

### Q1: Aspose.Page for .NET을 다른 이미지 형식과 함께 사용할 수 있나요?

A1: Aspose.Page는 주로 EPS 이미지에 중점을 두지만 Aspose는 다양한 형식에 대한 다양한 라이브러리를 제공합니다. 특정 형식에 대해서는 설명서를 확인하세요.

### Q2: Aspose.Page for .NET의 임시 라이선스를 어떻게 얻을 수 있나요?

 A2: 방문[이 링크](https://purchase.aspose.com/temporary-license/) 테스트를 위한 임시 라이센스를 얻으려면

### Q3: Aspose.Page for .NET으로 처리할 수 있는 이미지 크기에 제한이 있나요?

A3: Aspose.Page는 다양한 크기의 이미지를 처리하도록 설계되었습니다. 그러나 성능은 이미지의 복잡성에 따라 달라질 수 있습니다.

### Q4: Aspose.Page 토론을 위한 커뮤니티 포럼이 있습니까?

 A4: 예, Aspose.Page 커뮤니티에 참여할 수 있습니다.[여기](https://forum.aspose.com/c/page/39).

### Q5: .NET용 Aspose.Page에 대한 자세한 문서는 어디서 찾을 수 있나요?

 A5: 설명서를 참조하세요[여기](https://reference.aspose.com/page/net/).