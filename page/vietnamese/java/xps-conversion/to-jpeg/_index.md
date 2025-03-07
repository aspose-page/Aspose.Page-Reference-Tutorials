---
title: Chuyển đổi XPS sang JPEG trong Java
linktitle: Chuyển đổi XPS sang JPEG trong Java
second_title: API Java Aspose.Page
description: Tìm hiểu cách chuyển đổi XPS sang JPEG trong Java bằng Aspose.Page. Hướng dẫn toàn diện với hướng dẫn từng bước để tích hợp liền mạch.
weight: 11
url: /vi/java/xps-conversion/to-jpeg/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi XPS sang JPEG trong Java

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách chuyển đổi tệp XPS (Đặc tả giấy XML) thành hình ảnh JPEG bằng Aspose.Page cho Java. Aspose.Page là một thư viện Java mạnh mẽ cho phép các nhà phát triển làm việc liền mạch với XPS và các định dạng tài liệu khác. Hướng dẫn từng bước này sẽ giúp bạn hiểu quy trình và triển khai nó trong các ứng dụng Java của bạn.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Môi trường phát triển Java: Đảm bảo bạn đã thiết lập môi trường phát triển Java trên máy của mình.
-  Aspose.Page for Java Library: Tải xuống và cài đặt thư viện Aspose.Page cho Java. Bạn có thể tìm thấy thư viện[đây](https://releases.aspose.com/page/java/).
- Tài liệu XPS mẫu: Có một tài liệu XPS mẫu mà bạn muốn chuyển đổi sang JPEG.
## Gói nhập khẩu
Bắt đầu bằng cách nhập các gói cần thiết vào lớp Java của bạn:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```
## Bước 1: Khởi tạo đường dẫn và tài liệu XPS
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Khởi tạo luồng đầu vào XPS
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```
## Bước 2: Đặt tùy chọn JpegSave
```java
// Khởi tạo đối tượng tùy chọn với các tham số cần thiết.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```
## Bước 3: Tạo thiết bị kết xuất
```java
// Tạo thiết bị kết xuất cho định dạng PDF
ImageDevice device = new ImageDevice();
```
## Bước 4: Lưu XPS dưới dạng JPEG
```java
document.save(device, options);
```
## Bước 5: Lặp lại và lưu các trang JPEG
```java
//Lặp lại qua các phân vùng tài liệu (tài liệu cố định, theo thuật ngữ XPS)
for (int i = 0; i < device.getResult().length; i++) {
    // Lặp lại qua các trang phân vùng
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Khởi tạo luồng đầu ra hình ảnh
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Viết hình ảnh
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //đóng luồng
        imageStream.close();
    }
}
```
Chuỗi bước này sẽ chuyển đổi hiệu quả tài liệu XPS của bạn sang hình ảnh JPEG, mỗi tài liệu được lưu riêng biệt.
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách chuyển đổi XPS sang JPEG trong Java bằng Aspose.Page. Quá trình này rất có giá trị đối với các nhà phát triển làm việc với việc chuyển đổi tài liệu trong các ứng dụng Java.
## Các câu hỏi thường gặp

### Câu hỏi: Aspose.Page có phù hợp với các dự án thương mại không?
 Trả lời: Có, Aspose.Page là một sản phẩm thương mại có sẵn các tùy chọn cấp phép. Kiểm tra[đây](https://purchase.aspose.com/buy) để biết chi tiết.
### Hỏi: Tôi có thể dùng thử Aspose.Page trước khi mua không?
 Đ: Có, bạn có thể dùng thử miễn phí[đây](https://releases.aspose.com/).
### Câu hỏi: Tôi có thể tìm tài liệu Aspose.Page ở đâu?
 A: Tài liệu có sẵn[đây](https://reference.aspose.com/page/java/).
### Câu hỏi: Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Page?
 Đáp: Hãy ghé thăm[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để hỗ trợ dựa vào cộng đồng.
### Hỏi: Tôi có cần giấy phép tạm thời để thử nghiệm không?
 A: Có, bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
