---
date: 2025-12-17
description: 學習如何在 Java PostScript 中使用 Aspose.Page 添加 Unicode 文字——一步一步的指南，教您輕鬆添加 Unicode
  字串。
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: 如何在 Java PostScript 中使用 Aspose.Page 添加 Unicode 文本
url: /zh-hant/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java PostScript 中使用 Aspose.Page 添加 Unicode 文字

## 介紹
如果你想了解 **如何在 Java‑based PostScript（或 XPS）工作流程中加入 Unicode** 字元，這裡正是你需要的地方。在本教學中，我們會一步步說明如何使用 Aspose.Page for Java 套件將 Unicode 字串嵌入。完成本指南後，你就能直接在 PostScript 輸出中插入任何語言的文字——阿拉伯文、中文、表情符號，隨你挑選。

## 快速回答
- **需要哪個套件？** Aspose.Page for Java  
- **可以加入從右至左的文字嗎？** 可以，請依照程式碼設定 Bidi 等級  
- **開發階段需要授權嗎？** 測試可使用免費試用版；正式上線需購買商業授權  
- **推薦使用哪種 IDE？** 任何 Java IDE（IntelliJ IDEA、Eclipse、NetBeans）皆可  
- **程式碼是否跨平台？** 絕對支援——可在 Windows、macOS 或 Linux 上執行

## 在 PostScript 中「如何加入 Unicode」是什麼意思？
加入 Unicode 代表插入超出基本 ASCII 範圍的字元（即 Unicode 代碼點）。Aspose.Page 會抽象化底層編碼細節，讓你只需關注文字內容與視覺位置。

## 為什麼選擇 Aspose.Page 處理 Unicode 文字？
- **完整的 Unicode 支援** – 能處理複雜腳本、連字與從右至左語系。  
- **無需外部相依** – 不必手動管理字型檔，API 直接使用系統字型。  
- **簡易的 API** – 只需幾個方法呼叫，即可呈現多語言文字。

## 前置作業
在開始之前，請先準備好以下項目：

1. **Java Development Kit (JDK)** – 任意近期版本（8 以上）。  
2. **Aspose.Page for Java** – 從 [download link](https://releases.aspose.com/page/java/) 下載並安裝。  
3. **你慣用的 IDE** – IntelliJ IDEA、Eclipse，或其他任何 Java IDE。

## 匯入套件
在 Java 原始檔中加入必要的 Aspose.Page 類別：

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## 步驟 1：建立專案
建立新的 Java 專案，將 Aspose.Page JAR 加入專案的建置路徑，並建立一個資料夾用來存放產生的 XPS 檔案。此資料夾稍後會以 `dataDir` 變數引用。

## 步驟 2：初始化 XPS 文件
建立一個空的 XPS 文件，作為後續內容的容器：

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## 步驟 3：加入 Unicode 文字
現在正式加入 Unicode 字串。以下範例寫入反向的字串 “AVAJ rof SPX.esopsA”，此字串僅含 ASCII，但你可以替換成任何 Unicode 文字（例如阿拉伯文 “مرحبا” 或中文 “你好”）。

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **小技巧：** 若要正確呈現從右至左的語系，請設定 `glyphs.setBidiLevel(1);`。左至右語系則可省略此行。

## 步驟 4：儲存文件
將 XPS 檔寫入磁碟：

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

執行程式後，使用任意 XPS 檢視器開啟產生的 `AddEncodingText_out.xps`，即可看到在指定座標呈現的 Unicode 文字。

## 常見問題與解決方案
| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 文字顯示為方框 | 找不到字型或字型不支援該字元 | 使用包含所需字形的字型（例如 “Arial Unicode MS”） |
| 從右至左文字顯示為左至右 | 未設定 Bidi 等級 | 呼叫 `glyphs.setBidiLevel(1);` |
| 檔案未儲存 | `dataDir` 路徑無效或缺乏寫入權限 | 確認資料夾已建立且程式有寫入權限 |

## 常見問答
### 我可以在其他程式語言中使用 Aspose.Page for Java 嗎？
Aspose.Page 主要針對 Java 設計，但 Aspose 亦提供其他程式語言的套件。

### 有免費試用版嗎？
有，請前往 [此處](https://releases.aspose.com/) 取得 Aspose.Page 的免費試用版。

### 哪裡可以找到 Aspose.Page 的支援與討論？
請造訪 [Aspose.Page 論壇](https://forum.aspose.com/c/page/39) 取得支援與討論。

### 如何取得 Aspose.Page 的臨時授權？
可在 [此處](https://purchase.aspose.com/temporary-license/) 申請臨時授權。

### Aspose.Page 支援哪些字型樣式？
Aspose.Page 支援 Regular、Bold、Italic 與 BoldItalic 等字型樣式。

## 結論
現在你已掌握 **如何在 Java PostScript（XPS）文件中使用 Aspose.Page 添加 Unicode 文字**。此功能讓多語言報表、國際化發票以及任何需要非 ASCII 字元的情境變得輕鬆。歡迎探索更多功能，如文字旋轉、裁切路徑或嵌入自訂字型——相關細節請參考官方 [documentation](https://reference.aspose.com/page/java/)。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2025-12-17  
**測試環境：** Aspose.Page for Java 23.12（撰寫時的最新版本）  
**作者：** Aspose  

---