---
title: 在 Java XPS 中加入水平漸變
linktitle: 在 Java XPS 中加入水平漸變
second_title: Aspose.Page Java API
description: 了解如何使用 Aspose.Page 在 Java 中為 XPS 文件添加令人驚嘆的水平漸層。請按照我們的逐步指南進行無縫整合。
weight: 11
url: /zh-hant/java/xps-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java XPS 中加入水平漸變

## 介紹
歡迎閱讀本逐步指南，了解如何使用 Aspose.Page for Java 在 Java XPS 中加入水平漸層。 Aspose.Page for Java 是一個功能強大的程式庫，可讓開發人員無縫地處理 XPS（XML 紙張規格）文件。
在本教學中，我們將引導您完成建立 Java 應用程式以在 XPS 文件中新增水平漸層的過程。請按照以下步驟輕鬆實現此目的。
## 先決條件
在開始之前，請確保您具備以下先決條件：
1. Java 開發環境：確保您的系統上安裝了 Java。如果沒有，請從以下位置下載並安裝最新版本的 Java[java.com](https://www.java.com).
2.  Aspose.Page for Java 函式庫：您需要擁有 Aspose.Page for Java 函式庫。您可以從[Aspose.Page 用於 Java 文檔](https://reference.aspose.com/page/java/).
## 導入包
首先導入 Java 應用程式所需的套件。在您的專案中包含 Aspose.Page for Java 程式庫。您可以透過新增以下程式碼行來完成此操作：
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## 步驟1：初始化文檔
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//初始化文檔
XpsDocument doc = new XpsDocument();
```
## 第2步：建立水平漸層
```java
//水平漸變
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## 第三步：新增漸層路徑
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## 步驟 4：儲存文檔
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
根據需要重複這些步驟，並根據您的特定要求調整參數。
## 結論
恭喜！您已使用 Aspose.Page for Java 成功地為 XPS 文件新增水平漸層。本教學為尋求透過漸變效果增強 Java 應用程式的開發人員提供了全面的指南。
## 常見問題解答
### Q：我可以在單一 XPS 文件中套用多個漸層嗎？
是的，您可以新增具有不同漸層的多個路徑來建立複雜的設計。
### Q：Aspose.Page 與最新的 Java 版本相容嗎？
Aspose.Page for Java 會定期更新，以確保與最新 Java 版本的兼容性。
### Q：Aspose.Page 中還有其他可用的漸層類型嗎？
是的，除了線性漸變之外，Aspose.Page還支援徑向漸變，以實現更多樣化的效果。
### Q：我可以自訂漸層停止點的顏色和位置嗎？
絕對地！您可以完全控制每個漸變停止點的顏色和位置。
### Q：Aspose.Page 是否有社群論壇可供我尋求協助？
是的，您可以訪問[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)與社區聯繫並獲得協助。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
