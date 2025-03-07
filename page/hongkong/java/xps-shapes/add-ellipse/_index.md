---
title: 使用 Aspose.Page 加入徑向漸層橢圓
linktitle: 在 Java XPS 中加入橢圓
second_title: Aspose.Page Java API
description: 探索使用 Aspose.Page for Java 在 Java XPS 中新增徑向漸層描邊橢圓的分步指南。輕鬆增強您的文件建立。
weight: 10
url: /zh-hant/java/xps-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 加入徑向漸層橢圓

## 介紹
歡迎閱讀我們有關使用 Aspose.Page for Java 在 Java XPS 中新增橢圓的逐步指南。 Aspose.Page 是一個功能強大的 Java 程式庫，可讓開發人員輕鬆處理 XPS 文件。在本教學中，我們將引導您完成建立徑向漸層描邊橢圓並將其儲存為 XPS 文件的過程。
## 先決條件
在我們開始之前，請確保您具備以下先決條件：
- 您的電腦上安裝了 Java 開發工具包 (JDK)。
- 下載 Java 函式庫的 Aspose.Page。你可以得到它[這裡](https://releases.aspose.com/page/java/).
- 您選擇的程式碼編輯器（Eclipse、IntelliJ 等）用於編寫和執行 Java 程式碼。
## 導入包
確保您已在 Java 專案中匯入了使用 Aspose.Page 所需的套件。將以下導入語句加入 Java 檔案的頂部：
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## 第 1 步：設定文檔目錄
定義儲存 XPS 文件的文檔目錄的路徑：
```java
String dataDir = "Your Document Directory";
```
## 第 2 步：建立 XPS 文檔
使用以下程式碼初始化一個新的 XPS 文件：
```java
XpsDocument doc = new XpsDocument();
```
## 第 3 步：定義徑向漸變停止點
為徑向漸層描邊橢圓建立漸變停止點清單：
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## 第 4 步：建立路徑幾何圖形
使用路徑幾何定義徑向漸層描邊橢圓：
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## 第5步：新增畫布和路徑
將新畫布新增至文件並附加具有定義的幾何圖形的路徑：
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## 第6步：設定描邊和漸變
使用徑向漸層畫筆配置路徑的筆畫：
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## 步驟7：設定描邊粗細
指定路徑的描邊粗細：
```java
path.setStrokeThickness(12f);
```
## 第 8 步：儲存文檔
儲存產生的 XPS 文件：
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
恭喜！您已使用 Aspose.Page for Java 在 Java XPS 中成功新增了徑向漸層描邊橢圓。
## 結論
在本教學中，我們探索了建立具有視覺吸引力的徑向漸層描邊橢圓的 XPS 文件的步驟。 Aspose.Page for Java 簡化了 XPS 文件操作，為開發人員提供了強大的工具集。
## 經常問的問題
### 我可以將 Aspose.Page for Java 與其他 Java 程式庫一起使用嗎？
是的，Aspose.Page for Java 可以與其他 Java 程式庫無縫整合。
### Aspose.Page適合大規模文件處理嗎？
絕對地！ Aspose.Page 旨在有效處理大規模文件。
### 在哪裡可以找到有關 Aspose.Page for Java 的更多教學和範例？
參觀[Aspose.Page 用於 Java 文檔](https://reference.aspose.com/page/java/)取得全面的教學和範例。
### 如何取得 Aspose.Page for Java 的臨時授權？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 是否有用於 Aspose.Page 討論的社群論壇？
是的，加入[Aspose.Page 社群論壇](https://forum.aspose.com/c/page/39)與其他開發人員互動並獲得協助。
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
