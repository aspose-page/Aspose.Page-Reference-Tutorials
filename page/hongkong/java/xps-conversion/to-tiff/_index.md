---
date: 2025-12-23
description: 使用 Aspose.Page Java 輕鬆將 XPS 轉換為 TIFF。遵循我們的逐步指南，無縫整合 Aspose Page Java。立即下載！
linktitle: Convert XSP to TIFF in Java using Aspose.Page Java
second_title: Aspose.Page Java API
title: 使用 Aspose.Page Java 在 Java 中將 XSP 轉換為 TIFF
url: /zh-hant/java/xps-conversion/to-tiff/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中使用 Aspose.Page Java 將 XSP 轉換為 TIFF

在當今快速變化的軟件環境中，**aspose page java** 讓 Java 文件轉換變得簡單且可靠。無論您需要 **將 XPS 轉換為 TIFF** 以進行歸檔、列印或批次處理，本教程將逐步說明具體操作，解釋每一步背後的原因，並提供可立即應用的實用技巧。

## 快速答案
- **什麼函式庫負責 XPS‑to‑TIFF 轉換？** Aspose.Page Java。  
- **我需要在生產環境中使用授權嗎？** 是的，需要有效的 Aspose.Page Java 授權。  
- **支援哪個 Java 版本？** JDK 8 或更高。  
- **我可以一次轉換多個 XPS 檔案嗎？** 可以——您可以在相同程式碼周圍建立批次 XPS 轉換迴圈。  
- **列印就緒的 TIFF 最佳解析度為多少？** 300 DPI 是常見選擇，但您可以透過 TiffSaveOptions 調整。

## 什麼是 Aspose.Page Java？
Aspose.Page Java 是一個功能強大的 API，能夠將 XPS（XML Paper Specification）**java 文件轉換** 為多種光柵與向量格式，包括 TIFF。它能處理複雜的頁面佈局、字型與圖形，且不需要 Microsoft XPS Document Writer。

## 為何使用 Aspose.Page Java 進行 XPS 轉 TIFF 轉換？
- **高保真度：** 保留向量資料與文字渲染。  
- **效能：** 為大型檔案與批次 XPS 轉換情境進行最佳化。  
- **彈性：** 可使用 `tiff save options`（如解析度、壓縮與頁面選擇）微調輸出。  
- **跨平台：** 可在任何支援 Java 的作業系統上執行，適合伺服器端處理。

## 前置條件
在深入轉換流程之前，請確保您已具備以下條件：

- 已在機器上安裝 Java Development Kit（JDK）。  
- Aspose.Page for Java 函式庫。您可於[此處](https://releases.aspose.com/page/java/)下載。  
- 有效的 Aspose.Page for Java 授權。您可在[此處](https://purchase.aspose.com/temporary-license/)取得暫時授權，或在[此處](https://purchase.aspose.com/buy)購買完整授權。

## 匯入套件
首先在您的 Java 專案中匯入必要的套件。請確保已將 Aspose.Page for Java 的 JAR 加入建置路徑。

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## 步驟 1：設定文件目錄
定義包含來源 XPS 檔案之資料夾的路徑。

```java
String dataDir = "Your Document Directory";
```

## 步驟 2：載入 XPS 文件
建立指向輸入檔案的 `XpsDocument` 實例。

```java
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

## 步驟 3：初始化 TiffSaveOptions
設定控制影像品質、解析度以及要匯出的頁面的 **tiff save options**。

```java
TiffSaveOptions options = new TiffSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

## 步驟 4：建立渲染裝置
實例化一個 `ImageDevice`，用於將頁面渲染為 TIFF 影像。

```java
ImageDevice device = new ImageDevice();
```

## 步驟 5：將文件儲存為 TIFF
使用裝置與先前定義的選項渲染 XPS 文件。

```java
document.save(device, options);
```

## 步驟 6：迭代並儲存 TIFF 影像
遍歷已渲染的影像緩衝區，將每一頁寫入獨立的 TIFF 檔案。

```java
for (int i = 0; i < device.getResult().length; i++) {
    for (int j = 0; j < device.getResult()[i].length; j++) {
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoTIFF" + "_" + (i + 1) + "_" + (j + 1) + ".tif");
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

恭喜！您已成功使用 **aspose page java** 在 Java 中 **將 XPS 轉換為 TIFF**。歡迎前往[文件說明](https://reference.aspose.com/page/java/)探索更多函式庫的功能與特性。

## 結論
在本教程中，我們涵蓋了執行 **java 文件轉換** 從 XPS 到 TIFF 所需的全部知識，從環境設定到微調 `tiff save options`。使用 Aspose.Page Java，您亦可建立 **批次 XPS 轉換** 工作流程，自動處理數十或數百個檔案。

## 常見問題
### 我可以在沒有授權的情況下使用 Aspose.Page for Java 嗎？
雖然您可以取得暫時授權以進行評估，但在生產環境中必須使用有效授權。請於[此處](https://purchase.aspose.com/buy)取得授權。

### 轉換 XPS 檔案的大小是否有限制？
Aspose.Page for Java 能處理各種大小的文件，但建議在您的特定環境中對較大檔案進行測試。

### 我如何取得 Aspose.Page for Java 的支援或提問？
請前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39)取得社群支援與討論。

### 是否提供 Aspose.Page for Java 的免費試用？
是的，您可以透過免費試用探索此函式庫。請於[此處](https://releases.aspose.com/)下載。

### 此轉換中 TIFF 影像的建議解析度為何？
範例使用 300 DPI 的解析度，但您可依據具體需求自行調整。

---

**最後更新：** 2025-12-23  
**測試環境：** Aspose.Page Java 24.11（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}