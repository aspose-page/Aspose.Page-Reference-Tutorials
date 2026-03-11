---
date: 2026-02-18
description: Học cách thiết lập màu vẽ và tạo một hình ellipse PostScript trong Java
  bằng Aspose.Page. Hướng dẫn này chỉ cách tô đầy ellipse trong Java, vẽ đường viền
  ellipse và thiết lập độ dày nét.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Thiết lập màu vẽ để vẽ hình elip PostScript trong Java
url: /vi/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt màu sơn để vẽ hình elip PostScript trong Java

## Giới thiệu
Nếu bạn cần **đặt màu sơn** khi vẽ đồ họa vector, thư viện Aspose.Page for Java cung cấp cho bạn toàn quyền kiểm soát mọi nét vẽ và tô màu. Trong hướng dẫn này, bạn sẽ khám phá cách **đặt màu sơn**, **điền elip Java**, và **vẽ viền elip** bằng một quy trình đơn giản, từng bước một. Khi hoàn thành, bạn sẽ có thể thêm các hình elip PostScript chất lượng cao vào hoá đơn, báo cáo, hoặc bất kỳ tài liệu có thể in nào.

## Trả lời nhanh
- **Thư viện nào là tốt nhất để vẽ đồ họa PostScript trong Java?** Aspose.Page for Java.  
- **Tôi có thể điền một elip bằng màu đồng nhất không?** Có – sử dụng `document.setPaint(Color.YOUR_COLOR)` trước khi `fill`.  
- **Làm sao để chỉ vẽ viền của một elip?** Đặt màu sơn và stroke, sau đó gọi `document.draw(...)`.  
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Cần giấy phép thương mại; giấy phép tạm thời có sẵn cho mục đích thử nghiệm.  
- **Phiên bản Java nào được hỗ trợ?** Bất kỳ môi trường chạy Java 8+ nào cũng hoạt động với phiên bản Aspose.Page hiện tại.

## Elip PostScript là gì?
Elip PostScript là một hình dạng vector được định nghĩa bởi một hình chữ nhật bao quanh. Khác với hình ảnh raster, nó có thể phóng to mà không mất chất lượng, rất thích hợp cho việc in độ phân giải cao và chuyển đổi sang PDF.

## Tại sao nên dùng Aspose.Page để tạo elip PostScript?
- **Kiểm soát đầy đủ** các primitive vẽ (đường thẳng, đường cong, elip).  
- **Đa nền tảng** – hoạt động trên Windows, Linux và macOS.  
- **Không phụ thuộc bên ngoài** – API thuần Java, không có mã gốc.  
- **Dễ tích hợp** với các ứng dụng Java hiện có và công cụ xây dựng.

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn có:

1. Môi trường phát triển Java hoạt động (JDK 8 trở lên).  
2. Thư viện Aspose.Page for Java đã được thêm vào dự án của bạn. Bạn có thể tải xuống **[tại đây](https://releases.aspose.com/page/java/)**.  

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

## Cách đặt màu sơn cho một elip
Đặt màu sơn là bước đầu tiên trước bất kỳ thao tác điền hoặc nét vẽ nào. Phương thức `setPaint` xác định màu sẽ được sử dụng cho lệnh vẽ tiếp theo.

### Bước 1: Thiết lập tài liệu PostScript
Tạo luồng xuất, cấu hình kích thước trang, và khởi tạo một `PsDocument`.

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

### Bước 2: Cách điền elip – sử dụng set paint color
Để **điền elip**, bạn phải gọi `setPaint` với màu điền mong muốn, sau đó gọi `fill` với một đối tượng `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Bước 3: Vẽ viền elip và đặt độ dày stroke
Sau khi điền, bạn có thể thay đổi màu sơn sang màu khác, định nghĩa một `BasicStroke` để kiểm soát độ rộng đường, và vẽ viền elip.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Bước 4: Đóng và lưu tài liệu
Hoàn tất trang và ghi tệp PostScript ra đĩa.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Bây giờ bạn đã có một tệp PostScript chứa hai elip — một elip được điền màu cam và một elip khác có viền màu đỏ. Hãy tự do thử nghiệm với các tọa độ, kích thước và màu sắc khác nhau để phù hợp với nhu cầu thiết kế của bạn.

## Những lỗi thường gặp và cách khắc phục
- **Đường dẫn tệp không đúng** – Đảm bảo `dataDir` kết thúc bằng dấu phân cách (`/` hoặc `\\`) phù hợp với hệ điều hành của bạn.  
- **Thiếu giấy phép** – Nếu không có giấy phép hợp lệ, thư viện sẽ chạy ở chế độ đánh giá và có thể thêm watermark.  
- **Màu không được áp dụng** – Hãy nhớ gọi `document.setPaint(...)` *trước* mỗi lệnh `fill` hoặc `draw`; cài đặt màu không tự động kéo dài qua các thao tác riêng biệt.

## Câu hỏi thường gặp

**H: Tôi có thể dùng Aspose.Page for Java cùng với các thư viện Java khác không?**  
Đ: Có, Aspose.Page for Java được thiết kế để tích hợp liền mạch với các thư viện Java khác.

**H: Làm sao để lấy giấy phép tạm thời cho Aspose.Page for Java?**  
Đ: Nhận giấy phép tạm thời **[tại đây](https://purchase.aspose.com/temporary-license/)** để thử nghiệm.

**H: Aspose.Page có phù hợp cho các dự án thương mại không?**  
Đ: Hoàn toàn! Truy cập **[tại đây](https://purchase.aspose.com/buy)** để khám phá các tùy chọn giấy phép cho việc sử dụng thương mại.

**H: Tôi có thể tìm kiếm trợ giúp hoặc thảo luận các câu hỏi liên quan đến Aspose.Page ở đâu?**  
Đ: Tham gia cộng đồng tại **[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39)** để thảo luận và nhận hỗ trợ.

**H: Có tài nguyên miễn phí nào để học thêm về Aspose.Page for Java không?**  
Đ: Sử dụng **[bản dùng thử miễn phí](https://releases.aspose.com/)** và khám phá các ví dụ trong tài liệu.

## Kết luận
Aspose.Page for Java giúp bạn dễ dàng **đặt màu sơn**, **điền elip**, và **vẽ viền elip** — dù bạn cần một hình dạng đơn giản được tô màu hay một đồ họa phức tạp có nét vẽ. Với các bước ở trên, bạn có thể nhanh chóng thêm các đồ họa vector cấp chuyên nghiệp vào bất kỳ tài liệu có thể in nào. Để khám phá sâu hơn — như kết hợp nhiều hình dạng, áp dụng gradient, hoặc chuyển đổi sang PDF — hãy tham khảo **[tài liệu chính thức](https://reference.aspose.com/page/java/)**.

---

**Cập nhật lần cuối:** 2026-02-18  
**Kiểm tra với:** Aspose.Page for Java 24.11  
**Tác giả:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}