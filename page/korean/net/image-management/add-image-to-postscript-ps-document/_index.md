---
date: 2026-02-28
description: Aspose.Page for .NET을 사용하여 PostScript 문서에 이미지를 추가하는 방법을 배웁니다. 이 가이드는
  필요에 따라 비트맵을 PS에 삽입하고 PS에서 이미지를 추출하는 방법도 다룹니다.
linktitle: Add Image to PostScript (PS) Document
second_title: Aspose.Page .NET API
title: Aspose.Page를 사용하여 PostScript(PS) 문서에 이미지 추가하는 방법
url: /ko/net/image-management/add-image-to-postscript-ps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page를 사용하여 PostScript (PS) 문서에 이미지 추가하는 방법

## PostScript (PS) 문서에 이미지 추가하기

이 튜토리얼에서는 강력한 Aspose.Page for .NET 라이브러리를 사용하여 PostScript (PS) 문서에 **이미지를 추가하는 방법**을 배웁니다. 인쇄용 전단지, 기술 도면, 맞춤형 보고서 등을 준비할 때 그래픽을 PS 파일에 직접 삽입하면 시각적 품질을 크게 향상시킬 수 있습니다. 각 단계를 차례대로 살펴보고, 각 코드 라인이 왜 중요한지 설명하며, 향후 프로젝트에 재사용할 수 있는 팁을 제공합니다.

## 빠른 답변
- **필요한 라이브러리는?** Aspose.Page for .NET (최신 버전)
- **ps에 비트맵을 삽입할 수 있나요?** 예 – `DrawImage`와 `Bitmap` 객체를 사용합니다
- **구현 시간은 얼마나 걸리나요?** 기본 이미지 삽입은 보통 10분 이내
- **라이선스가 필요합니까?** 평가용 트라이얼은 가능하지만, 상용 라이선스가 필요합니다
- **나중에 ps에서 이미지를 추출할 수 있나요?** 물론 – Aspose.Page는 추출 API도 제공합니다

## 사전 요구 사항

코드 작성을 시작하기 전에 다음 요구 사항을 준비하십시오:

