---
date: 2026-10-31
description: Tìm hiểu cách set paint color và fill ellipse trong Java PostScript bằng
  Aspose.Page. Hướng dẫn này cho thấy cách fill ellipse, draw ellipse outline, và
  set stroke thickness với các code steps rõ ràng.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Thêm Ellipse trong Java PostScript
og_description: Tìm hiểu cách fill ellipse và set paint color trong Java PostScript
  bằng Aspose.Page. Thực hiện code step‑by‑step để draw ellipses đã fill và outlined
  trong vài giây.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Cách fill ellipse và set paint color trong Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Cách fill ellipse và set paint color trong Java PostScript
url: /vi/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách điền ellipse và đặt màu sơn trong Java PostScript

## Giới thiệu
Nếu bạn cần **đặt màu sơn** khi vẽ đồ họa vector, thư viện Aspose.Page for Java cung cấp cho bạn quyền kiểm soát đầy đủ mọi nét vẽ và việc tô. Trong hướng dẫn này, bạn sẽ khám phá cách **đặt màu sơn**, **điền ellipse**, và **vẽ đường viền ellipse** bằng một cách tiếp cận đơn giản, từng bước. Khi hoàn thành, bạn sẽ có thể thêm các ellipse PostScript chất lượng cao vào hoá đơn, báo cáo, hoặc bất kỳ tài liệu có thể in nào.

## Câu trả lời nhanh
- **Thư viện nào tốt nhất để vẽ đồ họa PostScript trong Java?** Aspose.Page for Java.  
- **Tôi có thể điền một ellipse bằng màu đặc không?** Có – sử dụng `document.setPaint(Color.YOUR_COLOR)` trước `fill`.  
- **Làm sao để chỉ vẽ đường viền của một ellipse?** Đặt màu sơn và nét vẽ, sau đó gọi `document.draw(...)`.  
- **Tôi có cần giấy phép cho việc sử dụng trong sản xuất không?** Cần giấy phép thương mại; giấy phép tạm thời có sẵn cho việc thử nghiệm.  
- **Phiên bản Java nào được hỗ trợ?** Bất kỳ môi trường chạy Java 8+ nào cũng hoạt động với phiên bản Aspose.Page hiện tại.

## Ellipse PostScript là gì?
Ellipse PostScript là một hình dạng vector được định nghĩa bởi một hình chữ nhật bao quanh. Không giống như hình ảnh raster, nó có thể phóng to mà không mất chất lượng, làm cho nó lý tưởng cho việc in ấn độ phân giải cao và chuyển đổi sang PDF. Vì hình dạng được mô tả bằng toán học, nó có thể được render ở bất kỳ kích thước hoặc độ phân giải nào mà vẫn giữ được các cạnh sắc nét và đường cong mượt mà.

## Tại sao nên dùng Aspose.Page để tạo ellipse PostScript?
Aspose.Page cho bạn quyền kiểm soát quyết định đối với mọi primitive vẽ. Nó hỗ trợ **3 hệ điều hành chính (Windows, Linux, macOS)**, **0 phụ thuộc native**, và có thể render **hơn 50 primitive vector** mỗi giây trên một máy chủ điển hình. Thư viện thuần Java, vì vậy bạn có thể nhúng nó vào bất kỳ ứng dụng Java 8+ nào mà không cần thư viện native bổ sung.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn có:

