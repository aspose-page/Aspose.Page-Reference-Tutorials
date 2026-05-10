---
date: 2026-02-13
description: Học cách tạo gradient PostScript trong Java bằng Aspose.Page. Hướng dẫn
  từng bước này cho bạn biết cách thêm gradient dọc vào tài liệu PostScript một cách
  dễ dàng.
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: Tạo Gradient PostScript trong Java – Thêm Gradient Dọc
url: /vi/java/postscript-gradient-addition/vertical/
weight: 14
---

 keep same link text? The link text can be translated? The rule says preserve markdown links format, but we can translate the link text while keeping URL unchanged. Usually we can translate link text. We'll translate link text.

Also for images none present.

Let's produce final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Gradient PostScript trong Java – Thêm Gradient Dọc

## Giới thiệu
Trong hướng dẫn toàn diện này, bạn sẽ học cách **tạo gradient PostScript trong Java** với Aspose.Page for Java. Thêm một gradient dọc có thể làm cho tài liệu của bạn trông sinh động và chuyên nghiệp hơn, và chỉ với vài dòng mã bạn đã có thể đạt được các hiệu ứng hình ảnh ấn tượng. Chúng tôi sẽ hướng dẫn bạn từng bước, giải thích lý do mỗi phần quan trọng, và cung cấp các mẹo thực tế để tránh những lỗi thường gặp. Khi kết thúc hướng dẫn này, bạn sẽ có thể tạo các tệp PostScript có chuyển đổi màu dọc mượt mà, bắt mắt.

## Câu trả lời nhanh
- **Thư viện nào cần thiết?** Aspose.Page for Java  
- **Có thể tùy chỉnh màu sắc không?** Có, bất kỳ `java.awt.Color` nào cũng có thể sử dụng  
- **Có hỗ trợ xoay không?** Có, bạn có thể xoay gradient bằng một `AffineTransform`  
- **Định dạng đầu ra là gì?** Tệp PostScript tiêu chuẩn (.ps)  
- **Có cần giấy phép cho môi trường sản xuất không?** Có, cần giấy phép thương mại  

## Tại sao nên thêm gradient dọc vào tài liệu PostScript?
Gradient dọc mang lại độ sâu cho các trang mà không làm tăng kích thước tệp. Chúng hoàn hảo cho:

* Đầu trang hoặc chân trang báo cáo cần một nền màu nhẹ nhàng.  
* Làm nổi bật các phần trong tài liệu kỹ thuật hoặc white‑paper.  
* Tạo phong cách hiện đại cho biểu đồ, sơ đồ, hoặc tờ rơi quảng cáo.

Vì gradient được định nghĩa dưới dạng vector, đầu ra luôn sắc nét ở bất kỳ độ phân giải nào.

## Yêu cầu trước
Trước khi bắt đầu tutorial, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:
- Java Development Kit (JDK) đã được cài đặt trên máy tính của bạn.  
- Thư viện Aspose.Page for Java. Bạn có thể tải xuống [tại đây](https://releases.aspose.com/page/java/).

## Nhập gói
Trong dự án Java của bạn, nhập các gói cần thiết để bắt đầu:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Bây giờ, chúng ta sẽ đi qua quy trình thêm gradient dọc từng bước một.

## Cách tạo gradient PostScript trong Java
Dưới đây là hướng dẫn chi tiết từng bước cho thấy cách **tạo gradient PostScript trong Java** bằng API Aspose.Page.

### Bước 1: Thiết lập thư mục tài liệu của bạn
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Bước 2: Tạo luồng xuất cho tài liệu PostScript
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Bước 3: Tạo tùy chọn lưu với kích thước A4
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Bước 4: Tạo tài liệu PS mới
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Bước 5: Tạo một hình chữ nhật
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Bước 6: Thiết lập màu và tỉ lệ cho gradient
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Bước 7: Tạo phép biến đổi gradient
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Bước 8: Tạo Paint gradient tuyến tính dọc
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Bước 9: Đặt Paint và tô đầy hình chữ nhật
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Bước 10: Đóng trang hiện tại và lưu tài liệu
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Chúc mừng! Bạn đã thành công thêm gradient dọc vào tài liệu PostScript Java của mình bằng Aspose.Page for Java.

## Các vấn đề thường gặp và giải pháp
- **Gradient trông phẳng:** Đảm bảo phép biến đổi `AffineTransform` có tỷ lệ phù hợp với kích thước hình chữ nhật.  
- **Màu sắc bị nhạt:** Kiểm tra bạn đang sử dụng đúng `ColorSpaceType` (SRGB) và mảng fractions được sắp xếp từ 0.0 đến 1.0.  
- **Không tạo được tệp:** Kiểm tra thư mục đầu ra (`dataDir`) có tồn tại và ứng dụng có quyền ghi.

## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Page for Java cùng với các thư viện Java khác không?
Có, Aspose.Page for Java được thiết kế để hoạt động liền mạch với các thư viện Java khác.

### Có bản dùng thử miễn phí cho Aspose.Page for Java không?
Có, bạn có thể nhận bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### Tôi có thể tìm tài liệu bổ sung ở đâu?
Tài liệu chi tiết có sẵn [tại đây](https://reference.aspose.com/page/java/).

### Làm sao để mua Aspose.Page for Java?
Bạn có thể mua Aspose.Page for Java [tại đây](https://purchase.aspose.com/buy).

### Có diễn đàn thảo luận về Aspose.Page không?
Có, bạn có thể tham gia diễn đàn cộng đồng [tại đây](https://forum.aspose.com/c/page/39).

## Các câu hỏi thường gặp bổ sung

**H: Tôi có thể tạo các hướng gradient khác (ngang, chéo) không?**  
Đ: Chắc chắn. Điều chỉnh các điểm bắt đầu và kết thúc trong `LinearGradientPaint` và thay đổi góc xoay trong `AffineTransform`.

**H: Điều này có hoạt động với đầu ra PDF không?**  
Đ: Logic gradient tương tự có thể áp dụng khi lưu dưới dạng PDF bằng cách sử dụng `PdfSaveOptions` thay vì `PsSaveOptions`.

**H: Làm sao để thay đổi kích thước gradient một cách động?**  
Đ: Tính toán kích thước hình chữ nhật tại thời gian chạy và truyền các giá trị đó cho cả `Rectangle2D` và hàm khởi tạo `AffineTransform`.

---

**Cập nhật lần cuối:** 2026-02-13  
**Đã kiểm tra với:** Aspose.Page for Java 24.11 (phiên bản mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}