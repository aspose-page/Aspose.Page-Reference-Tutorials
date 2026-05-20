---
date: 2026-04-24
description: 學習如何在 Java 中使用徑向漸層橢圓建立 XPS 文件。本分步指南示範如何設定筆畫粗細以及使用 Aspose.Page 定義路徑幾何。
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: 在 Java XPS 中新增橢圓形
second_title: Aspose.Page Java API
title: 在 Java 中建立 XPS 文件 – 新增徑向漸層橢圓
url: /zh-hant/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 新增徑向漸層橢圓

## 介紹
在本教學中，您將學習如何使用 Aspose.Page for Java 以美觀的徑向漸層描邊橢圓 **create XPS document Java**。Aspose.Page 是一個強大的函式庫，抽象化低階 XPS 細節，讓您專注於設計而非檔案格式的複雜性。完成本指南後，您將擁有可直接使用的 XPS 檔案，可嵌入報告、發票或任何文件產生工作流程中。

## 快速解答
- **此程式碼產生什麼？** 包含以多色徑向漸層描邊之橢圓的單頁 XPS 檔案。  
- **使用哪個主要 API？** `Aspose.Page` for Java（`XpsDocument`、`XpsCanvas`、`XpsPath` 等）。  
- **執行範例是否需要授權？** 臨時授權可用於評估；正式環境需購買完整授權。  
- **我們設定了哪些關鍵屬性？** 筆刷（徑向漸層）、擴散方式、漸層停點以及筆畫粗細。  
- **可以調整橢圓大小嗎？** 可以——修改路徑幾何字串或漸層筆刷座標。

## 什麼是「create XPS document Java」？
在 Java 中建立 XPS 文件是指以程式方式直接從 Java 程式碼產生 XML Paper Specification（XPS）檔案——一種類似 PDF 的固定版面文件格式。Aspose.Page 提供高階物件模型（`XpsDocument`、`XpsCanvas` 等），抽象化 XML 標記，使流程如同操作一般的 Java 物件般簡單。

## 為何使用徑向漸層橢圓？
徑向漸層能營造三維感，非常適合在報告中作為視覺重點、標誌或裝飾元素。相較於單色筆畫，漸層在不顯著增加檔案大小的情況下增添深度，且 XPS 格式保留向量品質，支援任意縮放。

## 前置條件
在開始之前，請確保已具備以下條件：
- 已在電腦上安裝 Java Development Kit（JDK）。
- 已下載 Aspose.Page for Java 函式庫。您可於[此處](https://releases.aspose.com/page/java/)取得。
- 您慣用的程式碼編輯器（Eclipse、IntelliJ 等），用於編寫與執行 Java 程式碼。

## 匯入套件
確保在 Java 專案中匯入必要的套件以使用 Aspose.Page。將以下 import 陳述式加入 Java 檔案的最上方：

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

## 步驟 1：設定文件目錄
定義儲存 XPS 文件的文件目錄路徑：

```java
String dataDir = "Your Document Directory";
```

## 步驟 2：建立 XPS 文件
使用以下程式碼初始化新的 XPS 文件：

```java
XpsDocument doc = new XpsDocument();
```

## 步驟 3：定義徑向漸層停點
為徑向漸層描邊橢圓建立漸層停點清單：

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## 步驟 4：建立路徑幾何
使用路徑幾何定義徑向漸層描邊橢圓：

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## 步驟 5：新增畫布與路徑
在文件中新增畫布，並以已定義的幾何形狀加入路徑：

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## 步驟 6：設定筆畫與漸層
以徑向漸層筆刷設定路徑的筆畫：

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## 步驟 7：設定筆畫粗細
指定路徑的 **筆畫粗細**：

```java
path.setStrokeThickness(12f);
```

## 步驟 8：儲存文件
儲存產生的 XPS 文件：

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

恭喜！您已成功在使用 Aspose.Page **create XPS document Java** 時加入徑向漸層描邊橢圓。

## 常見問題與解決方案
| 問題 | 為何發生 | 解決方案 |
|-------|----------------|-----|
| **橢圓呈平面** | 使用 `XpsSpreadMethod.Pad` 而非 `Reflect` | 如 Step 6 所示，將擴散方式改為 `XpsSpreadMethod.Reflect`。 |
| **未產生輸出檔案** | `dataDir` 指向不存在的資料夾 | 確保該目錄存在，或改用絕對路徑。 |
| **漸層顏色異常** | 漸層停點順序不正確 | 確認 `offset` 值（0→1）單調遞增。 |
| **編譯錯誤** | 類路徑缺少 Aspose.Page JAR | 將 `aspose-page-xx.jar` 加入專案相依性。 |

## 常見問答

**Q: 我可以將 Aspose.Page for Java 與其他 Java 函式庫一起使用嗎？**  
A: 可以，Aspose.Page for Java 可無縫整合其他 Java 函式庫。

**Q: Aspose.Page 是否適用於大規模文件處理？**  
A: 絕對可以！Aspose.Page 專為高效處理大規模文件而設計。

**Q: 我在哪裡可以找到更多 Aspose.Page for Java 的教學與範例？**  
A: 請前往 [Aspose.Page for Java 文件](https://reference.aspose.com/page/java/) 取得完整教學與範例。

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
A: 您可於[此處](https://purchase.aspose.com/temporary-license/)取得臨時授權。

**Q: 有 Aspose.Page 的社群論壇嗎？**  
A: 有，請加入 [Aspose.Page 社群論壇](https://forum.aspose.com/c/page/39) 與其他開發者交流並取得協助。

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}