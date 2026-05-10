---
date: 2026-01-25
description: Aspose.Page for .NET를 사용하여 EPS 파일에서 배열 항목을 설정하는 방법을 배웁니다. 효율적인 XMP 메타데이터
  조작을 위한 단계별 가이드.
linktitle: Change Array Items
second_title: Aspose.Page .NET API
title: aspose.page 배열 항목 설정 – Aspose.Page for .NET으로 배열 항목 변경
url: /ko/net/eps-metadata-management/modify-eps-metadata-change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page for .NET을 사용한 배열 항목 변경

## 소개

Aspose.Page for .NET을 사용한 **aspose.page set array item**에 대한 포괄적인 가이드에 오신 것을 환영합니다! Aspose.Page는 EPS 파일을 포함한 다양한 문서 형식을 다룰 수 있는 강력한 라이브러리입니다. 이 튜토리얼에서는 EPS 파일 내부의 XMP 메타데이터를 조작하는 방법, 특히 배열 항목을 효율적으로 변경하는 방법에 초점을 맞춥니다.

## 빠른 답변
- **aspose.page set array item**은 무엇을 하나요? EPS 파일 내 XMP 배열(예: title 또는 creator) 안의 특정 요소를 업데이트합니다.  
- **필요한 라이브러리는?** Aspose.Page for .NET (최신 버전).  
- **개발에 라이선스가 필요합니까?** 테스트용으로는 무료 체험판을 사용할 수 있으며, 프로덕션에서는 상용 라이선스가 필요합니다.  
- **지원되는 .NET 버전은?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **구현에 걸리는 시간은?** 기본 업데이트는 일반적으로 10분 미만 소요됩니다.

## **aspose.page set array item**이란?
`SetArrayItem` 메서드는 `XmpMetadata` 클래스에 속합니다. XMP 배열 속성(예: `dc:title[0]`)의 지정된 인덱스에 있는 기존 값을 교체할 수 있습니다. 전체 문서를 다시 만들지 않고 메타데이터를 수정하거나 갱신해야 할 때 필수적입니다.

## **aspose.page set array item**을 사용하는 이유는?
- **정밀성:** 대상 메타데이터 항목만 변경하고 나머지는 그대로 유지합니다.  
- **규정 준수:** EPS 파일을 XMP 규격에 맞게 유지하여 검색성과 보관성을 향상시킵니다.  
- **자동화:** 대량 문서 컬렉션의 배치 처리에 이상적입니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건을 확인하십시오:

1. Aspose.Page for .NET 라이브러리: Aspose.Page for .NET 라이브러리가 설치되어 있는지 확인하십시오. [here](https://releases.aspose.com/page/net/)에서 다운로드할 수 있습니다.
2. 개발 환경: Visual Studio든 .NET 개발을 지원하는 다른 IDE든 선호하는 개발 환경을 설정하십시오.

## 네임스페이스 가져오기

.NET 애플리케이션에서 Aspose.Page 기능에 접근하려면 필요한 네임스페이스를 가져와야 합니다. 코드 시작 부분에 다음 네임스페이스를 추가하십시오:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## 단계별 가이드

### Step 1: EPS 파일 입력 스트림 초기화

이 단계에서는 EPS 파일을 열고 메모리 내에서 문서를 나타내는 `PsDocument` 인스턴스를 생성합니다.

```csharp
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### Step 2: XMP 메타데이터 가져오기

EPS 파일에서 XMP 메타데이터를 가져옵니다. 파일에 XMP 메타데이터가 없으면 PS 메타데이터 주석에서 값을 가져와 새 메타데이터가 생성됩니다.

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

### Step 3: XMP 메타데이터 값 변경

여기서는 **aspose.page set array item** `dc:creator` 배열의 첫 번째 요소(`index 0`)를 새 값으로 교체합니다.

```csharp
xmp.SetArrayItem("dc:title", 0, new XmpValue("NewTitle"));
xmp.SetArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### Step 4: 변경된 XMP 메타데을 저장합니다.

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## 일반적인 문제 및 해결책

| 문제 | 원인 | 해결책| 출력 파일에 변경 사항이 나타나지 않음 | 원본 EPS에 XMP 메타데이터가 없어서 `GetXmpMetadata()`가 예상 스키마 없이 새 객체를 생성했습니다. | `xmp.AddArrayProperty("dc:title")`을 항목 길이를 확인하거나 `xmp.AppendArrayItem`으로 새 항목을 추가하십시오. |
| 저장 중 파일이 저장하기 전에 닫으십시오. |

## 결론

축하합니다! Aspose.Page for .NET을 사용하여 EPS 파일에서 **aspose.page set array item**을 성공적으로 적용하는 방법을 배웠습니다. 이 기능은 문서 내 메타데이터를 맞춤화하고 관리하는 데 필수적이며, 특히 대규모 컬렉션을 일관되고 검색 가능하게 유지해야 할 때 중요합니다.

## FAQ

### Q1: Aspose.Page for .NET을 다른 문서 형식과 함께 사용할 수 있나요?

A1: Aspose.Page는 주로 EPS 파일을 다루지만, Aspose는 다양한 문서 형식을 다루는 별도의 라이브러리를 제공합니다.

### Q2: 추가 문서는 어디에서 찾을 수 있나요?

A2: [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/)에서 문서를 확인하십시오.

### Q3: 무료 체험판을 이용할 수 있나요?

A3: 예, [here](https://releases.aspose.com/)에서 무료 체험판을 받을 수 있습니다.

### Q4: 임시 라이선스를 어떻게 받을 수 있나요?

A4: [this link](https://purchase.aspose.com/temporary-license/)에서 임시 라이선스를 받으십시오.

### Q5: 지원을 받거나 커뮤니티와 연결하려면 어디로 가야 하나요?

A5: 커뮤니티 지원 및 토론을 위해 [Aspose.Page Forum](https://forum.aspose.com/c/page/39)을 방문하십시오.

**추가 FAQ**

**Q: 한 번에 여러 배열 항목을 업데이트할 수 있나요?**  
A: 아니요, `SetArrayItem`은 한 번에 하나의 인덱스만 작업합니다. 여러 항목을 수정해야 하면 배열을 반복하십시오.

**Q: 메서드가 기존 네임스페이스를 보존합니까?**  
A: 예, Aspose.Page는 배열 항목을 수정할 때 기존 XMP 네임스페이스를 모두 유지합니다.

**Q: 교체 대신 새로운 배열 요소를 추가할 수 있나요?**  
A: `xmp.AppendArrayItem("dc:subject", new XmpValue("NewSubject"))**테스트 환경:** Aspose.Page 24.12 for .NET  
**작성자:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}