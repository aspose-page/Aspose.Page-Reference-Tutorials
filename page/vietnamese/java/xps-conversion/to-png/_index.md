---
title: Chuyển đổi XPS sang PNG trong Java
linktitle: Chuyển đổi XPS sang PNG trong Java
second_title: API Java Aspose.Page
description: Dễ dàng chuyển đổi XPS sang PNG trong Java bằng Aspose.Page. Hợp lý hóa các tác vụ tài liệu bằng giải pháp đáng tin cậy và thân thiện với nhà phát triển này.
type: docs
weight: 13
url: /vi/java/xps-conversion/to-png/
---
## Giới thiệu
Trong thế giới phát triển phần mềm năng động, nhu cầu chuyển đổi tài liệu XPS (Đặc tả giấy XML) sang hình ảnh PNG (Đồ họa mạng di động) phát sinh thường xuyên. Để thực hiện nhiệm vụ này một cách liền mạch trong Java, Aspose.Page cung cấp một giải pháp mạnh mẽ. Trong hướng dẫn này, chúng ta sẽ tìm hiểu quy trình chuyển đổi XPS sang PNG bằng Aspose.Page cho Java.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo rằng bạn đã thiết lập các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2.  Aspose.Page dành cho Java: Tải xuống và cài đặt thư viện Aspose.Page. Bạn có thể tìm thấy liên kết tải xuống[đây](https://releases.aspose.com/page/java/).
3. Môi trường phát triển tích hợp (IDE): Chọn một IDE tương thích với Java như IntelliJ IDEA hoặc Eclipse.
## Gói nhập khẩu
Trong dự án Java của bạn, hãy nhập các gói cần thiết để sử dụng các chức năng của Aspose.Page. Thêm các câu lệnh nhập sau vào đầu tệp Java của bạn:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Bước 1: Đặt thư mục tài liệu
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
```
## Bước 2: Tải tài liệu XPS
```java
// Tải tài liệu XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Bước 3: Khởi tạo các tùy chọn
```java
// Khởi tạo đối tượng tùy chọn với các tham số cần thiết.
PngSaveOptions options = new PngSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Bước 4: Tạo thiết bị kết xuất
```java
// Tạo thiết bị kết xuất cho định dạng PDF
ImageDevice device = new ImageDevice();
```
## Bước 5: Lưu và lặp lại
```java
// Lưu tài liệu XPS sang PNG bằng tùy chọn và thiết bị
document.save(device, options);
//Lặp lại qua các phân vùng tài liệu (tài liệu cố định, theo thuật ngữ XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Lặp lại qua các trang phân vùng
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Khởi tạo luồng đầu ra hình ảnh
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoPNG" + "_" + (i + 1) + "_" + (j + 1) + ".png");
        // Viết hình ảnh
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        // Đóng luồng
        imageStream.close();
    }
}
```
Bằng cách làm theo các bước này, bạn có thể dễ dàng chuyển đổi tài liệu XPS thành hình ảnh PNG bằng Aspose.Page cho Java.
## Phần kết luận
Tóm lại, Aspose.Page dành cho Java đơn giản hóa quá trình chuyển đổi XPS sang PNG, cung cấp cho các nhà phát triển một công cụ đáng tin cậy và hiệu quả. Kết hợp thư viện này vào các dự án Java của bạn để hợp lý hóa các tác vụ thao tác tài liệu.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Page cho Java trong các dự án thương mại không?
 Có, Aspose.Page là một sản phẩm thương mại. Bạn có thể tìm thấy thông tin cấp phép[đây](https://purchase.aspose.com/buy).
### Có bản dùng thử miễn phí không?
 Có, bạn có thể khám phá bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Tôi có thể tìm tài liệu về Aspose.Page cho Java ở đâu?
 Tài liệu đầy đủ có sẵn[đây](https://reference.aspose.com/page/java/).
### Làm cách nào để có được giấy phép tạm thời cho mục đích thử nghiệm?
 Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Có diễn đàn cộng đồng nào để thảo luận về Aspose.Page không?
 Có, hãy truy cập diễn đàn cộng đồng[đây](https://forum.aspose.com/c/page/39).