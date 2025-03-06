---
title: 使用 Java 在 XMP 中新增元數據
linktitle: 使用 Java 在 XMP 中新增元數據
second_title: Aspose.Page Java API
description: 探索 Aspose.Page for Java 的無縫集成，並了解如何輕鬆地將 XMP 元資料新增至 EPS 檔案。立即提升您的文件管理等級！
weight: 11
url: /zh-hant/java/xmp-metadata-manipulation/add-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Java 在 XMP 中新增元數據

## 介紹
您是否希望透過使用 Java 新增 XMP 資訊來增強文件的元資料？別再猶豫了！本逐步指南將引導您完成使用 Aspose.Page for Java 程式庫將元資料新增至 EPS 檔案的過程。 Aspose.Page 是一個功能強大的工具，可以簡化 Java 應用程式中的文件操作任務。
## 先決條件
在我們深入學習本教程之前，請確保您符合以下先決條件：
- Java 程式設計的基礎知識。
- 安裝了 Java 函式庫的 Aspose.Page。你可以下載它[這裡](https://releases.aspose.com/page/java/).
- 您要修改的 EPS 檔案。
## 導入包
首先，將必要的套件匯入到您的 Java 程式：
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## 第 1 步：取得 XMP 元數據
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//初始化輸入 EPS 檔案流
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
//取得 XMP 元資料。如果 EPS 檔案不包含 XMP 元數據，則會使用 PS 元資料註釋（%%Creator、%%CreateDate、%%Title 等）中的值建立新文件
XmpMetadata xmp = document.getXmpMetadata();
```
確保將“您的文件目錄”替換為儲存文件的實際路徑。

## 步驟 2：檢索 CreatorTool 值
```java
//取得“CreatorTool”值
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## 步驟 3：檢索 CreateDate 值
```java
//取得「建立日期」值
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## 第 4 步：檢索標題值
```java
//取得“標題”值
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## 第 5 步：檢索格式值
```java
//取得“格式”值
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## 第 6 步：檢索創造者價值
```java
//獲得「創造者」價值
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## 第 7 步：檢索 MetadataDate 值
```java
//取得「元資料日期」值
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## 步驟 8：使用新的 XMP 元資料儲存文檔
```java
//初始化輸出 EPS 檔案流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
//使用新的 XMP 元資料儲存文檔
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
最後，不要忘記關閉輸入 EPS 流：
```java
//關閉輸入 EPS 串流
psStream.close();
```
現在，您已經使用 Aspose.Page for Java 成功將元資料新增至您的 EPS 檔案！
## 結論
在本教程中，我們探索了使用 Aspose.Page for Java 函式庫將 XMP 元資料新增至 EPS 檔案的過程。這個強大的工具使您能夠無縫地操作文檔，從而增強您的整體文檔管理體驗。
## 常見問題解答
### Q：Aspose.Page for Java 可以免費使用嗎？
答：Aspose.Page for Java 是商業產品。您可以透過免費試用探索其功能[這裡](https://releases.aspose.com/).
### Q：在哪裡可以找到 Aspose.Page for Java 的文檔？
答：文檔已提供[這裡](https://reference.aspose.com/page/java/).
### Q：如何取得 Aspose.Page for Java 的臨時授權？
答：您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
### Q：Aspose.Page for Java 支援哪些文件格式？
答：Aspose.Page for Java 支援多種格式，包括 EPS、PDF 和 XPS。
### Q：我可以購買 Aspose.Page for Java 嗎？
答：是的，您可以購買 Aspose.Page for Java[這裡](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
