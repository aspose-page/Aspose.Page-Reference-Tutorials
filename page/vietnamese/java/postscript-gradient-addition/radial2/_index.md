---
date: 2026-09-09
description: Tìm hiểu cách tạo gradient trong Java PostScript và thêm gradient vào
  shape bằng cách sử dụng Aspose.Page. Thực hiện theo hướng dẫn step‑by‑step với code
  và tips.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Java PostScript Radial Gradient với Aspose.Page
og_description: Tìm hiểu cách tạo gradient trong Java PostScript và thêm gradient
  vào shape bằng cách sử dụng Aspose.Page. Thực hiện theo hướng dẫn step‑by‑step với
  code và tips.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Cách tạo gradient trong Java PostScript với radial fill
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Cách tạo gradient trong Java PostScript với radial fill
url: /vi/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo gradient trong Java PostScript với độ phủ dạng tròn

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học **cách tạo gradient** đồ họa trong tài liệu PostScript bằng Java và Aspose.Page. Chúng tôi sẽ hướng dẫn từng bước—từ thiết lập dự án đến việc vẽ một vòng tròn được lấp đầy bằng gradient dạng tròn mượt mà—để bạn có thể **thêm gradient vào hình dạng** ngay lập tức và nâng cao chất lượng hình ảnh của các ứng dụng Java của mình.

## Câu trả lời nhanh
- **Hướng dẫn này tạo gì?** A PostScript file (`.ps`) containing a circle filled with a radial gradient.  
- **Thư viện nào được yêu cầu?** Aspose.Page for Java (latest version).  
- **Thời gian thực hiện khoảng bao lâu?** Approximately 10‑15 minutes for a working example.  
- **Tôi có cần giấy phép không?** A temporary or full license is required for production use; a free trial works for development.  
- **Tôi có thể tái sử dụng mã cho PDF hoặc SVG không?** Yes—Aspose.Page supports multiple output formats with minimal changes.

## Cách lấp đầy hình dạng bằng gradient trong PostScript
Bạn có thể lấp đầy một hình dạng bằng gradient dạng tròn trong PostScript bằng cách tạo một `PsDocument`, định nghĩa một `RadialGradientPaint`, áp dụng nó vào hình mục tiêu, và cuối cùng lưu tài liệu. Quy trình ngắn gọn này cho phép bạn tạo đồ họa vector chuyên nghiệp mà không cần hình ảnh raster, và cùng một đoạn mã có thể được tái sử dụng cho đầu ra PDF hoặc SVG. Quá trình này đơn giản và hoạt động nhất quán trên tất cả các định dạng được hỗ trợ.

## Gradient dạng tròn là gì?
Gradient dạng tròn chuyển đổi màu từ một điểm trung tâm ra bên ngoài, tạo ra một sự pha trộn tròn mượt mà. Nó lý tưởng cho các điểm nhấn, nền nút, hoặc bất kỳ hình ảnh nào cần hiệu ứng “ánh sáng” tự nhiên. Bằng cách thay đổi các điểm màu và bán kính, bạn có thể mô phỏng ánh sáng, độ sâu và tính chất vật liệu trong dạng vector thuần.

## Tại sao nên dùng Aspose.Page cho gradient dạng tròn?
Aspose.Page cho phép bạn tạo đồ họa vector không phụ thuộc vào thiết bị bằng một API Java duy nhất. Nó hỗ trợ hơn 50 định dạng đầu vào và đầu ra—bao gồm PostScript, PDF và SVG—đồng thời giữ độ chính xác màu và khử răng cưa cho đầu ra độ phân giải cao. Thư viện cũng cung cấp các lớp gradient dễ sử dụng, giúp triển khai các hiệu ứng hình ảnh phức tạp trở nên đơn giản.

## Yêu cầu trước
- Kiến thức cơ bản về lập trình Java.  
- JDK 8 hoặc mới hơn được cài đặt trên máy của bạn.  
- Thư viện Aspose.Page for Java (tải xuống từ [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)).  

## Nhập các gói
Đầu tiên, nhập các lớp cần thiết. Chúng bao gồm các kiểu đồ họa AWT tiêu chuẩn và API của Aspose.Page.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Bước 1: thiết lập thư mục tài liệu
Xác định thư mục nơi file PostScript được tạo sẽ được lưu. Thay thế phần giữ chỗ bằng đường dẫn thực tế trên hệ thống của bạn.

```java
String dataDir = "Your Document Directory";
```

