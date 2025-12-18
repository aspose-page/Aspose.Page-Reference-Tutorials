---
date: 2025-12-18
description: 學習如何在 Java XPS 文件中使用 Aspose.Page 添加格線與透明矩形。逐步指南，教您高效儲存 XPS 文件。
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: 如何在 Java 中使用 Visual Brush 添加格線
url: /zh-hant/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Visual Brush 新增格線

## 介紹
如果你想 **在 Java 產生的 XPS 文件中新增格線**，來對了！本教學將一步步說明如何使用 Visual Brush 加入格線、在格線上疊加透明矩形，最後使用 Aspose.Page Java API **儲存 XPS 文件**。完成後，你將得到一個可在報表、發票或任何大量文件的應用程式中重複使用的精緻視覺效果。

## 快速回答
- **Visual Brush 的功能是什麼？** 它會在指定區域內以可重複使用的視覺內容繪製，適合用來製作格線等重複圖案。  
- **我可以更改格線顏色嗎？** 可以——只要修改筆刷的實色設定即可。  
- **如何在格線上方加入透明矩形？** 使用 `setOpacity` 於填滿實色的路徑上。  
- **哪個方法負責儲存檔案？** `doc.save(...)` 會將 XPS 檔寫入磁碟。  
- **需要授權嗎？** 生產環境必須使用臨時或正式授權。

## 什麼是 Visual Brush Grid？
Visual Brush 讓你先定義一個小的視覺（格線圖樣），再將它平鋪到較大的區域。相較於逐條繪製每條線，這種做法更省記憶體，且能保證像素級的重複精度。

## 為什麼選擇 Aspose.Page 來完成此任務？
- **跨平台** – 只要支援 Java 的作業系統皆可執行。  
- **高保真渲染** – 可精確控制顏色、透明度與平鋪方式。  
- **無外部相依** – 所有功能皆由 Aspose.Page 函式庫提供。

## 前置條件
在開始之前，請確保你已具備以下條件：

- 基本的 Java 程式設計知識。  
- 已安裝 Aspose.Page 函式庫，可從 [Aspose.Page for Java 文件](https://reference.aspose.com/page/java/) 下載。  
- 開發機器上已安裝 JDK 8 以上版本。

## 匯入套件
首先匯入所需的類別，讓編譯器知道要使用哪些型別：

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## 步驟說明

### 步驟 1：設定專案
建立 `XpsDocument` 物件，並指定要儲存輸出檔案的資料夾路徑。

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### 步驟 2：建立品紅色格線 Visual Brush
我們先定義一個小的品紅色圖形，之後會平鋪成格線。

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### 步驟 3：為格線筆刷定義幾何形狀
設定將接受平鋪視覺的矩形區域。

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### 步驟 4：為文件建立新 Canvas
在文件中新增一個 Canvas，並將它放置在格線要顯示的位置。

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### 步驟 5：將格線加入 Canvas
將 Visual Brush 套用到幾何形狀上，啟用平鋪功能。

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### 步驟 6：加入透明紅色矩形（次要功能）
此步驟示範如何在格線上方 **加入透明矩形** 以作為強調。

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### 步驟 7：儲存產生的 XPS 文件
最後將文件寫入磁碟——這就是 **儲存 XPS 文件** 的步驟。

```java
doc.save(dataDir + "AddGrid_out.xps");
```

依照上述步驟操作，即可產生具備透明覆蓋層的專業格線，全部以程式方式自動產出。

## 常見問題與技巧

- **平鋪尺寸不正確**：請確認用於筆刷的 `Rectangle2D` 與預期的重複尺寸相符，否則圖樣會被拉伸。  
- **透明度未生效**：記得在欲透明的路徑上呼叫 `setOpacity`，此設定不會影響筆刷本身。  
- **檔案未儲存**：請檢查 `dataDir` 是否指向已存在的資料夾，且程式具有寫入權限。

## 常見問答

**Q: Aspose.Page 適合用於專業文件產生嗎？**  
A: 適合，Aspose.Page 是一套為 Java 設計的高品質 XPS 與 PDF 產生函式庫。

**Q: 可以使用 Visual Brush 自訂格線顏色嗎？**  
A: 當然可以！只要在筆刷的 `setFill` 呼叫中更改 `createColor` 參數，即可使用任意 RGBA 顏色。

**Q: 哪裡可以取得 Aspose.Page 的其他支援？**  
A: 前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 取得社群協助與官方回覆。

**Q: 有免費試用版嗎？**  
A: 有，請使用 [免費試用](https://releases.aspose.com/) 來體驗全部功能。

**Q: 如何取得測試用的臨時授權？**  
A: 前往 [臨時授權](https://purchase.aspose.com/temporary-license/) 取得開發與評估用的授權。

---

**最後更新：** 2025-12-18  
**測試環境：** Aspose.Page for Java 23.12（最新）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}