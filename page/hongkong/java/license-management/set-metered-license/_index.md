---
date: 2026-09-24
description: 了解如何使用 Aspose.Page 在 Java 中將 EPS 轉換為 PNG，設定 metered license，並高效編寫 PNG
  檔案的 Java 程式碼。
keywords:
- aspose page convert eps
- write png file java
- metered license java
- eps to png conversion
lastmod: 2026-09-24
linktitle: 在 Java 中設定 Metered License
og_description: Aspose.Page 在 Java 中使用 metered license 將 EPS 轉換為 PNG。本指南逐步說明如何設定授權、渲染
  EPS，以及編寫 PNG 檔案的 Java 程式碼。
og_image_alt: Guide showing Aspose.Page Java converting EPS to PNG with metered license
og_title: Aspose.Page 在 Java 中將 EPS 轉換為 PNG（metered license）
schemas:
- author: Aspose
  dateModified: '2026-09-24'
  description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  headline: Aspose.Page convert EPS to PNG in Java (metered license)
  type: TechArticle
- description: Learn how to use Aspose.Page to convert EPS to PNG in Java, configure
    a metered license, and write PNG file Java code efficiently.
  name: Aspose.Page convert EPS to PNG in Java (metered license)
  steps:
  - name: initialize document and image format
    text: First, set the metered keys and define the output format (PNG). This establishes
      the foundation for the conversion. The `MeteredLicense` class stores your public
      and private keys, while `ImageSaveOptions` tells Aspose.Page to produce PNG
      output.
  - name: initialize PostScript input stream
    text: Open the EPS file you want to convert. The stream feeds the document into
      Aspose.Page. The `FileInputStream` reads the EPS file from disk, allowing the
      `Document` constructor to parse the PostScript data.
  - name: check document license
    text: Always verify that the metered license was applied correctly before processing.
      The `isLicensed()` method returns `true` only when the supplied keys are valid,
      preventing accidental usage of an unlicensed library.
  - name: initialize options and image device
    text: Create the options object that controls conversion settings and the device
      that will receive the rendered image. `ImageDevice` captures the rasterized
      output in memory, while `ImageSaveOptions` lets you tweak DPI, compression level,
      and color depth.
  - name: save EPS file as image
    text: This is the core **save EPS as PNG** call. The document is rendered into
      the image device using the options we configured. The `document.save(device,
      options)` method performs the rasterization in a single step.
  - name: get and save image bytes
    text: Extract the PNG bytes from the device and write them to a file on disk.
      This step demonstrates how to **write PNG file Java** safely. `Files.write(Paths.get("output.png"),
      device.getImagesBytes()[0])` persists the image without additional libraries.
  type: HowTo
