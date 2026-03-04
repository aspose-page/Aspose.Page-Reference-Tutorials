---
date: 2025-12-21
description: Tìm hiểu cách đặt độ phân giải khi chuyển đổi XPS sang BMP trong Java
  bằng Aspose.Page. Hướng dẫn chuyển đổi hình ảnh Java này đảm bảo kết quả chất lượng
  cao.
linktitle: Convert XPS to BMP in Java
second_title: Aspose.Page Java API
title: Cách đặt độ phân giải khi chuyển đổi XPS sang BMP trong Java
url: /vi/java/xps-conversion/to-bmp/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi XPS sang BMP trong Java

## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước về **cách đặt độ phân giải** khi chuyển đổi các tệp XPS (XML Paper Specification) sang định dạng BMP (Bitmap) trong Java bằng Aspose.Page. Aspose.Page cho Java là một thư viện mạnh mẽ cung cấp các tính năng toàn diện để làm việc với tài liệu XPS. Trong tutorial này, chúng tôi sẽ hướng dẫn bạn quy trình chuyển đổi các tệp XPS sang hình ảnh BMP một cách dễ dàng.

## Câu trả lời nhanh
- **Thư viện nào nên sử dụng?** Aspose.Page cho Java cung cấp các tính năng chuyển đổi XPS → BMP hoàn chỉnh nhất.  
- **Tôi có thể kiểm soát chất lượng hình ảnh không?** Có – sử dụng `BmpSaveOptions` để đặt độ phân giải và chế độ làm mịn.  
- **Tôi có cần chỉ chuyển đổi các trang cụ thể không?** Chắc chắn, `options.setPageNumbers()` cho phép bạn chọn các trang cụ thể.  
- **Đây có phải là chuyển đổi hình ảnh Java thực sự không?** API sẽ render các trang XPS trực tiếp thành dữ liệu bitmap, vì vậy không cần định dạng trung gian.  
- **Phiên bản Java nào được hỗ trợ?** Tất cả các phiên bản Java hiện đại (8 trở lên) đều tương thích.

## Mục đích của việc đặt độ phân giải là gì?
Độ phân giải xác định số điểm trên mỗi inch (DPI) trong hình ảnh BMP được tạo ra. DPI cao hơn tạo ra hình ảnh sắc nét hơn, điều này rất quan trọng cho việc in ấn hoặc công việc đồ họa chi tiết. Việc điều chỉnh độ phân giải cho phép bạn kiểm soát hoàn toàn chất lượng đầu ra của quy trình **java convert xps** của mình.

## Tại sao nên sử dụng Aspose.Page cho việc chuyển đổi XPS → BMP?
- **Độ trung thực cao** – giữ nguyên chất lượng vector của XPS gốc.  
- **Kiểm soát chi tiết** – bạn có thể đặt DPI, chế độ làm mịn, và thậm chí chọn các trang cụ thể để chuyển đổi.  
- **Không có phụ thuộc bên ngoài** – thuần Java, không cần thư viện gốc.  
- **Mở rộng được** – hoạt động cho tài liệu một trang cũng như các tệp XPS đa trang lớn.

## Các yêu cầu trước
Trước khi bắt đầu quá trình chuyển đổi, hãy đảm bảo bạn có các yêu cầu sau:

- **Môi trường phát triển Java** – Java 8 hoặc mới hơn đã được cài đặt trên máy của bạn.  
- **Thư viện Aspose.Page cho Java** – Tải xuống và đưa thư viện Aspose.Page cho Java vào dự án của bạn. Bạn có thể tìm thư viện tại [here](https://releases.aspose.com/page/java/).  
- **Tệp XPS mẫu** – Chuẩn bị một tài liệu XPS mẫu mà bạn muốn chuyển đổi sang BMP.

## Nhập gói
Bao gồm các gói Aspose.Page cần thiết trong mã Java của bạn:
```java
import com.aspose.xps.XpsDocument;
import java.io.FileOutputStream;
```

## Cách đặt độ phân giải cho chuyển đổi XPS sang BMP
Dưới đây là hướng dẫn ngắn gọn, có đánh số, cho thấy chính xác nơi và cách đặt độ phân giải, cũng như cách **chuyển đổi các trang cụ thể**.

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

### Bước 4: Lưu tài liệu bằng tùy chọn
```java
// Save XPS document to BMP using options and device
document.save(device, options);
```

### Bước 5: Duyệt qua các hình ảnh đã render và ghi file
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

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Đầu ra BMP chất lượng thấp** | Kiểm tra `options.setResolution()` được đặt thành giá trị ≥ 300 DPI. |
| **Chỉ một phần tài liệu được chuyển đổi** | Đảm bảo `options.setPageNumbers()` bao gồm tất cả các chỉ số trang mong muốn. |
| **OutOfMemoryError trên các tệp XPS lớn** | Xử lý tài liệu thành các phần nhỏ hơn hoặc tăng kích thước heap JVM (`-Xmx`). |
| **Không tìm thấy tệp** | Kiểm tra lại đường dẫn `dataDir` và đảm bảo tệp XPS đầu vào tồn tại. |

## Câu hỏi thường gặp
### Q: Tôi có thể tùy chỉnh độ phân giải của hình ảnh BMP không?
A: Có, bạn có thể điều chỉnh độ phân giải bằng cách sửa đổi tham số `options.setResolution()` trong mã.

### Q: Aspose.Page có tương thích với các phiên bản Java khác nhau không?
A: Có, Aspose.Page hỗ trợ nhiều phiên bản Java. Đảm bảo bạn đã cài đặt phiên bản tương thích.

### Q: Làm sao tôi có thể chuyển đổi các tệp XPS từ một phạm vi trang cụ thể?
A: Sử dụng phương thức `options.setPageNumbers()` để chỉ định các số trang bạn muốn chuyển đổi.

### Q: Có các định dạng đầu ra khác được Aspose.Page hỗ trợ không?
A: Có, Aspose.Page hỗ trợ nhiều định dạng đầu ra khác nhau. Tham khảo tài liệu để biết danh sách đầy đủ.

### Q: Tôi có thể tìm trợ giúp hoặc hỗ trợ bổ sung ở đâu?
A: Truy cập [Aspose.Page Forum](https://forum.aspose.com/c/page/39) để nhận hỗ trợ cộng đồng và thảo luận.

---

**Cập nhật lần cuối:** 2025-12-21  
**Đã kiểm tra với:** Aspose.Page cho Java 24.12  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}