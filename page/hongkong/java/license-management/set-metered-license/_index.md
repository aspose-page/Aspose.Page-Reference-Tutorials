---
date: 2025-12-03
description: 學習如何使用 Aspose.Page for Java 在設定計量授權的同時將 EPS 另存為 PNG。逐步指南，附完整程式碼範例。
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: 使用 Aspose.Page Java（計量授權）將 EPS 另存為 PNG
url: /zh-hant/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Save EPS as PNG with Aspose.Page Java (Metered License)

## Introduction
如果您需要在 Java 應用程式中 **save EPS as PNG**，且希望以免除繁瑣的方式管理授權，您來對地方了。本教學將逐步說明如何為 Aspose.Page 設定計量授權、載入 PostScript (EPS) 檔案，並將其轉換為 PNG 圖像，全部以清晰、簡潔的步驟即刻上手。

## Quick Answers
- **What does “save EPS as PNG” mean?** 它將向量 EPS 檔案轉換為點陣 PNG 圖像。  
- **Why use a metered license?** 只需為實際處理的頁數付費，適合工作負載變化的情況。  
- **Do I need an internet connection?** 不需要，計量金鑰會在本機驗證。  
- **Which Java version is required?** Java 8 或以上。  
- **How long does the setup take?** 基本實作約需 10 分鐘。

## What is “save EPS as PNG”?
將 EPS 轉存為 PNG 會把可縮放的 Encapsulated PostScript 文件轉換為廣受支援的點陣圖格式。PNG 支援透明度且採用無損壓縮，非常適合網頁圖形、縮圖與列印預覽。

## Why use Aspose.Page for this task?
- **Pure Java API** – 無需本機依賴。  
- **High fidelity** – 向量圖形能精確呈現。  
- **Metered licensing** – 只為實際轉換的內容付費。  
- **Support for multiple output formats** – 支援 PNG、JPEG、TIFF 等多種格式。

## Prerequisites
在開始之前，請確保您已具備：

- 基本的 Java 程式設計知識。  
- 已安裝 Aspose.Page 程式庫 – 可從 [here](https://releases.aspose.com/page/java/) 下載。  
- 計量授權的公鑰與私鑰，可於您的 Aspose 帳戶取得。

## Import Packages
首先，匯入我們將會使用的類別。請保持匯入區塊與示範完全相同，以確保程式碼能順利編譯。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Step 1: Initialize Document and Image Format
在此設定計量金鑰並定義輸出格式 (PNG)。這是 **save EPS as PNG** 作業的基礎。

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

## Step 2: Initialize PostScript Input Stream
開啟欲轉換的 EPS 檔案。此串流會將文件傳遞給 Aspose.Page。

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

## Step 3: Check Document License
在處理之前，務必確認計量授權已正確套用。

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

## Step 4: Initialize Options and Image Device
建立控制轉換設定的 Options 物件，以及接收已渲染圖像的裝置。

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

## Step 5: Save EPS File as Image
這是核心的 **save EPS as PNG** 呼叫。文件會依設定的 Options 渲染至圖像裝置。

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

## Step 6: Get and Save Image Bytes
從裝置中取得 PNG 位元組，並寫入磁碟檔案。

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

## Common Issues and Solutions
| Issue | Why it Happens | Fix |
|-------|----------------|-----|
| **License not recognized** | 金鑰不正確或放置順序錯誤。 | 再次確認公鑰/私鑰字串，並確保在任何文件處理之前呼叫 `setMeteredKey`。 |
| **Output file is empty** | `device.getImagesBytes()` 回傳 `null`。 | 確認 EPS 檔案有效，且 `ImageSaveOptions` 未設定為零尺寸畫布。 |
| **OutOfMemoryError on large EPS** | 大型向量檔案渲染時佔用大量記憶體。 | 改為逐頁處理或增加 JVM 堆積大小 (`-Xmx2g`)。 |

## Frequently Asked Questions

**Q: How do I obtain metered public and private keys?**  
A: 您可於 Aspose 帳戶中取得這些金鑰。

**Q: Is the Aspose.Page library free?**  
A: Aspose.Page 提供免費試用版與付費版。請前往 [here](https://releases.aspose.com/) 下載免費試用。

**Q: Can I use Aspose.Page for commercial projects?**  
A: 可以，Aspose.Page 提供商業授權。您可於 [here](https://purchase.aspose.com/buy) 購買。

**Q: Where can I find additional documentation?**  
A: 請參考文件 [here](https://reference.aspose.com/page/java/)。

**Q: How can I get temporary licenses?**  
A: 臨時授權可於 [here](https://purchase.aspose.com/temporary-license/) 取得。

---

**Last Updated:** 2025-12-03  
**Tested With:** Aspose.Page 24.12 for Java  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}