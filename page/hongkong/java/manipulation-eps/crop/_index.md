---
date: 2026-09-04
description: 了解如何使用 Aspose.Page 於 Java 中裁剪 EPS 檔案以減少 EPS 檔案大小 – 一個逐步說明的指南，展示如何裁剪 EPS、裁剪
  EPS 圖像以及修剪 EPS 檔案。
keywords:
- reduce eps file size
- how to crop eps
- Aspose.Page Java
- EPS cropping Java
lastmod: 2026-09-04
linktitle: 在 Java 中裁剪 EPS 檔案
og_description: 了解如何使用 Aspose.Page 於 Java 中裁剪 EPS 檔案以減少 EPS 檔案大小 – 快速指南，提供程式碼與技巧。
og_image_alt: 'Guide: cropping EPS files in Java to reduce file size with Aspose.Page'
og_title: 如何在 Java 中裁剪 EPS 檔案以減少 EPS 檔案大小
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  headline: How to crop EPS files in Java to reduce EPS file size
  type: TechArticle
- description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  name: How to crop EPS files in Java to reduce EPS file size
  steps:
  - name: set document directory and input stream
    text: Here we point the code to the folder that holds our source EPS file and
      open a stream for reading it.
  - name: initialize PsDocument object
    text: The `PsDocument` class represents an EPS file in memory, allowing you to
      read and modify its properties. The object gives you access to the original
      bounding box and other metadata.
  - name: extract initial bounding box
    text: Extracting the original bounding box gives you the coordinates of the current
      visible area – handy for deciding how much you need to trim.
  - name: create output stream
    text: We open a stream where the cropped EPS will be written.
  - name: define new bounding box and crop
    text: The `cropEps` method trims the document to a new bounding box and writes
      the result to an output stream. Provide the four coordinates (lower‑left x,
      lower‑left y, upper‑right x, upper‑right y) that define the area you want to
      keep. The method performs the cropping and writes the result to `output_cr
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works with Java 8 and any later version.
    question: Is Aspose.Page compatible with Java 8?
  - answer: Absolutely. A commercial license is required for production deployments.
      You can obtain one [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: Visit the official [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for discussions, code samples, and troubleshooting tips.
    question: Where can I find additional resources and community support?
  - answer: Yes, you can download a free trial of Aspose.Page from the releases page
      [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is there a free trial available for testing?
  - answer: A temporary license can be requested from the licensing portal [temporary
      license request page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for short‑term evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- reduce eps file size
- Aspose.Page
- Java EPS processing
- crop EPS
title: 如何在 Java 中裁剪 EPS 檔案以減少 EPS 檔案大小
url: /zh-hant/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中裁剪 EPS 檔案以減少 EPS 檔案大小

## 介紹
如果您需要在 Java 應用程式中以程式方式 **裁剪 EPS** 檔案，且希望 **減少 EPS 檔案大小**，您來對地方了。在本教學中，我們將逐步說明如何使用功能強大的 Aspose.Page for Java 函式庫裁剪 EPS 圖像。完成本指南後，您將了解為何裁剪 EPS 很重要，看到完整的程式碼，並能將此解決方案整合到自己的專案中。

## 快速回答
- **什麼函式庫處理 Java 中的 EPS 裁剪？** Aspose.Page for Java。  
- **實作基本裁剪需要多長時間？** 約 5‑10 分鐘。  
- **開發是否需要授權？** 免費試用可用於評估；正式上線需購買商業授權。  
- **支援哪些 Java 版本？** Java 8 及以上。  
- **我可以自訂任意邊界框嗎？** 可以——您提供所需的座標。

## 什麼是 EPS 裁剪以及為何使用它？
**EPS 裁剪會建立一個新的邊界框，定義 EPS 檔案的可見區域。**  
裁剪 EPS 檔案會移除不需要的空白，將圖形裁減至實際需要的區域，從而 **減少 EPS 檔案大小**，並提升下游文件（如 PDF 或報告）的版面一致性。

## 為什麼要裁剪 EPS 檔案？
裁剪 EPS 檔案可讓您 **將檔案大小縮小最高 30 %**，消除多餘的邊距，並為批次處理管線標準化圖形。當需要將大量 EPS 資產嵌入單一 PDF，或希望在低功耗裝置上加速渲染時，這特別有用。

## 前置條件
在深入程式碼之前，請確保您已具備：

- **Aspose.Page for Java** 函式庫已安裝 – 從官方頁面下載 [Aspose.Page for Java release page](https://releases.aspose.com/page/java/)。  
- **Java Development Kit (JDK)** 8 或更新版本已安裝於您的機器上。  
- **一個資料夾** 用於存放輸入 EPS (`input.eps`) 與產生的裁剪檔案 (`output_crop.eps`)。

## 匯入套件
首先，匯入必要的 Java 類別。此程式碼片段與原教學完全相同：

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

## 如何在 Java 中裁剪 EPS 圖像
載入來源 EPS，定義新的邊界框，呼叫裁剪 API – 整個操作在五個簡潔步驟內完成。

### 步驟 1：設定文件目錄與輸入串流
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
此處我們將程式指向存放來源 EPS 檔案的資料夾，並開啟讀取串流。

### 步驟 2：初始化 PsDocument 物件
`PsDocument` 類別代表記憶體中的 EPS 檔案，允許您讀取與修改其屬性。  
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
此物件讓您取得原始邊界框及其他中繼資料。

### 步驟 3：擷取初始邊界框
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
擷取原始邊界框可取得目前可見區域的座標，方便決定需要裁減多少。

### 步驟 4：建立輸出串流
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
我們開啟一個串流，用於寫入裁剪後的 EPS。

### 步驟 5：定義新邊界框並裁剪
`cropEps` 方法會將文件裁減至新邊界框，並將結果寫入輸出串流。  
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
提供四個座標（左下 x、左下 y、右上 x、右上 y）以定義要保留的區域。此方法執行裁剪並將結果寫入 `output_crop.eps`。

## 常見問題與解決方案
- **座標不正確：** EPS 使用點 (1/72 英吋)。若裁剪結果偏差，請再次確認單位換算。  
- **找不到檔案錯誤：** 確認 `dataDir` 以正確的路徑分隔符 (`/` 或 `\`) 結尾。  
- **授權例外：** 未使用有效授權執行程式可能會在輸出上加上浮水印。請在正式使用前套用臨時或永久授權。

## 常見問答

**Q: Aspose.Page 是否相容於 Java 8？**  
A: 是的，Aspose.Page 可在 Java 8 及更高版本上執行。

**Q: 我可以在商業專案中使用 Aspose.Page 嗎？**  
A: 當然可以。商業授權是正式部署的必要條件。您可於 [Aspose purchase page](https://purchase.aspose.com/buy) 取得授權。

**Q: 哪裡可以找到更多資源與社群支援？**  
A: 請造訪官方 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 參與討論、取得程式碼範例與故障排除建議。

**Q: 有免費試用版可供測試嗎？**  
A: 有，您可從發行頁面下載 Aspose.Page 的免費試用版，網址為 [Aspose.Page releases page](https://releases.aspose.com/)。

**Q: 如何取得短期評估用的臨時授權？**  
A: 可於授權入口的 [temporary license request page](https://purchase.aspose.com/temporary-license/) 申請臨時授權。

## 結論
您現在已了解如何使用 Aspose.Page 在 Java 中 **裁剪 EPS** 檔案以 **減少 EPS 檔案大小**。透過自訂邊界框並呼叫 `cropEps`，只需幾行程式碼即可去除不必要的邊距或擷取 EPS 圖形的特定部分。將此程式碼片段整合至更大的文件處理管線，即可自動化 EPS 操作，**裁剪 EPS 圖像** 資產，並高效 **修剪 EPS 檔案** 內容。

---

**最後更新：** 2026-09-04  
**測試環境：** Aspose.Page for Java 24.11  
**作者：** Aspose

## 相關教學

- [如何在 Java 中使用 Aspose.Page 調整 EPS 檔案大小](/page/java/manipulation-eps/resize/)
- [使用 Aspose.Page Java（計量授權）將 EPS 轉換為 PNG](/page/java/license-management/set-metered-license/)
- [Aspose Page Java 教學 – 為 EPS 檔案新增 XMP 中繼資料](/page/java/xmp-metadata-manipulation/add-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}