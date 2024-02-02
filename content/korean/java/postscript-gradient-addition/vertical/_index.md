---
title: Java PostScript에 수직 그라데이션 추가
linktitle: Java PostScript에 수직 그라데이션 추가
second_title: Aspose.페이지 자바 API
description: Java용 Aspose.Page를 사용하여 Java PostScript에 수직 그라데이션을 추가하는 방법에 대한 단계별 가이드를 살펴보세요. 생생한 시각적 요소로 문서를 쉽게 향상할 수 있습니다.
type: docs
weight: 14
url: /ko/java/postscript-gradient-addition/vertical/
---
## 소개
Java용 Aspose.Page를 사용하여 Java PostScript에 수직 그라데이션을 추가하는 방법에 대한 단계별 가이드에 오신 것을 환영합니다. 눈길을 사로잡는 그라데이션으로 문서를 향상시키고 싶다면 이 튜토리얼이 적합합니다. Aspose.Page for Java는 PostScript 문서를 원활하게 조작할 수 있는 강력한 도구를 제공합니다.
## 전제 조건
튜토리얼을 시작하기 전에 다음 전제 조건이 충족되었는지 확인하세요.
- 컴퓨터에 JDK(Java Development Kit)가 설치되어 있습니다.
-  Java 라이브러리용 Aspose.Page. 당신은 그것을 다운로드 할 수 있습니다[여기](https://releases.aspose.com/page/java/).
## 패키지 가져오기
Java 프로젝트에서 시작하려면 필요한 패키지를 가져옵니다.
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
이제 Java PostScript에서 수직 그라데이션을 추가하는 과정을 여러 단계로 나누어 보겠습니다.
## 1단계: 문서 디렉터리 설정
```java
// 문서 디렉터리의 경로입니다.
String dataDir = "Your Document Directory";
```
## 2단계: PostScript 문서에 대한 출력 스트림 생성
```java
// PostScript 문서의 출력 스트림 생성
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## 3단계: A4 크기로 저장 옵션 만들기
```java
// A4 크기로 저장 옵션 만들기
PsSaveOptions options = new PsSaveOptions();
```
## 4단계: 새 PS 문서 만들기
```java
// 페이지가 열린 상태에서 새 PS 문서 만들기
PsDocument document = new PsDocument(outPsStream, options, false);
```
## 5단계: 직사각형 만들기
```java
//직사각형 만들기
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## 6단계: 그라디언트에 대한 색상 및 분수 설정
```java
// 그라디언트에 대한 색상 및 분수 배열을 만듭니다.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## 7단계: 그라데이션 변환 생성
```java
// 그라데이션 변환을 만듭니다. 변환의 크기 조정 구성요소는 직사각형의 너비 및 높이와 같아야 합니다.
// 변환 구성요소는 직사각형의 오프셋입니다.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// 원점을 기준으로 그라디언트를 90도 회전합니다.
transform.rotate(90 * (Math.PI / 180));
```
## 8단계: 수직 선형 그라데이션 페인트 만들기
```java
// 수직 선형 그라데이션 페인트를 만듭니다.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## 9단계: 페인트 설정 및 직사각형 채우기
```java
// 페인트 세트
document.setPaint(paint);
// 직사각형을 채우세요
document.fill(rectangle);
```
## 10단계: 현재 페이지를 닫고 문서 저장
```java
// 현재 페이지 닫기
document.closePage();
// 문서 저장
document.save();
```
축하해요! Aspose.Page for Java를 사용하여 Java PostScript 문서에 수직 그라데이션을 성공적으로 추가했습니다.
## 결론
이 튜토리얼에서는 Java용 Aspose.Page를 사용하여 생생한 수직 그라데이션으로 문서를 향상시키는 프로세스를 살펴보았습니다. 이제 놀라운 시각적 요소를 통합하여 문서 조작을 한 단계 더 발전시킬 수 있습니다.
## 자주 묻는 질문
### 다른 Java 라이브러리와 함께 Java용 Aspose.Page를 사용할 수 있나요?
예, Aspose.Page for Java는 다른 Java 라이브러리와 원활하게 작동하도록 설계되었습니다.
### Aspose.Page for Java에 대한 무료 평가판이 있습니까?
 예, 무료 평가판을 받을 수 있습니다[여기](https://releases.aspose.com/).
### 추가 문서는 어디서 찾을 수 있나요?
 자세한 문서가 제공됩니다.[여기](https://reference.aspose.com/page/java/).
### Java용 Aspose.Page를 어떻게 구매할 수 있나요?
 Java용 Aspose.Page를 구매할 수 있습니다.[여기](https://purchase.aspose.com/buy).
### Aspose.Page 토론을 위한 포럼이 있습니까?
 예, 커뮤니티 포럼에 가입할 수 있습니다[여기](https://forum.aspose.com/c/page/39).