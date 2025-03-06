---
title: 使用 Java 從 XMP 取得元數據
linktitle: 使用 Java 從 XMP 取得元數據
second_title: Aspose.Page Java API
description: 釋放 Aspose.Page for Java 的強大功能，輕鬆擷取 XMP 元資料。透過我們的逐步指南提昇文件分析！
weight: 18
url: /zh-hant/java/xmp-metadata-manipulation/get-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 從 XMP 取得元數據

## 介紹
歡迎閱讀我們關於利用 Aspose.Page for Java 從 XMP 檔案中提取元資料的逐步指南。 XMP（可擴展元資料平台）提供了一種在檔案中儲存元資料的標準化方法。本教程重點介紹使用 Java 從 XMP 檢索基本信息，提供對文件詳細信息的見解。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- Java 開發工具包 (JDK)：確保您的電腦上安裝了 Java。
-  Aspose.Page for Java：下載並安裝 Aspose.Page 函式庫，您可以找到它[這裡](https://releases.aspose.com/page/java/).
## 導入包
在您的 Java 專案中，匯入必要的套件：
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## 第 1 步：初始化輸入 EPS 檔案流
首先設定文檔目錄的路徑並初始化輸入 EPS 檔案流。
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## 第 2 步：取得 XMP 元數據
從 EPS 檔案中檢索 XMP 元資料。如果檔案缺少 XMP 元數據，則會使用 PS 元資料註解中的值產生一個新檔案。
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## 步驟3：提取CreatorTool訊息
檢查並列印 XMP 元資料中的“CreatorTool”值。
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## 步驟 4：提取 CreateDate 信息
檢查並列印 XMP 元資料中的“CreateDate”值。
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## 第 5 步：擷取縮圖寬度
如果存在縮圖，則提取並列印第一個縮圖的寬度。
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## 第6步：提取格式信息
檢查並列印 XMP 元資料中的「格式」值。
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## 第7步：取得文檔ID
檢查並列印 XMP 元資料中的「DocumentID」值。
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## 結論
恭喜！您已經成功學習如何使用 Aspose.Page for Java 來擷取 XMP 元資料。本指南提供了該過程的全面概述，確保您可以有效地從文件中檢索重要資訊。
## 經常問的問題
### 我可以將 Aspose.Page for Java 與其他程式語言一起使用嗎？
是的，Aspose.Page 支援多種語言，包括 Java、.NET 等。檢查[文件](https://reference.aspose.com/page/java/)了解詳情。
### Aspose.Page for Java 可以免費試用嗎？
是的，您可以免費試用[這裡](https://releases.aspose.com/).
### 在哪裡可以找到對 Aspose.Page for Java 的支援？
參觀[Aspose.Page 論壇](https://forum.aspose.com/c/page/39)以獲得社區支持。
### 如何取得 Aspose.Page for Java 的臨時授權？
您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### Aspose.Page for Java 是否有其他資源？
探索完整[文件](https://reference.aspose.com/page/java/)並下載庫[這裡](https://releases.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
