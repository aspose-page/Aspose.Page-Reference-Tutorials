---
date: 2026-03-13
description: Học cách chuyển đổi XPS sang JPEG trong Java với Aspose.Page Java. Hướng
  dẫn từng bước này cho bạn biết cách chuyển đổi XPS sang JPEG một cách hiệu quả bằng
  thư viện Aspose.Page Java.
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: Cách chuyển đổi XPS sang JPEG trong Java bằng Aspose.Page Java
url: /vi/java/xps-conversion/to-jpeg/
weight: 11
---

 sure to keep date unchanged.

Now produce final content with shortcodes at top and bottom.

Let's write.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Chuyển Đổi XPS sang JPEG trong Java bằng Aspose.Page Java

## Giới thiệu về Aspose.Page Java
Trong hướng dẫn này **bạn sẽ học cách chuyển đổi XPS sang JPEG** bằng thư viện **Aspose.Page Java**. Chuyển đổi tệp XPS sang hình ảnh JPEG là nhu cầu phổ biến khi bạn cần hiển thị các trang tài liệu dưới dạng đồ họa raster trong các cổng thông tin web, trình xem trên máy tính để bàn, hoặc đính kèm email. Chúng tôi sẽ đi qua từng dòng mã, giải thích lý do mỗi thiết lập quan trọng, và chia sẻ các mẹo thực tế để bạn có thể tích hợp quy trình chuyển đổi này vào các ứng dụng Java của mình một cách tự tin.

## Câu trả lời nhanh
- **Thư viện nào thực hiện việc chuyển đổi?** Aspose.Page Java  
- **Tôi có thể chọn các trang cụ thể không?** Có – sử dụng `setPageNumbers` trong `JpegSaveOptions`  
- **Tôi có thể kiểm soát chất lượng hình ảnh như thế nào?** Chế độ làm mịn, độ phân giải và các thiết lập chất lượng JPEG  
- **Có cần giấy phép cho môi trường sản xuất không?** Có, cần giấy phép thương mại (có bản dùng thử miễn phí)  
- **Mã có tương thích với Java 8 không?** Hoàn toàn – API hoạt động với Java 8 và các phiên bản mới hơn  

## XPS là gì và Tại sao cần chuyển đổi XPS sang JPEG?
XPS (XML Paper Specification) là định dạng tài liệu bố cục cố định tương tự PDF. Chuyển đổi XPS sang JPEG hữu ích khi bạn cần hình ảnh raster cho ảnh thu nhỏ, đính kèm email, hoặc khi tích hợp với các hệ thống chỉ chấp nhận tệp hình ảnh. JPEG cung cấp cân bằng tốt giữa chất lượng hình ảnh và kích thước tệp, làm cho nó lý tưởng cho các bản xem trước trên web.

## Yêu cầu trước
Trước khi chúng ta bắt đầu với mã, hãy chắc chắn rằng bạn đã có:

