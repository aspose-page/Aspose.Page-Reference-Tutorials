---
date: 2025-12-25
description: 學習如何在 Java 中建立 XPS 文件，並使用 Aspose.Page 添加驚艷的對角漸層。本指南涵蓋如何加入漸層、套用線性漸層，以及有效運用
  Aspose。
linktitle: Add Diagonal Gradient in Java XPS
second_title: Aspose.Page Java API
title: 如何在 Java 中建立具有對角線漸層的 XPS 文件
url: /zh-hant/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java XPS 中添加對角漸層

## 介紹
在現代 Java 開發中，建立外觀精緻的 XPS 文件是一項關鍵差異化因素。在本教學中，您將學習 **how to create XPS document** 檔案，並使用 Aspose.Page for Java 為其加入對角漸層。我們將逐步說明每個步驟，解釋每個環節的重要性，並示範如何 **add gradient path**、**apply linear gradient**，快速獲得專業的視覺效果。

## 快速解答
- **主要的程式庫是什麼？** Aspose.Page for Java  
- **哪個方法會加入漸層？** `createLinearGradientBrush` with gradient stops  
- **我需要授權嗎？** 試用版可用於開發；正式環境需商業授權  
- **實作需要多久？** 基本對角漸層約 10‑15 分鐘即可完成  
- **可以與其他 Java 框架一起使用嗎？** 可以，API 與框架無關  

## XPS 文件中的對角漸層是什麼？
對角漸層沿斜線平滑過渡顏色，為形狀增添深度與視覺趣味。在 XPS 中，漸層由包含多個漸層停止點的筆刷定義，每個停止點指定顏色及其相對位置。

## 為什麼要使用 Aspose.Page 加入對角漸層？
- **豐富的視覺品質** – 漸層在 XPS 格式中精確呈現。  
- **跨平台一致性** – 同一 XPS 檔案在 Windows、macOS 與 Linux 檢視器上顯示相同。  
- **簡易的 API** – Aspose.Page 抽象化低階 XPS 規格，讓您專注於設計。  

## 前置條件
- 基本的 Java 程式設計知識。  
- 已在機器上安裝 JDK。  
- Aspose.Page for Java 程式庫。您可於 **[here](https://releases.aspose.com/page/java/)** 下載。  
- 如 IntelliJ IDEA 或 Eclipse 等 IDE。

## 匯入套件
先匯入所需的類別。這些匯入讓您可以使用幾何、漸層處理與 XPS 文件建立功能。

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
指定產生的 XPS 檔案要儲存的位置。

```java
String dataDir = "Your Document Directory";
```

## 步驟 3：建立 XPS 文件
實例化 `XpsDocument` 物件——這是您用來 **create XPS document** 內容的核心物件。

```java
XpsDocument doc = new XpsDocument();
```

## 步驟 4：加入對角漸層路徑
建立一個矩形路徑以接受漸層。路徑幾何使用簡單的 move‑line‑close 指令。

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## 步驟 5：定義線性漸層停止點
設定顏色與其位置。每個停止點定義了漸層中出現特定顏色的點。

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## 步驟 6：將線性漸層套用至路徑
現在 **apply linear gradient** 到您建立的路徑。筆刷由兩個點定義，決定漸層方向，停止點則附加於筆刷上。

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## 步驟 7：儲存文件
將 XPS 檔案寫入磁碟。檔案將包含填入您定義的對角漸層的矩形。

```java
doc.save(dataDir + "LinearGradient.xps");
```

## 常見陷阱與技巧
- **漸層方向** – 確保筆刷的起始與結束點反映您想要的對角線；交換兩點會顛倒漸層。  
- **顏色精度** – Aspose 使用 ARGB；若需要透明度，建立顏色時請包含 alpha 通道。  
- **檔案路徑** – 建議使用絕對路徑，或確認相對路徑指向可寫入的目錄。

## 常見問題

### Q: 我可以將 Aspose.Page for Java 與其他 Java 框架一起使用嗎？
Aspose.Page 設計上可無縫整合各種 Java 框架，是您專案的多功能選擇。

### Q: Aspose.Page 有哪些授權考量？
是的，請務必查閱 **[Aspose.Page purchase page](https://purchase.aspose.com/buy)** 上的授權細節。

### Q: 我可以在購買前試用 Aspose.Page for Java 嗎？
當然可以！您可於 **[free trial version here](https://releases.aspose.com/)** 取得試用版。

### Q: 我如何取得支援或與 Aspose 社群聯繫？
請造訪 **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** 與社群互動並尋求協助。

### Q: 是否提供臨時授權？
是的，您可於 **[temporary license here](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

## 其他常見問題 (AI 優化)

**Q: 我該如何 **how to add gradient** 到現有的 XPS 形狀？**  
A: 建立 `XpsLinearGradientBrush`，定義漸層停止點，並將其指派給形狀的 `Fill` 屬性，如 Step 6 所示。

**Q: **apply linear gradient** 實際上在背後做了什麼？**  
A: 它會在 XPS 套件中產生筆刷定義，引用起始/結束點與一系列漸層停止點，檢視器會將其渲染為平滑的顏色過渡。

**Q: 有沒有快速方式 **how to use aspose** 來實作其他 XPS 功能？**  
A: 有，Aspose.Page API 包含加入影像、文字與自訂形狀的方法，只要探索 `XpsDocument` 類別即可找到更多輔助功能。

**Q: 我可以 **add gradient path** 到非矩形形狀嗎？**  
A: 當然可以。使用 `createPathGeometry` 定義任意幾何形狀，然後將其 `Fill` 設為漸層筆刷。

**Q: 漸層會顯著影響檔案大小嗎？**  
A: 影響極小；漸層定義僅是 XPS 套件內的輕量級 XML 條目。

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}