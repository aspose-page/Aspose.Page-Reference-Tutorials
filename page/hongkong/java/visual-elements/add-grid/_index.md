---
date: 2026-03-05
description: 學習如何在 Java 中使用 Aspose.Page 的視覺筆刷添加格線。跟隨一步一步的指南，輕鬆提升文件視覺效果。
linktitle: Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: 如何在 Java 中使用 Visual Brush 添加網格
url: /zh-hant/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Visual Brush 添加格線

## 介紹
如果您想 **在 Java 產生的文件中加入格線**，Aspose.Page 的 Visual Brush 功能讓這件事變得相當簡單。在本教學中，我們將逐步說明每個步驟、解釋為什麼 Visual Brush 非常適合格線圖案，並提供完整可執行的範例。

## 快速解答
- **什麼是 Visual Brush？** 可重複使用的視覺元素，可平鋪或拉伸以填滿區域。  
- **為什麼使用格線？** 格線可協助布局結構、建立背景圖案，或在 XPS 文件中突顯特定區段。  
- **先決條件？** Java JDK、Aspose.Page for Java，以及基本的 Java 圖形概念。  
- **實作需要多長時間？** 在設定好函式庫後，大約 10‑15 分鐘即可完成。  
- **我可以自訂顏色嗎？** 可以——您可以在程式碼中直接控制填色、透明度與平鋪尺寸。

## 為什麼使用 Visual Brush 來添加格線？
Visual Brush 讓您只需定義一次小的視覺（「圖塊」），就能在任意形狀上重複使用。此方式記憶體使用率低，且程式碼保持簡潔，特別是需要在多個畫布上套用相同圖案時。

## 先決條件
在開始撰寫程式碼之前，請確保您已具備以下條件：
- 基本的 Java 程式設計知識。  
- 已安裝 Aspose.Page 函式庫。您可以從 [Aspose.Page for Java 文件](https://reference.aspose.com/page/java/) 下載。  
- 您的機器已安裝 Java Development Kit (JDK)。

## 匯入套件
確保在 Java 專案中已匯入必要的套件：
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

### 步驟 1：設定專案
首先，建立一個 `XpsDocument` 實例，並指向要儲存輸出檔案的資料夾。
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### 步驟 2：建立洋紅格線 Visual Brush
我們會建立一個小的洋紅圖塊，之後會重複使用。路徑幾何形狀定義了圖塊的外觀。
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### 步驟 3：為洋紅格線 Visual Brush 定義幾何形狀
此處說明將接受平鋪刷子的區域。
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### 步驟 4：建立新畫布
在文件中新增一個畫布，並套用平移變換，使格線出現在預期位置。
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### 步驟 5：將格線加入畫布
現在將 Visual Brush 綁定到幾何形狀，並設定平鋪模式。
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### 步驟 6：加入紅色半透明矩形
為了示範圖層效果，我們在格線上覆蓋一個半透明的紅色矩形。
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### 步驟 7：儲存產生的 XPS 文件
最後，將 XPS 檔案寫入磁碟。
```java
doc.save(dataDir + "AddGrid_out.xps");
```

依照上述步驟操作，即可在 Java 應用程式中使用 Aspose.Page 成功加入視覺上美觀的格線。

## 常見使用情境
- **報表背景：** 為財務或工程報表加入細緻的格線圖案，提高可讀性。  
- **設計範本：** 建立可重複使用的頁面範本，讓相同格線在多頁中自動平鋪。  
- **突顯區段：** 以彩色格線覆蓋特定區域，吸引用戶注意。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **格線出現拉伸** | 確認 `TileMode` 設為 `XpsTileMode.Tile`，且來源與目標矩形尺寸相同。 |
| **顏色顯示異常** | 建立實心色刷時使用正確的 RGBA 值（`createColor(alpha, red, green, blue)`）。 |
| **文件未儲存** | 檢查 `dataDir` 是否指向可寫入的資料夾，並確認檔案系統權限。 |

## 結論
恭喜！您已學會 **在 Java 中使用 Aspose.Page 的 Visual Brush 添加格線**。此技巧讓您在圖案渲染上擁有精細的控制，同時保持程式碼的簡潔與可維護性。

## 常見問題
### Aspose.Page 是否適合專業文件產生？
是的，Aspose.Page 是一套為 Java 設計的強大函式庫，適用於專業文件產生。

### 我可以使用 Visual Brush 自訂格線顏色嗎？
當然可以！Visual Brush 支援多種顏色繪製，提供高度的客製化彈性。

### 我可以在哪裡取得 Aspose.Page 的其他支援？
請前往 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 取得社群支援與討論。

### 是否提供 Aspose.Page 的免費試用？
有，您可以使用 [免費試用](https://releases.aspose.com/) 來體驗 Aspose.Page 的功能。

### 如何取得 Aspose.Page 的臨時授權？
可取得 [臨時授權](https://purchase.aspose.com/temporary-license/) 以進行測試。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-03-05  
**測試環境：** Aspose.Page for Java (latest release)  
**作者：** Aspose  

---