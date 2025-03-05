---
title: 使用 Java 在 XMP 中新增簡單屬性
linktitle: 使用 Java 在 XMP 中新增簡單屬性
second_title: Aspose.Page Java API
description: 透過我們為 EPS 檔案中的 XMP 元資料添加屬性的指南來釋放 Aspose.Page for Java 的潛力。輕鬆提昇文件處理能力！
type: docs
weight: 14
url: /zh-hant/java/xmp-metadata-manipulation/add-simple-properties/
---
## 介紹
在不斷發展的文件處理領域，有效管理元資料至關重要。 Aspose.Page for Java 讓開發人員能夠無縫操作可擴充元資料平台 (XMP) 資料。在本教程中，我們將探索使用 Java 為 XMP 添加簡單屬性的過程，為您提供全面的逐步指南。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- Java 程式設計的基礎知識。
- 安裝了 Java 函式庫的 Aspose.Page。你可以下載它[這裡](https://releases.aspose.com/page/java/).
- 包含元資料的範例 EPS 檔案。如果您沒有，請隨意使用提供的“xmp3.eps”檔案。
## 導入包
確保導入必要的套件來啟動您的專案：
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## 第 1 步：取得 XMP 元數據
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//初始化輸入 EPS 檔案流
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
//取得 XMP 元資料。如果 EPS 檔案不包含 XMP 元數據，我們會得到一個新文件，其中填入 PS 元資料註釋中的值（%%Creator、%%CreateDate、%%Title 等）
XmpMetadata xmp = document.getXmpMetadata();
```
## 第2步：新增日期屬性
```java
//新增日期屬性“xmp:Date1”值
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## 第 3 步：新增整數屬性
```java
//新增整數屬性“xmp:Intg1”值
xmp.put("xmp:Intg1", new XmpValue(111));
```
## 第4步：新增雙重屬性
```java
//新增雙屬性“xmp:Double1”值
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## 步驟5：新增字串屬性
```java
//新增字串屬性“xmp:String1”值
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## 第 6 步：儲存文檔
```java
//初始化輸出 EPS 檔案流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//儲存具有變更的 XMP 元資料的文檔
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 第 7 步：關閉流
```java
//關閉輸入 EPS 串流
psStream.close();
```
## 結論
Aspose.Page for Java 簡化了在 EPS 檔案中操作 XMP 元資料的過程。透過遵循此逐步指南，您可以輕鬆新增簡單的屬性來增強文件的元資料。
## 經常問的問題
### 我可以將 Aspose.Page for Java 與其他程式語言一起使用嗎？
Aspose.Page 主要支援 Java，但也有適用於其他語言（例如 .NET）的版本。
### Aspose.Page for Java 可以免費試用嗎？
是的，您可以透過免費試用來探索 Aspose.Page 的功能[這裡](https://releases.aspose.com/).
### 在哪裡可以找到 Aspose.Page for Java 的詳細文件？
文件可用[這裡](https://reference.aspose.com/page/java/).
### 如何取得 Aspose.Page for Java 的臨時授權？
可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### 哪裡可以購買 Java 版 Aspose.Page？
您可以購買該產品[這裡](https://purchase.aspose.com/buy).