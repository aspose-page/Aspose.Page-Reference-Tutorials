---
date: 2026-09-04
description: Tìm hiểu cách tạo gradient ngang java trong tệp PostScript bằng Linear
  Gradient Paint Java với Aspose.Page cho Java. Mã từng bước, các lỗi thường gặp và
  câu hỏi thường gặp.
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: Tạo gradient ngang java trong PostScript bằng Aspose
og_description: Tạo gradient ngang java trong PostScript với Linear Gradient Paint
  Java. Hướng dẫn Aspose.Page này cho bạn các bước chính xác, các điều kiện tiên quyết
  và mẹo khắc phục sự cố trong vòng chưa tới 15 phút.
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: Tạo gradient ngang java trong PostScript bằng Aspose
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: Tạo gradient ngang java trong PostScript bằng Aspose
url: /vi/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thêm gradient ngang trong Java PostScript bằng Linear Gradient Paint

## Giới thiệu
Trong hướng dẫn toàn diện này, bạn sẽ học **cách tạo gradient ngang java** trong tài liệu PostScript bằng cách sử dụng lớp **Linear Gradient Paint Java** đi kèm với Aspose.Page for Java. Chúng tôi sẽ hướng dẫn từng bước — từ thiết lập dự án đến việc vẽ gradient trên cả hình dạng và văn bản — để bạn có thể tạo ra đồ họa hoàn thiện, sẵn sàng in chỉ trong vài phút. Dù bạn đang xây dựng một công cụ báo cáo, một công cụ tự động thiết kế, hay một driver máy in tùy chỉnh, hướng dẫn này cung cấp cho bạn đoạn mã chính xác cần thiết.

## Câu trả lời nhanh
- **Thư viện nào được yêu cầu?** Aspose.Page for Java (includes Linear Gradient Paint Java).  
- **Thời gian triển khai mất bao lâu?** Khoảng 10‑15 phút cho một gradient ngang cơ bản.  
- **Tôi có cần giấy phép không?** Cần một giấy phép tạm thời hoặc đầy đủ cho việc sử dụng trong môi trường sản xuất.  
- **Phiên bản JDK nào hoạt động?** Java 8 hoặc mới hơn.  
- **Tôi có thể sử dụng gradient cho cả hình dạng và văn bản không?** Có – cùng một đối tượng `LinearGradientPaint` có thể tô hình và được áp dụng cho nét viền hoặc tô màu văn bản.

## Gradient ngang là gì và tại sao sử dụng nó?
Gradient ngang pha trộn các màu từ cạnh trái của đối tượng sang cạnh phải, tạo ra một chuyển đổi mượt mà giúp tăng độ sâu và thu hút thị giác. Nó lý tưởng cho các thành phần UI hiện đại, tiêu đề được làm nổi bật, hoặc các lớp nền nhẹ nhàng trong các báo cáo PDF hoặc PostScript. Sử dụng **Linear Gradient Paint Java** cho phép bạn kiểm soát chính xác màu bắt đầu và kết thúc, độ trong suốt và tỷ lệ, đảm bảo kết quả sắc nét trên bất kỳ thiết bị hoặc máy in nào.

## Yêu cầu trước
Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn đã có những thứ sau:

- Java Development Kit (JDK) được cài đặt trên máy của bạn.  
- Thư viện Aspose.Page for Java. Bạn có thể tải xuống từ [tài liệu Aspose.Page Java](https://reference.aspose.com/page/java/).

## Nhập các gói
Bắt đầu bằng việc nhập các gói cần thiết vào dự án Java của bạn. Các import này cho phép bạn truy cập vào các primitive đồ họa, xử lý gradient và API của Aspose.Page.

Lớp `PsDocument` đại diện cho một tài liệu PostScript mà bạn có thể vẽ đồ họa lên.

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

## Bước 1: tạo hình chữ nhật
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

## Bước 2: tạo gradient paint tuyến tính ngang
`LinearGradientPaint` là lớp cốt lõi định nghĩa chuyển đổi màu tuyến tính.  
Lớp `LinearGradientPaint` đại diện cho một đối tượng paint vẽ gradient dọc theo một đường thẳng; bạn chỉ định các điểm bắt đầu/kết thúc, các điểm dừng màu, và một `AffineTransform` tùy chọn để tỷ lệ nó với hình dạng của bạn.

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

## Bước 3: tô hình chữ nhật
Bây giờ tô hình chữ nhật bằng gradient mà chúng ta vừa định nghĩa.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Bước 4: tô văn bản bằng gradient
Bạn cũng có thể áp dụng cùng một gradient cho văn bản, tạo hiệu ứng hình ảnh ấn tượng.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Bước 5: viền văn bản bằng gradient
Cuối cùng, tạo viền cho văn bản bằng cách sử dụng gradient làm màu nét.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| Gradient bị kéo dài | Tỷ lệ `AffineTransform` không đúng | Đảm bảo chiều rộng và chiều cao của transform khớp với kích thước của hình chữ nhật (200 × 100 trong ví dụ). |
| Màu sắc trông nhạt | Giá trị alpha được đặt quá thấp | Tăng thành phần alpha (giá trị thứ tư trong `new Color(r,g,b,alpha)`). |
| Văn bản không hiển thị | Paint chưa được thiết lập trước khi vẽ văn bản | Gọi `document.setPaint(paint)` **trước** bất kỳ lệnh `fillAndStrokeText` hoặc `outlineText` nào. |

## Câu hỏi thường gặp
**Q:** Bạn có thể sử dụng Aspose.Page for Java trong các dự án thương mại không?  
**A:** Có, Aspose.Page for Java có thể được sử dụng trong các dự án thương mại. Để biết chi tiết giấy phép, hãy truy cập trang [Aspose.Purchase](https://purchase.aspose.com/buy).

**Q:** Có bản dùng thử miễn phí không?  
**A:** Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.Page for Java trên trang [Aspose.Page for Java free trial](https://releases.aspose.com/).

**Q:** Tôi có thể tìm tài liệu và hỗ trợ bổ sung ở đâu?  
**A:** Truy cập [tài liệu Aspose.Page Java](https://reference.aspose.com/page/java/) để có nguồn tài nguyên toàn diện. Đối với trợ giúp cộng đồng, kiểm tra [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39).

**Q:** Làm thế nào để tôi có được giấy phép tạm thời?  
**A:** Bạn có thể nhận giấy phép tạm thời từ [trang giấy phép tạm thời Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

**Q:** Yêu cầu hệ thống cho Aspose.Page for Java là gì?  
**A:** Tham khảo [tài liệu Aspose.Page Java](https://reference.aspose.com/page/java/) để biết yêu cầu hệ thống chi tiết.

---

**Cập nhật lần cuối:** 2026-09-04  
**Đã kiểm tra với:** Aspose.Page for Java 24.11  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo Gradient PostScript trong Java – Thêm Gradient Dọc](/page/java/postscript-gradient-addition/vertical/)
- [Cách Thêm Gradient: Gradient Đường chéo trong Java PostScript bằng Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Tạo Gradient PostScript – Gradient Tâm trong Java](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}