- questions:
  - answer: Log into your Aspose account, navigate to the **Metered License** section,
      and copy the generated public and private keys.
    question: How do I obtain metered public and private keys?
  - answer: Aspose.Page offers a free trial with full functionality; production use
      requires a paid license. Download the trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is the Aspose.Page library free?
  - answer: Yes, a commercial license permits deployment in production environments.
      Purchase a license [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: The full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: Temporary licenses are provided through the Aspose portal [Aspose temporary
      license page](https://purchase.aspose.com/temporary-license/).
    question: How can I get a temporary license for evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- aspose.page
- java image conversion
- metered licensing
title: Aspose.Page 在 Java 中將 EPS 轉換為 PNG（metered license）
url: /zh-hant/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page 在 Java 中將 EPS 轉換為 PNG（計量授權）

## 介紹
如果您需要在 Java 應用程式中 **將 EPS 另存為 PNG**，且希望授權方式簡單，您來對地方了。本教學將帶您設定 Aspose.Page 的 **計量授權**、載入 EPS（Encapsulated PostScript）檔案，並將其轉換為 PNG 影像。完成後，您將了解如何 **有效率地將 EPS 渲染為 PNG**，以及如何編寫可靠的 **write PNG file Java** 程式碼以供正式環境使用。

## 快速答覆
- **「將 EPS 另存為 PNG」是什麼意思？** 它會將向量 EPS 檔案轉換為光柵 PNG 影像，保留透明度並使用無損壓縮。  
- **為什麼使用計量授權？** 您只需為實際處理的頁數付費，適合工作負載變化大的情況。  
- **需要網路連線嗎？** 不需要，計量金鑰會在 JVM 本機驗證。  
- **需要哪個 Java 版本？** 完全支援 Java 8 以上。  
- **設定需要多久？** 基本實作大約 10 分鐘即可完成。

## 什麼是「將 EPS 另存為 PNG」？
將 EPS 另存為 PNG 會把向量 Encapsulated PostScript 文件轉換為光柵 PNG 影像，保留透明度並提供無損壓縮。當您需要網頁就緒的圖形、縮圖或可在任何瀏覽器中顯示的可列印預覽，而不必安裝 PostScript 直譯器時，此轉換非常有用。

## 為什麼使用 Aspose.Page 將 EPS 渲染為 PNG？
Aspose.Page 提供純 Java API，能以高保真度光柵化 EPS 檔案，支援超過 50 種輸出格式，且採計量授權模式，讓您只為實際轉換的頁面付費。此函式庫可在不將整個檔案載入記憶體的情況下處理上百頁文件，於任何支援 JVM 的平台上提供快速且精確的渲染。

## 前置條件
在開始之前，請確保您已具備：

- 基本的 Java 開發經驗。  
- 從 [Aspose.Page Java 下載頁面](https://releases.aspose.com/page/java/) 取得的 Aspose.Page 函式庫。  
- 從您的 Aspose 帳戶取得的一對計量公私金鑰。  

## 匯入套件
`import` 陳述式會將所需類別匯入作用域。請保持此區塊與示範完全相同，以免程式碼編譯失敗。

`java.io` 類別負責檔案串流，而 Aspose.Page 類別則管理授權、文件載入與影像渲染。

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## 使用 Aspose.Page Java 將 EPS 另存為 PNG 的方法
以下是結合授權、載入、渲染與寫入最終 PNG 檔案的逐步指南。

### 直接答案
載入 EPS 檔案、套用計量授權、為 PNG 設定 `ImageSaveOptions`、將文件渲染至 `ImageDevice`，最後將產生的位元組寫入磁碟。這一連串動作即可在幾行 Java 程式碼內完成 **將 EPS 另存為 PNG** 的工作流程。

### 步驟 1：初始化文件與影像格式
首先設定計量金鑰並定義輸出格式（PNG），為轉換奠定基礎。

`MeteredLicense` 類別儲存您的公私金鑰，而 `ImageSaveOptions` 告訴 Aspose.Page 產生 PNG 輸出。

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
開啟您想要轉換的 EPS 檔案。串流會將文件資料傳遞給 Aspose.Page。

`FileInputStream` 從磁碟讀取 EPS 檔案，讓 `Document` 建構子能解析 PostScript 資料。

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### 步驟 3：檢查文件授權
在處理之前，務必確認計量授權已正確套用。

`isLicensed()` 方法僅在提供的金鑰有效時回傳 `true`，可防止未授權使用函式庫的情況。

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### 步驟 4：初始化選項與影像裝置
建立控制轉換設定的選項物件，以及接收渲染影像的裝置。

`ImageDevice` 會在記憶體中捕捉光柵化輸出，而 `ImageSaveOptions` 讓您調整 DPI、壓縮等級與色彩深度。

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### 步驟 5：將 EPS 檔案另存為影像
這是核心的 **將 EPS 另存為 PNG** 呼叫。文件會使用先前設定的選項渲染至影像裝置。

`document.save(device, options)` 方法一次完成光柵化工作。

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### 步驟 6：取得並儲存影像位元組
從裝置中取出 PNG 位元組，並寫入磁碟檔案。此步驟示範如何安全地 **write PNG file Java**。

`Files.write(Paths.get("output.png"), device.getImagesBytes()[0])` 可在不額外函式庫的情況下持久化影像。

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
| **授權未被識別** | 金鑰不正確或 `setMeteredKey` 在文件處理之後才呼叫。 | 再次檢查公私金鑰字串，並確保 `setMeteredKey` 於任何 Aspose.Page 呼叫之前執行。 |
| **輸出檔案為空** | `device.getImagesBytes()` 回傳 `null`，可能是 EPS 檔案無法解析。 | 確認 EPS 檔案有效，且 `ImageSaveOptions` 設定了非零的畫布大小。 |
| **大型 EPS 發生 OutOfMemoryError** | 渲染大型向量檔案會消耗大量堆積記憶體。 | 改為一次處理單一頁面，或增加 JVM 堆積大小（`-Xmx2g`）。 |

## 常見問答

**Q: 如何取得計量公私金鑰？**  
A: 登入您的 Aspose 帳戶，前往 **Metered License** 區段，複製產生的公私金鑰。

**Q: Aspose.Page 函式庫是免費的嗎？**  
A: Aspose.Page 提供功能完整的免費試用版；正式使用需購買授權。下載試用版請前往 [Aspose trial download page](https://releases.aspose.com/).

**Q: 我可以在商業專案中使用 Aspose.Page 嗎？**  
A: 可以，商業授權允許在生產環境部署。請至 [Aspose purchase page](https://purchase.aspose.com/buy) 購買授權。

**Q: 哪裡可以找到更多文件說明？**  
A: 完整的 API 參考位於 [Aspose.Page Java API reference](https://reference.aspose.com/page/java/)。

**Q: 如何取得臨時授權以進行評估？**  
A: 臨時授權可透過 Aspose 入口網站的 [Aspose temporary license page](https://purchase.aspose.com/temporary-license/) 取得。

**Q: 若要轉換多頁 EPS 檔案該怎麼做？**  
A: 使用 `device.getImagesBytes()` 逐頁迭代，將每個位元組陣列寫入獨立的 PNG 檔案。

**Q: 能否調整 PNG 的品質或色彩深度？**  
A: 可以，在呼叫 `document.save(...)` 前設定 `ImageSaveOptions`（例如 `options.setCompressionLevel(9)`）。

---

**最後更新：** 2026-09-24  
**測試環境：** Aspose.Page 24.12 for Java（最新）  
**作者：** Aspose

## 相關教學

- [How to Set License for Aspose.Page Java API – License Management](/page/java/license-management/)
- [Convert PS to PNG with Aspose.Page Java API](/page/java/postscript-conversion/to-image/)
- [Resize EPS using Aspose.Page – Java EPS Manipulation](/page/java/manipulation-eps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}