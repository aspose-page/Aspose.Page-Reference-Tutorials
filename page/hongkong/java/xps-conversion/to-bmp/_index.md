---
date: 2025-12-21
description: 學習如何在 Java 中使用 Aspose.Page 將 XPS 轉換為 BMP 時設定解析度。本 Java 圖像轉換指南確保高品質的結果。
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: 如何在 Java 中將 XPS 轉換為 BMP 時設定解析度
url: /zh-hant/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中將 XPS 轉換為 BMP

## 介紹
歡迎閱讀本步驟指南，說明在使用 Aspose.Page 於 Java 時，**如何設定解析度**，將 XPS（XML Paper Specification）檔案轉換為 BMP（Bitmap）格式。Aspose.Page for Java 是一套功能強大的函式庫，提供完整的 XPS 文件處理功能。本教學將帶領您輕鬆將 XPS 檔案轉換為 BMP 圖片。

## 快速回答
- **應該使用哪個函式庫？** Aspose.Page for Java 提供最完整的 XPS → BMP 轉換功能。  
- **可以控制圖像品質嗎？** 可以 – 使用 `BmpSaveOptions` 來設定解析度與平滑模式。  
- **只能轉換特定頁面嗎？** 當然可以，`options.setPageNumbers()` 讓您挑選精確的頁面。  
- **這是真正的 Java 圖像轉換嗎？** API 直接將 XPS 頁面渲染為位圖資料，無需中間格式。  
- **支援哪個 Java 版本？** 所有現代 Java 版本（8 以上）皆相容。

## 設定解析度的目的為何？
解析度決定產生的 BMP 圖片每英吋點數（DPI）。較高的 DPI 會產生更銳利的圖像，對於列印或細部圖形工作尤為重要。調整解析度讓您完整掌控 **java convert xps** 工作流程的輸出品質。

## 為何選擇 Aspose.Page 進行 XPS → BMP 轉換？
- **高保真** – 保留原始 XPS 的向量品質。  
- **細緻控制** – 您可以設定 DPI、平滑度，甚至選擇要轉換的特定頁面。  
- **無外部相依** – 純 Java 實作，無需本機函式庫。  
- **可擴充** – 同時支援單頁文件與大型多頁 XPS 檔案。

## 前置條件
在開始轉換流程前，請確保具備以下條件：
- **Java 開發環境** – 已在機器上安裝 Java 8 或更新版本。  
- **Aspose.Page for Java 函式庫** – 下載並將 Aspose.Page for Java 函式庫加入專案中。您可於[此處](https://releases.aspose.com/page/java/)取得。  
- **範例 XPS 檔案** – 準備一個您想要轉換為 BMP 的 XPS 文件。

## 匯入套件
在 Java 程式碼中加入必要的 Aspose.Page 套件：
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## 如何設定 XPS 轉 BMP 的解析度
以下提供簡潔的編號步驟，說明在何處以及如何設定解析度，並說明**如何轉換特定頁面**。

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

### 步驟 5：遍歷已渲染的圖像並寫入檔案
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

如需其他客製化或修改，請重複上述步驟。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **BMP 輸出品質低** | 確認 `options.setResolution()` 設為 ≥ 300 DPI。 |
| **文件只轉換了部分內容** | 確認 `options.setPageNumbers()` 包含所有欲轉換的頁碼。 |
| **大型 XPS 檔案發生 OutOfMemoryError** | 將文件分段處理或增大 JVM 堆積大小（`-Xmx`）。 |
| **找不到檔案** | 再次檢查 `dataDir` 路徑，並確認輸入的 XPS 檔案確實存在。 |

## 常見問答
### Q: 我可以自訂 BMP 圖片的解析度嗎？
A: 可以，您只需在程式碼中修改 `options.setResolution()` 參數即可。

### Q: Aspose.Page 是否相容於不同的 Java 版本？
A: 可以，Aspose.Page 支援多種 Java 版本，請確保已安裝相容的版本。

### Q: 如何只轉換特定頁碼範圍的 XPS 檔案？
A: 使用 `options.setPageNumbers()` 方法指定欲轉換的頁碼。

### Q: Aspose.Page 還支援其他輸出格式嗎？
A: 可以，Aspose.Page 支援多種輸出格式，詳情請參閱文件中的完整列表。

### Q: 我可以在哪裡取得更多協助或支援？
A: 前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 取得社群支援與討論。

---

**最後更新：** 2025-12-21  
**測試環境：** Aspose.Page for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}