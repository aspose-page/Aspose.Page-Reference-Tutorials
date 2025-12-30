---
date: 2025-12-30
description: 學習如何使用 Aspose.Page 透過加入矩形在 Java 中建立 XPS 文件。遵循此逐步指南，輕鬆操作 XPS 文件。
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: 在 Java 中建立 XPS 文件 – 使用 Aspose.Page 添加矩形
url: /zh-hant/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 XPS 文件 Java – 新增矩形

## 簡介
在本完整教學中，你將 **create XPS document Java** 檔案，並學習如何使用 Aspose.Page 函式庫新增矩形。無論是建立報告、發票或自訂圖形，掌握矩形的建立都能讓你精確控制 XPS 版面配置。我們會逐步說明每一行程式碼背後的原因，並示範如何自訂顏色與筆觸，以達到專業效果。

## 快速答覆
- **建議使用哪個函式庫？** Aspose.Page for Java  
- **實作需要多久時間？** 基本矩形約 10 分鐘即可完成  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權  
- **支援哪個 Java 版本？** Java 8 及以上版本  
- **可以新增多個形狀嗎？** 可以 – 為每個形狀重複相同步驟

## 先決條件
在開始之前，請確保你已具備：

- 具備 Java 程式語言的基本知識。  
- 已安裝 Aspose.Page 函式庫。若尚未安裝，可從 [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) 下載。  
- 可正常運作的 Java 開發環境（IDE、JDK，若使用 Maven/Gradle 亦可）。

## 匯入套件
要開始使用，先將必要的套件匯入你的 Java 專案。請確保 Aspose.Page 函式庫已正確加入 classpath。以下為基本範例：

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

現在，讓我們將提供的範例拆解為多個步驟，以在 Java XPS 中新增矩形。

## 步驟 1：設定文件目錄
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

將 `"Your Document Directory"` 替換為你想儲存 XPS 檔案的資料夾路徑。

## 步驟 2：建立新的 XPS 文件
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

此行 **creates** 一個全新的 XPS 文件，之後你可以在其中加入形狀、文字或圖像。

## 步驟 3：新增 CMYK 實色描邊矩形
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

此步驟會加入一個使用 CMYK 實色的描邊矩形。你可以修改幾何字串（`"M 20,10 L 220,10 220,100 20,100 Z"`）以調整大小或位置，並在 `createColor` 中調整顏色值以符合設計需求。

## 步驟 4：儲存產生的 XPS 文件
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

最後，將已加入矩形的 XPS 文件儲存至先前指定的目錄中。

## 常見使用情境
- **報告標題** – 使用矩形作為標題的背景區塊。  
- **發票表格** – 以彩色邊框突顯儲存格或區段。  
- **自訂圖形** – 結合多個矩形以形成複雜圖形。

## 故障排除提示
- **找不到檔案錯誤：** 請確認 `dataDir` 指向已存在的資料夾，且 ICC 配置檔 (`uswebuncoated.icc`) 已放置於該處。  
- **顏色不正確：** 請確保 ICC 配置檔與你使用的色彩空間相符（CMYK 或 RGB）。  
- **尺寸異常：** 調整幾何字串以符合正確的座標。

## 結論
恭喜！你已成功學會如何 **create XPS document Java** 檔案，並使用 Aspose.Page 新增矩形。此基礎讓你能打造更豐富的 XPS 文件、客製化圖形，並將形狀整合至更大的工作流程中。

## 常見問答
### 我可以在單一 XPS 文件中新增多個矩形嗎？
可以，透過重複本教學中的步驟，即可新增任意數量的矩形。

### 如何變更矩形的顏色？
只需在 `createColor` 方法中修改顏色值，即可得到想要的顏色。

### Aspose.Page 是否適合處理複雜的 XPS 文件操作？
絕對適合！Aspose.Page 提供完整且強大的功能，能應付各種 XPS 文件的需求。

### 在哪裡可以找到更多範例與支援？
前往 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 瀏覽更多範例，並向社群尋求協助。

### 我可以在購買前試用 Aspose.Page 嗎？
可以，請使用 [free trial](https://releases.aspose.com/) 體驗 Aspose.Page 的功能。

## Frequently Asked Questions

**Q: 此方法是否支援 Java 11 或更新版本？**  
A: 是的，Aspose.Page 函式庫相容於 Java 8 及以上版本，包括 Java 11、17 以及更高版本。

**Q: 我可以在矩形區域內嵌入圖像嗎？**  
A: 可以，使用 `XpsImage` 元素並以相同的幾何座標將其放置於矩形上方或內部。

**Q: 如何設定填充顏色而非僅有筆觸？**  
A: 呼叫 `path.setFill(...)`，並使用 `doc.createSolidColorBrush(...)` 建立實色筆刷。

**Q: 能否將矩形旋轉？**  
A: 可以，透過 `path.setTransform(...)` 套用變換矩陣，以實現旋轉或縮放。

**Q: 正式上線需要什麼授權？**  
A: 部署時必須購買商業版 Aspose.Page 授權；免費試用版僅限於評估與開發階段。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2025-12-30  
**測試環境：** Aspose.Page for Java 24.12（最新）  
**作者：** Aspose  

---