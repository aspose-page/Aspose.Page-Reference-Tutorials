---
title: 在 Java XPS 中設定不透明蒙版
linktitle: 在 Java XPS 中設定不透明蒙版
second_title: Aspose.Page Java API
description: 探索使用 Aspose.Page 在 Java XPS 中設定不透明遮罩的強大功能。請按照我們的逐步指南獲得視覺增強的文件體驗。
weight: 11
url: /zh-hant/java/xps-transparency/set-opacity-mask/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java XPS 中設定不透明蒙版

## 介紹
歡迎閱讀我們有關使用 Aspose.Page 在 Java XPS 中設定不透明遮罩的綜合指南。在本教學中，我們將引導您完成使用 Aspose.Page for Java 的強大功能建立 XPS 文件、新增畫布以及將不透明遮罩套用至矩形的過程。
## 先決條件
在深入學習本教學之前，請確保您具備以下條件：
- 對 Java 程式設計有基本的了解。
- 安裝了 Java 函式庫的 Aspose.Page。你可以下載它[這裡](https://releases.aspose.com/page/java/).
-  Aspose.Page 的有效許可證。如果沒有，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
- 設定用於運行 Java 應用程式的開發環境。
## 導入包
首先將必要的套件匯入到您的 Java 專案中。確保您已正確整合 Aspose.Page 庫。以下是指導您的片段：
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
現在，讓我們將範例程式碼分解為多個步驟：
## 第 1 步：建立新的 XPS 文檔
```java
//建立新的 XPS 文檔
XpsDocument doc = new XpsDocument();
```
## 第 2 步：新增畫布
```java
//新畫布
XpsCanvas canvas = doc.addCanvas();
```
## 第 3 步：新增帶有不透明蒙版的矩形
```java
//中間左側的矩形，不透明度被 ImageBrush 遮蓋
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## 步驟 4： 使用 ImageBrush 設定不透明蒙版
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## 第 5 步：儲存產生的 XPS 文檔
```java
//儲存產生的 XPS 文檔
doc.save(dataDir + "OpacityMask_out.xps"); 
```
仔細按照以下步驟使用 Aspose.Page 將不透明遮罩合併到 Java XPS 文件中。
## 結論
恭喜！您已經成功學習如何使用 Aspose.Page 在 Java XPS 中設定不透明遮罩。此功能為您的文件增添了一層視覺豐富性，使它們更具吸引力和活力。
## 常見問題解答
### Aspose.Page 是否與所有 Java 開發環境相容？
是的，Aspose.Page 旨在與各種 Java 開發環境無縫協作。
### 我可以在沒有許可證的情況下使用 Aspose.Page 嗎？
雖然您可以在沒有許可證的情況下使用 Aspose.Page，但建議您取得許可證以獲得全部功能和支援。
### 試用版有任何限制嗎？
試用版可能有一些功能限制。建議查看文件以了解詳細資訊。
### 我如何獲得 Aspose.Page 的支援？
您可以訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)以獲得社區支持或購買許可證以獲得高級幫助。
### Aspose.Page 有退款保證嗎？
請參閱[購買頁面](https://purchase.aspose.com/buy)有關退款政策的資訊。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