## Bước 2: tạo luồng đầu ra
`FileOutputStream` ghi các byte thô vào file, cho phép lưu dữ liệu nhị phân. Mở một luồng hướng tới file `.ps` cho phép Aspose.Page truyền dữ liệu PostScript đã tạo trực tiếp lên đĩa.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Bước 3: tạo tùy chọn lưu
`PsSaveOptions` cấu hình cách một file PostScript được lưu, bao gồm kích thước trang và nén. Bạn có thể tùy chỉnh các thiết lập này, nhưng mặc định đã đủ cho ví dụ này.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Bước 4: tạo tài liệu ps
`PsDocument` đại diện cho một tài liệu PostScript trong bộ nhớ và cung cấp các phương thức để thêm trang và đồ họa.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Bước 5: tạo một vòng tròn
`Ellipse2D.Float` mô tả một hình elip; khi chiều rộng = chiều cao nó trở thành một vòng tròn hoàn hảo. Đối tượng này sẽ làm nền cho việc lấp đầy gradient của chúng ta.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Cách vẽ vòng tròn với gradient
Để vẽ một vòng tròn với gradient dạng tròn, bạn tải một `RadialGradientPaint` vào ngữ cảnh đồ họa và sau đó lấp đầy elip đã định nghĩa trước. Hoạt động duy nhất này tô màu hình dạng với sự chuyển đổi màu mượt mà từ trung tâm ra ngoài, tạo ra hiệu ứng hấp dẫn về mặt hình ảnh.

## Bước 6: định nghĩa màu gradient
Chuẩn bị hai mảng: một cho các màu sẽ xuất hiện trong gradient và một cho các vị trí phân số tương ứng (0 = trung tâm, 1 = cạnh).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Bước 7: tạo AffineTransform
`AffineTransform` là một ma trận có thể dịch, quay, thu phóng hoặc kéo dài các đối tượng đồ họa. Ở đây nó thu phóng và dịch gradient sao cho vừa khít bên trong vòng tròn.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Bước 8: tạo RadialGradientPaint
`RadialGradientPaint` tạo một gradient màu dạng tròn dựa trên một điểm trung tâm, bán kính và các điểm màu.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Bước 9: đặt paint và lấp đầy vòng tròn
Áp dụng gradient paint vào tài liệu và lấp đầy vòng tròn đã định nghĩa trước. Đây là phần cốt lõi của **ví dụ gradient dạng tròn** của chúng tôi và minh họa cách **lấp đầy hình dạng bằng gradient**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Bước 10: đóng trang và lưu tài liệu
Hoàn thiện trang, ghi nội dung ra đĩa và đóng luồng. File PostScript của bạn bây giờ đã sẵn sàng để xem bằng bất kỳ trình xem PS nào.

```java
document.closePage();
document.save();
```

Chúc mừng! Bạn đã tạo thành công một ví dụ gradient dạng tròn trong Java PostScript bằng Aspose.Page. Bây giờ bạn có một mẫu có thể tái sử dụng cho **lấp đầy hình dạng bằng gradient** có thể được áp dụng cho các hình dạng và định dạng đầu ra khác.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|---------|----------|
| **FileNotFoundException** khi mở luồng đầu ra | Xác minh rằng `dataDir` trỏ tới một thư mục tồn tại và bạn có quyền ghi. |
| Gradient trông phẳng hoặc thiếu | Đảm bảo mảng `fractions` có độ dài bằng mảng `colors` và `AffineTransform` được thu phóng đúng. |
| Màu sắc xuất hiện ngược | Đổi thứ tự các màu trong mảng `colors` hoặc điều chỉnh tọa độ điểm `focus`. |

## Câu hỏi thường gặp

**Q: Tôi có thể tìm tài liệu cho Aspose.Page for Java ở đâu?**  
A: Tham khảo đầy đủ API có sẵn trong [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).

**Q: Làm sao tôi có thể tải Aspose.Page for Java?**  
A: Tải JAR mới nhất từ [releases page](https://releases.aspose.com/page/java/).

**Q: Có bản dùng thử miễn phí không?**  
A: Có—tải phiên bản dùng thử từ [Aspose free trial download page](https://releases.aspose.com/).

**Q: Tôi có thể nhận giấy phép tạm thời để thử nghiệm không?**  
A: Chắc chắn, yêu cầu một giấy phép tạm thời từ [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể nhận hỗ trợ cộng đồng ở đâu?**  
A: Tham gia thảo luận trên [Aspose.Page forum](https://forum.aspose.com/c/page/39).

## Kết luận
Trong hướng dẫn này, chúng tôi đã xây dựng một **ví dụ gradient dạng tròn** hoàn chỉnh cho tài liệu PostScript bằng Aspose.Page for Java. Bằng cách làm theo các bước, bạn hiện có một mẫu có thể tái sử dụng cho **lấp đầy hình dạng bằng gradient**, có thể áp dụng cho PDF, SVG hoặc bất kỳ định dạng nào khác được Aspose.Page hỗ trợ. Hãy thử nghiệm với các màu sắc, bán kính và hình dạng khác nhau để làm phong phú dự án đồ họa Java của bạn.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## Hướng dẫn liên quan

- [Tạo Gradient PostScript trong Java – Thêm Gradient Dọc](/page/java/postscript-gradient-addition/vertical/)
- [Tạo Mẫu Kết Cấu trong PostScript với Aspose.Page for Java](/page/java/postscript-texture-patterns/)
- [Hướng dẫn Độ Trong Suốt Aspose.Page – Thêm Độ Trong Suốt trong Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}