---
date: 2026-03-08
description: Tìm hiểu cách chuyển đổi XPS sang BMP trong Java và thiết lập độ phân
  giải BMP bằng thư viện chuyển đổi hình ảnh Aspose.Page cho Java. Hướng dẫn này bao
  gồm cách xuất ra chất lượng cao và các mẹo tiết kiệm bộ nhớ.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Chuyển đổi XPS sang BMP trong Java – Đặt độ phân giải cho đầu ra chất lượng
  cao
url: /vi/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi XPS sang BMP trong Java

## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước về cách **chuyển đổi XPS sang BMP** trong Java và thiết lập độ phân giải để đạt chất lượng hình ảnh tối ưu bằng Aspose.Page. Dù bạn đang xây dựng quy trình in ấn, tạo ảnh thu nhỏ, hay cần đồ họa độ phân giải cao, việc kiểm soát DPI mang lại sự linh hoạt để đáp ứng mọi yêu cầu.

## Câu trả lời nhanh
- **Thư viện nào nên sử dụng?** Aspose.Page for Java là thư viện **java image conversion library** hoàn chỉnh nhất cho XPS → BMP.  
- **Tôi có thể kiểm soát chất lượng ảnh không?** Có – sử dụng `BmpSaveOptions` để **đặt độ phân giải BMP** và chế độ làm mịn.  
- **Làm sao tránh OutOfMemoryError Java khi xử lý các tệp XPS lớn?** Render các trang theo phân đoạn hoặc tăng bộ nhớ heap của JVM (`-Xmx`).  
- **Có cần chỉ chuyển đổi các trang cụ thể không?** Chắc chắn, `options.setPageNumbers()` cho phép bạn chọn các trang mong muốn.  
- **Các phiên bản Java nào được hỗ trợ?** Tất cả các phiên bản Java hiện đại (8 trở lên) hoạt động mượt mà.

## Mục đích của việc thiết lập độ phân giải là gì?
Độ phân giải xác định số điểm ảnh trên mỗi inch (DPI) trong ảnh BMP được tạo ra. DPI cao hơn mang lại hình ảnh sắc nét hơn, điều này rất quan trọng đối với việc in ấn hoặc công việc đồ họa chi tiết. Điều chỉnh độ phân giải cho phép bạn kiểm soát hoàn toàn chất lượng đầu ra của quy trình **convert xps to bmp**.

## Tại sao nên sử dụng Aspose.Page để chuyển đổi XPS → BMP?
- **Độ trung thực cao** – giữ nguyên chất lượng vector của XPS gốc.  
- **Kiểm soát chi tiết** – bạn có thể đặt DPI, chế độ làm mịn, và thậm chí chọn các trang cụ thể để chuyển đổi.  
- **Không phụ thuộc bên ngoài** – thuần Java, không cần thư viện native.  
- **Mở rộng** – hoạt động tốt với tài liệu một trang cũng như các tệp XPS đa trang lớn.  

