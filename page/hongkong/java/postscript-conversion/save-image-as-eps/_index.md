---
date: 2026-02-10
description: 學習如何在 Java 中使用 Aspose.Page——這個功能強大的圖形與列印函式庫——儲存 EPS。
linktitle: Save Image as EPS in Java
second_title: Aspose.Page Java API
title: aspose.page 儲存 EPS – 在 Java 中將圖像儲存為 EPS
url: /zh-hant/java/postscript-conversion/save-image-as-eps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中使用 Aspose.Page 將圖像另存為 EPS

## 介紹
在 Java 程式設計的世界中，**Aspose.Page** 為 Java 所提供的 **aspose.page save eps** 功能是一個強大的工具，可用於操作和匯出各種格式的圖像。其最實用的功能之一是能將點陣圖另存為 Encapsulated PostScript (EPS) 檔案——此格式在專業圖形與高解析度印刷工作流程中被廣泛採用。在本教學中，您將一步一步學會如何使用 Aspose.Page 將 JPEG（或任何支援的點陣圖）轉換為 EPS 檔案，並對每行程式碼作出清晰說明。

## 快速解答
- **需要哪個函式庫？** Aspose.Page for Java  
- **支援的來源格式？** JPEG, PNG, BMP, GIF, TIFF, 以及其他  
- **轉換需要多長時間？** 通常在標準尺寸圖像下不到一秒  
- **開發時需要授權嗎？** 免費試用可用於評估；正式使用需購買授權  
- **可以自訂 EPS 輸出嗎？** 可以——透過 `PsSaveOptions`（壓縮、顏色模式等）

## 什麼是 aspose.page save eps？
Aspose.Page 是一個 Java API，讓開發人員能在不依賴本機圖形函式庫的情況下，建立、編輯與轉換向量與點陣圖形。**aspose.page save eps** 功能專門讓您將點陣圖轉換為裝置無關的 EPS 檔案，使其成為伺服器端文件處理與列印流程的理想選擇。

## 為什麼要將圖像另存為 EPS？
- **可伸縮向量輸出：** EPS 以裝置無關的格式儲存圖形，無論解析度如何皆能保留品質。  
- **列印就緒：** 大多數專業印表機與出版工具皆原生支援 EPS。  
- **跨平台相容性：** EPS 檔案可在 Adobe Illustrator、CorelDRAW 以及許多開源編輯器中開啟。

## 前置條件
在深入程式碼之前，請確保您已準備好以下項目：

1. **Java Development Kit (JDK)** – 已在您的機器上安裝可使用的 JDK。您可從 [here](https://www.oracle.com/java/technologies/javase-downloads.html) 下載最新版本。  
2. **Aspose.Page for Java Library** – 從 Aspose.Page 的 [release page](https://releases.aspose.com/page/java/) 下載最新的 JAR。將 JAR 加入專案的 classpath。

## 匯入套件
將所需的匯入加入您的 Java 原始檔。這些敘述會引入 EPS 轉換所需的核心類別。

```java
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create default options
PsSaveOptions options = new PsSaveOptions();
```

這些程式碼設定文件目錄，並建立用於將圖像另存為 EPS 的預設選項。

現在，讓我們將流程分解為清晰、易於管理的步驟。

## 步驟 1：設定文件目錄
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
將 `"Your Document Directory"` 替換為您希望寫入輸出 EPS 檔案的絕對路徑。使用絕對路徑可避免應用程式在不同工作目錄執行時產生歧義。

## 步驟 2：建立儲存選項
```java
// Create default options
PsSaveOptions options = new PsSaveOptions();
```
`PsSaveOptions` 讓您微調 EPS 輸出。預設建構子會建立一組合理的選項，但若工作流程需要，您之後仍可調整 `Compression`、`ColorMode` 或 `Resolution` 等屬性。

## 步驟 3：將圖像另存為 EPS
```java
// Save JPEG image to EPS file
PsDocument.saveImageAsEps(dataDir + "input1.jpg", dataDir + "output1.eps", options);
```
此單行程式碼執行轉換：

- `dataDir + "input1.jpg"` – 原始 JPEG（或任何支援的點陣圖）之路徑。  
- `dataDir + "output1.eps"` – 產生之 EPS 檔案的目標路徑與檔名。  
- `options` – 控制輸出特性的 `PsSaveOptions` 實例。

執行程式後，您會在指定的目錄中找到 `output1.eps`，即可在任何支援 EPS 的應用程式中使用。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|-------|--------|-----|
| **FileNotFoundException** | `dataDir` 路徑不正確或缺少來源圖像 | 檢查目錄字串，並確保圖像檔案存在。 |
| **OutOfMemoryError**（大型圖像） | 載入極高解析度的點陣圖檔案可能會超出 JVM 堆積 | 增加 JVM 堆積大小（`-Xmx`）或在轉換前縮小來源圖像。 |
| **EPS 檔案顯示空白** | 使用不支援的圖像格式 | 在呼叫 `saveImageAsEps` 前，將來源轉換為支援的格式（如 JPEG、PNG）。 |

## 常見問答

**Q: Aspose.Page for Java 是否相容所有圖像格式？**  
A: 是的，Aspose.Page for Java 支援廣泛的點陣圖格式——包括 JPEG、PNG、BMP、GIF 與 TIFF——使其在各種應用中都相當靈活。

**Q: 我可以自訂 EPS 儲存選項嗎？**  
A: 當然可以！雖然本教學使用預設的 `PsSaveOptions`，您仍可修改 `Compression`、`ColorMode` 與 `Resolution` 等屬性，以符合您的特定需求。

**Q: 我可以在哪裡找到有關 Aspose.Page for Java 的其他支援與討論？**  
A: 前往 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 參與社群並尋求協助。

**Q: 是否提供 Aspose.Page for Java 的免費試用？**  
A: 有的，您可在 [here](https://releases.aspose.com/) 探索免費試用。

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
A: 可在 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

## 結論
恭喜！您已成功學會如何在 Java 中使用 **Aspose.Page** 進行 **aspose.page save eps**。此功能為進階圖形與列印工作流程開啟大門，讓您能直接從 Java 應用程式產生高品質、列印就緒的檔案。

歡迎透過官方的 [documentation](https://reference.aspose.com/page/java/) 探索 Aspose.Page for Java 的更多功能。準備好後，可嘗試使用 `PsSaveOptions` 來調整壓縮、色深與其他 EPS 參數。

---

**最後更新：** 2026-02-10  
**測試環境：** Aspose.Page 24.12 for Java  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}