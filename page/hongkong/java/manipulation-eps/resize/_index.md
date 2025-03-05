---
title: 使用 Aspose.Page 在 Java 中調整 EPS 檔案大小
linktitle: 在Java中調整EPS文件的大小
second_title: Aspose.Page Java API
description: 了解如何使用 Aspose.Page for Java 輕鬆調整 Java 中的 EPS 檔案大小。請按照我們的綜合指南取得逐步說明。
type: docs
weight: 11
url: /zh-hant/java/manipulation-eps/resize/
---
## 介紹
歡迎來到我們關於使用強大的 Aspose.Page 函式庫在 Java 中調整 EPS 檔案大小的逐步指南。如果您曾經需要以程式方式調整 EPS 影像的尺寸，那麼您來對地方了。在本教程中，我們將探索各種調整大小選項，包括點、英吋、毫米和百分比，為您提供滿足特定要求所需的靈活性。
## 先決條件
在我們深入學習本教學之前，請確保您具備以下條件：
- 您的電腦上安裝了 Java 開發工具包 (JDK)。
-  Java 函式庫的 Aspose.Page。你可以下載它[這裡](https://releases.aspose.com/page/java/).
- 對 Java 程式設計有基本的了解。
## 導入包
在您的 Java 專案中，請確保您具有使用 Aspose.Page 功能所需的匯入。這是一個例子：
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
現在，讓我們將教程分解為每個調整大小選項的多個步驟：
## 使用點調整 EPS 大小
### 第 1 步：設定輸入流
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### 步驟2：初始化PsDocument對象
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### 步驟3：擷取EPS影像的目前尺寸
```java
Dimension oldSize = doc.extractEpsSize();
```
### 第 4 步：建立輸出流
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### 第 5 步：調整大小並以磅為單位保存
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## 使用英吋調整 EPS 大小
按照與範例 1 類似的步驟，將「點」替換為「英吋」並相應地調整新尺寸。
## 使用毫米調整 EPS 大小
按照與範例 1 類似的步驟，將「點」替換為「毫米」並相應地調整新尺寸。
## 使用百分比調整 EPS 大小
按照與範例 1 類似的步驟，將「點」替換為「百分比」並相應地調整新大小。
## 結論
恭喜！您已經成功學習如何使用 Aspose.Page 在 Java 中調整 EPS 檔案的大小。本指南為您提供了多種選項，確保您可以自訂調整大小流程以滿足您的特定需求。

## 常見問題解答
### 我可以將此庫用於其他圖像格式嗎？
不，Aspose.Page 是專門為處理 PostScript 和 EPS 檔案而設計的。
### Aspose.Page for Java 是否有免費試用版？
是的，您可以探索免費試用版[這裡](https://releases.aspose.com/).
### 我可以在哪裡找到更多幫助和討論？
參觀[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)以獲得社區支持。
### 我怎麼才能獲得臨時許可證？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 有可用的範例項目嗎？
是的，檢查文檔[這裡](https://reference.aspose.com/page/java/).