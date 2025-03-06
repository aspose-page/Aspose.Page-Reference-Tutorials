---
title: 在 Java XPS 中新增平鋪影像
linktitle: 在 Java XPS 中新增平鋪影像
second_title: Aspose.Page Java API
description: 使用 Aspose.Page 探索無縫 Java XPS 文件操作。使用此逐步指南學習輕鬆添加平鋪圖像。
weight: 11
url: /zh-hant/java/xps-image-manipulation/add-tiled-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java XPS 中新增平鋪影像

## 介紹
在 Java 開發的動態世界中，對高效文件操作和創建的需求不斷增長。 Aspose.Page for Java 成為一個強大的工具，為開發人員提供無縫處理 XPS 文件的能力。本教學重點在於一項特定任務 - 將平鋪影像新增至 Java XPS 文件。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. Java 開發工具包 (JDK)：確保您的系統上安裝了 JDK。
2.  Aspose.Page for Java：從下列位置下載並安裝 Aspose.Page for Java：[網站](https://releases.aspose.com/page/java/).
3. 您的文檔目錄：選擇或建立要儲存 XPS 文件的目錄。
## 導入包
在您的 Java 專案中，匯入必要的套件以利用 Aspose.Page 功能：
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
現在，讓我們將向 Java XPS 文件添加平鋪影像的過程分解為清晰、可管理的步驟。
## 第 1 步：設定您的項目
首先設定您的 Java 項目，確保正確整合 Aspose.Page for Java。
## 第 2 步：建立 XPS 文檔
使用以下程式碼初始化一個新的 XPS 文件：
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//建立新的 XPS 文檔
XpsDocument doc = new XpsDocument();
```
## 第 3 步：定義平鋪影像路徑
指定要新增至 XPS 文件的平鋪影像的路徑。
## 第 4 步：新增平鋪影像
使用下面的程式碼片段將平鋪圖像新增至 XPS 文件：
```java
//平鋪影像
//ImageBrush 填滿矩形位於右上方下方
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## 第 5 步：儲存文檔
最後，使用以下程式碼儲存產生的 XPS 文件：
```java
//儲存產生的 XPS 文檔
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
重複這些步驟，即可使用 Aspose.Page 輕鬆地將平鋪影像合併到 Java XPS 文件中。
## 結論
Aspose.Page for Java 簡化了 XPS 文件的處理過程，為開發人員提供了高效的文件操作解決方案。透過遵循此逐步指南，您可以輕鬆地將平鋪影像新增至 Java XPS 文件。

## 常見問題解答
### Aspose.Page 與所有 Java 版本相容嗎？
 Aspose.Page 設計用於各種 Java 版本。透過檢查文件確保相容性[這裡](https://reference.aspose.com/page/java/).
### 我可以將 Aspose.Page 用於商業項目嗎？
是的，Aspose.Page 提供商業許可。購買它們[這裡](https://purchase.aspose.com/buy).
### 有免費試用嗎？
是的，透過免費試用探索 Aspose.Page 功能[這裡](https://releases.aspose.com/).
### 我可以在哪裡找到社區支持和討論？
與 Aspose.Page 社群互動[論壇](https://forum.aspose.com/c/page/39).
### 如何獲得 Aspose.Page 的臨時許可證？
獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
