---
date: 2026-02-05
description: 學習如何在設定計量授權的同時，使用 Aspose.Page for Java 將 EPS 另存為 PNG。一步一步的指南，附完整程式碼範例。
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: 使用 Aspose.Page Java（計量授權）將 EPS 另存為 PNG
url: /zh-hant/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page Java（計量授權）將 EPS 儲存為 PNG

## 介紹
如果您需要在 Java 應用程式中 **將 EPS 儲存為 PNG**，且想要以最簡便的方式管理授權，您來對地方了。本教學將一步步說明如何為 Aspose.Page 設定計量授權、載入 PostScript（EPS）檔案，並將其轉換為 PNG 圖像，全部以清晰、易於上手的步驟呈現。完成後，您也會了解如何高效 **將 EPS 轉換為 PNG**，以及在生產環境中可用的 **Java PNG 檔寫入** 程式碼。

## 快速答覆
- **「將 EPS 儲存為 PNG」是什麼意思？** 它會把向量 EPS 檔案轉換成點陣 PNG 圖片。  
- **為什麼使用計量授權？** 只需為實際處理的頁數付費，適合工作負載變化大的情況。  
- **需要網路連線嗎？** 不需要，計量金鑰會在本機驗證。  
- **需要哪個 Java 版本？** Java 8 或以上。  
- **設定大約需要多久？** 基本實作約 10 分鐘即可完成。  

## 什麼是「將 EPS 儲存為 PNG」？
將 EPS 儲存為 PNG 會把可縮放的 Encapsulated PostScript 文件轉換成廣受支援的點陣圖格式。PNG 支援透明度且採用無損壓縮，非常適合用於網頁圖形、縮圖與列印預覽。

## 為什麼使用 Aspose.Page 來渲染 EPS 為 PNG？
- **純 Java API** – 無需本機相依性，可在任何支援 JVM 的環境執行。  
- **高保真渲染** – 向量圖形會被準確光柵化，保持線條品質。  
- **計量授權** – 只為實際轉換的頁數付費，成本可預測。  
- **多種輸出選項** – 除 PNG 外，亦可產生 JPEG、TIFF 等，提供不同專案的彈性。

## 前置條件
在開始之前，請確保您已具備：

- 基本的 Java 程式設計知識。  
- 已安裝 Aspose.Page 程式庫 – 可從 [此處](https://releases.aspose.com/page/java/) 下載。  
- 計量授權的公鑰與私鑰，可於 Aspose 帳號中取得。

## 匯入套件
首先，匯入我們將會使用的類別。請保持匯入區塊與範例完全相同，以免編譯錯誤。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## 使用 Aspose.Page Java 將 EPS 儲存為 PNG 的步驟
以下是結合授權、載入、渲染與寫入最終 PNG 檔案的逐步指南。

### 步驟 1：初始化文件與圖像格式
在此設定計量金鑰並定義輸出格式（PNG），這是 **將 EPS 儲存為 PNG** 作業的基礎。

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### 步驟 2：初始化 PostScript 輸入串流
開啟欲轉換的 EPS 檔案。串流會將文件傳入 Aspose.Page。

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### 步驟 3：檢查文件授權
在處理之前，務必確認計量授權已正確套用。

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### 步驟 4：初始化選項與圖像裝置
建立控制轉換設定的選項物件，以及接收渲染圖像的裝置。

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### 步驟 5：將 EPS 檔案儲存為圖像
這是核心的 **將 EPS 儲存為 PNG** 呼叫。文件會使用先前設定的選項渲染至圖像裝置。

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### 步驟 6：取得並寫入圖像位元組
從裝置中提取 PNG 位元組，並寫入磁碟檔案。此步驟示範如何安全地 **在 Java 中寫入 PNG 檔**。

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## 常見問題與解決方案
| 問題 | 為什麼會發生 | 解決方式 |
|------|--------------|----------|
| **授權未被識別** | 金鑰不正確或放置順序錯誤。 | 再次確認公私鑰字串，並確保在任何文件處理之前呼叫 `setMeteredKey`。 |
| **輸出檔案為空** | `device.getImagesBytes()` 回傳 `null`。 | 確認 EPS 檔案有效，且 `ImageSaveOptions` 未設定為零尺寸畫布。 |
| **大型 EPS 產生 OutOfMemoryError** | 渲染大型向量檔案會消耗大量記憶體。 | 改為一次處理單頁，或增加 JVM 堆積大小（`-Xmx2g`）。 |

## 常見問答

**Q: 如何取得計量授權的公鑰與私鑰？**  
A: 可於您的 Aspose 帳號中取得這些金鑰。

**Q: Aspose.Page 程式庫是免費的嗎？**  
A: Aspose.Page 提供免費試用版與付費版。請前往 [此處](https://releases.aspose.com/) 下載試用。

**Q: 可以將 Aspose.Page 用於商業專案嗎？**  
A: 可以，Aspose.Page 提供商業授權。您可於 [此處](https://purchase.aspose.com/buy) 購買。

**Q: 哪裡可以找到更多文件說明？**  
A: 請參考文件說明 [此處](https://reference.aspose.com/page/java/)。

**Q: 如何取得臨時授權？**  
A: 臨時授權可於 [此處](https://purchase.aspose.com/temporary-license/) 取得。

**Q: 若要轉換多頁 EPS 檔案該怎麼做？**  
A: 使用 `device.getImagesBytes()` 逐頁迴圈，將每個位元組陣列寫入獨立的 PNG 檔案。

**Q: 能否調整 PNG 的品質或色深？**  
A: 可以，在呼叫 `document.save(...)` 前，設定 `ImageSaveOptions`（例如 `options.setCompressionLevel(...)`）來調整。

---

**最後更新日期：** 2025-12-03  
**測試環境：** Aspose.Page 24.12 for Java  
**作者：** Aspose  

**最後更新日期：** 2026-02-05  
**測試環境：** Aspose.Page 24.12 for Java（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}