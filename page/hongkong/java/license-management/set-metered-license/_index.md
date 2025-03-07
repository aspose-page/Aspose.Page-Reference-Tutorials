---
title: 與 Aspose.Page Java 輕鬆整合計量許可證
linktitle: 在 Java 中設定計量許可證
second_title: Aspose.Page Java API
description: 探索 Aspose.Page 與 Java 的無縫整合。輕鬆設定計量許可證並增強您的文件處理能力。
weight: 10
url: /zh-hant/java/license-management/set-metered-license/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 與 Aspose.Page Java 輕鬆整合計量許可證

## 介紹
歡迎閱讀我們有關使用 Aspose.Page 在 Java 中設定計量許可證的綜合指南。如果您希望增強文件處理能力並確保與 Aspose.Page 無縫集成，那麼您來對地方了。在本教程中，我們將引導您完成整個過程，將每個步驟分解為易於理解的區塊。
## 先決條件
在深入學習本教程之前，請確保您具備以下先決條件：
- Java 程式設計的基礎知識。
-  Aspose.Page 庫已安裝。您可以從以下位置下載：[這裡](https://releases.aspose.com/page/java/).
- 計量公鑰和私鑰，您可以透過您的 Aspose 帳戶取得。
## 導入包
讓我們先導入 Java 程式所需的套件。確保您已將 Aspose.Page 庫整合到您的專案中。
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## 步驟1：初始化文件和圖像格式
第一步是設定文件並定義所需的圖像格式。
```java
//設定計量公鑰和私鑰
com.aspose.page.Metered metered = new com.aspose.page.Metered();
//存取 setMeteredKey 屬性並將公鑰和私鑰作為參數傳遞
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
//文檔目錄的路徑。
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## 步驟 2： 初始化 PostScript 輸入流
在此步驟中，我們初始化 PostScript 輸入流以進行處理。
```java
//初始化 PostScript 輸入流
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## 步驟3：檢查文件許可證
在繼續之前，驗證該文件是否獲得適當許可至關重要。
```java
//檢查文件是否已獲得許可
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## 第四步：初始化選項和影像設備
現在，讓我們使用預設參數初始化選項和圖像設備。
```java
//使用預設參數初始化選項物件。
ImageSaveOptions options = new ImageSaveOptions();
//使用預設參數初始化 ImageDevice 物件。
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## 步驟 5：將 EPS 檔案另存為映像
使用定義的選項和裝置將 EPS 檔案另存為影像。
```java
//將 EPS 檔案另存為映像
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## 第 6 步：取得並儲存圖像位元組
檢索圖像位元組並將其保存到文件中。
```java
//取得圖像位元組。一頁一個位元組數組。在我們的例子中，我們有一頁。
byte[][] imagesBytes = device.getImagesBytes();
//將圖像位元組儲存到文件
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## 結論
恭喜！您已使用 Aspose.Page 在 Java 中成功設定了計量許可證。本教程提供了逐步指南，以確保整合過程順利進行。
## 常見問題解答
### Q：如何取得計量公鑰和私鑰？
您可以透過您的 Aspose 帳戶取得這些金鑰。
### Q：Aspose.Page 庫是免費的嗎？
 Aspose.Page 提供免費試用版和付費版本。訪問[這裡](https://releases.aspose.com/)免費試用。
### Q：我可以將 Aspose.Page 用於商業項目嗎？
是的，Aspose.Page 提供商業許可。您可以購買它們[這裡](https://purchase.aspose.com/buy).
### Q：在哪裡可以找到其他文件？
參考文檔[這裡](https://reference.aspose.com/page/java/).
### Q：如何獲得臨時許可證？
可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
