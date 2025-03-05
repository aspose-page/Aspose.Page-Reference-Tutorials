---
title: Thêm siêu dữ liệu trong XMP bằng Java
linktitle: Thêm siêu dữ liệu trong XMP bằng Java
second_title: API Java Aspose.Page
description: Khám phá khả năng tích hợp liền mạch của Aspose.Page cho Java và tìm hiểu cách thêm siêu dữ liệu XMP vào tệp EPS của bạn một cách dễ dàng. Nâng cao trò chơi quản lý tài liệu của bạn ngay hôm nay!
type: docs
weight: 11
url: /vi/java/xmp-metadata-manipulation/add-metadata/
---
## Giới thiệu
Bạn đang tìm cách nâng cao siêu dữ liệu của tài liệu bằng cách thêm thông tin XMP bằng Java? Đừng tìm đâu xa! Hướng dẫn từng bước này sẽ hướng dẫn bạn quy trình thêm siêu dữ liệu vào tệp EPS bằng thư viện Aspose.Page cho Java. Aspose.Page là một công cụ mạnh mẽ giúp đơn giản hóa các tác vụ thao tác tài liệu trong các ứng dụng Java.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Kiến thức cơ bản về lập trình Java.
-  Aspose.Page cho thư viện Java đã được cài đặt. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/page/java/).
- Tệp EPS mà bạn muốn sửa đổi.
## Gói nhập khẩu
Đầu tiên, nhập các gói cần thiết vào chương trình Java của bạn:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## Bước 1: Nhận siêu dữ liệu XMP
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo luồng tệp EPS đầu vào
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Nhận siêu dữ liệu XMP. Nếu tệp EPS không chứa siêu dữ liệu XMP thì một tệp mới sẽ được tạo bằng cách sử dụng các giá trị từ nhận xét siêu dữ liệu PS (%%Creator, %%CreatDate, %%Title, v.v.)
XmpMetadata xmp = document.getXmpMetadata();
```
Đảm bảo thay thế "Thư mục tài liệu của bạn" bằng đường dẫn thực tế nơi tài liệu của bạn được lưu trữ.

## Bước 2: Truy xuất giá trị CreatorTool
```java
// Nhận giá trị "CreatorTool"
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Bước 3: Truy xuất giá trị CreateDate
```java
// Nhận giá trị "CreatDate"
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Bước 4: Truy xuất giá trị tiêu đề
```java
// Nhận giá trị "Tiêu đề"
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Bước 5: Truy xuất giá trị định dạng
```java
//Nhận giá trị "định dạng"
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Bước 6: Truy xuất Giá trị của Người sáng tạo
```java
// Nhận giá trị "người sáng tạo"
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Bước 7: Truy xuất giá trị ngày siêu dữ liệu
```java
// Nhận giá trị "MetadataDate"
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## Bước 8: Lưu tài liệu với siêu dữ liệu XMP mới
```java
// Khởi tạo luồng tệp EPS đầu ra
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Lưu tài liệu với siêu dữ liệu XMP mới
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Cuối cùng, đừng quên đóng luồng EPS đầu vào:
```java
// Đóng luồng EPS đầu vào
psStream.close();
```
Bây giờ, bạn đã thêm thành công siêu dữ liệu vào tệp EPS của mình bằng Aspose.Page cho Java!
## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá quy trình thêm siêu dữ liệu XMP vào tệp EPS bằng thư viện Aspose.Page cho Java. Công cụ mạnh mẽ này cho phép bạn thao tác tài liệu một cách liền mạch, nâng cao trải nghiệm quản lý tài liệu tổng thể của bạn.
## Câu hỏi thường gặp
### Câu hỏi: Aspose.Page dành cho Java có được sử dụng miễn phí không?
 Đáp: Aspose.Page dành cho Java là một sản phẩm thương mại. Bạn có thể khám phá các tính năng của nó thông qua bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể tìm tài liệu về Aspose.Page cho Java ở đâu?
 A: Tài liệu có sẵn[đây](https://reference.aspose.com/page/java/).
### Câu hỏi: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page cho Java?
 A: Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Câu hỏi: Aspose.Page cho Java hỗ trợ những định dạng tệp nào?
Trả lời: Aspose.Page dành cho Java hỗ trợ nhiều định dạng khác nhau, bao gồm EPS, PDF và XPS.
### Câu hỏi: Tôi có thể mua Aspose.Page cho Java không?
 Trả lời: Có, bạn có thể mua Aspose.Page cho Java[đây](https://purchase.aspose.com/buy).