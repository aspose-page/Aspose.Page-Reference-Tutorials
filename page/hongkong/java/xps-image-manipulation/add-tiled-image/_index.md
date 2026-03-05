---
date: 2025-12-28
description: 學習如何在 Java 中使用 Aspose.Page 建立 XPS 文件，並透過此一步一步的指南輕鬆加入平鋪圖像。
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: 如何在 Java 中使用平鋪圖像建立 XPS 文件
url: /zh-hant/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 XPS 文件並在 Java 中加入平鋪圖像

## 簡介
在現代 Java 開發中，能以程式方式 **create XPS document** 檔案是一項寶貴的技能，尤其當您需要以平鋪圖像等圖形豐富文件時。Aspose.Page for Java 讓此流程變得簡單，讓您專注於視覺設計，而非低階檔案處理。在本教學中，您將學會如何建立 XPS 文件、**add tiled image**，並儲存結果，全部以清晰的逐步程式碼範例說明。

## 快速解答
- **What does Aspose.Page do?** 它提供高階 API 以在 Java 中產生與操作 XPS 文件。  
- **Can I tile an image?** 可以 – 使用 `XpsImageBrush` 搭配 `XpsTileMode.Tile`。  
- **Do I need a license?** 生產環境需要臨時或商業授權。  
- **What Java version is supported?** 任意 JDK 8 以上皆相容。  
- **How long does implementation take?** 基本平鋪圖像情境大約需要 10–15 分鐘。

## What is “create XPS document”?
XPS（XML Paper Specification）檔案是一種固定版面配置的文件格式，類似 PDF。以程式方式建立 XPS 文件可直接從 Java 程式碼產生可列印、與裝置無關的檔案。

## 為什麼要加入平鋪圖像？
平鋪圖像會在指定區域內重複圖形，非常適合作為背景、浮水印或圖案填充。使用 Aspose.Page 的 `XpsTileMode.Tile`，只需幾行程式碼即可實現。

## 先決條件
1. **Java Development Kit (JDK)** – 已安裝 JDK 8 或更新版本。  
2. **Aspose.Page for Java** – 從 [website](https://releases.aspose.com/page/java/) 下載。  
3. **A writable directory** – 用於儲存產生的 XPS 檔案之可寫入目錄。

## 匯入套件
在您的 Java 專案中，匯入必要的類別：

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## 逐步指南

### 步驟 1：設定您的專案
將 Aspose.Page 的 JAR 檔案加入專案的 classpath，並確認匯入語句能順利編譯，無錯誤。

### 步驟 2：建立 XPS 文件
建立一個新的 `XpsDocument` 物件。這是用來容納所有頁面、路徑與資源的核心容器。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### 步驟 3：定義平鋪圖像路徑
將您想平鋪的圖像（例如 `R08LN_NN.jpg`）放置於 `dataDir` 所指向的目錄中。該圖像將作為筆刷圖樣使用。

### 步驟 4：加入平鋪圖像
建立一個矩形路徑，並以 `XpsImageBrush` 填充。將平鋪模式設定為 `Tile` 後，圖像會在矩形內重複。

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### 步驟 5：儲存文件
將 XPS 檔案寫入磁碟。輸出檔案將包含您剛剛定義的平鋪圖像。

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

每當需要在同一 XPS 文件的其他頁面或形狀中 **add tiled image** 時，請重複上述步驟。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| Image not showing | 確認檔案路徑 (`dataDir + "R08LN_NN.jpg"`) 正確且圖像可存取。 |
| Tile pattern appears stretched | 調整來源與目標的 `Rectangle2D` 值，以控制平鋪大小。 |
| Opacity has no effect | 確保在設定平鋪模式後再設定筆刷的不透明度 **after**。 |

## 常見問答

### Aspose.Page 是否相容所有 Java 版本？
Aspose.Page 設計可在多種 Java 版本上運作。請透過檢查文件 [here](https://reference.aspose.com/page/java/) 以確保相容性。

### 我可以在商業專案中使用 Aspose.Page 嗎？
可以，Aspose.Page 提供商業授權。請於 [here](https://purchase.aspose.com/buy) 購買。

### 是否提供免費試用？
可以，請透過免費試用 [here](https://releases.aspose.com/) 體驗 Aspose.Page 功能。

### 我可以在哪裡找到社群支援與討論？
可於 [forum](https://forum.aspose.com/c/page/39) 參與 Aspose.Page 社群討論。

### 如何取得 Aspose.Page 的臨時授權？
請於 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

---

**最後更新：** 2025-12-28  
**測試環境：** Aspose.Page for Java 24.12 (latest)  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
