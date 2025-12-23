---
date: 2025-12-23
description: Tìm hiểu cách chuyển đổi XPS sang JPEG trong Java và khám phá cách chuyển
  đổi tệp XPS một cách hiệu quả bằng Aspose.Page. Hướng dẫn toàn diện với các bước
  chi tiết để tích hợp liền mạch.
linktitle: Convert XPS to JPEG in Java
second_title: Aspose.Page Java API
title: Cách chuyển đổi XPS sang JPEG trong Java
url: /vi/java/xps-conversion/to-jpeg/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Chuyển Đổi XPS sang JPEG trong Java

## Giới thiệu
Trong hướng dẫn này, **bạn sẽ học cách chuyển đổi XPS sang JPEG** bằng thư viện mạnh mẽ Aspose.Page cho Java. Việc chuyển đổi các tệp XPS sang định dạng hình ảnh là một yêu cầu phổ biến khi bạn cần hiển thị, xem trước hoặc xử lý tiếp các trang tài liệu trong các ứng dụng web hoặc desktop. Chúng tôi sẽ hướng dẫn từng bước, giải thích lý do mỗi dòng mã quan trọng, và cung cấp các mẹo thực tế để bạn có thể tích hợp logic chuyển đổi vào dự án của mình một cách tự tin.

## Trả lời nhanh
- **Thư viện nào thực hiện việc chuyển đổi?** Aspose.Page for Java  
- **Có thể chọn các trang cụ thể không?** Có – sử dụng `setPageNumbers` trong `JpegSaveOptions`  
- **Có thể kiểm soát chất lượng hình ảnh như thế nào?** Chế độ làm mịn, độ phân giải và các thiết lập chất lượng JPEG  
- **Cần giấy phép cho môi trường sản xuất không?** Có, cần giấy phép thương mại (có bản dùng thử miễn phí)  
- **Mã có tương thích với Java 8 không?** Hoàn toàn – API hoạt động với Java 8 và các phiên bản mới hơn  

## XPS là gì và tại sao chuyển sang JPEG?
XPS (XML Paper Specification) là định dạng tài liệu bố cục cố định tương tự PDF. Chuyển XPS sang JPEG hữu ích khi bạn cần hình ảnh raster cho ảnh thu nhỏ, tệp đính kèm email, hoặc khi tích hợp với các hệ thống chỉ chấp nhận tệp hình ảnh. JPEG cung cấp cân bằng tốt giữa chất lượng hình ảnh và kích thước tệp, rất thích hợp cho việc xem trước trên web.

## Yêu cầu trước
Trước khi bắt đầu với mã, hãy đảm bảo bạn có:

- **Môi trường phát triển Java** – JDK 8 trở lên đã được cài đặt và cấu hình.  
- **Aspose.Page for Java** – Tải thư viện mới nhất từ trang chính thức [tại đây](https://releases.aspose.com/page/java/).  
- **Tài liệu XPS mẫu** – Một tệp XPS mà bạn muốn chuyển thành các hình ảnh JPEG.  

## Nhập gói
Bắt đầu bằng việc nhập các lớp cần thiết vào tệp nguồn Java của bạn:

```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Bước 1: Khởi tạo đường dẫn và tải tài liệu XPS
Đặt thư mục chứa tệp XPS nguồn và tạo một thể hiện `XpsDocument`:

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize XPS input stream
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

> **Mẹo chuyên nghiệp:** Sử dụng `Paths.get()` từ `java.nio.file` để xử lý đường dẫn một cách độc lập với nền tảng.

## Bước 2: Cấu hình tùy chọn lưu JPEG
Xác định cách các hình ảnh JPEG sẽ được render – độ phân giải, làm mịn và các trang sẽ xuất:

```java
// Initialize options object with necessary parameters.
JpegSaveOptions options = new JpegSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);
options.setResolution(300);
options.setPageNumbers(new int[] { 1, 2, 6 });
```

- `setResolution(300)` tạo ra đầu ra độ phân giải cao, phù hợp cho việc in ấn.  
- `setPageNumbers` cho phép bạn chọn chỉ những trang cần thiết, tiết kiệm thời gian và bộ nhớ.

## Bước 3: Tạo thiết bị render
`ImageDevice` sẽ ghi lại các trang đã render dưới dạng mảng byte:

```java
// Create rendering device for PDF format
ImageDevice device = new ImageDevice();
```

## Bước 4: Render tài liệu XPS sang JPEG
Gọi phương thức `save`, truyền thiết bị và các tùy chọn bạn đã cấu hình:

```java
document.save(device, options);
```

Tại thời điểm này, `device` chứa một mảng hai chiều, mỗi phần tử đại diện cho một trang đã được mã hoá dưới dạng JPEG.

## Bước 5: Duyệt kết quả và ghi tệp
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

Mỗi tệp sẽ được đặt tên `XPStoJPEG_<documentIndex>_<pageIndex>.jpeg`, giúp dễ dàng nhận biết tài liệu nguồn và số trang.

## Các vấn đề thường gặp & Khắc phục
| Triệu chứng | Nguyên nhân khả dĩ | Cách khắc phục |
|------------|---------------------|----------------|
| **Tệp JPEG trống** | Luồng đầu ra không được flush hoặc close đúng cách | Đảm bảo gọi `imageStream.close()` bên trong vòng lặp nội bộ (như trong ví dụ). |
| **Lỗi hết bộ nhớ** trên các tệp XPS lớn | Render toàn bộ trang cùng lúc tiêu tốn quá nhiều RAM | Xử lý các trang theo lô nhỏ hơn hoặc tăng heap JVM (`-Xmx`). |
| **Thiếu trang** | `setPageNumbers` không bao gồm trang mong muốn | Kiểm tra mảng số trang có khớp với chỉ số trang thực tế của XPS (đánh số từ 1). |

## Câu hỏi thường gặp

### H: Aspose.Page có phù hợp cho dự án thương mại không?
Đ: Có, Aspose.Page là sản phẩm thương mại với các tùy chọn cấp phép. Xem chi tiết [tại đây](https://purchase.aspose.com/buy).

### H: Tôi có thể dùng thử Aspose.Page trước khi mua không?
Đ: Có, bạn có thể lấy bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### H: Tôi có thể tìm tài liệu Aspose.Page ở đâu?
Đ: Tài liệu có sẵn [tại đây](https://reference.aspose.com/page/java/).

### H: Làm sao tôi có thể nhận hỗ trợ cho Aspose.Page?
Đ: Truy cập [Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để được cộng đồng hỗ trợ.

### H: Tôi có cần giấy phép tạm thời cho việc thử nghiệm không?
Đ: Có, bạn có thể lấy giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

## Kết luận
Bạn đã nắm vững **cách chuyển đổi XPS sang JPEG** bằng Aspose.Page cho Java. Bằng cách làm theo hướng dẫn từng bước, bạn có thể tích hợp quy trình chuyển đổi này vào bất kỳ ứng dụng Java nào — dù là công cụ desktop, dịch vụ web, hay tiện ích xử lý batch. Hãy tự do thử nghiệm các độ phân giải, lựa chọn trang và định dạng hình ảnh khác nhau để phù hợp với nhu cầu dự án của bạn.

---

**Cập nhật lần cuối:** 2025-12-23  
**Kiểm thử với:** Aspose.Page 24.11 for Java (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}