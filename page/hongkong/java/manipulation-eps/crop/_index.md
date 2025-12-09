---
date: 2025-11-30
description: 學習如何在 Java 中使用 Aspose.Page 裁剪 EPS 檔案——一個清晰、逐步說明的教學，教您如何使用 Aspose.Page
  函式庫裁剪 EPS。
linktitle: Crop EPS File in Java
second_title: Aspose.Page Java API
title: 如何在 Java 中裁剪 EPS 檔案 – Aspose.Page 指南
url: /zh-hant/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中裁剪 EPS 檔案 – Aspose.Page 步驟指南

## 介紹
如果您需要在 Java 應用程式中以程式方式 **裁剪 eps** 檔案，您來對地方了。在本教學中，我們將完整示範如何使用功能強大的 Aspose.Page for Java 函式庫來裁剪 EPS 圖像。閱讀完本指南後，您將了解為何需要裁剪 EPS、看到完整的程式碼範例，並能將此解決方案整合到自己的專案中。

## 快速回答
- **哪個函式庫負責在 Java 中裁剪 EPS？** Aspose.Page for Java。  
- **實作基本裁剪大約需要多久？** 約 5‑10 分鐘。  
- **開發時需要授權嗎？** 免費試用可用於評估；正式上線需購買商業授權。  
- **支援哪些 Java 版本？** Java 8 及以上。  
- **可以自訂任意裁剪框嗎？** 可以——只要提供您需要的座標即可。

## 什麼是 EPS 裁剪，為什麼要使用？
Encapsulated PostScript (EPS) 是一種圖形格式，會儲存向量圖像以及定義可見區域的邊界框。裁剪 EPS 檔案即是建立一個新的邊界框，讓只有您關心的區域被保留下來。這在您想去除白色邊距、擷取商標，或在不重新建立來源檔的情況下將圖形放入更緊湊的版面時非常有用。

## 前置條件
在開始撰寫程式碼之前，請確保您已具備：

- 已安裝 **Aspose.Page for Java** 函式庫——可從官方頁面 [here](https://releases.aspose.com/page/java/) 下載。  
- 已在電腦上安裝 **Java Development Kit (JDK)** 8 或更新版本。  
- **一個資料夾** 用來存放輸入的 EPS (`input.eps`) 與產生的裁剪後檔案 (`output_crop.eps`)。

## 匯入套件
首先，匯入必要的 Java 類別。此程式碼片段與原教學完全相同：

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

### 步驟 1：設定文件目錄與輸入串流
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
此處將程式指向保存來源 EPS 檔案的資料夾，並開啟讀取串流。

### 步驟 2：初始化 PsDocument 物件
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
`PsDocument` 類別代表記憶體中的 EPS 文件，讓我們能查詢與操作其屬性。

### 步驟 3：擷取初始邊界框
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
取得原始邊界框可得到目前可見區域的座標——這對決定需要裁剪多少非常有幫助。

### 步驟 4：建立輸出串流
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
開啟一個串流，將裁剪後的 EPS 寫入其中。

### 步驟 5：定義新邊界框並執行裁剪
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
提供四個座標（左下 x、左下 y、右上 x、右上 y）以定義要保留的區域。`cropEps` 方法會執行裁剪，並將結果寫入 `output_crop.eps`。

## 常見問題與解決方案
- **座標不正確：** EPS 使用點 (1/72 英吋) 為單位。若裁剪結果偏差，請再次確認單位換算。  
- **找不到檔案錯誤：** 確認 `dataDir` 以正確的路徑分隔符 (`/` 或 `\`) 結尾。  
- **授權例外：** 未使用有效授權執行程式可能會在輸出上加上浮水印。請在正式上線前套用臨時或永久授權。

## 常見問答

**Q: Aspose.Page 是否相容於 Java 8？**  
A: 是的，Aspose.Page 可在 Java 8 及之後的所有版本上執行。

**Q: 我可以在商業專案中使用 Aspose.Page 嗎？**  
A: 當然可以。商業部署必須購買商業授權。您可於 [here](https://purchase.aspose.com/buy) 取得。

**Q: 哪裡可以找到更多資源與社群支援？**  
A: 前往官方 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 參與討論、取得程式碼範例與除錯技巧。

**Q: 有提供免費試用嗎？**  
A: 有，您可從發行頁面 [here](https://releases.aspose.com/) 下載 Aspose.Page 的免費試用版。

**Q: 如何取得短期評估用的臨時授權？**  
A: 可於授權入口 [here](https://purchase.aspose.com/temporary-license/) 申請臨時授權。

## 結論
現在您已掌握 **如何在 Java 中裁剪 eps** 檔案的技巧，透過自訂邊界框並呼叫 `cropEps`，只需幾行程式碼即可去除不需要的邊距或擷取 EPS 圖形的特定部分。將此程式碼片段整合到更大的文件處理流程中，即可自動化 EPS 操作，讓您的視覺資產保持整潔。

---

**最後更新：** 2025-11-30  
**測試環境：** Aspose.Page for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}