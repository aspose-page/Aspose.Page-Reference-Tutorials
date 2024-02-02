---
title: Aspose.Page를 사용하여 PS(PostScript)에 Circle Ellipse 추가
linktitle: PostScript에 원 타원 추가(PS)
second_title: Aspose.페이지 .NET API
description: .NET용 Aspose.Page를 사용하여 PostScript(PS) 문서에 원 타원을 손쉽게 추가하는 방법을 알아보세요. 원활한 통합을 위한 단계별 가이드를 따르세요.
type: docs
weight: 10
url: /ko/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---
## 소개

.NET용 Aspose.Page를 사용하여 PS(PostScript) 문서에 원 타원을 추가하는 방법에 대한 포괄적인 튜토리얼에 오신 것을 환영합니다. Aspose.Page는 개발자가 PostScript 및 기타 문서 형식을 원활하게 사용할 수 있게 해주는 강력한 라이브러리입니다. 이 가이드에서는 원 타원을 PS 문서에 쉽게 통합하는 과정을 안내합니다.

## 전제 조건

튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.

1.  .NET용 Aspose.Page 라이브러리: 다음에서 .NET용 Aspose.Page 라이브러리를 다운로드하고 설치하세요.[여기](https://releases.aspose.com/page/net/).

2. 개발 환경: 컴퓨터에 작동하는 .NET 개발 환경이 설정되어 있는지 확인하세요.

이제 단계별 가이드를 시작해 보겠습니다.

## 네임스페이스 가져오기

첫 번째 단계에서는 코드에서 Aspose.Page 기능을 사용할 수 있도록 필요한 네임스페이스를 가져와야 합니다.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

이제 제공된 예제를 여러 단계로 나누어 PostScript 문서에 원 타원을 추가하는 과정을 안내해 보겠습니다.

## 1단계: 문서 디렉터리 설정

```csharp
// ExStart:1
// 문서 디렉터리의 경로입니다.
string dataDir = "Your Document Directory";
```

"Your Document Directory"를 문서 디렉터리의 실제 경로로 바꾸십시오.

## 2단계: PostScript 문서에 대한 출력 스트림 생성

```csharp
//PostScript 문서의 출력 스트림 생성
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

여기서는 PostScript 문서를 작성하기 위한 FileStream을 생성하고, 새로운 파일을 생성하기 위한 파일 모드를 설정합니다.

## 3단계: 저장 옵션 및 PS 문서 생성

```csharp
//A4 크기로 저장 옵션 만들기
PsSaveOptions options = new PsSaveOptions();

// 새로운 1페이지 PS 문서 만들기
PsDocument document = new PsDocument(outPsStream, options, false);
```

이 단계에는 A4 크기로 저장 옵션을 생성하고 새로운 1페이지 PS 문서를 초기화하는 작업이 포함됩니다.

## 4단계: 첫 번째 타원에 대한 그래픽 경로 만들기

```csharp
//첫 번째 타원에서 그래픽 경로 만들기
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

위치와 치수를 지정하는 첫 번째 타원에 대한 그래픽 경로가 생성됩니다.

## 5단계: 페인트 설정 및 타원 채우기

```csharp
//페인트 세트
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//타원 채우기
document.Fill(path);
```

여기에서는 페인트가 설정되고 첫 번째 타원이 지정된 색상으로 채워집니다.

## 6단계: 두 번째 타원에 대한 그래픽 경로 만들기

```csharp
//두 번째 타원에서 그래픽 경로 만들기
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

마찬가지로 두 번째 타원에 대한 그래픽 경로가 생성되어 해당 위치와 치수를 정의합니다.

## 7단계: 획 설정 및 타원 그리기

```csharp
//스트로크 설정
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//타원을 획(윤곽선)으로 지정
document.Draw(path);
```

이 단계에서는 획이 설정되고 두 번째 타원의 윤곽이 지정된 색상과 선 두께로 그려집니다.

## 8단계: 현재 페이지를 닫고 문서 저장

```csharp
//현재 페이지 닫기
document.ClosePage();

//문서 저장
document.Save();
```

마지막으로 현재 페이지가 닫히고 문서 전체가 저장되면서 모든 과정이 완료됩니다.

## 결론

축하해요! .NET용 Aspose.Page를 사용하여 PostScript 문서에 원 타원을 추가하는 방법을 성공적으로 배웠습니다. 이 튜토리얼에서는 이 기능을 프로젝트에 원활하게 통합하는 데 도움이 되는 자세한 단계별 가이드를 제공했습니다.

## FAQ

### Q1: Aspose.Page for .NET을 다른 문서 형식과 함께 사용할 수 있습니까?

 A1: Aspose.Page는 주로 PostScript에 중점을 두지만 Aspose는 다양한 문서 형식을 위한 다른 라이브러리를 제공합니다. 을 체크 해봐[Aspose 문서](https://reference.aspose.com/page/net/) 상세 사항은.

### Q2: 추가 지원 및 커뮤니티 토론은 어디에서 찾을 수 있습니까?

 A2: 다음을 방문하세요.[Aspose.페이지 포럼](https://forum.aspose.com/c/page/39) 커뮤니티 토론 및 지원을 위해.

### Q3: .NET용 Aspose.Page에 대한 무료 평가판이 있습니까?

 A3: 예, 액세스할 수 있습니다.[무료 시험판](https://releases.aspose.com/).NET용 Aspose.Page의 기능을 탐색합니다.

### Q4: Aspose.Page에 대한 임시 라이선스를 어떻게 얻을 수 있나요?

 A4: 임시 라이센스 취득[여기](https://purchase.aspose.com/temporary-license/) 테스트 및 평가 목적으로.

### Q5: .NET용 Aspose.Page를 어디서 구입할 수 있나요?

 A5: 다음에서 .NET용 Aspose.Page를 구입하세요.[구매 페이지](https://purchase.aspose.com/buy).