1. Môi trường phát triển Java hoạt động (JDK 8 hoặc mới hơn).  
2. Thư viện Aspose.Page for Java được thêm vào dự án của bạn. Bạn có thể tải xuống **[from the Aspose.Page for Java release page](https://releases.aspose.com/page/java/)**.  

## Nhập các gói
Trong tệp nguồn Java của bạn, nhập các lớp cần thiết để vẽ và lưu nội dung PostScript.

Gói `java.awt` cung cấp các kiểu đồ họa cơ bản như `Color`, `Ellipse2D`, và `BasicStroke`. Gói `com.aspose.page` cung cấp lớp `PsDocument` để ghi đầu ra PostScript.

- **`Color`** – đại diện cho màu sRGB được dùng để vẽ.  
- **`Ellipse2D`** – mô tả hình ellipse được xác định bởi một hình chữ nhật bao quanh.  
- **`BasicStroke`** – chỉ định độ rộng đường, mẫu gạch, và kiểu đầu mút cho việc vẽ đường viền.  
- **`PsDocument`** – đại diện cho tài liệu PostScript và cung cấp các phương thức để vẽ đồ họa và quản lý các trang.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Cách đặt màu sơn cho một ellipse
Bước đầu tiên là cho tài liệu biết màu nào sẽ được dùng cho thao tác vẽ tiếp theo. Phương thức `setPaint` đặt một màu đặc sẽ được áp dụng cho việc tô hoặc nét, tùy thuộc vào lời gọi tiếp theo.

### Bước 1: Thiết lập tài liệu PostScript
Tạo một luồng đầu ra, cấu hình kích thước trang, và khởi tạo một `PsDocument`.

`PsDocument` là lớp cốt lõi đại diện cho tệp PostScript trong bộ nhớ. Tất cả các lệnh vẽ đều được truyền qua đối tượng này, và nó xử lý bố cục trang, quản lý tài nguyên, và tạo file cuối cùng.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Bước 2: Điền ellipse – sử dụng đặt màu sơn
Để **điền ellipse**, bạn phải gọi `setPaint` trước với màu tô mong muốn, sau đó gọi `fill` với một thể hiện `Ellipse2D`.

`setPaint` đặt màu vẽ hiện tại được dùng cho các thao tác tô hoặc nét tiếp theo.  
`Ellipse2D` định nghĩa giới hạn hình học của ellipse; hàm khởi tạo của nó nhận tọa độ X‑Y của góc trên‑trái cộng với chiều rộng và chiều cao.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Bước 3: Vẽ đường viền ellipse và đặt độ dày nét
Sau khi tô, bạn có thể đổi màu sơn sang màu khác, định nghĩa một `BasicStroke` để kiểm soát độ rộng đường, và vẽ đường viền ellipse.

`BasicStroke` chỉ định độ rộng đường, mẫu gạch, và kiểu đầu mút cho việc vẽ đường viền. Bằng cách điều chỉnh thuộc tính `width` của nó, bạn kiểm soát độ đậm của viền ellipse.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Bước 4: Đóng và lưu tài liệu
Hoàn thiện trang và ghi tệp PostScript ra đĩa.

Gọi `document.close()` sẽ flush tất cả các lệnh vẽ còn lại và giải phóng tài nguyên. Tệp `.ps` tạo ra có thể được mở bằng bất kỳ trình xem PostScript nào hoặc chuyển đổi sang PDF.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Bây giờ bạn đã có một tệp PostScript chứa hai ellipse—một được tô màu cam và một khác chỉ có viền màu đỏ. Hãy tự do thử nghiệm với các tọa độ, kích thước và màu sắc khác nhau để phù hợp với nhu cầu thiết kế của bạn.

## Những lỗi thường gặp và khắc phục
- **Đường dẫn tệp không đúng** – Đảm bảo `dataDir` kết thúc bằng dấu phân tách (`/` hoặc `\\`) phù hợp với hệ điều hành của bạn.  
- **Thiếu giấy phép** – Nếu không có giấy phép hợp lệ, thư viện sẽ chạy ở chế độ đánh giá và có thể thêm watermark.  
- **Màu không được áp dụng** – Hãy nhớ đặt `document.setPaint(...)` *trước* mỗi lời gọi `fill` hoặc `draw`; cài đặt màu không tự động duy trì qua các thao tác riêng biệt.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Page for Java cùng với các thư viện Java khác không?**  
A: Có, Aspose.Page for Java được thiết kế để tích hợp liền mạch với các thư viện Java khác.

**Q: Làm sao để tôi có được giấy phép tạm thời cho Aspose.Page for Java?**  
A: Nhận giấy phép tạm thời **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)** cho mục đích thử nghiệm.

**Q: Aspose.Page có phù hợp cho các dự án thương mại không?**  
A: Chắc chắn! Truy cập **[the Aspose purchase page](https://purchase.aspose.com/buy)** để khám phá các tùy chọn giấy phép cho việc sử dụng thương mại.

**Q: Tôi có thể tìm trợ giúp hoặc thảo luận các câu hỏi liên quan đến Aspose.Page ở đâu?**  
A: Tham gia cộng đồng tại **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** để thảo luận và nhận hỗ trợ.

**Q: Có tài nguyên miễn phí nào để học thêm về Aspose.Page for Java không?**  
A: Sử dụng **[Aspose free trial page](https://releases.aspose.com/)** và khám phá các ví dụ trong tài liệu.

## Kết luận
Aspose.Page for Java giúp bạn dễ dàng **đặt màu sơn**, **điền ellipse**, và **vẽ đường viền ellipse**—cho dù bạn cần một hình dạng đơn giản được tô đầy hay một đồ họa phức tạp có nét. Với các bước trên, bạn có thể nhanh chóng thêm đồ họa vector cấp chuyên nghiệp vào bất kỳ tài liệu có thể in nào. Để khám phá sâu hơn—như kết hợp nhiều hình dạng, áp dụng gradient, hoặc chuyển đổi sang PDF—hãy tham khảo **[Aspose.Page Java documentation](https://reference.aspose.com/page/java/)** chính thức.

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## Hướng dẫn liên quan

- [Cách vẽ hình chữ nhật trong Java PostScript với Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Cách thêm văn bản Unicode trong Java PostScript với Aspose.Page](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Tạo gradient bán kính trong PostScript với Aspose.Page cho Java](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}