---
title: 使用 Java 變更 XMP 中的命名值
linktitle: 使用 Java 變更 XMP 中的命名值
second_title: Aspose.Page Java API
description: 探索 Aspose.Page for Java - 透過我們的簡化文件處理逐步指南，輕鬆更改 EPS 檔案中的 XMP 元資料。
weight: 16
url: /zh-hant/java/xmp-metadata-manipulation/change-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 變更 XMP 中的命名值

在文件操作領域，Aspose.Page for Java 是一款功能強大的工具，可讓開發人員無縫地使用 EPS 檔案中的 XMP 元資料。本逐步指南將引導您完成使用 Aspose.Page for Java 變更 XMP 中命名值的過程。在我們深入研究細節之前，讓我們先做一個介紹。
## 介紹
Aspose.Page for Java 是一個強大的 Java 函式庫，可促進 EPS 檔案的操作和處理。在處理這些文件中的 XMP 元資料時，Aspose.Page 為開發人員提供了一套全面的功能。在本教程中，我們將專注於更改 XMP 中的命名值，為希望增強文件處理能力的開發人員提供清晰簡潔的指南。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
1. Java 開發環境：確保您的電腦上設定了 Java 開發環境。
2.  Aspose.Page for Java 函式庫：下載 Aspose.Page for Java 函式庫並將其整合到您的專案中。您可以找到該庫和詳細文檔[這裡](https://reference.aspose.com/page/java/).
3. 範例 EPS 檔：準備好範例 EPS 檔以供實驗。如果您沒有，可以使用提供的名為“xmp4.eps”的範例檔案。
## 導入包
要開始該過程，請在 Java 程式碼中匯入必要的套件。這些套件對於與 Aspose.Page for Java 互動至關重要。在 Java 檔案的開頭包含以下行：
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
現在，讓我們將使用 Aspose.Page for Java 更改 XMP 中命名值的過程分解為多個步驟：
## 第 1 步：初始化輸入 EPS 檔案流
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
        
//初始化輸入 EPS 檔案流
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```
## 第2步：初始化PsDocument
```java
PsDocument document = new PsDocument(psStream);
```
## 第 3 步：取得 XMP 元數據
```java
//取得 XMP 元資料。如果 EPS 檔案不包含 XMP 元數據，我們會得到一個新文件，其中填入 PS 元資料註釋中的值（%%Creator、%%CreateDate、%%Title 等）
XmpMetadata xmp = document.getXmpMetadata();
```
## 第 4 步：在 XMP 中設定新值
```java
//為結構“xmpTPg:MaxPageSize”的命名值“stDim:unit”設定新字串值“Inches”
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```
## 步驟5：初始化輸出EPS檔案流
```java
//初始化輸出 EPS 檔案流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```
## 步驟 6：儲存具有變更的 XMP 元資料的文檔
```java
//儲存具有變更的 XMP 元資料的文檔
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 第 7 步：關閉輸入 EPS 流
```java
//關閉輸入 EPS 串流
psStream.close();
```
本逐步指南確保了使用 Aspose.Page for Java 更改 XMP 中命名值的系統方法。透過執行以下步驟，您可以將此功能無縫整合到您的 Java 應用程式中。
## 結論
總之，Aspose.Page for Java 簡化了在 EPS 檔案中使用 XMP 元資料的過程。本教學為您提供了有效更改 XMP 中命名值的知識，從而增強您的文件處理能力。
## 經常問的問題
### 我可以將 Aspose.Page for Java 與其他程式語言一起使用嗎？
Aspose.Page主要支援Java，但Aspose為各種程式語言提供了類似的函式庫。
### Aspose.Page for Java 是否有免費試用版？
是的，您可以探索 Aspose.Page for Java 的免費試用版[這裡](https://releases.aspose.com/).
### 在哪裡可以找到有關 Aspose.Page for Java 的其他支援和討論？
參觀[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)以獲得社區支持和討論。
### 如何取得 Aspose.Page for Java 的臨時授權？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 哪裡可以購買 Java 版 Aspose.Page？
要購買 Java 版 Aspose.Page，請訪問[購買頁面](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
