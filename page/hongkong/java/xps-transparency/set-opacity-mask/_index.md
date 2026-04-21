---
date: 2026-01-02
description: 學習如何使用 Aspose.Page Java 為 XPS 文件添加不透明遮罩。一步一步的指南，教您建立不透明遮罩矩形並提升視覺品質。
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: 在 Java XPS 中使用 Aspose.Page Java 設定不透明遮罩
url: /zh-hant/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java XPS 中使用 Aspose.Page Java 設定不透明遮罩

## 介紹
歡迎閱讀我們關於 **aspose page java** 不透明遮罩的完整指南。在本教學中，您將學習如何建立 XPS 文件、加入畫布，並將不透明遮罩套用到矩形——全部使用功能強大的 Aspose.Page Java API。完成後，您將能夠新增不透明遮罩矩形，為您的 XPS 檔案帶來精緻的半透明效果。

## 快速解答
- **不透明遮罩的作用是什麼？** 它為形狀定義不同的透明度等級，讓底層內容得以顯示。  
- **需要哪個函式庫？** Aspose.Page for Java（aspose page java）。  
- **我需要授權嗎？** 測試時可使用臨時授權；正式環境則需完整授權。  
- **程式碼有多少行？** 大約 20 行 Java 程式碼，加上少量設定語句。  
- **我可以在多個形狀上重複使用同一個遮罩嗎？** 可以，您可以將相同的 ImageBrush 指派給多條路徑。  

## XPS 中的不透明遮罩是什麼？
不透明遮罩是一種位圖或向量，用於控制形狀中每個像素的 alpha（透明度）值。將其套用於矩形時，矩形的部分會變為完全不透明、部分透明或完全透明，從而產生精緻的視覺效果。

## 為何使用 Aspose.Page Java 來處理不透明遮罩？
- **完整的 .NET 風格 API（Java 版）** – 直觀的物件模型。  
- **無外部相依性** – 可在純 Java 環境下運作。  
- **高保真度渲染** – 遮罩的呈現與 XPS 規範完全一致。  
- **跨平台** – 可在 Windows、Linux 或 macOS 上執行，無需修改。  

## 前置條件
- 具備 Java 程式設計的基礎知識。  
- 已安裝 Aspose.Page for Java 函式庫。您可於 **[此處](https://releases.aspose.com/page/java/)** 下載。  
- 擁有有效的 Aspose.Page 授權。若尚未取得，可於 **[此處](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。  
- 具備能編譯與執行 Java 應用程式的開發環境（例如 IntelliJ IDEA、Eclipse 或 VS Code）。  

## 匯入套件
首先從 Aspose.Page 函式庫匯入所需的類別，以確保 API 可在您的專案中使用。

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
首先，實例化一個全新的 XPS 文件，用於容納所有圖形。

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
此處我們建立一條矩形路徑，並以實心紅色填色。此矩形稍後將套用不透明遮罩。

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### 步驟 4：使用 ImageBrush 加入不透明遮罩
我們載入一張 TIFF 圖片，定義來源與目標矩形，並將畫筆設定為平鋪模式，使遮罩在需要時可重複。

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

請依照上述步驟，將 **add opacity mask** 功能整合至您的 Java XPS 文件中，使用 Aspose.Page。

## 常見問題與疑難排解
- **找不到影像** – 請確認 `dataDir` 指向正確的資料夾，且 `R08SY_NN.tif` 確實存在。  
- **遮罩呈現為實心** – 請確認來源影像確實包含不同的 alpha 值；若影像完全不透明，則不會顯示透明效果。  
- **平鋪模式未生效** – 目標矩形必須小於來源矩形，才能明顯看到平鋪效果。  

## 常見問答

**Q: Aspose.Page 是否相容於所有 Java 開發環境？**  
A: 是的，Aspose.Page 設計上可與各種 Java IDE 與建置工具無縫合作。

**Q: 我可以在沒有授權的情況下使用 Aspose.Page 嗎？**  
A: 雖然您可使用臨時授權來評估此函式庫，但正式使用仍需完整授權。

**Q: 試用版有什麼限制嗎？**  
A: 試用版可能會對檔案大小或功能施加限制，詳情請參考官方文件。

**Q: 如何取得 Aspose.Page 的支援？**  
A: 前往 **[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)** 取得社群協助，或購買授權以獲得高階支援。

**Q: Aspose.Page 有提供退款保證嗎？**  
A: 請參考 **[購買頁面](https://purchase.aspose.com/buy)** 了解退款政策。

---

**最後更新：** 2026-01-02  
**測試環境：** Aspose.Page Java 24.11（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}