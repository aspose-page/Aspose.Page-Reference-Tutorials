---
title: Thêm thuộc tính đơn giản trong XMP bằng Java
linktitle: Thêm thuộc tính đơn giản trong XMP bằng Java
second_title: API Java Aspose.Page
description: Khám phá tiềm năng của Aspose.Page cho Java với hướng dẫn của chúng tôi về cách thêm thuộc tính vào siêu dữ liệu XMP trong tệp EPS. Nâng cao khả năng xử lý tài liệu một cách dễ dàng!
weight: 14
url: /vi/java/xmp-metadata-manipulation/add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm thuộc tính đơn giản trong XMP bằng Java

## Giới thiệu
Trong bối cảnh xử lý tài liệu ngày càng phát triển, việc quản lý siêu dữ liệu một cách hiệu quả là rất quan trọng. Aspose.Page dành cho Java trao quyền cho các nhà phát triển thao tác dữ liệu Nền tảng siêu dữ liệu mở rộng (XMP) một cách liền mạch. Trong hướng dẫn này, chúng ta sẽ khám phá quy trình thêm các thuộc tính đơn giản vào XMP bằng Java, cung cấp cho bạn hướng dẫn từng bước toàn diện.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Kiến thức cơ bản về lập trình Java.
-  Aspose.Page cho thư viện Java đã được cài đặt. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/page/java/).
- Tệp EPS mẫu chứa siêu dữ liệu. Nếu bạn không có, vui lòng sử dụng tệp "xmp3.eps" được cung cấp.
## Gói nhập khẩu
Đảm bảo bạn nhập các gói cần thiết để khởi động dự án của mình:
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
## Bước 1: Nhận siêu dữ liệu XMP
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo luồng tệp EPS đầu vào
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Nhận siêu dữ liệu XMP. Nếu tệp EPS không chứa siêu dữ liệu XMP, chúng tôi sẽ nhận được một tệp mới chứa đầy các giá trị từ nhận xét siêu dữ liệu PS (%%Creator, %%CreatDate, %%Title, v.v.)
XmpMetadata xmp = document.getXmpMetadata();
```
## Bước 2: Thêm thuộc tính ngày
```java
// Thêm giá trị thuộc tính ngày "xmp:Date1"
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## Bước 3: Thêm thuộc tính số nguyên
```java
// Thêm giá trị thuộc tính số nguyên "xmp:Intg1"
xmp.put("xmp:Intg1", new XmpValue(111));
```
## Bước 4: Thêm thuộc tính kép
```java
// Thêm giá trị thuộc tính kép "xmp:Double1"
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## Bước 5: Thêm thuộc tính chuỗi
```java
// Thêm giá trị thuộc tính chuỗi "xmp:String1"
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## Bước 6: Lưu tài liệu
```java
// Khởi tạo luồng tệp EPS đầu ra
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//Lưu tài liệu với siêu dữ liệu XMP đã thay đổi
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Bước 7: Đóng luồng
```java
// Đóng luồng EPS đầu vào
psStream.close();
```
## Phần kết luận
Aspose.Page dành cho Java đơn giản hóa quá trình thao tác siêu dữ liệu XMP trong các tệp EPS. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng thêm các thuộc tính đơn giản để nâng cao siêu dữ liệu của tài liệu.
## Các câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Page cho Java với các ngôn ngữ lập trình khác không?
Aspose.Page chủ yếu hỗ trợ Java, nhưng cũng có phiên bản dành cho các ngôn ngữ khác như .NET.
### Aspose.Page cho Java có bản dùng thử miễn phí không?
 Có, bạn có thể khám phá các tính năng của Aspose.Page bằng cách dùng thử miễn phí[đây](https://releases.aspose.com/).
### Tôi có thể tìm tài liệu chi tiết về Aspose.Page cho Java ở đâu?
 Tài liệu có sẵn[đây](https://reference.aspose.com/page/java/).
### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page cho Java?
 Có thể lấy được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Tôi có thể mua Aspose.Page cho Java ở đâu?
 Bạn có thể mua sản phẩm[đây](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
