---
date: 2026-01-02
description: 學習如何使用 Aspose.Page 為 Java XPS 文件加入透明度。請參考我們的逐步指南，為物件添加透明效果，呈現驚豔的視覺效果。
linktitle: Add Transparent Object in Java XPS
second_title: Aspose.Page Java API
title: 如何在 Java XPS 文件中加入透明度
url: /zh-hant/java/xps-transparency/add-transparent-object/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java XPS 文件中添加透明度

## 簡介
如果你想要 **如何添加透明度** 到你的 Java XPS 文件，並賦予它們現代化、分層的外觀，Aspose.Page for Java 讓這變得簡單。 在本教學中，我們將逐步說明所有需要的內容——從環境設定、建立透明路徑、操作不透明度，到最後儲存結果。 完成後，你將能自信地為任何 XPS 物件添加透明度。

## 快速答案
- **需要哪個函式庫？** Aspose.Page for Java  
- **可以程式化控制不透明度嗎？** 可以，透過刷子的 `setOpacity` 方法。  
- **生產環境需要授權嗎？** 非評估用途需購買商業授權。  
- **支援哪個 Java 版本？** Java 8 及以上。  
- **輸出是否相容於標準 XPS 檢視器？** 當然——標準檢視器會正確呈現透明度。

## 什麼是 XPS 中的透明度？
透明度允許你以不同的不透明度渲染物件，讓背景元素透過顯示。此效果適用於浮水印、覆蓋圖形，或任何透過分層視覺提升可讀性的設計。

## 為什麼使用 Aspose.Page 來添加透明度？
- **完整控制** 幾何、刷子與變換。  
- **無外部相依性**——所有功能皆在 API 內處理。  
- **跨平台** 支援，讓相同程式碼可在 Windows、Linux 與 macOS 上執行。

## 先決條件
在開始之前，請確保你已具備：

- Java 開發環境 (JDK 8+)。  
- 已安裝 Aspose.Page for Java 函式庫。你可以從官方網站 [here](https://releases.aspose.com/page/java/) 下載。

## 匯入套件
在你的 Java 專案中，匯入必要的 Aspose.Page 套件以開始加入透明物件。於 Java 檔案開頭加入以下程式碼：

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.Color;
```

現在，讓我們將範例程式碼分成多個步驟說明。

## 步驟 1：初始化文件
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize document
XpsDocument doc = new XpsDocument();
```
首先設定文件，並指定 XPS 文件將儲存的目錄。

## 步驟 2：建立透明物件
```java
// Just to demonstrate transparency
doc.addPath(doc.createPathGeometry("M120,0 H400 v1000 H120")).setFill(doc.createSolidColorBrush(Color.GRAY));
doc.addPath(doc.createPathGeometry("M300,120 h600 V420 h-600")).setFill(doc.createSolidColorBrush(Color.GRAY));
```
此處，我們建立兩條灰色路徑，作為稍後要加入的透明形狀的背景。

## 步驟 3：加入填充路徑
```java
// Create path with closed rectangle geometry
XpsPath path1 = doc.createPath(doc.createPathGeometry("M20,20 h200 v200 h-200 z"));
// Set blue solid brush to fill path1
path1.setFill(doc.createSolidColorBrush(Color.BLUE));
// Add it to the current page
XpsPath path2 = doc.add(path1);
```
在此步驟中，我們建立一個實心藍色矩形並放置於頁面上。此矩形稍後會被透明形狀覆蓋，以示範效果。

## 步驟 4：操作透明度
```java
// path1 and path2 are the same as long as path1 hasn't been placed inside any other element
path2.setFill(doc.createSolidColorBrush(Color.GREEN));
// Now add path2 once again. Now path2 has a parent, so path3 won't be the same as path2.
XpsPath path3 = doc.add(path2);
path3.setRenderTransform(doc.createMatrix(1, 0, 0, 1, 0, 300));
path3.setFill(doc.createSolidColorBrush(Color.RED));
```
此處我們變更複製路徑的填色，並套用平移變換。此示例說明當物件共享同一父元素時，透明度的相互作用。

## 步驟 5：複製與修改路徑
```java
// Create new path4 with path2's geometry
XpsPath path4 = doc.addPath(path2.getData());
path4.setRenderTransform(doc.createMatrix(1, 0, 0, 1, 300, 0));
path4.setFill(doc.createSolidColorBrush(Color.BLUE));
// Add path4 once again.
XpsPath path5 = doc.add(path4);
path5.setRenderTransform(path5.getRenderTransform().deepClone());
path5.getRenderTransform().translate(0, 300);
path5.getFill().setOpacity(0.8f);
```
我們複製現有路徑，移動它，並將不透明度調整為 0.8（80 % 不透明）。此步驟展示了如何重複使用幾何形狀，同時為每個實例自訂透明度。

## 步驟 6：儲存文件
```java
// Save the modified document
doc.save(dataDir + "WorkingWithTransparency_out.xps");
```
最後，我們將 XPS 檔案寫入磁碟。使用任何 XPS 檢視器開啟產生的檔案，即可看到分層透明度的效果。

## 常見問題與技巧
- **不透明度未顯示？** 請確認使用支援不透明度的刷子（例如 `createSolidColorBrush`）。  
- **變換未套用？** 請確認在將路徑加入文件 **之前** 呼叫 `setRenderTransform`。  
- **效能提示：** 在建立大量相似形狀時，重複使用幾何物件以減少記憶體開銷。

## 常見問答
### Q：我可以將透明度套用於除矩形之外的其他形狀嗎？
A：可以，你可以使用提供的幾何形狀將透明度套用於各種形狀。

### Q：如何控制物件的透明度等級？
A：調整填充的不透明度屬性即可控制透明度等級。

### Q：Aspose.Page 適合用於專業文件製作嗎？
A：絕對適合！Aspose.Page 提供強大的功能以進行專業文件操作。

### Q：我可以將 Aspose.Page 與其他 Java 函式庫整合嗎？
A：可以，Aspose.Page 能與其他 Java 函式庫無縫整合，以擴充功能。

### Q：在哪裡可以找到 Aspose.Page 的其他範例與支援？
A：請前往 [Aspose.Page Java 論壇](https://forum.aspose.com/c/page/39) 取得社群支援，並在此處 [here](https://reference.aspose.com/page/java/) 瀏覽文件。

---

**最後更新：** 2026-01-02  
**測試環境：** Aspose.Page for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}