- **Môi trường phát triển Java** – JDK 8 hoặc mới hơn đã được cài đặt và cấu hình.  
- **Aspose.Page for Java** – Tải thư viện mới nhất từ trang chính thức [đây](https://releases.aspose.com/page/java/).  
- **Tài liệu XPS mẫu** – Một tệp XPS mà bạn muốn chuyển đổi thành hình ảnh JPEG.  

## Nhập các Gói
Bắt đầu bằng cách nhập các lớp cần thiết vào tệp nguồn Java của bạn:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Bước 1: Khởi tạo Đường dẫn và Tải tài liệu XPS
Đặt thư mục chứa tệp XPS nguồn và tạo một thể hiện `XpsDocument`:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **Mẹo chuyên nghiệp:** Sử dụng `Paths.get()` từ `java.nio.file` để xử lý đường dẫn độc lập với nền tảng.

## Bước 2: Cấu hình tùy chọn lưu JPEG
Xác định cách các hình ảnh JPEG sẽ được render – độ phân giải, làm mịn, và các trang sẽ xuất ra:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` tạo ra đầu ra độ phân giải cao, phù hợp cho việc in ấn.  
- `setPageNumbers` cho phép bạn chọn chỉ các trang cần thiết, tiết kiệm thời gian và bộ nhớ.

## Bước 3: Tạo Thiết bị Kết xuất
`ImageDevice` sẽ ghi lại các trang đã render dưới dạng mảng byte:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## Bước 4: Kết xuất tài liệu XPS sang JPEG
Gọi phương thức `save`, truyền thiết bị và các tùy chọn bạn đã cấu hình:

```java
document.save(device, options);
```

Tại thời điểm này, `device` chứa một mảng hai chiều, mỗi phần tử đại diện cho một trang đã mã hoá JPEG.

## Bước 5: Duyệt qua Kết quả và Ghi các Tập tin
Lặp qua các trang đã render và ghi mỗi mảng byte vào một tệp JPEG riêng:

```java
// Iterate through document partitions (fixed documents, in XPS terms)
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoJPEG" + "_" + (i + 1) + "_" + (j + 1) + ".jpeg");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        //close the stream
        imageStream.close();
    }
}
```

Mỗi tệp sẽ được đặt tên `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg`, giúp dễ dàng xác định tài liệu nguồn và số trang.

## Các trường hợp sử dụng phổ biến
- **Tạo ảnh thu nhỏ** cho hệ thống quản lý tài liệu.  
- **Nhúng bản xem trước trang** trong các ứng dụng web nơi chỉ hỗ trợ định dạng hình ảnh.  
- **Xử lý hàng loạt các kho lưu trữ XPS lớn** thành JPEG để lưu trữ hoặc báo cáo.  

## Các vấn đề thường gặp & Khắc phục
| Triệu chứng | Nguyên nhân khả dĩ | Cách khắc phục |
|------------|--------------------|----------------|
| **Tệp JPEG trống** | Luồng đầu ra không được flush hoặc close đúng cách | Đảm bảo `imageStream.close()` được gọi trong vòng lặp bên trong (như đã minh họa). |
| **Lỗi hết bộ nhớ** trên các tệp XPS lớn | Render toàn bộ các trang cùng lúc tiêu tốn quá nhiều RAM | Xử lý các trang theo lô nhỏ hơn hoặc tăng heap JVM (`-Xmx`). |
| **Thiếu trang** | `setPageNumbers` không bao gồm trang mong muốn | Kiểm tra mảng số trang có khớp với chỉ số thực tế của các trang XPS (đánh số từ 1). |

## Câu hỏi thường gặp

### H: Aspose.Page có phù hợp cho dự án thương mại không?
Đ: Có, Aspose.Page là sản phẩm thương mại với các tùy chọn cấp phép. Xem chi tiết [đây](https://purchase.aspose.com/buy).

### H: Tôi có thể dùng thử Aspose.Page trước khi mua không?
Đ: Có, bạn có thể tải bản dùng thử miễn phí [đây](https://releases.aspose.com/).

### H: Tôi có thể tìm tài liệu Aspose.Page ở đâu?
Đ: Tài liệu có sẵn [đây](https://reference.aspose.com/page/java/).

### H: Làm sao tôi có thể nhận hỗ trợ cho Aspose.Page?
Đ: Truy cập [Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để được cộng đồng hỗ trợ.

### H: Tôi có cần giấy phép tạm thời để thử nghiệm không?
Đ: Có, bạn có thể lấy giấy phép tạm thời [đây](https://purchase.aspose.com/temporary-license/).

## Kết luận
Bạn đã nắm vững **cách chuyển đổi XPS sang JPEG** bằng **Aspose.Page Java**. Bằng cách làm theo hướng dẫn từng bước, bạn có thể tích hợp quy trình chuyển đổi này vào bất kỳ ứng dụng Java nào — dù là công cụ desktop, dịch vụ web, hay tiện ích xử lý hàng loạt. Hãy thoải mái thử nghiệm các độ phân giải, lựa chọn trang và định dạng hình ảnh khác nhau để đáp ứng nhu cầu dự án của bạn.

---

**Cập nhật lần cuối:** 2026-03-13  
**Đã kiểm tra với:** Aspose.Page 24.11 cho Java (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}