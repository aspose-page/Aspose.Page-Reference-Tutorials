---
date: 2026-02-13
description: Tìm hiểu cách thêm gradient trong Java PostScript bằng Linear Gradient
  Paint Java với Aspose.Page cho Java.
linktitle: How to Add Gradient in Java PostScript with Linear Gradient Paint
second_title: Aspose.Page Java API
title: Cách Thêm Gradient trong Java PostScript bằng Linear Gradient Paint
url: /vi/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Gradient trong Java PostScript với Linear Gradient Paint

## Introduction
Trong hướng dẫn toàn diện này, bạn sẽ khám phá **cách thêm gradient** vào tài liệu PostScript bằng Java. Chúng tôi sẽ hướng dẫn tạo một gradient ngang đẹp mắt bằng cách tận dụng **Linear Gradient Paint Java**, một lớp cho phép bạn kiểm soát chuyển đổi màu một cách pixel‑perfect. Với Aspose.Page for Java, bạn có thể render gradient trên cả **hình dạng** **và** văn bản, mang lại cho tài liệu của bạn vẻ ngoài tinh tế, bắt mắt.

## Quick Answers
- **Thư viện nào cần thiết?** Aspose.Page for Java (hỗ trợ Linear Gradient Paint Java).  
- **Thời gian thực hiện là bao lâu?** Khoảng 10‑15 phút cho một gradient cơ bản.  
- **Tôi có cần giấy phép không?** Cần một giấy phép tạm thời hoặc đầy đủ cho việc sử dụng trong môi trường sản xuất.  
- **Phiên bản JDK nào hoạt động?** Java 8 hoặc mới hơn.  
- **Tôi có thể dùng gradient cho cả hình dạng và văn bản không?** Có – bạn có thể tô màu hình dạng và viền hoặc tô màu văn bản bằng cùng một gradient.

## What is a Horizontal Gradient and Why Use It?
Gradient ngang làm cho các màu chuyển đổi mượt mà từ trái sang phải trên một hình dạng hoặc văn bản. Nó lý tưởng để tạo các yếu tố UI hiện đại, tiêu đề được làm nổi bật, hoặc hiệu ứng nền nhẹ nhàng trong báo cáo. Sử dụng **Linear Gradient Paint Java** cho phép bạn xác định chính xác màu bắt đầu và màu kết thúc, độ trong suốt và tỉ lệ, vì vậy kết quả luôn sắc nét trên bất kỳ thiết bị nào.

## Prerequisites
Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn có những thứ sau:

- Java Development Kit (JDK) đã được cài đặt trên máy của bạn.  
- Thư viện Aspose.Page for Java. Bạn có thể tải xuống từ [Aspose.Page Java documentation](https://reference.aspose.com/page/java/).

## Import Packages
Bắt đầu bằng cách nhập các gói cần thiết vào dự án Java của bạn. Các import này cung cấp quyền truy cập vào các primitive đồ họa, xử lý gradient và API của Aspose.Page.

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

## Step 1: Create a Rectangle
Đầu tiên, thiết lập luồng đầu ra, tài liệu và một hình chữ nhật sẽ chứa gradient.

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

## Step 2: Create Horizontal Linear Gradient Paint
Ở đây chúng ta tạo đối tượng **Linear Gradient Paint Java** định nghĩa chuyển đổi màu ngang. `AffineTransform` sẽ thay đổi tỉ lệ gradient để khớp với chiều rộng và chiều cao của hình chữ nhật.

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

## Step 3: Fill the Rectangle
Bây giờ tô màu cho hình chữ nhật bằng gradient mà chúng ta vừa định nghĩa.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Step 4: Fill a Text with the Gradient
Bạn cũng có thể áp dụng cùng một gradient cho văn bản, tạo hiệu ứng hình ảnh ấn tượng.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Step 5: Stroke a Text with the Gradient
Cuối cùng, tạo viền cho văn bản bằng cách sử dụng gradient làm màu viền.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Common Issues and Solutions
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|-----------|
| Gradient bị kéo dài | Thang đo `AffineTransform` không đúng | Đảm bảo chiều rộng và chiều cao của transform khớp với kích thước của hình chữ nhật (200 × 100 trong ví dụ). |
| Màu sắc trông nhạt | Giá trị alpha được đặt quá thấp | Tăng thành phần alpha (giá trị thứ tư trong `new Color(r,g,b,alpha)`). |
| Văn bản không hiển thị | Paint chưa được đặt trước khi vẽ văn bản | Gọi `document.setPaint(paint)` **trước** bất kỳ lệnh `fillAndStrokeText` hoặc `outlineText` nào. |

## Frequently Asked Questions
**Q:** Tôi có thể sử dụng Aspose.Page for Java trong các dự án thương mại không?  
**A:** Có, Aspose.Page for Java có thể được sử dụng trong các dự án thương mại. Để biết chi tiết về giấy phép, hãy truy cập [Aspose.Purchase](https://purchase.aspose.com/buy).

**Q:** Có bản dùng thử miễn phí không?  
**A:** Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.Page for Java [tại đây](https://releases.aspose.com/).

**Q:** Tôi có thể tìm tài liệu và hỗ trợ bổ sung ở đâu?  
**A:** Tham khảo [Aspose.Page Java documentation](https://reference.aspose.com/page/java/) để có tài nguyên đầy đủ. Đối với hỗ trợ cộng đồng, xem [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Làm thế nào để tôi có được giấy phép tạm thời?  
**A:** Bạn có thể nhận giấy phép tạm thời từ [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

**Q:** Yêu cầu hệ thống cho Aspose.Page for Java là gì?  
**A:** Tham khảo [documentation](https://reference.aspose.com/page/java/) để biết yêu cầu hệ thống chi tiết.

---

**Cập nhật lần cuối:** 2026-02-13  
**Đã kiểm tra với:** Aspose.Page for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}