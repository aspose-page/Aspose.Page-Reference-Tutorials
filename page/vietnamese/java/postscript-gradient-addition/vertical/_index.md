---
date: 2026-09-14
description: Tìm hiểu cách tạo gradient PostScript Java với Aspose.Page. Hướng dẫn
  từng bước này chỉ cho bạn cách thêm vertical gradient vào tệp PostScript chỉ với
  vài dòng mã Java.
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: Thêm Vertical Gradient vào Java PostScript
og_description: Tìm hiểu cách tạo gradient PostScript Java với Aspose.Page. Hướng
  dẫn từng bước này chỉ cho bạn cách thêm vertical gradient vào tệp PostScript chỉ
  với vài dòng mã Java.
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: Tạo gradient PostScript Java – vertical gradient
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: Tạo gradient PostScript Java – vertical gradient
url: /vi/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo gradient postscript java – gradient dọc

## Giới thiệu
Aspose.Page for Java là một thư viện cho phép tạo và thao tác các tệp PostScript và PDF một cách lập trình. Trong hướng dẫn toàn diện này, bạn sẽ học cách **create postscript gradient java** bằng thư viện đó. Thêm một gradient dọc có thể làm cho tài liệu của bạn trông sinh động và chuyên nghiệp hơn, và chỉ với vài dòng mã bạn có thể đạt được hiệu ứng hình ảnh ấn tượng. Chúng tôi sẽ hướng dẫn bạn từng bước, giải thích lý do mỗi phần quan trọng, và cung cấp các mẹo thực tế để tránh những lỗi thường gặp. Khi kết thúc hướng dẫn, bạn sẽ có thể tạo các tệp PostScript có chuyển đổi màu dọc mượt mà, bắt mắt.

## Câu trả lời nhanh
- **Thư viện nào cần thiết?** Aspose.Page for Java  
- **Tôi có thể tùy chỉnh màu sắc không?** Yes, any `java.awt.Color` can be used  
- **Có hỗ trợ xoay không?** Yes, you can rotate the gradient with an `AffineTransform`  
- **Định dạng đầu ra là gì?** A standard PostScript (.ps) file  
- **Tôi có cần giấy phép để sản xuất không?** Yes, a commercial license is required  

## Tại sao nên thêm gradient dọc vào tài liệu PostScript?
Thêm một gradient dọc giúp các trang của bạn có độ sâu, cải thiện thứ tự trực quan, và giữ kích thước tệp nhỏ vì gradient được định nghĩa dưới dạng vector thay vì hình ảnh raster. Kỹ thuật này hoàn hảo cho tiêu đề báo cáo, sách hướng dẫn kỹ thuật, hoặc bất kỳ tờ rơi nào cần vẻ hiện đại mà không làm mất khả năng mở rộng.

## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn, hãy chắc chắn rằng bạn đã chuẩn bị các điều kiện tiên quyết sau:
- Java Development Kit (JDK) đã được cài đặt trên máy của bạn.  
- Thư viện Aspose.Page for Java. Bạn có thể tải xuống từ [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).

## Nhập các gói
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

## Cách tạo postscript gradient java
Tải môi trường Java của bạn, tạo một thể hiện `PsSaveOptions`, và gọi `Document.save` – đó là chuỗi lệnh cốt lõi tạo ra tệp PostScript với gradient dọc. API xử lý việc nội suy màu, biến đổi tọa độ và việc flush trang cho bạn, vì vậy bạn chỉ cần tập trung vào việc định nghĩa hình chữ nhật và các tham số gradient.

