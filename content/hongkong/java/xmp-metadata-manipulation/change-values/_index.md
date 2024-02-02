---
title: 使用 Java 更改 XMP 中的值
linktitle: 使用 Java 更改 XMP 中的值
second_title: Aspose.Page Java API
description: 使用 Aspose.Page for Java 增強 EPS 文件。輕鬆修改 XMP 元資料以獲得客製化的專業內容。 #Java開發
type: docs
weight: 17
url: /zh-hant/java/xmp-metadata-manipulation/change-values/
---
## 介紹
在文件處理和操作領域，Aspose.Page for Java 是一款脫穎而出的強大工具。本教學深入探討使用 Java 和 Aspose.Page 程式庫變更 EPS（封裝 PostScript）文件中的 XMP（可擴充元資料平台）值的過程。透過遵循提供的逐步指南，您將了解如何輕鬆修改元數據，確保您的文件適合您的特定要求。
## 先決條件
在開始本教學之前，請確保您具備以下先決條件：
1. Java 開發環境：確保您的電腦上有一個有效的 Java 開發環境。
2.  Aspose.Page for Java 函式庫：下載並安裝 Aspose.Page for Java 函式庫。就可以找到需要的套件了[這裡](https://releases.aspose.com/page/java/).
## 導入包
首先將所需的套件匯入到您的 Java 專案中。這些套件對於與 EPS 文件互動和操作至關重要。
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
從 EPS 文件中檢索 XMP 元資料。如果 EPS 檔案不包含 XMP 元數據，則會使用 PS 元資料註釋（例如 %%Creator、%%CreateDate 和 %%Title）中的值建立新檔案。
```java
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
//初始化輸入 EPS 檔案流
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
//取得 XMP 元資料。如果 EPS 檔案不包含 XMP 元數據，則會使用 PS 元資料註釋中的值建立一個新文件
XmpMetadata xmp = document.getXmpMetadata();
```
## 第 2 步：更改「修改日期」值
修改 XMP 元資料中的「ModifyDate」值以反映所需的日期。
```java
//更改“修改日期”值
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## 第 3 步：更改「創建者」值
更新 XMP 元資料中的「Creator」值以指定文件的建立者。
```java
//改變「創造者」價值
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## 第 4 步：更改「標題」值
修改 XMP 元資料中的「標題」值以為文件設定適當的標題。
```java
//變更“標題”值
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## 步驟 5：使用變更的 XMP 元資料儲存文檔
將包含更新的 XMP 元資料的文件儲存到新的 EPS 檔案。
```java
//初始化輸出 EPS 檔案流
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//儲存具有變更的 XMP 元資料的文檔
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## 結論
恭喜！您已經成功完成了使用 Aspose.Page for Java 更改 EPS 文件中的 XMP 值的過程。本教學為您提供了修改元資料的知識，確保您的文件無縫地符合您的特定要求。
## 常見問題解答
### Q：修改 XMP 值時如何處理時區注意事項？
利用`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))`以確保時區設定的一致性。
### Q：我可以在一次操作中更改多個 XMP 值嗎？
是的，透過使用`put`方法為每個所需的值，您可以同時修改多個 XMP 值。
### Q：在哪裡可以找到 Aspose.Page for Java 的附加文件？
探索全面的文檔[這裡](https://reference.aspose.com/page/java/).
### Q：Aspose.Page for Java 是否有免費試用版？
是的，您可以免費試用[這裡](https://releases.aspose.com/).
### Q：如何取得 Aspose.Page for Java 的臨時授權？
獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).