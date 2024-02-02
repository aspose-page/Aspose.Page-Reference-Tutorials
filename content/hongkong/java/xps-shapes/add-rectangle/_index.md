---
title: 在 Java XPS 中新增矩形
linktitle: 在 Java XPS 中新增矩形
second_title: Aspose.Page Java API
description: 了解如何使用 Aspose.Page 在 Java XPS 中新增矩形。請按照我們的逐步指南進行無縫文件操作。 #JavaXPS #AsposePage
type: docs
weight: 11
url: /zh-hant/java/xps-shapes/add-rectangle/
---
## 介紹
歡迎閱讀這份有關使用 Aspose.Page 在 Java XPS 中添加矩形的綜合指南！無論您是經驗豐富的開發人員還是剛開始使用 Java XPS，本教學都將透過逐步說明引導您完成整個過程，確保您深入了解主題。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
- Java 程式語言的基礎知識。
-  Aspose.Page 庫已安裝。如果沒有，您可以從以下位置下載[Aspose.Page Java 文檔](https://reference.aspose.com/page/java/).
- 一個有效的 Java 開發環境。
## 導入包
首先，將必要的套件匯入到您的 Java 專案中。確保 Aspose.Page 庫已正確新增至您的類別路徑。這是一個基本範例：
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
現在，讓我們將提供的範例分解為多個步驟，以在 Java XPS 中新增矩形。
## 步驟1：設定文檔目錄
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
```
將「您的文件目錄」替換為所需目錄的路徑。
## 第 2 步：建立新的 XPS 文檔
```java
//建立新的 XPS 文檔
XpsDocument doc = new XpsDocument();
```
這將初始化一個新的 XPS 文件。
## 步驟 3：新增 CMYK 純色描邊矩形
```java
//左下角的 CMYK（藍色）純色描邊矩形
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
此步驟新增帶有 CMYK 純色系的描邊矩形。
## 步驟 4：儲存產生的 XPS 文檔
```java
//儲存產生的 XPS 文檔
doc.save(dataDir + "AddRectangle_out.xps");
```
最後，儲存修改後的 XPS 文件以及新增的矩形。
重複這些步驟，根據需要調整參數，以進一步自訂您的矩形。
## 結論
恭喜！您已經成功學習如何使用 Aspose.Page 在 Java XPS 中新增矩形。本教學為您的 XPS 文件操作工作奠定了堅實的基礎。
## 常見問題解答
### 我可以在單一 XPS 文件中新增多個矩形嗎？
是的，您可以透過重複教程中概述的步驟來新增所需數量的矩形。
### 如何改變矩形的顏色？
修改顏色值`createColor`方法來達到所需的顏色。
### Aspose.Page 適合處理複雜的 XPS 文件操作嗎？
絕對地！ Aspose.Page 提供了一組強大的功能來處理各種 XPS 文件任務。
### 在哪裡可以找到更多範例和支援？
探索[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)取得更多範例並尋求社群協助。
### 我可以在購買前試用 Aspose.Page 嗎？
是的，您可以探索[免費試用](https://releases.aspose.com/)體驗Aspose.Page的功能。