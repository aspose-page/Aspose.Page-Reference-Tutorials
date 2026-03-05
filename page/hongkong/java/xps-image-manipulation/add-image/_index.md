---
date: 2025-12-28
description: 了解如何在 Java 中使用 Aspose.Page 向 XPS 文件添加圖片。本分步指南將向您展示如何輕鬆加入圖片，提升文件處理效能。
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: 如何在 Java XPS 文件中加入圖片 – Aspose.Page 簡易指南
url: /zh-hant/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java XPS 文件中加入圖片（使用 Aspose.Page）

在 XPS 檔案中加入圖片是許多 Java 開發人員需要的常見需求，無論是豐富報表、發票或任何視覺文件。本教學將示範 **如何加入圖片** 到 XPS 文件，使用功能強大的 Aspose.Page for Java 函式庫。我們會一步步說明每行程式碼的意義，並提供避免常見問題的技巧。

## 快速解答
- **需要的函式庫是什麼？** Aspose.Page for Java  
- **我可以加入多張圖片嗎？** 是 – 為每張圖片重複加入圖片的步驟  
- **支援的圖片格式？** TIFF, JPEG, PNG, GIF (and others supported by .NET)  
- **需要授權嗎？** 免費試用可用於評估；正式環境需購買商業授權  
- **典型實作時間？** 基本圖片插入大約需要 10‑15 分鐘  

## 簡介
在許多 Java 應用程式中，將圖片加入 XPS 文件是常見需求，從報表產生到文件處理皆是如此。Aspose.Page for Java 簡化了這項工作，提供高效的方法讓您無縫地將圖片整合到 XPS 檔案中。本教學將示範如何使用 Aspose.Page for Java 在 XPS 文件中加入圖片。

## 前提條件
在開始教學之前，請確保您已具備以下前置條件：
1. **Aspose.Page for Java Library** – 從[網站](https://releases.aspose.com/page/java/)下載並安裝 Aspose.Page for Java 函式庫。  
2. **Java Development Environment** – 確保您的機器已設定 Java 開發環境。

現在，讓我們繼續下一步。

## 導入包
在您的 Java 專案中，匯入必要的 Aspose.Page for Java 套件，以存取所需的類別與方法。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## 步驟 1：設定文件目錄
定義文件目錄的路徑，該目錄將存放 XPS 文件與圖片檔案。

```java
String dataDir = "Your Document Directory";
```

## 步驟 2：建立新的 XPS 文檔
使用以下程式碼片段初始化一個新的 XPS 文件：

```java
XpsDocument doc = new XpsDocument();
```

## 步驟 3：在 XPS 文件中新增影像
若要加入圖片，先在 XPS 文件中建立路徑，然後使用提供的圖片檔案與座標設定圖片筆刷。

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## 步驟 4：儲存產生的 XPS 文檔
將修改後的 XPS 文件儲存至您指定的目錄。

```java
doc.save(dataDir + "AddImage_out.xps");
```

重複上述步驟即可加入更多圖片，或依照專案需求自訂現有圖片。

## 總結
恭喜！您已成功學會 **如何加入圖片** 到 XPS 文件，使用 Aspose.Page for Java。此技能對提升 Java 應用程式與文件的視覺效果相當重要。

### 常見問題解答
### 我可以在同一個 XPS 文件中加入多張圖片嗎？
是的，您可以透過重複本教學中的步驟，為每張圖片加入多次。

### Aspose.Page for Java 支援哪些圖片格式？
Aspose.Page for Java 支援多種圖片格式，包括 TIFF、JPEG、PNG 與 GIF。

### 有提供 Aspose.Page for Java 的試用版嗎？
有，您可以從[此連結](https://releases.aspose.com/)取得 Aspose.Page for Java 的免費試用版。

### 如何取得 Aspose.Page for Java 的臨時授權？
您可以從[此連結](https://purchase.aspose.com/temporary-license/)取得臨時授權。

### 哪裡可以找到額外的支援或討論 Aspose.Page for Java 的相關問題？
請造訪[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)尋求協助、分享經驗，並與 Aspose.Page 社群互動。

## 其他提示和常見陷阱
- **路徑幾何精確度** – 確保 SVG 風格的路徑字串與圖片尺寸相符，否則圖片可能會被拉伸或裁切。  
- **圖片筆刷縮放** – `createImageBrush` 方法接受來源與目標矩形；調整這些值可精確控制位置與縮放。  
- **授權啟用** – 若在未取得有效授權的情況下執行程式，Aspose 會在產生的 XPS 檔案上加上浮水印。

---

**最後更新：** 2025-12-28  
**測試環境：** Aspose.Page for Java 23.12（撰寫時最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}