---
date: 2026-04-30
description: 學習如何使用 Aspose.Page Java 在 Java 中建立 XPS 文件並加入不透明遮罩。提供程式碼範例的逐步指南。
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: 在 Java XPS 中設定不透明遮罩
second_title: Aspose.Page Java API
title: 建立 XPS 文件（Java） – 使用 Aspose.Page 設定不透明遮罩
url: /zh-hant/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java XPS 中使用 Aspose.Page Java 設定不透明遮罩

## 介紹
在本教學中，你將 **建立 XPS document Java** 檔案，並學習如何套用不透明遮罩，使圖形呈現精緻的半透明效果。我們會一步步說明整個流程——從初始化 XPS 文件、加入畫布、繪製矩形，到套用基於影像的不透明遮罩——全部使用直觀的 Aspose.Page Java API。完成後，你即可以程式方式產生專業的 XPS 檔，並在任何需要的形狀上重複使用此遮罩。

## 快速回答
- **不透明遮罩的作用是什麼？** 它為形狀定義不同的透明度等級，讓底層內容得以透視。  
- **需要哪個函式庫？** Aspose.Page for Java（aspose page java）。  
- **需要授權嗎？** 測試時可使用臨時授權；正式環境必須使用正式授權。  
- **程式碼行數大約多少？** 約 20 行 Java 程式碼，加上少量設定語句。  
- **可以在多個形狀上重複使用遮罩嗎？** 可以，將相同的 `ImageBrush` 指派給多條路徑即可。

## 什麼是不透明遮罩（Opacity Mask）？
不透明遮罩是一種位圖或向量，用來控制形狀中每個像素的 alpha（透明度）。將其套用於矩形時，矩形的部分區域會變成完全不透明、部分透明或完全透明，從而在不增加額外繪圖層的情況下產生複雜的視覺效果。

## 為什麼使用 Aspose.Page Java 來 **create XPS document java**？
- **純 Java API** – 無需本機相依，程式碼可在 Windows、Linux 或 macOS 上執行。  
- **完整符合 XPS 規範** – 遮罩的呈現與 XPS 標準完全一致。  
- **物件導向設計** – 與 .NET 類似，若曾使用過其他語言的 Aspose，學習曲線平緩。  
- **高效能** – 為大型文件與批次處理進行了最佳化。

## 常見使用情境
- **浮水印** – 在頁面上套用半透明的商標。  
- **動態佈景主題** – 在產生的報表中變更 UI 元素的視覺風格。  
- **列印前預覽** – 在送至印表機前，先顯示不同透明度的設計效果。

## 前置條件
在開始之前，請確保你已具備以下條件：
- 基本的 Java 程式設計知識。  
- 已安裝 Aspose.Page for Java 函式庫。你可以在 **[此處](https://releases.aspose.com/page/java/)** 下載。  
- 有效的 Aspose.Page 授權。若尚未取得，可在 **[此處](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。  
- 可編譯與執行 Java 應用程式的開發環境（如 IntelliJ IDEA、Eclipse 或 VS Code）。

## 匯入套件
先匯入 Aspose.Page 函式庫中所需的類別，確保 API 可在專案中使用。

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## 步驟說明

### 步驟 1：建立新的 XPS 文件
首先，實例化一個全新的 XPS 文件，用來容納所有圖形。

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### 步驟 2：加入畫布
畫布是 XPS 頁面內的繪圖表面。

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### 步驟 3：加入矩形並套用實心填色
此處建立矩形路徑，並以實心紅色填充。稍後會為此矩形套用不透明遮罩。

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### 步驟 4：使用 ImageBrush 加入不透明遮罩
我們載入 TIFF 影像，定義來源與目標矩形，並將畫筆設定為平鋪模式，使遮罩在需要時重複。

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### 步驟 5：儲存產生的 XPS 文件
最後，將文件寫入磁碟。輸出檔案將包含已套用不透明遮罩的矩形。

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

依照上述步驟操作，即可在 Java XPS 文件中加入 **add opacity mask** 功能，並使用 Aspose.Page 完成。

## 常見問題與除錯
- **找不到影像** – 請確認 `dataDir` 指向正確資料夾，且 `R08SY_NN.tif` 確實存在。  
- **遮罩呈現為實心** – 請確保來源影像本身具有不同的 alpha 值；全不透明的影像不會顯示透明效果。  
- **平鋪模式未生效** – 必須讓目標矩形小於來源矩形，才能觀察到平鋪效果。

## 常見問答

**Q: Aspose.Page 是否相容所有 Java 開發環境？**  
A: 是，Aspose.Page 設計可無縫配合各種 Java IDE 與建置工具。

**Q: 可以在沒有授權的情況下使用 Aspose.Page 嗎？**  
A: 雖然可使用臨時授權進行評估，但正式環境必須取得正式授權。

**Q: 試用版有什麼限制？**  
A: 試用版可能會對檔案大小或功能施加限制，詳情請參閱官方文件。

**Q: 如何取得 Aspose.Page 的支援？**  
A: 前往 **[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)** 取得社群協助，或購買授權以獲得專業支援。

**Q: Aspose.Page 提供退款保證嗎？**  
A: 請參考 **[購買頁面](https://purchase.aspose.com/buy)** 了解退款政策。

---

**最後更新：** 2026-04-30  
**測試環境：** Aspose.Page Java 24.11（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}