## Yêu cầu trước
Trước khi bắt đầu quá trình chuyển đổi, hãy đảm bảo bạn đã chuẩn bị các yêu cầu sau:
- **Môi trường phát triển Java** – Java 8 hoặc mới hơn đã được cài đặt trên máy của bạn.  
- **Thư viện Aspose.Page for Java** – Tải xuống và đưa thư viện Aspose.Page for Java vào dự án của bạn. Bạn có thể tìm thư viện [tại đây](https://releases.aspose.com/page/java/).  
- **Tệp XPS mẫu** – Chuẩn bị một tài liệu XPS mẫu mà bạn muốn chuyển đổi sang BMP.

## Nhập khẩu các gói
Bao gồm các gói Aspose.Page cần thiết trong mã Java của bạn:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Cách thiết lập độ phân giải cho chuyển đổi XPS sang BMP
Dưới đây là hướng dẫn ngắn gọn, có đánh số, cho thấy chính xác nơi và cách thiết lập độ phân giải, cũng như cách **chuyển đổi các trang cụ thể**.

### Bước 1: Tải tài liệu XPS
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Load XPS document
XpsDocument document = new XpsDocument(dataDir + "input.xps");
```

### Bước 2: Khởi tạo tùy chọn (Độ phân giải & Lựa chọn trang)
```java
// Initialize options object with necessary parameters.
BmpSaveOptions options = new BmpSaveOptions();
options.setSmoothingMode(SmoothingMode.HighQuality);

// Primary setting – this is the **how to set resolution** part.
options.setResolution(300);               // 300 DPI for high‑quality output

// Optional: convert specific pages only (e.g., pages 1, 2, and 6)
options.setPageNumbers(new int[]{1, 2, 6});
```

### Bước 3: Tạo thiết bị render
```java
// Create rendering device for BMP format
ImageDevice device = new ImageDevice();
```

### Bước 4: Lưu tài liệu bằng các tùy chọn
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Bước 5: Duyệt qua các ảnh đã render và ghi file
```java
// Iterate through document partitions
for (int i = 0; i < device.getResult().length; i++) {
    // Iterate through partition pages
    for (int j = 0; j < device.getResult()[i].length; j++) {
        // Initialize image output stream
        FileOutputStream imageStream = new FileOutputStream(dataDir + "XPStoBMP" + "_" + (i + 1) + "_" + (j + 1) + ".bmp");
        // Write image
        imageStream.write(device.getResult()[i][j], 0, device.getResult()[i][j].length);
        imageStream.close();
    }
}
```

Lặp lại các bước này cho bất kỳ tùy chỉnh hoặc sửa đổi bổ sung nào bạn có thể cần trong quá trình chuyển đổi.

## Cách tránh OutOfMemoryError Java khi chuyển đổi các tệp XPS lớn
- **Xử lý theo phân đoạn** – Ví dụ đã render tài liệu theo phân đoạn (`device.getResult()`), giúp giảm áp lực bộ nhớ.  
- **Tăng bộ nhớ heap của JVM** – Sử dụng tham số `-Xmx` (ví dụ: `-Xmx2g`) để cấp phát thêm bộ nhớ cho các tài liệu lớn.  
- **Giải phóng tài nguyên** – Gọi `document.close()` khi hoàn thành để giải phóng tài nguyên native.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Đầu ra BMP chất lượng thấp** | Kiểm tra `options.setResolution()` đã được đặt giá trị ≥ 300 DPI. |
| **Chỉ một phần tài liệu được chuyển đổi** | Đảm bảo `options.setPageNumbers()` bao gồm tất cả các chỉ số trang mong muốn. |
| **OutOfMemoryError trên các tệp XPS lớn** | Xử lý tài liệu theo các phân đoạn nhỏ hơn hoặc tăng kích thước heap JVM (`-Xmx`). |
| **Không tìm thấy tệp** | Kiểm tra lại đường dẫn `dataDir` và chắc chắn tệp XPS đầu vào tồn tại. |

## Câu hỏi thường gặp
### Q: Tôi có thể tùy chỉnh độ phân giải của ảnh BMP không?
A: Có, bạn có thể điều chỉnh độ phân giải bằng cách thay đổi tham số `options.setResolution()` trong mã.

### Q: Aspose.Page có tương thích với các phiên bản Java khác nhau không?
A: Có, Aspose.Page hỗ trợ nhiều phiên bản Java. Đảm bảo bạn đã cài đặt phiên bản tương thích.

### Q: Làm sao tôi có thể chuyển đổi các tệp XPS từ một phạm vi trang cụ thể?
A: Sử dụng phương thức `options.setPageNumbers()` để chỉ định các số trang bạn muốn chuyển đổi.

### Q: Có các định dạng đầu ra khác được Aspose.Page hỗ trợ không?
A: Có, Aspose.Page hỗ trợ nhiều định dạng đầu ra khác nhau. Tham khảo tài liệu để biết danh sách đầy đủ.

### Q: Tôi có thể tìm thêm trợ giúp hoặc hỗ trợ ở đâu?
A: Truy cập [Aspose.Page Forum](https://forum.aspose.com/c/page/39) để nhận hỗ trợ cộng đồng và thảo luận.

---

**Cập nhật lần cuối:** 2026-03-08  
**Kiểm tra với:** Aspose.Page for Java 24.12  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}