---
date: 2025-12-03
description: 探索如何使用 Aspose.Page for Java 將檔案儲存為 PostScript 並裁剪形狀。了解如何設定筆畫樣式以及在 Java
  圖形裁剪中套用裁剪區域。
language: zh-hant
linktitle: Save as PostScript – Clipping in Java Page Manipulation
second_title: Aspose.Page Java API
title: 另存為 PostScript – Java 頁面操作中的裁剪
url: /java/page-manipulation/clipping/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 儲存為 PostScript – Java 頁面操作中的裁剪

## 簡介
當您在製作複雜圖形時需要 **儲存為 PostScript**，裁剪就是您最強大的幫手。在 Aspose.Page 進行 Java 頁面操作時，裁剪讓您能夠定義繪圖操作可見的精確區域，從而對最終輸出進行細緻的控制。本教學將帶您了解 **如何裁剪形狀**、**設定筆劃樣式**，以及使用 Aspose.Page for Java 套件 **套用裁剪**，讓您自信地產出精緻的 PostScript 檔案。

## 快速解答
- **「儲存為 PostScript」是什麼意思？**  
  會產生一個 .ps 檔案，將向量圖形以 PostScript 語言儲存，適合列印與高解析度渲染。  
- **哪個程式庫在 Java 中處理裁剪？**  
  Aspose.Page for Java 提供簡易的 `java graphics clipping` API。  
- **執行範例是否需要授權？**  
  測試時可使用臨時授權；正式上線則需商業授權。  
- **我可以變更筆劃外觀嗎？**  
  可以——使用 `set stroke style` 搭配 `BasicStroke` 來自訂寬度、虛線樣式與端點。  
- **程式碼是否相容於 Java 8 以上？**  
  完全相容，範例可在任何 Java 8 或更新的執行環境中執行。

## 什麼是 Aspose.Page 中的「儲存為 PostScript」？
將文件儲存為 PostScript 會把您的繪圖指令轉換成 PostScript 頁面描述語言。產生的 `.ps` 檔案可被印表機、檢視器開啟，或在不失真的情況下轉換為 PDF。

## 為什麼在 Java 圖形中使用裁剪？
裁剪讓您 **套用裁剪區域**，將繪圖限制在特定形狀內——非常適合製作遮罩、複雜版面配置，或聚焦於頁面的特定區域。它同時也能減少檔案大小，避免在可見區域之外執行不必要的繪圖指令。

## 先決條件
在開始之前，請確保您已具備：

- **Aspose.Page for Java** – 從 [Aspose.Page 文件](https://reference.aspose.com/page/java/) 下載。  
- **Java 開發環境** – JDK 8 或更新版本，搭配您慣用的 IDE（IntelliJ、Eclipse 等）。

##件
在您的 Java 專案中匯入必要的類別：

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

這些匯入讓您可以使用形狀定義、顏色處理、筆劃設定，以及 Aspose.Page API 來建立 PostScript 文件。

## 逐步指南

### 步驟 1：設定文件與輸出串流
首先，建立一個 `PsDocument`，並指向將寫入 **PostScript** 檔案的輸出串流。

```java
String dataDir = "Your Document Directory";
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Clipping_outPS.ps");
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

> **專業提示：** 請將 `dataDir` 設為絕對路徑，或使用 `Paths.get(...)` 以取得跨平台的路徑。

### 步驟 2：建立形狀與 **如何裁剪形狀**
現在我們定義要使用的幾何圖形——一個矩形與一個圓形。接著使用圓形 **套用裁剪區域**，使只有矩形在圓形內的部分被繪製。

```java
Shape rectangle = new Rectangle2D.Float(0, 0, 300, 200);
document.setPaint(Color.BLUE);
// Clipping by shape
document.writeGraphicsSave();
document.translate(100, 100);
Shape circle = new Ellipse2D.Float(50, 0, 200, 200);
document.clip(circle);
document.fill(rectangle);
document.writeGraphicsRestore();
```

`writeGraphicsSave()` / `writeGraphicsRestore()` 這對呼叫會保留圖形狀態，確保裁剪僅影響預期的繪圖指令。

### 步驟 3：**設定筆劃樣式** 並繪製輪廓
在填滿裁剪後的矩形後，我們示範 **java graphics clipping**，以自訂的虛線樣式繪製矩形邊框。

```java
document.translate(100, 100);
BasicStroke stroke = new BasicStroke(2, BasicStroke.CAP_BUTT, BasicStroke.JOIN_MITER, 10.0f, new float[]{5.0f}, 0.0f);
document.setStroke(stroke);
document.draw(rectangle);
```

此處，`BasicStroke` 定義了寬度為 2 像素、虛線長度為 5 像素的線條，展示了如何 **設定筆劃樣式** 以獲得更豐富的視覺效果。

### 步驟 4：關閉頁面並 **儲存為 PostScript**
最後，完成頁面並寫入輸出檔案。

```java
document.closePage();
document.save();
```

您的 `Clipping_outPS.ps` 檔案現在包含一個被圓形區域裁剪的藍色矩形，並帶有虛線輪廓——即可列印或進一步轉換。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **找不到檔案** | `dataDir` 路徑不正確 | 使用絕對路徑，或在建立串流前先執行 `new File(dataDir).mkdirs()`。 |
| **裁剪未生效** | 缺少 `writeGraphicsSave()` / `writeGraphicsRestore()` | 確認將裁剪程式碼包在這兩個呼叫之間，以保留狀態。 |
| **筆劃呈實線** | `BasicStroke` 的虛線陣列未設定 | 檢查虛線模式陣列 (`new float[]{5.0f}`) 是否正確傳入。 |

## 常見問答

### Aspose.Page 是否相容於不同的文件格式？
是的，Aspose.Page 支援多種文件格式，提供文件處理任務的多樣性。

### 我可以在商業專案中使用 Aspose.Page for Java 嗎？
當然可以！Aspose.Page 提供商業授權，允許在個人與商業專案中使用。

### 如何取得測試用的臨時授權？
可從 [此處](https://purchase.aspose.com/temporary-license/) 取得測試用的臨時授權。

### 哪裡可以找到更多範例與文件說明？
請參考 [文件說明](https://reference.aspose.com/page/java/) 與 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 取得豐富資源。

### 有免費試用版嗎？
有，您可前往 [此處](https://releases.aspose.com/) 下載 Aspose.Page 的免費試用版。

**其他問答**

**Q:** *「套用裁剪區域」實際上對渲染管線有什麼影響？*  
**A:** 它會指示圖形引擎忽略所有落在定義形狀之外的繪圖指令，等同於對輸出做遮罩。

**Q:** *我可以結合多個裁剪形狀嗎？*  
**A:** 可以——多次呼叫 `document.clip()`，每次都會將目前的裁剪區域與新形狀取交集。

**Q:** *繪完成後可以變更裁剪形狀嗎？*  
**A:** 只能在已保存的圖形狀態內變更。於裁剪前使用 `writeGraphicsSave()`，結束後使用 `writeGraphicsRestore()` 復原。

## 結論
掌握 **儲存為 PostScript**、**如何裁剪形狀**、**設定筆劃樣式** 以及 **套用裁剪區域** 後，您即可以 Aspose.Page 精確控制 Java 圖形的渲染。嘗試不同的幾何圖形、虛線樣式與顏色，發掘向量文件創建的全部潛能。

---

**最後更新：** 2025-12-03  
**測試環境：** Aspose.Page for Java 24.11  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
