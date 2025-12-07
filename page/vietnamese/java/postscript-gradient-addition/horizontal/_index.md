---
date: 2025-12-07
description: Tìm hiểu cách thêm gradient ngang trong Java PostScript bằng Linear Gradient
  Paint Java với Aspose.Page cho Java.
language: vi
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: Thêm Gradient trong Java PostScript bằng Linear Gradient Paint Java
url: /java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Gradient trong Java PostScript bằng Linear Gradient Paint Java

## Giới thiệu
Trong hướng dẫn toàn diện này, bạn sẽ khám phá cách tạo một gradient ngang đẹp mắt trong tài liệu PostScript bằng cách tận dụng **Linear Gradient Paint Java**. Aspose.Page for Java giúp bạn làm việc với PostScript, PDF và các định dạng vector khác một cách dễ dàng, và lớp `LinearGradientPaint` cho phép bạn kiểm soát chi tiết quá trình chuyển đổi màu. Khi hoàn thành hướng dẫn này, bạn sẽ có thể vẽ gradient lên các hình **và** văn bản, mang lại cho tài liệu của bạn vẻ chuyên nghiệp, bắt mắt.

## Câu trả lời nhanh
- **Thư viện nào cần thiết?** Aspose.Page for Java (hỗ trợ Linear Gradient Paint Java).  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút cho một gradient cơ bản.  
- **Có cần giấy phép không?** Cần một giấy phép tạm thời hoặc đầy đủ cho việc sử dụng trong môi trường sản xuất.  
- **Phiên bản JDK nào hỗ trợ?** Java 8 hoặc mới hơn.  
- **Có thể dùng gradient cho cả hình và văn bản không?** Có – bạn có thể tô màu hình và viền hoặc tô màu văn bản bằng cùng một gradient.

## Yêu cầu trước
Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn đã có:

- Java Development Kit (JDK) được cài đặt trên máy tính của bạn.  
- Thư viện Aspose.Page for Java. Bạn có thể tải xuống từ [tài liệu Aspose.Page Java](https://reference.aspose.com/page/java/).

## Nhập khẩu các gói
Bắt đầu bằng cách nhập các gói cần thiết vào dự án Java của bạn. Những import này cho phép bạn truy cập vào các primitive đồ họa, xử lý gradient và API của Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Bước 1: Tạo một Rectangle
Đầu tiên, thiết lập luồng xuất, tài liệu và một hình chữ nhật sẽ chứa gradient.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Bước 2: Tạo Horizontal Linear Gradient Paint
Ở đây chúng ta xây dựng đối tượng **Linear Gradient Paint Java** xác định một chuyển đổi màu ngang. `AffineTransform` sẽ mở rộng gradient để khớp với chiều rộng và chiều cao của hình chữ nhật.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Bước 3: Đổ màu cho Rectangle
Bây giờ hãy đổ màu cho hình chữ nhật bằng gradient mà chúng ta vừa định nghĩa.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Bước 4: Đổ màu cho Văn bản bằng Gradient
Bạn cũng có thể áp dụng cùng một gradient cho văn bản, tạo hiệu ứng hình ảnh ấn tượng.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Bước 5: Viền Văn bản bằng Gradient
Cuối cùng, tạo viền cho văn bản bằng cách sử dụng gradient làm màu viền.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| Gradient bị kéo dài | Thuộc tính `AffineTransform` không đúng | Đảm bảo chiều rộng và chiều cao trong transform khớp với kích thước của hình chữ nhật (200 × 100 trong ví dụ). |
| Màu sắc nhạt | Giá trị alpha được đặt quá thấp | Tăng giá trị alpha (thành phần thứ tư trong `new Color(r,g,b,alpha)`). |
| Văn bản không hiển thị | Paint chưa được thiết lập trước khi vẽ văn bản | Gọi `document.setPaint(paint)` **trước** bất kỳ lệnh `fillAndStrokeText` hoặc `outlineText` nào. |

## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Page for Java trong dự án thương mại không?
Có, Aspose.Page for Java có thể được sử dụng trong các dự án thương mại. Để biết chi tiết về giấy phép, hãy truy cập [Aspose.Purchase](https://purchase.aspose.com/buy).

### Có bản dùng thử miễn phí không?
Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.Page for Java [tại đây](https://releases.aspose.com/).

### Tôi có thể tìm tài liệu và hỗ trợ bổ sung ở đâu?
Truy cập [tài liệu Aspose.Page Java](https://reference.aspose.com/page/java/) để có các nguồn tài nguyên toàn diện. Đối với hỗ trợ cộng đồng, hãy xem [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39).

### Làm sao để lấy giấy phép tạm thời?
Bạn có thể lấy giấy phép tạm thời từ [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

### Yêu cầu hệ thống cho Aspose.Page for Java là gì?
Xem [tài liệu](https://reference.aspose.com/page/java/) để biết chi tiết yêu cầu hệ thống.

---

**Cập nhật lần cuối:** 2025-12-07  
**Đã kiểm tra với:** Aspose.Page for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}