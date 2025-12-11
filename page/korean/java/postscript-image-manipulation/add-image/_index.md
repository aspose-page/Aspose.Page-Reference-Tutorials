---
date: 2025-12-09
description: Aspose.Page를 사용하여 이미지 변환 및 회전을 통해 원활한 이미지 조작을 수행하는 방법과 Java에서 PostScript
  문서를 만드는 방법을 배워보세요.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Java에서 PostScript 문서 만들기 – Java PostScript에 이미지 추가
url: /ko/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Create PostScript Document Java – Add Image in Java PostScript

## Introduction
이 튜토리얼에서는 **Java에서 PostScript 문서를 생성**하고 Aspose.Page for Java 라이브러리를 사용해 이미지를 삽입하는 방법을 배웁니다. 문서 설정부터 **이미지 변환(translate 및 rotate)** 작업까지 단계별로 안내합니다. 최종적으로 프로그래밍 방식으로 풍부한 PostScript 파일을 생성하고 이미지 배치를 정확히 맞출 수 있게 됩니다.

## Quick Answers
- **필요한 라이브러리는?** Aspose.Page for Java  
- **여러 이미지를 추가할 수 있나요?** 예 – 변환 및 그리기 단계를 반복하면 됩니다  
- **개발에 라이선스가 필요합니까?** 테스트용 무료 체험판을 사용할 수 있으며, 실제 운영에서는 라이선스가 필요합니다  
- **지원되는 Java 버전은?** Java 8 이상  
- **이미지 회전이 지원되나요?** 물론입니다 – `AffineTransform.rotate()`를 사용합니다  

## What is creating a PostScript document in Java?
PostScript 문서는 텍스트, 그래픽, 이미지를 설명하는 페이지 기술 언어 파일입니다. Aspose.Page를 사용하면 Java에서 이러한 파일을 프로그래밍 방식으로 생성할 수 있어 레이아웃, 그래픽 상태, 이미지 처리를 완전히 제어할 수 있으며 별도의 PostScript 인터프리터가 필요하지 않습니다.

## Why use Aspose.Page for image manipulation?
- **High‑level API:** 복잡한 PostScript 명령을 단순화합니다.  
- **Cross‑platform:** Java를 지원하는 모든 OS에서 동작합니다.  
- **Full graphics state control:** 그래픽을 쉽게 저장, 복원, 이동, 스케일 및 회전할 수 있습니다.  
- **No external dependencies:** 이미지 로드와 변환을 내부적으로 처리합니다.

## Prerequisites
코드 작성을 시작하기 전에 다음을 준비하세요:

- 시스템에 Java Development Kit (JDK)가 설치되어 있어야 합니다.  
- Aspose.Page for Java 라이브러리. [여기](https://releases.aspose.com/page/java/)에서 다운로드할 수 있습니다.  
- Java 프로그래밍에 대한 기본 지식.

## Import Packages
프로젝트에 필요한 패키지를 가져옵니다. 아래 코드 스니펫을 참고하세요:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Step 1: Write Graphics Save
첫 번째 단계는 문서에 그래픽 저장 명령을 쓰는 것입니다. 이를 통해 이후에 적용되는 변환이나 수정 작업을 필요 시 되돌릴 수 있습니다.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## Step 2: Translate and Transform (translate and rotate image)
다음으로 문서를 이동하고 이미지 파일에서 `BufferedImage` 객체를 생성합니다. `AffineTransform`을 사용해 스케일링 및 회전과 같은 일련의 변환을 적용합니다. 여기서 **translate 및 rotate 이미지** 작업이 수행됩니다.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## Step 3: Add Image to Document
변환된 이미지를 문서에 추가합니다.

```java
document.drawImage(image, transform, null);
```

## Step 4: Write Graphics Restore
이미지를 추가한 뒤 그래픽 복원 명령을 작성해 변경 사항을 최종 확정합니다.

```java
document.writeGraphicsRestore();
```

## Step 5: Close Current Page and Save
현재 페이지를 닫고 문서를 저장합니다.

```java
document.closePage();
document.save();
```

이 단계를 반복하면 여러 이미지를 추가하거나 요구 사항에 맞게 변환을 맞춤 설정할 수 있습니다.

## Common Issues and Solutions
- **FileNotFoundException:** `dataDir` 경로가 파일 구분자(`/` 또는 `\\`)로 끝나는지, 이미지 파일 이름이 정확히 일치하는지 확인하세요.  
- **ImageIO.read returns null:** 이미지 형식이 지원되는지 확인합니다(예: JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate`는 라디안을 기대합니다. 필요하면 각도를 라디안으로 변환하세요(`Math.toRadians(degrees)`).

## Frequently Asked Questions

**Q: Can I use Aspose.Page for Java with other programming languages?**  
A: Aspose.Page는 주로 Java를 지원하지만, 다른 프로그래밍 언어용 버전도 제공됩니다.

**Q: Is there a free trial available for Aspose.Page for Java?**  
A: 예, 무료 체험판을 [여기](https://releases.aspose.com/)에서 이용할 수 있습니다.

**Q: How can I obtain a temporary license for Aspose.Page for Java?**  
A: 임시 라이선스를 [여기](https://purchase.aspose.com/temporary-license/)에서 받을 수 있습니다.

**Q: Where can I find community support and discussions related to Aspose.Page for Java?**  
A: 커뮤니티 지원은 [Aspose.Page Forum](https://forum.aspose.com/c/page/39)에서 확인하세요.

**Q: Are there any additional resources for purchasing Aspose.Page for Java?**  
A: 라이브러리는 [여기](https://purchase.aspose.com/buy)에서 구매할 수 있습니다.

## Conclusion
축하합니다! 이제 **Java에서 PostScript 문서를 생성**하고 Aspose.Page for Java를 사용해 이미지를 삽입하는 방법을 익혔습니다. 더 고급 기능과 활용법은 [문서](https://reference.aspose.com/page/java/)를 참고해 보세요. 벡터 그래픽, 텍스트 렌더링, 사용자 정의 페이지 크기 등 다양한 기능을 활용할 수 있습니다.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}