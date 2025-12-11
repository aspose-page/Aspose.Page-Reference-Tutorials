---
date: 2025-12-11
description: Học cách vẽ các hình chữ nhật trong Java PostScript bằng Aspose.Page.
  Hướng dẫn từng bước này chỉ cách thiết lập màu vẽ, đặt màu hình chữ nhật trong Java
  và tạo đồ họa sống động.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Cách vẽ hình chữ nhật trong Java PostScript bằng Aspose.Page
url: /vi/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Vẽ Hình Chữ Nhật trong Java PostScript với Aspose.Page

## Giới thiệu
Nếu bạn cần **cách vẽ hình chữ nhật** trong một tệp Java PostScript, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn cách sử dụng Aspose.Page cho Java để thêm các hình chữ nhật màu sắc, kiểm soát màu nền và viền, và lưu kết quả dưới dạng tài liệu PostScript. Bạn sẽ thấy **cách thiết lập màu vẽ**, cách xác định hình học của hình chữ nhật, và tại sao cách tiếp cận này lý tưởng cho việc tạo đồ họa có thể in được một cách lập trình.

## Trả lời nhanh
- **Thư viện nào cần thiết?** Aspose.Page cho Java  
- **Có thể thay đổi màu của hình chữ nhật không?** Có – sử dụng `setPaint` với bất kỳ `java.awt.Color` nào  
- **Cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; cần giấy phép cho môi trường sản xuất  
- **Kích thước trang nào được dùng trong ví dụ?** A4 (mặc định `PsSaveOptions`)  
- **Mã có tương thích với Java 8+ không?** Hoàn toàn – nó sử dụng các lớp AWT tiêu chuẩn  

## Các yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn đã chuẩn bị các yêu cầu sau:
- Hiểu biết cơ bản về lập trình Java.  
- Thư viện Aspose.Page cho Java đã được cài đặt. Nếu chưa, tải về từ [tài liệu Aspose.Page cho Java](https://reference.aspose.com/page/java/).  
- Môi trường phát triển Java đã được thiết lập trên máy tính của bạn.

## Nhập gói
Trong dự án Java của bạn, bắt đầu bằng cách nhập các gói cần thiết:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Cách Vẽ Hình Chữ Nhật trong Java PostScript
Dưới đây là quy trình hoàn chỉnh được chia thành các bước rõ ràng. Mỗi bước bao gồm một giải thích ngắn gọn và sau đó là khối mã gốc (không thay đổi).

### Bước 1: Đặt màu nền cho hình chữ nhật  
**Cách thiết lập màu vẽ** – chúng ta chọn màu cam làm màu nền cho hình chữ nhật đầu tiên.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Bước 2: Đặt màu viền cho hình chữ nhật  
**Set rectangle color java** – bây giờ chúng ta thay đổi màu vẽ thành màu đỏ và xác định độ rộng đường viền.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Bước 3: Đóng trang hiện tại và lưu tài liệu  
Sau khi vẽ, chúng ta đóng trang và ghi lại tệp.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Tại sao nên dùng Aspose.Page cho Đồ họa Hình chữ nhật?
- **Đa nền tảng**: Tạo PostScript tiêu chuẩn hoạt động trên mọi máy in.  
- **Kiểm soát chi tiết**: Bạn có thể đặt màu nền, màu viền và độ dày đường độc lập.  
- **Không phụ thuộc bên ngoài**: Chỉ sử dụng các lớp hình học AWT có sẵn.  

## Các vấn đề thường gặp & Mẹo
- **Lỗi đường dẫn tệp** – đảm bảo `dataDir` kết thúc bằng dấu phân cách (`/` hoặc `\\`).  
- **Ngoại lệ giấy phép** – phiên bản dùng thử sẽ thêm watermark; cần mua giấy phép đầy đủ cho môi trường sản xuất.  
- **Hiển thị màu** – một số máy in có thể diễn giải các giá trị RGB khác nhau; hãy thử với một hình chữ nhật đen đơn giản trước.

## Kết luận
Trong hướng dẫn này, chúng tôi đã trình bày **cách vẽ hình chữ nhật** trong tài liệu Java PostScript, đề cập **cách thiết lập màu vẽ**, và chỉ ra cách **set rectangle color java** bằng Aspose.Page. Hãy tự do thử nghiệm với các hình dạng, màu sắc và kiểu đường khác nhau để tạo ra đồ họa in ấn phong phú cho báo cáo, hoá đơn hoặc các bản in tùy chỉnh.

## Câu hỏi thường gặp

### Tôi có thể dùng Aspose.Page cho Java với các ngôn ngữ lập trình khác không?
Aspose.Page chủ yếu hỗ trợ Java, nhưng các thư viện tương tự cũng có sẵn cho các ngôn ngữ khác.

### Có phiên bản dùng thử của Aspose.Page cho Java không?
Có, bạn có thể khám phá các tính năng của Aspose.Page cho Java qua [phiên bản dùng thử miễn phí](https://releases.aspose.com/).

### Tôi có thể tìm thêm trợ giúp và thảo luận ở đâu?
Truy cập [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để giao lưu với cộng đồng và nhận hỗ trợ.

### Làm sao để lấy giấy phép tạm thời cho Aspose.Page cho Java?
Nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể mua phiên bản có giấy phép của Aspose.Page cho Java ở đâu?
Mua phiên bản có giấy phép [tại đây](https://purchase.aspose.com/buy).

**Câu hỏi & Trả lời bổ sung**

**H:** *Tôi có thể thay đổi kích thước hình chữ nhật một cách động không?*  
**Đ:** Có – chỉ cần sửa các tham số `Rectangle2D.Float(x, y, width, height)` trước khi gọi `fill` hoặc `draw`.

**H:** *Có thể thêm văn bản bên trong hình chữ nhật không?*  
**Đ:** Chắc chắn. Sau khi vẽ hình chữ nhật, sử dụng `document.drawString(...)` với phông chữ và vị trí mong muốn.

**H:** *Aspose.Page có hỗ trợ các hình dạng khác như vòng tròn hoặc đa giác không?*  
**Đ:** Có, API cung cấp các phương thức như `drawEllipse` và `drawPolygon` cho nhiều loại đồ họa vector.

---

**Cập nhật lần cuối:** 2025-12-11  
**Đã kiểm tra với:** Aspose.Page cho Java 24.12 (mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}