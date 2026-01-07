---
date: 2026-01-07
description: Aspose.Page for .NET을 사용하여 XPS 문서를 만들고, 글리프 복제본을 추가하고, 단색 브러시를 사용하며,
  XPS 파일을 저장하는 방법을 배웁니다.
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: XPS 문서 생성 – Aspose.Page for .NET을 사용하여 글리프 복제 및 색상 변경
url: /ko/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# XPS 문서 만들기 – Glyph 복제 추가 및 색상 변경 Aspose.Page for .NET를 사용하여

## 소개

Aspose.Page for .NET를 사용하여 **XPS 문서** 파일을 만들고, glyph를 복제하며, 색상을 변경하는 방법을 단계별로 안내합니다. 동적 보고서, 청구서 또는 맞춤형 그래픽을 만들고 있든, 이 기술을 마스터하면 .NET 생태계를 떠나지 않고 시각적으로 풍부한 XPS 출력을 생성할 수 있습니다.

## 빠른 답변
- **주요 목표는 무엇입니까?** XPS 문서를 만들고, glyph 복제본을 추가하며, 색상을 변경합니다.  
- **사용된 라이브러리는?** Aspose.Page for .NET.  
- **라이선스가 필요합니까?** 평가용 임시 라이선스를 사용할 수 있으며, 프로덕션에서는 정식 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **결과를 어떻게 저장합니까?** `Save` 메서드를 사용하여 XPS 파일을 디스크에 기록합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건을 확인하십시오:

- C# 프로그래밍 언어에 대한 기본 이해.  
- Visual Studio 또는 기타 선호하는 C# 개발 환경이 설치되어 있어야 합니다.  
- Aspose.Page for .NET 라이브러리. [여기](https://releases.aspose.com/page/net/)에서 다운로드할 수 있습니다.  
- XPS 문서 형식에 대한 친숙함.  

## 네임스페이스 가져오기

시작하려면 C# 프로젝트에 필요한 네임스페이스를 포함하십시오:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## XPS 문서 만들기 및 Glyph 복제 추가 방법

### 1단계: 문서 디렉터리 설정

문서를 저장할 디렉터리를 설정합니다:

```csharp
string dataDir = "Your Document Directory";
```

### 2단계: 첫 번째 XPS 문서 만들기

이제 첫 번째 XPS 문서를 만들어 보겠습니다:

```csharp
XpsDocument doc1 = new XpsDocument();
```

### 3단계: 첫 번째 문서에 Glyph 추가

지정된 매개변수를 사용하여 첫 번째 문서에 glyph를 추가합니다:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### 4단계: Glyph를 단색 브러시로 채우기

첫 번째 문서의 glyph를 **단색 브러시**(예: 녹색)로 채웁니다:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### 5단계: 두 번째 XPS 문서 만들기

이제 두 번째 XPS 문서를 만듭니다:

```csharp
XpsDocument doc2 = new XpsDocument();
```

### 6단계: 다른 문서에 Glyph 복제 추가 방법

첫 번째 문서에서 glyph를 복제하여 두 번째 문서에 추가합니다:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### 7단계: 복제된 Glyph 색상 변경 방법

두 번째 문서에서 복제된 glyph의 색상을 예를 들어 빨간색으로 변경합니다. 이는 복제 후 glyph의 **색상 변경 방법**을 보여줍니다:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### 8단계: XPS 파일 저장 – 첫 번째 문서

앞서 정의한 폴더에 첫 번째 XPS 문서를 저장합니다:

```csharp
doc1.Save(dataDir + "out1.xps");
```

### 9단계: XPS 파일 저장 – 두 번째 문서

두 번째 XPS 문서를 저장합니다:

```csharp
doc2.Save(dataDir + "out2.xps");
```

축하합니다! Aspose.Page for .NET를 사용하여 **XPS 문서** 파일을 성공적으로 만들고, glyph 복제본을 추가했으며, 색상을 변경했습니다.

## Glyph 복제 및 색상 변경을 사용하는 이유

- **재사용성:** 기존 glyph를 복제하여 복잡한 벡터 형태를 다시 정의하지 않고 재사용합니다.  
- **성능:** glyph를 처음부터 다시 만드는 것에 비해 처리 시간을 줄여줍니다.  
- **디자인 유연성:** 동일한 glyph에 서로 다른 `SolidColorBrush` 인스턴스를 적용하여 다양한 시각적 테마를 구현합니다.  
- **문서 간 편집:** 여러 XPS 파일에 걸쳐 glyph를 복제하여 보고서 전반에 일관된 브랜딩을 가능하게 합니다.  

## 일반적인 문제 및 해결 방법

| 문제 | 해결책 |
|-------|----------|
| **복제 결과가 null** | 복제하기 전에 원본 glyph(`glyphs`)가 첫 번째 문서에 추가되었는지 확인하십시오. |
| **색상이 변경되지 않음** | `glyphs.Fill`을 `XpsSolidColorBrush`로 캐스팅한 후 `Color` 속성을 설정하십시오(예: 7단계 참조). |
| **파일이 저장되지 않음** | `dataDir`이 유효하고 쓰기 가능한 폴더를 가리키는지, 파일 시스템 권한이 적절한지 확인하십시오. |
| **예상치 못한 glyph 크기** | `AddGlyphs`의 두 번째 인수인 폰트 크기 매개변수를 조정하여 glyph를 적절히 스케일링하십시오. |

## 자주 묻는 질문

**Q1: Aspose.Page for .NET를 다른 문서 형식과 함께 사용할 수 있나요?**  
A1: Aspose.Page for .NET는 XPS 문서 작업을 위해 특별히 설계되었습니다. 다른 형식을 조작해야 하는 경우 해당 형식에 맞는 다른 Aspose 라이브러리를 살펴볼 수 있습니다.

**Q2: Aspose.Page for .NET에 대한 임시 라이선스를 제공하나요?**  
A2: 네, 테스트용 임시 라이선스를 얻을 수 있습니다. 자세한 내용은 [여기](https://purchase.aspose.com/temporary-license/)를 방문하십시오.

**Q3: 문제에 대한 지원이나 도움을 어떻게 받을 수 있나요?**  
A3: [Aspose.Page 포럼](https://forum.aspose.com/c/page/39)을 방문하여 커뮤니티와 연결하고 도움을 받을 수 있습니다.

**Q4: 무료 체험 버전에 제한이 있나요?**  
A4: 무료 체험 버전에는 몇 가지 제한이 있으며, 사용 전에 문서를 검토하여 자세한 내용을 확인하는 것이 좋습니다.

**Q5: Aspose.Page for .NET에 대한 포괄적인 문서는 어디에서 찾을 수 있나요?**  
A5: 자세한 정보와 예제는 [여기](https://reference.aspose.com/page/net/)의 문서를 참고하십시오.

**Q6: 채우기 대신 glyph의 스트로크 색상을 어떻게 변경하나요?**  
A6: 스트로크 브러시를 설정하려면 `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);`를 사용하십시오.

**Q7: 동일한 문서에 여러 glyph 복제본을 추가할 수 있나요?**  
A7: 네, 필요에 따라 위치를 조정하면서 `doc2.Add(glyphs.Clone());`를 반복 호출하면 됩니다.

---

**마지막 업데이트:** 2026-01-07  
**테스트 환경:** Aspose.Page 24.11 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}