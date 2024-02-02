---
title: 使用 Aspose.Page for .NET 應用計量許可證
linktitle: 申請計量許可證
second_title: Aspose.Page .NET API
description: 透過此有關應用計量授權的逐步指南，探索 Aspose.Page for .NET 的無縫整合。輕鬆優化文件處理。
type: docs
weight: 10
url: /zh-hant/net/getting-started/apply-metered-license/
---
## 介紹

透過應用計量許可證來釋放 Aspose.Page for .NET 的全部潛力。本教學將引導您完成設定和應用計量許可證的過程，確保順利且最佳化地使用這個強大的 .NET 程式庫。

## 先決條件

在深入了解這些步驟之前，請確保滿足以下先決條件：

- 適用於 .NET 授權的有效 Aspose.Page：您可以從下列位置取得它：[購買.aspose.com](https://purchase.aspose.com/buy).
-  Aspose.Page庫安裝：參考[文件](https://reference.aspose.com/page/net/)取得安裝說明。
- .NET 開發環境：確保您的電腦上設定了有效的 .NET 環境。

## 導入命名空間

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

## 第 1 步：設定計量公鑰和私鑰

初始化`Aspose.Page.Metered`類並設定計量的公鑰和私鑰。代替`<type public key here>`和`<type private key here>`用你的實際鑰匙。

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## 步驟 2：載入 EPS 檔案並建立文檔

指定 EPS 檔案的路徑並建立一個流來讀取其內容。然後，建立一個實例`PsDocument`來自流的類別。

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## 步驟 3：將 EPS 轉換為 PNG 影像

創建一個`ImageDevice`用於將 EPS 檔案轉換為 PNG 映像。使用以下命令將 EPS 檔案另存為映像`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## 第 4 步：檢索影像位元組

取得圖像字節，其中每個位元組數組代表一頁。在本例中，我們有一頁。

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## 第 5 步：將圖像位元組儲存到文件

將圖像位元組儲存到檔案中，確保從 EPS 成功轉換為 PNG。

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## 第 6 步：驗證計量許可證

目視檢查計量許可證是否已成功應用。如果產生的影像不包含紅色評估訊息，則表示已套用計量許可證，沒有任何問題。

現在您已準備好透過計量授權來利用 Aspose.Page for .NET 的全部功能！

## 結論

本逐步指南為您提供了使用 Aspose.Page for .NET 無縫應用計量授權的知識。增強您的文件處理能力並探索這個強大的庫提供的大量功能。

## 常見問題解答

### 問題 1：如何取得 Aspose.Page for .NET 的計量授權？

 A1：參觀[購買.aspose.com](https://purchase.aspose.com/buy)獲得有效的許可證。

### Q2：在哪裡可以找到 Aspose.Page for .NET 的文件？

 A2：參考[Aspose.Page .NET](https://reference.aspose.com/page/net/)以獲得全面的文件。

### Q3：有 Aspose.Page 討論和支持的論壇嗎？

 A3：是的，請訪問[論壇](https://forum.aspose.com/c/page/39)與社區互動並尋求協助。

### Q4：我可以在購買前試用 Aspose.Page for .NET 嗎？

 A4：當然！造訪免費試用版[這裡](https://releases.aspose.com/).

### Q5：如何取得 Aspose.Page for .NET 的臨時授權？

A5：參觀[臨時牌照/](https://purchase.aspose.com/temporary-license/)獲得臨時許可證。