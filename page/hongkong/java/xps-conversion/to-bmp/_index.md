---
date: 2026-03-08
description: 了解如何在 Java 中使用 Aspose.Page Java 圖像轉換函式庫將 XPS 轉換為 BMP 並設定 BMP 解析度。本指南涵蓋高品質輸出與節省記憶體的技巧。
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: 在 Java 中將 XPS 轉換為 BMP – 設定解析度以獲得高品質輸出
url: /zh-hant/java/xps-conversion/to-bmp/
weight: 10
---

ed With:** Aspose.Page for Java 24.12" keep.

"**Author:** Aspose" keep.

Then closing shortcodes.

Also there is a backtop button shortcode.

Make sure to keep all markdown formatting.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中將 XPS 轉換為 BMP

## 介紹
歡迎閱讀本一步一步的指南，說明如何在 Java 中 **將 XPS 轉換為 BMP**，並使用 Aspose.Page 設定解析度以獲得最佳影像品質。無論您是建立列印流程、產生縮圖，或需要高解析度圖形，控制 DPI 都能讓您彈性因應任何需求。

## 快速解答
- **應該使用哪個函式庫？** Aspose.Page for Java 是最完整的 **java image conversion library**，用於 XPS → BMP。  
- **我可以控制影像品質嗎？** 可以 – 使用 `BmpSaveOptions` 來 **設定 BMP 解析度** 以及平滑模式。  
- **如何在處理大型 XPS 檔案時避免 OutOfMemoryError Java？** 可將頁面分批渲染或增加 JVM 記憶體上限 (`-Xmx`)。  
- **我只需要轉換特定頁面嗎？** 當然可以，`options.setPageNumbers()` 讓您選擇精確的頁碼。  
- **支援哪些 Java 版本？** 所有現代的 Java 版本（8 及以上）皆可順利使用。

## 為何要設定解析度？
解析度決定產生的 BMP 影像每英吋點數 (DPI)。較高的 DPI 會產生更銳利的圖像，這對列印或精細圖形工作至關重要。調整解析度讓您完整掌控 **convert xps to bmp** 工作流程的輸出品質。

## 為何使用 Aspose.Page 進行 XPS → BMP 轉換？
- **高保真** – 保留原始 XPS 的向量品質。  
- **細緻控制** – 您可以設定 DPI、平滑度，甚至選擇要轉換的特定頁面。  
- **無外部相依性** – 純 Java，無需本機函式庫。  
- **可擴充** – 可處理單頁文件以及大型多頁 XPS 檔案。  

## 前置條件
在深入轉換流程之前，請確保您具備以下前置條件：
- **Java 開發環境** – 在您的機器上安裝 Java 8 或更新版本。  
- **Aspose.Page for Java 函式庫** – 下載並在專案中加入 Aspose.Page for Java 函式庫。您可於此處取得函式庫 [here](https://releases.aspose.com/page/java/)。  
- **範例 XPS 檔案** – 準備一個您想要轉換為 BMP 的 XPS 範例文件。

## 匯入套件
在您的 Java 程式碼中加入必要的 Aspose.Page 套件：
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## 如何設定 XPS 轉換為 BMP 的解析度
以下是一個簡潔的編號步驟說明，展示如何設定解析度，以及如何 **轉換特定頁面**。

### 步驟 1：載入 XPS 文件
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### 步驟 2：初始化選項（解析度與頁面選擇）
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### 步驟 3：建立渲染裝置
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### 步驟 4：使用選項儲存文件
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### 步驟 5：遍歷已渲染的影像並寫入檔案
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

如需其他自訂或修改，請重複上述步驟。

## 如何在轉換大型 XPS 檔案時避免 OutOfMemoryError Java
- **分批處理** – 範例已透過分區渲染文件 (`device.getResult()`)，可降低記憶體壓力。  
- **增加 JVM 堆積** – 使用 `-Xmx` 參數（例如 `-Xmx2g`）為大型文件分配更多記憶體。  
- **釋放資源** – 完成後呼叫 `document.close()` 以釋放本機資源。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **BMP 輸出品質低** | 確認 `options.setResolution()` 設為 ≥ 300 DPI 的值。 |
| **僅轉換文件的一部份** | 確保 `options.setPageNumbers()` 包含所有欲轉換的頁碼。 |
| **大型 XPS 檔案發生 OutOfMemoryError** | 將文件分成較小的區段處理或增加 JVM 堆積大小 (`-Xmx`)。 |
| **找不到檔案** | 再次確認 `dataDir` 路徑以及輸入的 XPS 檔案是否存在。 |

## 常見問答
### Q：我可以自訂 BMP 影像的解析度嗎？
A：可以，您只要在程式碼中修改 `options.setResolution()` 參數即可調整解析度。

### Q：Aspose.Page 相容於不同的 Java 版本嗎？
A：可以，Aspose.Page 支援多種 Java 版本。請確保您已安裝相容的版本。

### Q：我如何從特定頁面範圍轉換 XPS 檔案？
A：使用 `options.setPageNumbers()` 方法指定您想要轉換的頁碼。

### Q：Aspose.Page 支援其他輸出格式嗎？
A：可以，Aspose.Page 支援多種輸出格式。請參考文件取得完整清單。

### Q：我可以在哪裡取得其他協助或支援？
A：前往 [Aspose.Page Forum](https://forum.aspose.com/c/page/39) 取得社群支援與討論。

---

**Last Updated:** 2026-03-08  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}