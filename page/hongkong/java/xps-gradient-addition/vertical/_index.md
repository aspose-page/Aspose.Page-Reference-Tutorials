---
date: 2025-12-25
description: 了解如何在 Java XPS 中使用 Aspose.Page 添加垂直漸層。請跟隨此一步一步的指南，提升文件的視覺效果。
linktitle: How to Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
title: 如何在 Java XPS 中加入垂直漸層
url: /zh-hant/java/xps-gradient-addition/vertical/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java XPS 中添加垂直漸層

## 介紹
在本教學中，您將學會 **如何在 Java XPS 文件中添加垂直漸層**。使用垂直漸層可以大幅提升報表、發票或任何可列印內容的視覺衝擊力。我們將一步步說明，從專案設定到最終 XPS 檔案的儲存，全部使用功能強大的 Aspose.Page for Java 函式庫。

## 快速回答
- **垂直漸層的作用是什麼？** 它在形狀的上方到下方之間產生平滑的顏色過渡。  
- **需要哪個函式庫？** Aspose.Page for Java（可從官方網站下載）。  
- **我需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **是否相容於 Java 8 以上？** 是，API 支援 Java 8 及更高版本。  
- **實作需要多久？** 環境設定完成後通常在 10 分鐘以內。

## 前置條件
在進入程式碼之前，請確保您已具備以下條件：

- 一個可正常運作的 Java 開發環境（JDK 8 或更新版本）。  
- Aspose.Page for Java 函式庫。可從 [此處](https://releases.aspose.com/page/java/) 下載。  
- 基本的 Java 程式設計概念。  

## 匯入套件
首先匯入 Java 專案所需的套件，並確保 Aspose.Page for Java 函式庫已加入專案的 classpath。

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```

## 步驟 1：初始化文件
建立一個新的 XPS 文件，此物件將容納之後加入的所有繪圖元素。

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

## 步驟 2：建立帶垂直漸層的路徑
接著定義一個矩形路徑，並套用垂直線性漸層。漸層停點決定顏色以及它們在垂直軸上的位置。

```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## 步驟 3：儲存文件
最後將 XPS 檔寫入磁碟。產生的檔案將包含您先前定義的填滿垂直漸層的矩形。

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

恭喜！您已成功學會 **如何在 Java XPS 文件中添加垂直漸層**，使用 Aspose.Page。

## 為什麼使用垂直漸層？
- **提升美觀度：** 漸層為靜態圖形增添層次感與現代感。  
- **品牌一致性：** 在各頁面之間平滑匹配企業色彩。  
- **輕鬆自訂：** 可在不重新設計圖形的情況下變更顏色或漸層停點。  

## 常見問題與除錯
- **漸層未顯示：** 確認 `LinearGradientBrush` 的起點與終點正確設定為垂直方向。  
- **檔案未儲存：** 確認 `dataDir` 指向可寫入的資料夾，且您具備寫入權限。  
- **找不到函式庫：** 再次確認 Aspose.Page 的 JAR加入專案的建置路徑。  

## 常見問答

**Q: 我可以在商業專案中使用 Aspose.Page for Java 嗎？**  
A: 可以，Aspose.Page for Java 可用於商業用途。您可於 [此處](https://purchase.aspose.com/buy) 購買。

**Q: Aspose.Page for Java 有免費試用版嗎？**  
A: 有，您可在 [此處](https://releases.aspose.com/) 取得免費試用版。

**Q: 我可以在哪裡找到 Aspose.Page for Java 的文件說明？**  
A: 文件說明可於 [此處](https://reference.aspose.com/page/java/) 取得。

**Q: 如何取得 Aspose.Page for Java 的臨時授權？**  
A: 您可在 [此處](https://purchase.aspose.com/temporary-license/) 取得臨時授權。

**Q: 需要協助或有其他問題？**  
A: 請前往 Aspose.Page 社群 [論壇](https://forum.aspose.com/c/page/39)。

---

**最後更新：** 2025-12-25  
**測試環境：** Aspose.Page for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}