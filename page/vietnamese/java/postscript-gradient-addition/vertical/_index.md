---
date: 2025-12-09
description: Tìm hiểu cách tạo gradient PostScript trong Java bằng Aspose.Page. Hướng
  dẫn từng bước này sẽ chỉ cho bạn cách thêm gradient dọc vào tài liệu PostScript
  một cách dễ dàng.
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: Tạo Gradient PostScript trong Java – Thêm Gradient Dọc
url: /vi/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Gradient PostScript trong Java – Thêm Gradient Dọc

## Introduction
Trong hướng dẫn toàn diện này, bạn sẽ học cách **tạo gradient PostScript trong Java** với Aspose.Page cho Java. Thêm một gradient dọc có thể làm cho tài liệu của bạn trông sinh động và chuyên nghiệp hơn, và chỉ với vài dòng mã bạn có thể đạt được hiệu ứng hình ảnh ấn tượng. Chúng tôi sẽ hướng dẫn bạn qua từng bước, giải thích lý do mỗi phần quan trọng, và cung cấp các mẹo thực tế để tránh những lỗi thường gặp.  
Trong hướng dẫn này, chúng tôi sẽ **tạo gradient postscript java** từng bước.

## Quick Answers
- **What library is needed?** Aspose.Page for Java  
- **Can I customize colors?** Yes, any `java.awt.Color` can be used  
- **Is rotation supported?** Yes, you can rotate the gradient with an `AffineTransform`  
- **What output format is produced?** A standard PostScript (.ps) file  
- **Do I need a license for production?** Yes, a commercial license is required  

## Prerequisites
Trước khi bắt đầu hướng dẫn, hãy chắc chắn rằng bạn đã chuẩn bị các điều kiện tiên quyết sau:
- Java Development Kit (JDK) đã được cài đặt trên máy của bạn.  
- Aspose.Page for Java library. Bạn có thể tải xuống [tại đây](https://releases.aspose.com/page/java/).

## Import Packages
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

Bây giờ, chúng ta sẽ phân tích quá trình thêm gradient dọc trong PostScript Java thành nhiều bước.

## How to create PostScript gradient Java
Dưới đây là hướng dẫn từng bước cho thấy cách **tạo gradient PostScript trong Java** bằng API Aspose.Page.

### Step 1: Set up Your Document Directory
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Step 2: Create Output Stream for PostScript Document
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Step 3: Create Save Options with A4 Size
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Step 4: Create a New PS Document
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Step 5: Create a Rectangle
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Step 6: Set Up Colors and Fractions for the Gradient
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Step 7: Create the Gradient Transform
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Step 8: Create Vertical Linear Gradient Paint
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Step 9: Set Paint and Fill the Rectangle
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Step 10: Close Current Page and Save the Document
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Chúc mừng! Bạn đã thành công thêm gradient dọc vào tài liệu PostScript Java của mình bằng Aspose.Page cho Java.

## Why use vertical gradients in PostScript?
Gradient dọc mang lại độ sâu và sự thu hút trực quan cho các trang mà không làm tăng kích thước tệp đáng kể. Chúng đặc biệt hữu ích cho:
- Tiêu đề và chân trang báo cáo  
- Nền cho biểu đồ hoặc sơ đồ  
- Làm nổi bật các phần trong tài liệu kỹ thuật  

## Common Issues and Solutions
- **Gradient appears flat:** Đảm bảo tỷ lệ `AffineTransform` phù hợp với kích thước hình chữ nhật.  
- **Colors look washed out:** Xác minh bạn đang sử dụng `ColorSpaceType` (SRGB) đúng và mảng tỷ lệ được sắp xếp từ 0.0 đến 1.0.  
- **File not generated:** Kiểm tra thư mục đầu ra (`dataDir`) tồn tại và ứng dụng có quyền ghi.  

## Frequently Asked Questions
### Can I use Aspose.Page for Java with other Java libraries?
Có, Aspose.Page cho Java được thiết kế để hoạt động liền mạch với các thư viện Java khác.

### Is there a free trial available for Aspose.Page for Java?
Có, bạn có thể nhận bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### Where can I find additional documentation?
Tài liệu chi tiết có sẵn [tại đây](https://reference.aspose.com/page/java/).

### How can I purchase Aspose.Page for Java?
Bạn có thể mua Aspose.Page cho Java [tại đây](https://purchase.aspose.com/buy).

### Is there a forum for Aspose.Page discussions?
Có, bạn có thể tham gia diễn đàn cộng đồng [tại đây](https://forum.aspose.com/c/page/39).

## Additional Frequently Asked Questions

**Q: Can I create other gradient directions (horizontal, diagonal)?**  
A: Chắc chắn. Điều chỉnh điểm bắt đầu và kết thúc trong `LinearGradientPaint` và thay đổi góc xoay trong `AffineTransform`.

**Q: Does this work with PDF output as well?**  
A: Logic gradient tương tự có thể áp dụng khi lưu thành PDF bằng cách sử dụng `PdfSaveOptions` thay vì `PsSaveOptions`.

**Q: How do I change the gradient size dynamically?**  
A: Tính toán kích thước hình chữ nhật tại thời gian chạy và truyền các giá trị đó cho cả `Rectangle2D` và hàm khởi tạo `AffineTransform`.

---

**Last Updated:** 2025-12-09  
**Tested With:** Aspose.Page for Java 24.11 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}