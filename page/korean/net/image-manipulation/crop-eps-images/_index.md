---
date: 2026-03-16
description: Aspose.Page를 사용하여 .NET에서 EPS 이미지를 자르고 EPS 이미지 파일의 크기를 조정하는 방법을 배워보세요.
  이 단계별 가이드를 따라 EPS를 손쉽게 자르고 크기를 조정하세요.
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: Aspose.Page for .NET을 사용하여 EPS 이미지 자르기
url: /ko/net/image-manipulation/crop-eps-images/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET을 사용한 EPS 이미지 자르기 방법

## Introduction

.NET 애플리케이션에서 **EPS 이미지를 어떻게 자를지** 알고 싶다면, 바로 이곳이 맞습니다. 이 튜토리얼에서는 강력한 Aspose.Page for .NET 라이브러리를 사용해 EPS 파일을 자르고 크기를 조정하는 방법을 단계별로 안내합니다. 보고서 도구를 다듬거나 웹 서비스용 그래픽을 준비하든, 이 기술을 마스터하면 시간을 절약하고 픽셀 단위로 정확한 결과를 얻을 수 있습니다.

## Quick Answers
- **What library handles EPS cropping?** Aspose.Page for .NET  
- **Primary method?** `doc.CropEps(outputStream, newBoundingBox)`  
- **Can I also resize the EPS?** Yes – use `ResizeEps` with inches, millimeters or percents.  
- **Prerequisites?** .NET (Framework 4.5+ / .NET Core 3.1+), Aspose.Page installed, an EPS file.  
- **Typical implementation time?** About 10 minutes for a basic crop‑and‑resize workflow.

## Prerequisites

코드를 진행하기 전에 다음을 확인하세요:

- .NET 개발에 대한 기본 지식  
- Aspose.Page for .NET 라이브러리 설치. 설치되지 않았다면 [여기](https://releases.aspose.com/page/net/)에서 다운로드할 수 있습니다.  
- 샘플 EPS 이미지 (코드에서 `"input.eps"`를 실제 파일명으로 교체)

## Import Namespaces

EPS 처리 클래스를 사용하기 위해 네임스페이스를 가져옵니다.

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

## How to Crop EPS Images – Step‑by‑Step Guide

### Step 1: Initialize `PsDocument`

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

입력 EPS 스트림으로부터 `PsDocument` 인스턴스를 생성합니다. 이 객체는 메모리 상의 EPS 파일을 나타내며, 자르기 및 크기 조정 메서드에 접근할 수 있게 해줍니다.

### Step 2: Extract the Original Bounding Box

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

바운딩 박스는 EPS 캔버스의 현재 크기를 알려줍니다. 이 값을 알면 안전한 자르기 사각형을 정의하는 데 도움이 됩니다.

### Step 3: Create an Output Stream

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

잘라낸 EPS를 저장할 쓰기 가능한 스트림을 엽니다. `using` 블록을 사용하면 스트림이 올바르게 닫히도록 보장됩니다.

### Step 4: Define a New Bounding Box

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

보관하고 싶은 좌표값으로 숫자를 교체하세요. 새로운 값이 원본 바운딩 박스 안에 있어야 하며, 그렇지 않으면 작업이 실패합니다.

### Step 5: Crop and Save the EPS

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

이 한 줄이 자르기를 수행하고 결과를 `output_crop.eps`에 기록합니다. 메서드는 메모리 내 문서를 수정하므로 필요에 따라 추가 작업을 연쇄할 수 있습니다.

## Resize EPS Image

자른 후에는 표시나 인쇄를 위해 EPS 크기를 변경하고 싶을 때가 많습니다. Aspose.Page는 세 가지 측정 단위를 지원합니다.

### Resize in Inches

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### Resize in Millimeters

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### Resize in Percents

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

각 호출은 이전 출력을 덮어쓰므로, 각 크기에 대해 별도 파일이 필요하면 새로운 스트림을 생성하세요.

## Common Issues & Troubleshooting

| Symptom | Likely Cause | Fix |
|---------|--------------|-----|
| **Bounding box values out of range** | New box exceeds original dimensions | Verify `initialBoundingBox` values and choose coordinates inside that range. |
| **Output file is empty** | Output stream not flushed or closed | Ensure the `using` block completes before accessing the file, or call `outputEpsStream.Flush()`. |
| **Unexpected scaling** | Mixing units (e.g., inches vs. millimeters) | Always specify the correct `Units` enum that matches your size values. |

## FAQs

### Q1: Can I use Aspose.Page for .NET with other image formats?

A1: Aspose.Page primarily focuses on EPS images, but Aspose provides various libraries for different formats. Check their documentation for specific formats.

### Q2: How can I obtain a temporary license for Aspose.Page for .NET?

A2: Visit [this link](https://purchase.aspose.com/temporary-license/) to get a temporary license for testing.

### Q3: Are there any limitations to the image size I can process with Aspose.Page for .NET?

A3: Aspose.Page is designed to handle images of various sizes. However, performance may vary based on the complexity of the image.

### Q4: Is there a community forum for Aspose.Page discussions?

A5: Yes, you can engage with the Aspose.Page community [here](https://forum.aspose.com/c/page/39).

### Q5: Where can I find detailed documentation for Aspose.Page for .NET?

A5: Refer to the documentation [here](https://reference.aspose.com/page/net/).

---

**Last Updated:** 2026-03-16  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}