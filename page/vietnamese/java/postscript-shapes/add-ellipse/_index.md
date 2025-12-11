---
date: 2025-12-11
description: Tìm hiểu cách tạo hình ellipse PostScript trong Java bằng Aspose.Page.
  Hướng dẫn từng bước này cho bạn biết cách tô màu cho ellipse và vẽ ellipse bằng
  Java.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Cách tạo elip PostScript trong Java bằng Aspose.Page
url: /vi/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo hình elip PostScript trong Java với Aspose.Page

## Giới thiệu
Việc tạo **hình elip PostScript** một cách lập trình cho phép bạn kiểm soát chi tiết các đồ họa vector trong báo cáo, hoá đơn hoặc bất kỳ tài liệu có thể in nào. Trong hướng dẫn này, bạn sẽ học cách **tạo hình elip PostScript** bằng thư viện Aspose.Page cho Java, tô màu cho một elip và vẽ viền cho elip. Khi hoàn thành, bạn sẽ sẵn sàng nhúng đồ họa tùy chỉnh trực tiếp vào đầu ra PostScript của mình.

## Câu trả lời nhanh
- **Thư viện nào là tốt nhất để vẽ đồ họa PostScript trong Java?** Aspose.Page for Java.  
- **Tôi có thể tô màu đồng nhất cho một elip không?** Có – sử dụng `document.setPaint(Color.YOUR_COLOR)` trước `fill`.  
- **Làm thế nào để chỉ vẽ viền của một elip?** Đặt màu và stroke, sau đó gọi `document.draw(...)`.  
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Cần giấy phép thương mại; giấy phép tạm thời có sẵn để thử nghiệm.  
- **Phiên bản Java nào được hỗ trợ?** Bất kỳ môi trường chạy Java 8+ nào cũng hoạt động với phiên bản Aspose.Page hiện tại.

## Hình elip PostScript là gì?
Hình elip PostScript là một hình dạng vector được định nghĩa bằng một hình chữ nhật bao quanh. Không giống như hình ảnh raster, nó có thể phóng to mà không mất chất lượng, làm cho nó lý tưởng cho việc in ấn độ phân giải cao và chuyển đổi sang PDF.

## Tại sao nên dùng Aspose.Page để tạo hình elip PostScript?
- **Kiểm soát đầy đủ** các primitive vẽ (đường thẳng, đường cong, elip).  
- **Đa nền tảng** – hoạt động trên Windows, Linux và macOS.  
- **Không phụ thuộc bên ngoài** – API Java thuần, không có mã gốc.  
- **Dễ dàng tích hợp** với các ứng dụng Java hiện có và công cụ xây dựng.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn có:

1. Môi trường phát triển Java hoạt động (JDK 8 hoặc mới hơn).  
2. Thư viện Aspose.Page cho Java được thêm vào dự án của bạn. Bạn có thể tải xuống **[tại đây](https://releases.aspose.com/page/java/)**.  

## Nhập gói
Trong tệp nguồn Java của bạn, nhập các lớp cần thiết để vẽ và lưu nội dung PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Hướng dẫn từng bước

### Bước 1: Thiết lập tài liệu PostScript
Tạo một luồng đầu ra, cấu hình kích thước trang và khởi tạo một `PsDocument`.

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

### Bước 2: Tô màu cho elip
Đặt màu vẽ thành màu tô mong muốn và gọi `fill` với một thể hiện `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Bước 3: Vẽ viền elip với stroke
Chuyển màu vẽ sang màu stroke, định nghĩa một `BasicStroke` cho độ dày đường, và vẽ viền elip.

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

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Bây giờ bạn đã có một tệp PostScript chứa hai elip — một elip được tô màu cam và một elip khác có viền màu đỏ. Hãy tự do thử nghiệm với các tọa độ, kích thước và màu sắc khác nhau để phù hợp với nhu cầu thiết kế của bạn.

## Những khó khăn thường gặp và khắc phục
- **Đường dẫn tệp không đúng** – Đảm bảo `dataDir` kết thúc bằng dấu phân cách (`/` hoặc `\\`) phù hợp với hệ điều hành của bạn.  
- **Thiếu giấy phép** – Nếu không có giấy phép hợp lệ, thư viện sẽ chạy ở chế độ đánh giá và có thể thêm watermark.  
- **Màu không được áp dụng** – Hãy nhớ đặt `document.setPaint(...)` *trước* mỗi lệnh `fill` hoặc `draw`; cài đặt màu không tự động duy trì qua các thao tác riêng biệt.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Page cho Java cùng với các thư viện Java khác không?**  
A: Có, Aspose.Page cho Java được thiết kế để tích hợp liền mạch với các thư viện Java khác.

**Q: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Page cho Java?**  
A: Nhận giấy phép tạm thời **[tại đây](https://purchase.aspose.com/temporary-license/)** để thử nghiệm.

**Q: Aspose.Page có phù hợp cho các dự án thương mại không?**  
A: Chắc chắn! Truy cập **[tại đây](https://purchase.aspose.com/buy)** để khám phá các tùy chọn giấy phép cho việc sử dụng thương mại.

**Q: Tôi có thể tìm trợ giúp hoặc thảo luận các câu hỏi liên quan đến Aspose.Page ở đâu?**  
A: Tham gia cộng đồng tại **[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39)** để thảo luận và nhận hỗ trợ.

**Q: Có tài nguyên miễn phí nào để tìm hiểu thêm về Aspose.Page cho Java không?**  
A: Sử dụng **[bản dùng thử miễn phí](https://releases.aspose.com/)** và khám phá các ví dụ trong tài liệu.

## Kết luận
Aspose.Page cho Java giúp bạn dễ dàng **tạo hình elip PostScript**, dù bạn cần một hình dạng đơn giản được tô màu hay một viền phức tạp. Với các bước ở trên, bạn có thể nhanh chóng thêm đồ họa vector cấp chuyên nghiệp vào bất kỳ tài liệu có thể in nào. Để khám phá sâu hơn — chẳng hạn như kết hợp nhiều hình dạng, áp dụng gradient, hoặc chuyển đổi sang PDF — hãy tham khảo **[tài liệu chính thức](https://reference.aspose.com/page/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2025-12-11  
**Được kiểm tra với:** Aspose.Page for Java 24.11  
**Tác giả:** Aspose