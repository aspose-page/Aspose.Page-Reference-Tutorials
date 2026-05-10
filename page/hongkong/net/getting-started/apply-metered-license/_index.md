---
date: 2026-01-28
description: 學習如何使用 Aspose.Page for .NET 將 EPS 轉換為 PNG，並套用計量授權以實現無縫的文件處理。
linktitle: Apply Metered License
second_title: Aspose.Page .NET API
title: 使用 Aspose.Page for .NET 將 EPS 轉換為 PNG 並套用計量授權
url: /zh-hant/net/getting-started/apply-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 轉換 EPS 為 PNG 並套用計量授權 – Aspose.Page for .NET

## 介紹

透過 **將 EPS 轉換為 PNG** 並套用計量授權，發揮 Aspose.Page for .NET 的完整潛能。本教學將逐步說明從載入 EPS 檔案到儲存為 PNG 圖像的每個步驟，讓您能高效處理文件且不會出現評估水印。

## 快速解答
- **本教學涵蓋什麼內容？** 將 EPS 檔案轉換為 PNG 圖像並使用 Aspose.Page for .NET 套用計量授權。  
- **我需要授權嗎？** 是的，正式環境必須使用計量授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **實作大約需要多久？** 基本轉換約需 10–15 分鐘。  
- **可以在 Linux/macOS 上執行嗎？** 當然可以——Aspose.Page 為跨平台產品。

## 什麼是「將 EPS 轉換為 PNG」？
將 EPS 轉換為 PNG 即是將向量式的 Encapsulated PostScript (EPS) 檔案光柵化為位圖 PNG 圖像。當您需要在網頁、報告或不支援 EPS 的 UI 元件中顯示或嵌入圖形時，此功能非常實用。

## 為什麼在 EPS 轉圖像轉換時使用計量授權？
計量授權讓您僅為實際處理的頁面付費，特別適合工作量不固定的情境。它同時會移除免費試用版的紅色評估標語，確保最終使用者看到的輸出乾淨無痕。

## 前置條件

在開始之前，請確保已具備以下條件：

- 有效的 Aspose.Page for .NET 授權：可從 [purchase.aspose.com](https://purchase.aspose.com/buy) 取得。  
- 已安裝 Aspose.Page 程式庫：請參考 [documentation](https://reference.aspose.com/page/net/) 了解安裝說明。  
- .NET 開發環境：確保您的機器上已設定好可運作的 .NET 環境。

## 匯入命名空間

在您的 .NET 專案中，匯入必要的命名空間以存取 Aspose.Page 功能：

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## 如何使用計量授權將 EPS 轉換為 PNG？

以下提供逐步說明，涵蓋所有您需要了解的內容。

### 步驟 1：設定計量公鑰與私鑰

初始化 `Aspose.Page.Metered` 類別，並設定計量公鑰與私鑰。將 `<type public key here>` 與 `<type private key here>` 替換為您實際取得的金鑰。

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

### 步驟 2：載入 EPS 檔案並建立文件

指定 EPS 檔案的路徑，建立串流以讀取其內容。接著，從該串流建立 `PsDocument` 類別的實例。

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

### 步驟 3：將 EPS 轉換為 PNG 圖像

建立 `ImageDevice` 以將 EPS 檔案轉換為 PNG 圖像。使用 `ImageSaveOptions` 將 EPS 儲存為圖像。

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

### 步驟 4：取得圖像位元組

取得圖像位元組，每個位元組陣列代表一頁。本範例僅有一頁。

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

### 步驟 5：將圖像位元組儲存至檔案

將圖像位元組寫入檔案，確保 EPS 成功轉換為 PNG。

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

### 步驟 6：驗證計量授權

目視檢查計量授權是否成功套用。若產生的圖像未出現紅色評估訊息，即表示計量授權已正確套用，無任何問題。

現在您已準備好使用 Aspose.Page for .NET 的完整功能，並搭配計量授權進行文件處理！

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 紅色評估標語仍然出現 | 未設定授權或金鑰錯誤 | 再次確認公私鑰，並確保在任何文件處理前呼叫 `SetMeteredKey` |
| 未產生輸出檔案 | `dataDir` 路徑錯誤或檔案權限不足 | 確認目錄存在且應用程式具備寫入權限 |
| 多頁未全部儲存 | 只寫入了第一頁 | 迭代 `imagesBytes`，將每個陣列寫入獨立的 PNG 檔案 |

## 常見問答

**Q: 我可以在 CI/CD 流程中使用計量授權嗎？**  
A: 可以，您可以將金鑰安全地儲存（例如放在環境變數），並在建置過程中呼叫 `SetMeteredKey`。

**Q: Aspose.Page 在轉換為 PNG 時是否支援色彩配置檔的保留？**  
A: PNG 輸出會保留原始色彩資訊，您亦可透過 `ImageSaveOptions` 進一步自訂。

**Q: 是否可以將 EPS 轉換為其他點陣格式（JPEG、BMP）？**  
A: 當然可以，只需將 `ImageSaveOptions` 設定為目標格式即可。

**Q: 支援的最大 EPS 檔案大小為多少？**  
A: Aspose.Page 能處理大型檔案，但記憶體使用量會隨圖像解析度提升。對於極大文件，建議逐頁處理。

**Q: 如何以程式方式取得 EPS 檔案的頁數？**  
A: 載入 `PsDocument` 後，可使用 `document.PagesCount` 取得頁數。

## 常見問答集

### Q1：如何取得 Aspose.Page for .NET 的計量授權？

A1：請前往 [purchase.aspose.com](https://purchase.aspose.com/buy) 取得有效授權。

### Q2：在哪裡可以找到 Aspose.Page for .NET 的文件說明？

A2：請參考 [Aspose.Page .NET](https://reference.aspose.com/page/net/) 取得完整文件。

### Q3：是否有 Aspose.Page 的討論論壇與支援渠道？

A3：有，請造訪 [forum](https://forum.aspose.com/c/page/39) 與社群互動並尋求協助。

### Q4：在購買前我可以先試用 Aspose.Page for .NET 嗎？

A4：當然可以！請前往 [here](https://releases.aspose.com/) 下載免費試用版。

### Q5：如何取得 Aspose.Page for .NET 的臨時授權？

A5：請前往 [temporary license/](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

---

**最後更新：** 2026-01-28  
**測試環境：** Aspose.Page 24.12 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}