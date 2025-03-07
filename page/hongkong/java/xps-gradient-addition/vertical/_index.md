---
title: 在 Java XPS 中加入垂直漸變
linktitle: 在 Java XPS 中加入垂直漸變
second_title: Aspose.Page Java API
description: 了解如何使用 Aspose.Page 將垂直漸層新增至 Java XPS 文件。毫不費力地增強視覺吸引力。裡面有逐步指南。
weight: 12
url: /zh-hant/java/xps-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java XPS 中加入垂直漸變

## 介紹
在本教程中，我們將探索如何使用 Aspose.Page for Java 在 Java XPS 中新增垂直漸層。在 XPS 文件中添加漸變可以增強內容的視覺吸引力，使其更具吸引力且美觀。
## 先決條件
在我們深入學習本教程之前，請確保您具備以下先決條件：
- 一個有效的 Java 開發環境。
-  Java 函式庫的 Aspose.Page。您可以從以下位置下載：[這裡](https://releases.aspose.com/page/java/).
- 對 Java 程式設計有基本的了解。
## 導入包
首先導入 Java 專案所需的套件。確保您已在專案依賴項中包含 Aspose.Page for Java 程式庫。
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
        
//導入 Java 版 Aspose.Page
```
## 步驟1：初始化文檔
首先初始化 XPS 文件。這為為文件添加路徑和漸變等元素奠定了基礎。
```java
//初始化文檔
XpsDocument doc = new XpsDocument();
```
## 步驟2：建立具有垂直漸層的路徑
現在，讓我們建立一條具有垂直漸層的路徑。這涉及定義路徑幾何形狀並指定漸變停止點。
```java
//建立具有幾何形狀的路徑
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
//定義垂直梯度停止點
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//將垂直漸層應用於路徑
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## 第 3 步：儲存文檔
最後，將新增了垂直漸層的 XPS 文件儲存到所需目錄。
```java
//儲存文件
doc.save(dataDir + "VerticalGradient.xps");
```
恭喜！您已成功使用 Aspose.Page 將垂直漸層新增至 Java XPS 文件中。
## 結論
使用漸變增強 XPS 文件可以顯著提高其視覺吸引力。 Aspose.Page for Java 簡化了這個過程，讓您輕鬆建立令人驚嘆的文件。

### 常見問題解答
### 我可以在商業專案中使用 Aspose.Page for Java 嗎？
是的，Aspose.Page for Java 可用於商業用途。您可以購買[這裡](https://purchase.aspose.com/buy).
### Aspose.Page for Java 是否有免費試用版？
是的，您可以免費試用[這裡](https://releases.aspose.com/).
### 在哪裡可以找到 Aspose.Page for Java 的文檔？
文件可用[這裡](https://reference.aspose.com/page/java/).
### 如何取得 Aspose.Page for Java 的臨時授權？
獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 需要協助或有疑問嗎？
請造訪 Aspose.Page 社區[論壇](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
