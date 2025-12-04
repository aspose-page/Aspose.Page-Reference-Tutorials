---
date: 2025-12-04
description: 學習如何在 Java 中使用 Aspose.Page 將 PS 轉換為 PNG。提供逐步指南、先決條件、常見問題與程式碼範例，實現無縫的
  PostScript 轉圖像。
language: zh-hant
linktitle: How to Convert PS to PNG in Java Using Aspose.Page
second_title: Aspose.Page Java API
title: 如何在 Java 中使用 Aspose.Page 將 PS 轉換為 PNG
url: /java/postscript-conversion/to-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.Page 將 PS 轉換為 PNG

## 介紹
如果您需要 **快速且可靠地將 PS 轉換為 PNG**，Aspose.Page for Java 提供了一個簡潔的 API，負責所有繁重的工作。在本教學中，我們將一步步說明整個流程——從專案設定到從 PostScript（.ps）檔案產生高品質 PNG 圖片。完成後，您將了解為何此方法非常適合伺服器端文件處理、批次轉換，或任何需要處理圖形檔案的 Java 應用程式。

## 快速回答
- **需要哪個函式庫？** Aspose.Page for Java（最新版本）。  
- **可以一次轉換多頁嗎？** 可以——每一頁都會另存為單獨的 PNG 檔案。  
- **需要授權嗎？** 免費試用可用於評估；正式上線需購買授權。  
- **支援哪些影像格式？** PNG、JPEG、BMP、GIF、TIFF（此處示範 PNG）。  
- **實作時間大約？** 基本轉換約 10‑15 分鐘即可完成。

## 什麼是 PS 轉 PNG？
PostScript（PS）是一種主要用於列印的頁面描述語言。將 PS 檔案轉成 PNG，等於把描述轉換為點陣圖，方便在瀏覽器中顯示、嵌入文件，或以影像編輯工具進一步處理。

## 為何選擇 Aspose.Page for Java？
- **無外部相依** – 純 Java，無需本機二進位檔。  
- **渲染精確** – 完整保留字型、向量與顏色。  
- **錯誤處理** – 可選擇抑制次要錯誤，確保轉換不中斷。  
- **可擴充** – 適用於單一檔案或大規模批次作業。

## 前置作業
開始之前，請確保您已具備：

- **Aspose.Page for Java 函式庫** 已整合至專案中。可從 [releases page](https://releases.aspose.com/page/java/) 下載。  
- **PostScript 檔案**（`.ps`）已放置於檔案系統的已知目錄。  
- **Java 8+** 已安裝並在開發環境中正確設定。

## 步驟說明

### 步驟 1：匯入必要的套件
先將需要的類別匯入 Java 原始檔，以便使用串流、Aspose EPS API 與影像格式。

```java
// Import necessary packages
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
import com.aspose.page.ImageFormat;
```

### 步驟 2：設定文件目錄並選擇影像格式
定義來源 PS 檔案所在位置，並指定輸出為 PNG。

```java
// Set the path to the documents directory
String dataDir = "Your Document Directory";
// Initialize image format
ImageFormat imageFormat = ImageFormat.PNG;
```

### 步驟 3：初始化 PostScript 輸入串流
為 `.ps` 檔案開啟串流，並建立 Aspose 會渲染的 `PsDocument` 實例。

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### 步驟 4：設定轉換選項
您可以告訴 Aspose 是否要抑制非關鍵錯誤，避免因小問題而中止轉換。

```java
// Set conversion options
boolean suppressErrors = true;
ImageSaveOptions options = new ImageSaveOptions(suppressErrors);
```

### 步驟 5：建立影像裝置
`ImageDevice` 充當接收已光柵化頁面的容器。

```java
// Create ImageDevice
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### 步驟 6：執行轉換
呼叫 `save` 方法將 PS 文件渲染至影像裝置。`try/finally` 區塊確保輸入串流最終會被關閉。

```java
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### 步驟 7：儲存產生的 PNG 檔案
每一頁的位元組陣列都存放在裝置內。遍歷這些陣列，將每個寫入獨立的 PNG 檔，並以連續編號命名。

```java
byte[][] imagesBytes = device.getImagesBytes();
int i = 0;
for (byte [] imageBytes : imagesBytes) {
    String imagePath = dataDir + "PSToImage" + i + "." + imageFormat.toString().toLowerCase();
    FileOutputStream fs = new FileOutputStream(imagePath);
    try {
        fs.write(imageBytes, 0, imageBytes.length);
    } catch (IOException ex) {
        System.out.println(ex.getMessage());
    } finally {
        fs.close();
    }
    i++;
}
```

### 步驟 8：檢查錯誤（可選）
若您啟用了錯誤抑制，仍可檢視渲染過程中產生的警告訊息。

```java
if (suppressErrors) {
    for (Exception ex : options.getExceptions()) {
        System.out.println(ex.getMessage());
    }
}
```

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **未產生輸出檔案** | `dataDir` 路徑不正確或缺乏寫入權限。 | 確認目錄存在且應用程式具有寫入權限。 |
| **缺少字型** | PS 檔案使用的字型未被 Aspose 識別。 | 使用 `options.setAdditionalFontsFolders(...)` 指向自訂字型資料夾。 |
| **頁面渲染不完整** | `suppressErrors` 設為 `false`，導致在次要錯誤時中止。 | 保持 `suppressErrors = true`，或檢查 `options.getExceptions()` 取得詳細資訊。 |

## 常見問答

**Q: 可以轉換含有輕微錯誤的 PS 檔案嗎？**  
A: 可以——在 `ImageSaveOptions` 中將 `suppressErrors` 設為 `true`，即可在非關鍵問題下繼續轉換。

**Q: 如何加入對 JPEG 等其他影像格式的支援？**  
A: 將 `ImageFormat.PNG` 改為 `ImageFormat.JPEG`（或其他支援的列舉值），同時在儲存迴圈中調整檔案副檔名。

**Q: 能否自訂影像尺寸？**  
A: 可以在呼叫 `document.save(...)` 前，使用 `ImageDevice` 的寬度與高度屬性進行設定。

**Q: 哪裡可以找到更詳細的 API 文件？**  
A: 請造訪官方 [documentation](https://reference.aspose.com/page/java/) 與 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 取得社群協助。

**Q: 開發版需要授權嗎？**  
A: 評估用的免費授權即可測試；正式上線則需購買商業授權。

## 結論
現在您已掌握使用 Aspose.Page 在 Java 中 **將 PS 轉換為 PNG** 的完整、可投入生產的作法。依照上述步驟，您可以將 PostScript 渲染整合至任何 Java 應用程式——無論是產生縮圖的 Web 服務、檔案批次處理器，或是可視化列印工作的桌面工具。

---

**最後更新：** 2025-12-04  
**測試環境：** Aspose.Page for Java 24.11（撰寫時最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}