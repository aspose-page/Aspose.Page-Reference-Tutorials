---
title: Thay đổi các mục mảng trong XMP bằng Java
linktitle: Thay đổi các mục mảng trong XMP bằng Java
second_title: API Java Aspose.Page
description: Tìm hiểu cách thay đổi các mục mảng trong XMP bằng Aspose.Page cho Java. Sửa đổi siêu dữ liệu dễ dàng với hướng dẫn từng bước của chúng tôi. Nâng cao tài liệu EPS của bạn ngay bây giờ!
weight: 15
url: /vi/java/xmp-metadata-manipulation/change-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thay đổi các mục mảng trong XMP bằng Java

## Giới thiệu
Chào mừng bạn đến với hướng dẫn toàn diện của chúng tôi về cách thay đổi các mục mảng trong XMP bằng Aspose.Page cho Java! Aspose.Page là một thư viện Java mạnh mẽ cho phép bạn làm việc liền mạch với siêu dữ liệu XMP trong các tệp EPS. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình sửa đổi các mục mảng trong siêu dữ liệu XMP, giúp bạn nâng cao và tùy chỉnh tài liệu EPS của mình.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
-  Thư viện Aspose.Page cho Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/page/java/).
## Gói nhập khẩu
Để bắt đầu, hãy nhập các gói cần thiết vào dự án Java của bạn. Đảm bảo bạn có thư viện Aspose.Page trong dự án của mình.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;

```
## Bước 1: Nhận siêu dữ liệu XMP
Đầu tiên, truy xuất siêu dữ liệu XMP từ tệp EPS của bạn. Nếu tệp EPS chưa chứa siêu dữ liệu XMP thì một tệp mới sẽ được tạo với các giá trị từ nhận xét siêu dữ liệu PS như %%Creator, %%CreateDate, %%Title, v.v.
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo luồng tệp EPS đầu vào
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Nhận siêu dữ liệu XMP. Nếu tệp EPS không chứa siêu dữ liệu XMP thì tệp mới sẽ chứa các giá trị từ nhận xét siêu dữ liệu PS.
XmpMetadata xmp = document.getXmpMetadata();
```
## Bước 2: Đặt mục mảng "dc:title"
Bây giờ, hãy đặt mục mảng "dc:title" ở chỉ mục 0 với một giá trị mới.
```java
// Đặt mục mảng "dc:title" theo chỉ mục 0
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```
## Bước 3: Đặt mục mảng "dc:creator"
Tương tự, đặt mục mảng "dc:creator" ở chỉ mục 0 với giá trị Creator mới.
```java
// Đặt mục mảng "dc:creator" theo chỉ mục 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```
## Bước 4: Khởi tạo luồng tệp EPS đầu ra
Chuẩn bị luồng tệp EPS đầu ra nơi tài liệu đã sửa đổi sẽ được lưu.
```java
// Khởi tạo luồng tệp EPS đầu ra
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
## Bước 5: Lưu tài liệu với siêu dữ liệu XMP đã thay đổi
Lưu tài liệu với siêu dữ liệu XMP được cập nhật.
```java
//Lưu tài liệu với siêu dữ liệu XMP đã thay đổi
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách thay đổi các mục mảng trong XMP bằng Aspose.Page cho Java. Hướng dẫn này cung cấp hướng dẫn từng bước, đảm bảo bạn có thể dễ dàng nâng cao tài liệu EPS của mình bằng siêu dữ liệu tùy chỉnh.

## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Page cho Java với các ngôn ngữ lập trình khác không?
Aspose.Page được thiết kế chủ yếu cho Java, nhưng Aspose cung cấp các thư viện tương tự cho các ngôn ngữ khác.
### Tôi có thể tìm tài liệu chi tiết về Aspose.Page cho Java ở đâu?
 Tài liệu có sẵn[đây](https://reference.aspose.com/page/java/).
### Có bản dùng thử miễn phí cho Aspose.Page cho Java không?
 Có, bạn có thể dùng thử miễn phí[đây](https://releases.aspose.com/).
### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page cho Java?
 Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Tôi có thể mua phiên bản đầy đủ của Aspose.Page cho Java ở đâu?
 Bạn có thể mua phiên bản đầy đủ[đây](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
