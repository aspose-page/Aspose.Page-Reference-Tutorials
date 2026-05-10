---
date: 2026-02-20
description: 學習如何使用 Aspose.Page for Java 設定文字顏色、變更字型大小、產生 PostScript 檔案、填色與描邊文字，並在建立
  PostScript 文件時使用自訂字型。
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: 在 Java 中使用 Aspose.Page 設定文字顏色 – 文字操作指南
url: /zh-hant/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.Page 設定文字顏色 Java – 文字操作指南

## 介紹
歡迎閱讀我們的逐步指南，說明在使用 Aspose.Page for Java 處理 PostScript 檔案時，如何 **set text color java**。Aspose.Page for Java 是一個功能強大的函式庫，讓開發人員能 **create postscript document** 檔案、操作字型，並精確地設定文字樣式。在本教學中，您將學會如何新增文字、變更其顏色、**change font size java**，甚至 **apply fill and stroke text**，以獲得精緻的效果。

## 快速解答
- **什麼函式庫可以讓我在 Java 中設定文字顏色？** Aspose.Page for Java.  
- **我可以使用系統字型和自訂字型嗎？** 可以，兩者皆受支援，且您可以輕鬆 **use custom fonts java**。  
- **如何變更文字大小？** 在建立 `Font` 或 `DrFont` 時指定字型大小即可。  
- **是否可以同時描邊與填充文字？** 當然可以 – 使用 `fillAndStrokeText`。  
- **本教學產生的輸出格式為何？** 為 PostScript（`.ps`）文件，您可以程式化 **generate postscript file**。

## 什麼是「set text color java」？
在 Java 中設定文字顏色是指定 `Color` 物件，讓渲染引擎（此處為 Aspose.Page）在頁面上繪製字元時使用。此操作對於建立視覺上有區別的文件至關重要，尤其在需要程式化 **generate postscript file** 時。

## 為何使用 Aspose.Page for Java？
- **完整控制** PostScript 產生過程，無需本機解譯器。  
- **支援系統字型與外部字型**，讓您嵌入任何所需的排版。  
- **簡易 API** 以填充、描邊以及 **fill and stroke text**，提供樣式上的彈性。  
- **跨平台** 相容性 – 一次編寫，於任何支援 Java 的環境執行。  

## 前置條件
在深入之前，請確保您已具備：

- 具備 Java 程式設計的基礎知識。  
- 已安裝 Aspose.Page for Java 函式庫。您可從 [Aspose.Page for Java download page](https://releases.aspose.com/page/java/) 下載。  
- 必要的字型已放置於指定資料夾。更多細節請參閱 [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/)。  

## 匯入套件
在您的 Java 專案中，匯入 Aspose.Page for Java 所需的套件：

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```

## 步驟 1：設定文件
首先，我們建立一個新的 **PostScript document**，並設定輸出選項。

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## 如何使用系統字型設定文字顏色 Java
現在示範如何使用系統提供的字型進行 **set text color java**。

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **提示：** 若未傳入 `Color` 參數，`fillText` 方法會自動使用目前的顏色，預設為黑色。

## 使用自訂字型與變更文字大小
您也可以 **change font size java**，並使用儲存在字型資料夾中的自訂字型。

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## 文字描邊（Stroke） – 套用描邊文字
文字描邊可產生清晰的輪廓。此處我們使用 `BasicStroke` **apply stroke text**。

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## 使用自訂字型的文字描邊
相同的技巧亦適用於自訂字型。

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## 步驟 6：儲存文件
最後，關閉頁面並將檔案寫入磁碟。

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## 為何這很重要
能夠 **set text color java** 並將填充與描邊結合，讓您對最終的 PostScript 輸出擁有完整的藝術控制。無論是產生發票、證書或自訂圖形，具備 **create postscript document** 檔案的精確樣式，皆可減少在圖形編輯器中後製的需求。

## 常見問題與解決方案
| 問題 | 解決方案 |
|-------|----------|
| **找不到字型** | 確保字型檔案放置於 `necessary_fonts`，且透過 `options.setAdditionalFontsFolders` 正確加入資料夾路徑。 |
| **顏色未套用** | 確認您呼叫的 `fillText` 或 `outlineText` 重載版本包含 `Color` 參數。 |
| **描邊過細** | 增加 `BasicStroke` 的寬度（例如 `new BasicStroke(3)`）。 |
| **文件無法開啟** | 確認產生的 `.ps` 檔案已使用正確的副檔名，且您的檢視器支援 PostScript。 |

## 常見問答

**Q:** 我可以在 Aspose.Page for Java 中使用自訂字型嗎？  
A: 可以，您可透過在 `DrFont` 類別中指定字型名稱與大小來 **use custom fonts java**。

**Q:** 如何變更文字的顏色？  
A: 您可在填充或描邊文字時使用 `Color` 類別設定所需的顏色。

**Q:** 是否可以在 PostScript 文件中加入多頁？  
A: 當然可以！只要重複文件建立與儲存的步驟，即可產生多頁。

**Q:** `ExternalFontCache` 類別的用途是什麼？  
A: `ExternalFontCache` 用於取得自訂字型，確保其可供文字操作使用。

**Q:** 我可以為描邊文字套用不同的描邊嗎？  
A: 可以，您可分別使用 `Stroke` 類別與 `Color` 類別自訂描邊的寬度與顏色。

## 結論
恭喜！您現在已了解如何使用 Aspose.Page for Java **set text color java**、**change font size java**、**apply fill and stroke text**，以及 **create postscript document** 檔案。請嘗試不同的字型、顏色與描邊樣式，以產生專業外觀的 PostScript 輸出。

---

**最後更新：** 2026-02-20  
**測試環境：** Aspose.Page for Java 23.12 (latest)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}