- Aspose.Page for .NET Library: [여기](https://releases.aspose.com/page/net/)에서 Aspose.Page for .NET 라이브러리를 다운로드하고 설치합니다.
- 문서 디렉터리: 문서와 이미지 파일을 저장할 디렉터리를 시스템에 생성합니다.

## 네임스페이스 가져오기

프로젝트에 필요한 네임스페이스를 가져옵니다. 이 네임스페이스들을 통해 .NET 애플리케이션에서 Aspose.Page 기능을 사용할 수 있습니다:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## 단계 1: 문서 디렉터리 설정

문서를 저장할 전용 디렉터리가 있는지 확인합니다. 아래 코드 스니펫에서 `"Your Document Directory"`를 실제 문서 디렉터리 경로로 교체하십시오.

```csharp
string dataDir = "Your Document Directory";
```

## 단계 2: PS 문서용 출력 스트림 만들기

PostScript 문서를 저장할 출력 스트림을 설정합니다. 이 스트림은 수정된 문서를 저장하는 데 사용됩니다.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "AddImage_outPS.ps", FileMode.Create))
```

## 단계 3: 저장 옵션 만들기

페이지 크기와 같은 원하는 설정을 지정하여 PS 문서용 저장 옵션을 생성합니다.

```csharp
PsSaveOptions options = new PsSaveOptions();
```

## 단계 4: PS 문서 만들기

새로운 1페이지 PS 문서를 초기화하고 그래픽 작업을 준비합니다.

```csharp
PsDocument document = new PsDocument(outPsStream, options, false);
document.WriteGraphicsSave();
document.Translate(100, 100);
```

## 단계 5: PS 문서에 비트맵 삽입하기

이미지 파일에서 `Bitmap` 객체를 로드하고 변환을 적용합니다. 이것이 **이미지를 추가하는 방법**의 핵심이며, 비트맵을 PS 캔버스에 그립니다.

```csharp
using (Bitmap image = new Bitmap(dataDir + "TestImage Format24bppRgb.jpg"))
{
    System.Drawing.Drawing2D.Matrix transform = new System.Drawing.Drawing2D.Matrix();
    transform.Translate(35, 300);
    transform.Scale(3, 3);
    transform.Rotate(-45);
    
    document.DrawImage(image, transform, Color.Empty);
}
```

> **프로 팁:** `Translate`, `Scale`, `Rotate` 값을 조정하여 이미지의 위치와 크기를 정확히 맞출 수 있습니다.

## 단계 6: 그래픽 작업 마무리

그래픽 작업을 종료하고 현재 페이지를 닫습니다.

```csharp
document.WriteGraphicsRestore();
document.ClosePage();
```

## 단계 7: 문서 저장하기

수정된 PS 문서를 저장합니다.

```csharp
document.Save();
```

## PS 문서에서 이미지 추출하기

나중에 그래픽을 다시 가져와야 할 경우, Aspose.Page는 `PsDocument.ExtractImages`와 같은 추출 메서드를 제공합니다. 이 튜토리얼은 삽입에 초점을 맞추지만, 동일한 라이브러리를 사용해 **ps 파일에서 이미지 추출**도 가능합니다.

## 일반적인 문제와 해결책

| 문제 | 발생 원인 | 해결 방법 |
|------|----------|-----------|
| 이미지가 왜곡됨 | 잘못된 스케일 매트릭스 | `Scale` 값을 재검토하고 원본 크기를 유지하려면 균일 스케일(`Scale(1,1)`)을 사용 |
| 출력 파일이 비어 있음 | 스트림이 플러시되지 않음 | `using` 블록 안에서 `document.Save()`가 호출되는지 확인 |
| 지원되지 않는 이미지 형식 | Bitmap이 파일을 로드하지 못함 | JPEG, PNG, BMP, GIF 등 지원되는 형식으로 변환 |

## 결론

축하합니다! Aspose.Page for .NET을 사용하여 PostScript 문서에 **이미지를 추가하는 방법**을 성공적으로 배웠습니다. 이제 그래픽 삽입에 대한 탄탄한 기반을 갖추었으며, 필요할 때 **ps에서 이미지 추출** 및 **ps에 비트맵 삽입**도 할 수 있습니다. 여러 이미지를 사용하거나 다양한 변환, 맞춤형 그리기 명령을 실험하여 풍부하고 인쇄 가능한 콘텐츠를 만들어 보세요.

## FAQ

### Q1: Aspose.Page를 사용하여 하나의 PS 문서에 여러 이미지를 추가할 수 있나요?

A1: 예, 가능합니다. 문서 내에서 이미지 추가 단계를 반복하면 됩니다.

### Q2: Aspose.Page for .NET이 지원하는 이미지 형식은 무엇인가요?

A2: JPEG, PNG, BMP, GIF 등 다양한 이미지 형식을 지원합니다.

### Q3: 추가할 수 있는 이미지의 크기 제한이 있나요?

A3: 제한은 PS 문서 사양 및 시스템 리소스에 따라 달라집니다. Aspose.Page는 다양한 이미지 크기를 처리할 수 있습니다.

### Q4: 이미지에 필터나 오버레이와 같은 추가 효과를 적용할 수 있나요?

A4: 예, Aspose.Page를 사용하면 이미지를 문서에 추가하기 전에 다양한 변환 및 효과를 적용할 수 있습니다.

### Q5: PS 문서에서 이미지를 어떻게 추출하나요?

A5: Aspose.Page for .NET은 PS 문서에서 이미지를 추출하는 메서드를 제공합니다. 자세한 내용은 공식 문서를 참고하십시오.

---

**마지막 업데이트:** 2026-02-28  
**테스트 환경:** Aspose.Page for .NET (최신 릴리스)  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}