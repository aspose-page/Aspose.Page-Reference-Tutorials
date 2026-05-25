---
date: 2026-05-25
description: 了解如何在 Java 中使用 Aspose.Page 為 XPS 文件加入 gradient。此逐步指南說明如何加入 diagonal gradient、套用
  linear gradient brushes，並產生專業的 XPS 檔案。
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: 在 Java XPS 中加入 Diagonal Gradient
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 如何在 Java XPS 中加入 Gradient：Diagonal Gradient
url: /zh-hant/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java XPS 中加入漸層：對角漸層

## 介紹
在現代 Java 開發中，掌握 **如何加入漸層** 到 XPS 文件，可讓您的報告呈現出精緻且吸睛的效果。本教學將一步步示範如何從頭建立 XPS 檔案、加入對角漸層，並儲存結果——全部使用 Aspose.Page for Java。您將了解為何漸層重要、看到完整的 API 呼叫，並取得避免常見問題的實用技巧。

## 快速回答
- **主要使用的函式庫是什麼？** Aspose.Page for Java  
- **哪個方法加入漸層？** `createLinearGradientBrush` 搭配 gradient stops  
- **需要授權嗎？** 開發階段可使用試用版，正式上線需購買商業授權  
- **實作大約需要多久？** 基本的對角漸層約 10‑15 分鐘即可完成  
- **可以與其他 Java 框架一起使用嗎？** 可以，API 與框架無關  

## 什麼是 XPS 文件中的對角漸層？
對角漸層是一種從形狀的一個角落平滑過渡到相對角落的顏色變化，產生斜向的視覺效果。在 XPS 中，這種效果由包含有序 gradient stops 的 linear gradient brush 定義，這些 stops 指定顏色與在對角線上的相對位置。

## 為什麼要使用 Aspose.Page 加入對角漸層？
Aspose.Page 為超過 20 種 XPS 檢視器提供 **100 % 的渲染相容性**，且支援 **30+ XPS 功能**，包括文字、影像與向量圖形。API 抽象了複雜的 XPS 標記，讓您專注於設計，同時保證同一檔案在 Windows、macOS 與 Linux 平台上呈現一致。

## 前置條件
- 具備基本的 Java 程式設計知識。  
- 已在機器上安裝 JDK。  
- Aspose.Page for Java 函式庫 – 下載 **[此處](https://releases.aspose.com/page/java/)**。  
- 使用 IntelliJ IDEA 或 Eclipse 等 IDE。

## 匯入套件
先匯入所需的類別，這些匯入讓您可以存取幾何、漸層處理與 XPS 文件建立的功能。

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## 步驟 1：設定專案
在您偏好的 IDE 中建立新的 Java 專案，並將 Aspose.Page 的 JAR 檔加入專案的建置路徑。

## 步驟 2：定義文件目錄
指定產生的 XPS 檔案要儲存的路徑。

```java
String dataDir = "Your Document Directory";
```

## 步驟 3：建立 XPS 文件
`XpsDocument` 是代表記憶體中 XPS 檔案的核心物件。實例化它即可取得畫布，進而加入頁面、圖形與畫筆。

```java
XpsDocument doc = new XpsDocument();
```

## 步驟 4：加入對角漸層路徑
建立一個矩形路徑以接受漸層。路徑幾何使用簡單的 move‑line‑close 指令。  
XpsPath 定義 XPS 文件中的向量圖形，例如矩形或自訂幾何形狀。

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## 步驟 5：定義線性漸層 Stops
設定顏色與其位置。每個 stop 定義漸層中出現特定顏色的點。  
XpsGradientStop 代表漸層中的單一顏色 stop，包含顏色與偏移量。

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## 步驟 6：將線性漸層套用至路徑
`XpsLinearGradientBrush` 是 Aspose.Page 用於線性顏色過渡的畫筆類型。它接受兩個點來定義漸層方向，並接受一組 gradient stops 來決定沿線的顏色。

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## 步驟 7：儲存文件
將 XPS 檔案寫入磁碟。檔案將包含已填入對角漸層的矩形。

```java
doc.save(dataDir + "LinearGradient.xps");
```

## 如何在 Java XPS 中加入漸層？
載入 XpsDocument，建立一個起點為 `(0,0)`、終點為 `(width,height)` 的 `XpsLinearGradientBrush`，加入 gradient stops，將畫筆指派給圖形的 `Fill`，最後呼叫 `save`。這個簡潔流程讓您只需少量 API 呼叫即可嵌入對角漸層，保持程式碼乾淨且易於維護。

## 常見問題與技巧
- **漸層方向** – 確保畫筆的起點與終點對應您想要的對角線；交換兩點會使漸層方向相反。  
- **顏色精度** – Aspose 使用 ARGB；若需透明度請務必包含 alpha 通道。  
- **檔案路徑** – 建議使用絕對路徑，或確認相對路徑指向可寫入的目錄。

## 其他 FAQ

**Q: 如何 **how to add gradient** 到既有的 XPS 形狀？**  
A: 建立 `XpsLinearGradientBrush`，定義 gradient stops，然後將其指派給該形狀的 `Fill` 屬性，如 Step 6 所示。

**Q: **apply linear gradient** 在背後實際執行了什麼？**  
A: 它會在 XPS 套件中產生一個畫筆定義，包含起始/結束點與一組 gradient stops，檢視器會將其渲染為平滑的顏色過渡。

**Q: 有沒有快速方式 **how to use aspose** 來使用其他 XPS 功能？**  
A: 有，Aspose.Page API 提供加入影像、文字與自訂形狀的方法，只要探索 `XpsDocument` 類別即可找到更多輔助功能。

**Q: 我可以將 **add gradient path** 套用到非矩形形狀嗎？**  
A: 當然可以。使用 `createPathGeometry` 定義任意幾何形狀，然後將其 `Fill` 設為漸層畫筆。

**Q: 漸層會顯著增加檔案大小嗎？**  
A: 只會略微增加；漸層定義在 XPS 套件中是輕量的 XML 條目。

---

**最後更新：** 2026-05-25  
**測試環境：** Aspose.Page for Java 24.11  
**作者：** Aspose

## 相關教學

- [Aspose Page XPS Gradient Addition](/page/java/xps-gradient-addition/)
- [Java XPS Text Addition - Aspose.Page Tutorial](/page/java/xps-text-manipulation/add-text/)
- [How to Add Image to Java XPS Documents – A Simple Guide with Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}