### Bước 1: thiết lập thư mục tài liệu của bạn
Các đối tượng `File` đại diện cho thư mục nơi sẽ ghi đầu ra. Thư mục phải tồn tại trước khi mở luồng, nếu không sẽ ném ra một `IOException`.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Bước 2: tạo luồng đầu ra cho tài liệu PostScript
`FileOutputStream` ghi dữ liệu PostScript nhị phân ra đĩa. Sử dụng khối `try‑with‑resources` đảm bảo luồng được đóng ngay cả khi có ngoại lệ xảy ra.
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Bước 3: tạo tùy chọn lưu với kích thước A4
`PsSaveOptions` cho phép bạn chỉ định kích thước trang, DPI và việc nhúng phông chữ. Đặt kích thước thành A4 (595 × 842 points) phù hợp với hầu hết các tài liệu có thể in.
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Bước 4: tạo tài liệu PS mới
`Document` là đối tượng cấp cao nhất đại diện cho một tệp PostScript duy nhất trong bộ nhớ. Tất cả các lệnh vẽ được thực hiện trên đối tượng này.
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Bước 5: tạo một hình chữ nhật
`Rectangle2D.Double` xác định khu vực sẽ được tô bằng gradient. Các tọa độ của hình chữ nhật được biểu diễn bằng points (1 point = 1/72 inch).
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Bước 6: thiết lập màu và tỉ lệ cho gradient
Mảng `float[]` xác định vị trí của mỗi điểm dừng màu (từ 0.0 đến 1.0). Các đối tượng `Color` chứa giá trị RGB thực tế. Bạn có thể sử dụng bất kỳ `java.awt.Color` nào bạn muốn.
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Bước 7: tạo biến đổi gradient
`AffineTransform` thực hiện việc phóng đại và xoay gradient. Đối với gradient dọc thuần túy, bạn chỉ cần phóng đại trục Y; việc xoay có thể được thêm vào sau nếu muốn.
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Bước 8: tạo màu gradient tuyến tính dọc
`LinearGradientPaint` kết hợp hình chữ nhật, các điểm dừng màu và biến đổi. Đối tượng này sau đó được truyền vào ngữ cảnh đồ họa.
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Bước 9: đặt màu và tô hình chữ nhật
`Graphics2D.setPaint` áp dụng gradient, và `fill` vẽ nó bên trong hình chữ nhật bạn đã định nghĩa trước đó.
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Bước 10: đóng trang hiện tại và lưu tài liệu
Gọi `document.save` ghi toàn bộ luồng PostScript vào tệp đầu ra và giải phóng tất cả tài nguyên gốc.
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Chúc mừng! Bạn đã thành công thêm một gradient dọc vào tài liệu PostScript Java của mình bằng Aspose.Page for Java.

## Các vấn đề thường gặp và giải pháp
- **Gradient xuất hiện phẳng:** Ensure the `AffineTransform` scaling matches the rectangle dimensions.  
- **Màu sắc trông nhạt:** Verify you are using the correct `ColorSpaceType` (SRGB) and that the fractions array is ordered from 0.0 to 1.0.  
- **File không được tạo:** Check that the output directory (`dataDir`) exists and the application has write permissions.  

## Câu hỏi thường gặp
**Q: Tôi có thể sử dụng Aspose.Page cho Java cùng với các thư viện Java khác không?**  
A: Có, Aspose.Page for Java được thiết kế để hoạt động liền mạch cùng với các thư viện Java khác như Apache Commons hoặc Spring.

**Q: Có bản dùng thử miễn phí cho Aspose.Page cho Java không?**  
A: Có, bạn có thể tải bản dùng thử miễn phí [free trial download page](https://releases.aspose.com/).

**Q: Tôi có thể tìm tài liệu bổ sung ở đâu?**  
A: Tài liệu chi tiết có sẵn tại [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Làm thế nào để mua Aspose.Page cho Java?**  
A: Bạn có thể mua Aspose.Page cho Java tại [Aspose.Page purchase page](https://purchase.aspose.com/buy).

**Q: Có diễn đàn thảo luận về Aspose.Page không?**  
A: Có, bạn có thể tham gia diễn đàn cộng đồng [Aspose.Page community forum](https://forum.aspose.com/c/page/39).

## Câu hỏi thường gặp bổ sung

**Q: Tôi có thể tạo các hướng gradient khác (ngang, chéo) không?**  
A: Chắc chắn. Điều chỉnh các điểm bắt đầu và kết thúc trong `LinearGradientPaint` và thay đổi góc xoay trong `AffineTransform`.

**Q: Điều này có hoạt động với đầu ra PDF không?**  
A: Logic gradient tương tự có thể được áp dụng khi lưu dưới dạng PDF bằng cách sử dụng `PdfSaveOptions` thay vì `PsSaveOptions`.

**Q: Làm thế nào để thay đổi kích thước gradient một cách động?**  
A: Tính toán kích thước hình chữ nhật tại thời gian chạy và truyền các giá trị đó vào cả constructor của `Rectangle2D` và `AffineTransform`.

---

**Cập nhật lần cuối:** 2026-09-14  
**Kiểm tra với:** Aspose.Page for Java 24.11 (latest)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo Gradient Hình Tròn trong PostScript với Aspose.Page cho Java](/page/java/postscript-gradient-addition/)
- [Cách Chuyển Đổi PostScript sang PDF Sử Dụng Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Hướng Dẫn Transparency của Aspose.Page – Thêm Transparency trong PostScript Java](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}