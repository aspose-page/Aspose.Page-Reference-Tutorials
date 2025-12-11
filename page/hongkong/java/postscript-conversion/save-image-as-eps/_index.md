---
date: 2025-12-07
description: 學習如何在 Java 中使用 Aspose.Page 這個強大的圖形與列印庫，將圖像儲存為 EPS。
linktitle: Save Image as EPS in Java
second_title: Aspose.Page Java API
title: 在 Java 中使用 Aspose.Page 將圖像儲存為 EPS
url: /zh-hant/java/postscript-conversion/save-image-as-eps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中使用 Aspose.Page 將圖像保存為 EPS

## 介紹
在 Java 程式開發的世界裡，**Aspose.Page** for Java 成為一個強大的工具，能夠操作並以多種格式保存圖像。其最實用的功能之一是將圖像保存為 Encapsulated PostScript (EPS) 檔案——這是一種在專業圖形與高解析度列印工作流程中廣泛採用的格式。  
在本教學中，你將一步步學會如何使用 Aspose.Page 將 JPEG（或任何支援的點陣圖）轉換為 EPS 檔案，並對每一行程式碼提供清晰說明。

## 快速回答
- **需要什麼程式庫？** Aspose.Page for Java  
- **支援的來源格式？** JPEG、PNG、BMP、GIF、TIFF 等  
- **轉換需要多久？** 對於一般尺寸的圖像，通常在一秒以下  
- **開發時需要授權嗎？** 免費試用可用於評估；正式使用需購買授權  
- **可以自訂 EPS 輸出嗎？** 可以——透過 `PsSaveOptions`（壓縮、顏色模式等）

## Aspose.Page 是什麼？
Aspose.Page 是一套 Java API，讓開發者能在不依賴本機圖形函式庫的情況下，建立、編輯與轉換向量與點陣圖形。它支援 PDF、EPS、SVG 以及多種點陣圖格式，是伺服器端文件處理與列印管線的理想選擇。

## 為什麼要將圖像保存為 EPS？
- **可伸縮向量輸出：** EPS 以與設備無關的格式儲存圖形，無論解析度如何都能保持品質。  
- **列印就緒：** 大多數專業印表機和出版工具原生支援 EPS。  
- **跨平台相容性：** EPS 檔案可在 Adobe Illustrator、CorelDRAW 以及許多開源編輯器中開啟。

## 前置條件
在開始編寫程式碼之前，請確保已準備好以下項目：

1. **Java Development Kit (JDK)** – 在機器上已安裝可使用的 JDK。您可從[此處](https://www.oracle.com/java/technologies/javase-downloads.html)下載最新版本。  
2. **Aspose.Page for Java Library** – 從 Aspose.Page [發行頁面](https://releases.aspose.com/page/java/)下載最新的 JAR，並將其加入專案的 classpath。

## 匯入套件
將必要的匯入語句加入 Java 原始檔，這些語句會載入執行 EPS 轉換所需的核心類別。

```java
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create default options
PsSaveOptions options = new PsSaveOptions();
```

這些程式碼設定文件目錄，並建立用於將圖像保存為 EPS 的預設選項。

現在，讓我們將整個流程拆解成清晰、易於管理的步驟。

## 步驟 1：設定文件目錄
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
將 `"Your Document Directory"` 替換為你希望寫入輸出 EPS 檔案的絕對路徑。使用絕對路徑可避免程式在不同工作目錄下執行時產生歧義。

## 步驟 2：建立儲存選項
```java
// Create default options
PsSaveOptions options = new PsSaveOptions();
```
`PsSaveOptions` 讓你可以微調 EPS 輸出。預設建構子會產生一組合理的設定，之後你仍可根據工作流程的需求調整 `Compression`、`ColorMode`、`Resolution` 等屬性。

## 步驟 3：將圖像保存為 EPS
```java
// Save JPEG image to EPS file
PsDocument.saveImageAsEps(dataDir + "input1.jpg", dataDir + "output1.eps", options);
```
此行程式碼執行轉換：

- `dataDir + "input1.jpg"` – 原始 JPEG（或任何支援的點陣圖）路徑。  
- `dataDir + "output1.eps"` – 產生的 EPS 檔案的目標路徑與檔名。  
- `options` – 控制輸出特性的 `PsSaveOptions` 實例。

執行程式後，你會在指定的目錄中找到 `output1.eps`，即可在任何支援 EPS 的應用程式中使用。

## 常見問題與解決方案
| 問題 | 原因 | 解決方案 |
|------|------|----------|
| **FileNotFoundException** | `dataDir` 路徑不正確或缺少來源圖像 | 核對目錄字串，並確保圖像檔案存在。 |
| **OutOfMemoryError**（大型圖像） | 載入極高解析度的點陣圖可能超出 JVM 堆積 | 增加 JVM 堆積大小（`-Xmx`）或在轉換前縮小來源圖像。 |
| **EPS 檔案顯示空白** | 使用不支援的圖像格式 | 在呼叫 `saveImageAsEps` 前，先將來源轉換為支援的格式（例如 JPEG、PNG）。 |

## 常見問與答
### Aspose.Page for Java 是否相容所有圖像格式？
是的，Aspose.Page for Java 支援廣泛的圖像格式，適用於各種應用情境。

### 我可以自訂 EPS 儲存選項嗎？
當然可以！本教學示範了預設選項，你可以根據實際需求調整 `PsSaveOptions` 的屬性。

### 我可以在哪裡找到 Aspose.Page for Java 的其他支援與討論？
請前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 與社群互動，取得協助。

### 是否提供 Aspose.Page for Java 的免費試用？
是的，你可以在[此處](https://releases.aspose.com/)探索免費試用版。

### 如何取得 Aspose.Page for Java 的臨時授權？
請至[此處](https://purchase.aspose.com/temporary-license/)申請臨時授權。

## 結論
恭喜！你已成功學會如何使用 **Aspose.Page** 在 Java 中將圖像保存為 EPS。此功能為進階圖形與列印工作流程開啟了新大門，讓你能直接從 Java 應用程式產生高品質、列印就緒的檔案。

歡迎參考官方 [文件](https://reference.aspose.com/page/java/)，探索 Aspose.Page for Java 的更多功能。準備好後，可嘗試使用 `PsSaveOptions` 來控制壓縮、色深及其他 EPS 參數。

---

**最後更新：** 2025-12-07  
**測試環境：** Aspose.Page 24.12 for Java  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}