---
date: 2025-12-13
description: 學習如何在 Java 的 asp 頁面加入文字、設定字型樣式，以及使用 Aspose.Page 新增 Unicode 文字。請跟隨我們的逐步指南。
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: ASP 頁面加入文字 – Java PostScript 中的 Unicode
url: /zh-hant/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – Unicode 在 Java PostScript 中

## 簡介
如果您需要在 Java PostScript 工作流程中 **asp page add text** 並保留 Unicode 字元，您來對地方了。在本教學中，我們將逐步說明如何加入 Unicode 文字、設定字型樣式，並使用 **Aspose.Page for Java** 儲存結果。完成後，您將了解如何在 Java 中設定字型樣式以及如何在專案中有效地加入 Unicode 文字。

## 快速解答
- **什麼函式庫可以在 Java PostScript 中加入 Unicode 文字？** Aspose.Page for Java.  
- **哪個主要方法用於加入文字？** `doc.addGlyphs(...)` 搭配 `XpsGlyphs` 物件.  
- **是否需要特殊字型來支援 Unicode？** 任意支援所需碼點的 TrueType/OpenType 字型（例如 Arial）.  
- **我可以變更字型樣式嗎？** 可以，使用 `XpsFontStyle`（Regular、Bold、Italic 等）.  
- **在正式環境是否需要授權？** 需要，非試用版必須擁有有效的 Aspose.Page 授權.

## 什麼是 asp page add text？
`asp page add text` 指的是使用 Aspose.Page API 將文字字串插入 PostScript 或 XPS 文件的過程。該 API 抽象化低階的 PostScript 指令，讓您能夠使用像 `XpsGlyphs` 這樣的高階物件。

## 為什麼使用 Aspose.Page 來設定字型樣式 java 並加入 Unicode 文字？
- **完整的 Unicode 支援** – 處理從右至左的文字腳本與複雜字形。  
- **簡易 API** – 單行呼叫即可加入文字並套用樣式。  
- **跨平台** – 可在任何相容 Java 的環境中執行。  
- **無外部相依性** – 不需額外的渲染引擎。

## 先決條件
在開始本教學之前，請確保您已具備以下先決條件：

1. **Java Development Kit (JDK)** – 確保您的機器已安裝 Java。  
2. **Aspose.Page for Java** – 從 [download link](https://releases.aspose.com/page/java/) 下載並安裝 Aspose.Page 函式庫。  
3. **Integrated Development Environment (IDE)** – 選擇您偏好的 Java IDE，例如 IntelliJ IDEA 或 Eclipse。

## 匯入套件
在您的 Java 專案中，匯入 Aspose.Page 所需的套件。將以下程式碼行加入您的程式碼中：

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## 步驟 1：設定專案
在您的 IDE 中建立新的 Java 專案並設定專案結構。確保在專案相依性中加入 Aspose.Page 函式庫。

## 步驟 2：初始化 XPS 文件
首先在專案中初始化一個新的 XPS 文件：

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## 步驟 3：加入 Unicode 文字
現在，使用 Aspose.Page 函式庫將 Unicode 文字加入您的 XPS 文件。請使用以下程式碼片段：

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

此程式碼段會在座標 (400, 200) 處將 Unicode 文字 **"AVAJ rof SPX.esopsA"** 加入 XPS 文件，並使用指定的字型與樣式。請注意 `setBidiLevel(1)` 呼叫會啟用從右至左的渲染，以正確顯示 Unicode。

## 步驟 4：儲存文件
使用以下程式碼儲存產生的 XPS 文件：

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## 結論
恭喜！您已成功使用 Aspose.Page 在 Java PostScript 情境中 **asp page add text** 並設定字型樣式。此方法讓您對 Unicode 渲染與樣式擁有精細的控制，十分適合國際化的報告、發票與圖形。

歡迎在 [documentation](https://reference.aspose.com/page/java/) 中探索 Aspose.Page 的更多功能與特性。

## 常見問題

**Q:** 我可以將 Aspose.Page for Java 與其他程式語言一起使用嗎？  
**A:** Aspose.Page 主要設計給 Java 使用，但 Aspose 也提供其他程式語言的函式庫。

**Q:** 是否提供免費試用？  
**A:** 有，您可以在此取得 Aspose.Page 的免費試用版 [here](https://releases.aspose.com/).

**Q:** 我該到哪裡尋求 Aspose.Page 的支援與討論？  
**A:** 請前往 [Aspose.Page forum](https://forum.aspose.com/c/page/39) 獲得支援與討論。

**Q:** 我如何取得 Aspose.Page 的臨時授權？  
**A:** 您可以在此取得臨時授權 [here](https://purchase.aspose.com/temporary-license/).

**Q:** Aspose.Page 提供哪些字型樣式？  
**A:** Aspose.Page 支援的字型樣式包括 Regular、Bold、Italic 以及 BoldItalic。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2025-12-13  
**測試環境：** Aspose.Page for Java (latest)  
**作者：** Aspose