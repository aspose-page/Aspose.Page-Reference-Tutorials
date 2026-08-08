---
date: 2026-05-05
description: Tìm hiểu cách thêm các mẫu lặp kết cấu vào tài liệu PostScript bằng Aspose.Page
  cho Java. Hướng dẫn này cho thấy cách thêm kết cấu một cách hiệu quả và khám phá
  các khả năng sáng tạo.
keywords:
- how to add texture
- fill shape with texture
- fill rectangle with texture
linktitle: Thêm mẫu lát kết cấu trong Java PostScript
second_title: Aspose.Page Java API
title: Cách Thêm Mẫu Lát Kết Cấu trong Java PostScript
url: /vi/java/postscript-texture-patterns/add-texture-tiling-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Mẫu Lát Kết Cấu trong Java PostScript

## Giới thiệu
Trong lĩnh vực phát triển Java, việc học **cách thêm kết cấu** vào tài liệu PostScript là một yêu cầu phổ biến. Aspose.Page for Java làm cho nhiệm vụ này trở nên đơn giản, cho phép bạn tập trung vào thiết kế thay vì cú pháp PostScript mức thấp. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn từng bước cần thiết để thêm mẫu lát kết cấu, tô hình và thậm chí áp dụng kết cấu cho văn bản trong tài liệu Java PostScript.

## Câu trả lời nhanh
- **Thư viện cần thiết?** Aspose.Page for Java  
- **Từ khóa chính mà hướng dẫn này nhắm tới?** *how to add texture*  
- **Có cần giấy phép để thử nghiệm không?** Có bản dùng thử miễn phí; giấy phép cần thiết cho môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 hoặc cao hơn.  
- **Có thể tái sử dụng cọ kết cấu cho nhiều hình không?** Có – tạo `TexturePaint` một lần và áp dụng cho bất kỳ hình nào.  
- **Làm thế nào để tô một hình chữ nhật bằng kết cấu?** Sử dụng `document.fill(shape)` sau khi đặt `TexturePaint` làm màu vẽ hiện tại.

## Mẫu lát kết cấu là gì?
Mẫu lát kết cấu là một hình ảnh nhỏ (gạch) được lặp lại trên một khu vực lớn hơn, cho phép bạn **tô hình bằng kết cấu** mà không cần vẽ từng gạch một cách thủ công. Kỹ thuật này lý tưởng cho nền, tô màu và hiệu ứng văn bản trang trí trong PostScript.

## Tại sao sử dụng Aspose.Page cho Java?
- **Kết xuất không phụ thuộc** – không cần trình thông dịch PostScript bên ngoài.  
- **Kiểm soát đầy đủ đồ họa** – kết hợp các hình dạng vector, văn bản và kết cấu bitmap.  
- **Đa nền tảng** – hoạt động trên bất kỳ hệ điều hành nào hỗ trợ Java.  

## Yêu cầu trước
Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn đã chuẩn bị các yêu cầu sau:
- Hiểu biết cơ bản về ngôn ngữ lập trình Java.  
- Quen thuộc với cấu trúc tài liệu PostScript.  
- Thư viện Aspose.Page for Java đã được cài đặt. Bạn có thể tải xuống [đây](https://releases.aspose.com/page/java/).

## Nhập gói
Bắt đầu bằng việc nhập các gói cần thiết cho dự án Java của bạn:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Cách Thêm Mẫu Lát Kết Cấu trong Java PostScript
Dưới đây là hướng dẫn từng bước. Mỗi bước bao gồm một giải thích ngắn gọn và sau đó là đoạn mã chính xác mà bạn cần sao chép.

### Bước 1: Tạo tài liệu PostScript
Bắt đầu bằng việc tạo một tài liệu PostScript mới, chỉ định luồng đầu ra và các tùy chọn lưu. Đảm bảo bạn đã cấu hình các đường dẫn cần thiết.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddTextureTilingPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Bước 2: Thiết lập môi trường đồ họa
Dịch gốc tọa độ đến vị trí thuận tiện và tải bitmap sẽ dùng làm gạch kết cấu.

```java
document.writeGraphicsSave();
document.translate(200, 100);
// Create a BufferedImage object from image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestTexture.bmp"));
```

### Bước 3: Tạo cọ kết cấu
Định nghĩa một `TexturePaint` lặp lại bitmap trên toàn bộ khu vực của hình. Điều chỉnh kích thước hình chữ nhật nếu bạn muốn gạch xuất hiện lớn hơn hoặc nhỏ hơn.

```java
// Create image area doubled in width
Rectangle2D.Float imageArea = new Rectangle2D.Float(0, 0, image.getWidth() * 2, image.getHeight());
// Create texture brush from the image
TexturePaint paint = new TexturePaint(image, imageArea);
```

### Bước 4: Vẽ và tô hình
Tạo một hình chữ nhật và **tô hình chữ nhật bằng kết cấu** bằng cọ. Sau đó vẽ viền cho hình để kết quả rõ ràng hơn.

```java
// Create rectangle
Rectangle2D.Float shape = new Rectangle2D.Float(0, 0, 200, 100);
// Set this texture brush as current paint
document.setPaint(paint);
// Fill rectangle
document.fill(shape);
document.setPaint(Color.RED);
document.setStroke(new BasicStroke(2));
document.draw(shape);
```

### Bước 5: Thêm văn bản với mẫu kết cấu
Bạn cũng có thể áp dụng cùng một kết cấu cho các glyph văn bản. Điều này minh họa **cách tô kết cấu** lên các ký tự trong khi vẫn có thể vẽ viền chúng.

```java
// Fill the text with the texture pattern
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
// Outline the text with the texture pattern
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

### Bước 6: Lưu và Đóng
Cuối cùng, đóng trang, lưu tài liệu và giải phóng tài nguyên.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Các vấn đề thường gặp & Mẹo
- **Thiếu tệp kết cấu** – Kiểm tra đường dẫn tới `TestTexture.bmp` có đúng và tệp có thể truy cập được.  
- **Kích thước hình ảnh không đúng** – Nếu kết cấu bị kéo dài, điều chỉnh `imageArea` để khớp với kích thước gốc của hình ảnh.  
- **Hiệu suất** – Tái sử dụng cùng một thể hiện `TexturePaint` cho nhiều hình để tránh tạo đối tượng không cần thiết.  
- **Mẹo chuyên nghiệp:** Sử dụng bitmap độ phân giải cao cho gạch để giữ kết cấu sắc nét khi phóng to.

## Câu hỏi thường gặp

**Q: Aspose.Page cho Java có phù hợp cho người mới bắt đầu không?**  
A: Chắc chắn! Aspose.Page cho Java cung cấp tài liệu đầy đủ, giúp nó dễ tiếp cận cho các nhà phát triển ở mọi trình độ.

**Q: Tôi có thể tích hợp Aspose.Page cho Java vào dự án Java hiện có của mình không?**  
A: Có, bạn có thể dễ dàng tích hợp Aspose.Page cho Java vào dự án của mình bằng cách theo dõi tài liệu được cung cấp [đây](https://reference.aspose.com/page/java/).

**Q: Tôi có thể tìm hỗ trợ hoặc thảo luận các câu hỏi liên quan đến Aspose.Page ở đâu?**  
A: Truy cập [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để giao lưu với cộng đồng và nhận hỗ trợ.

**Q: Có bản dùng thử miễn phí cho Aspose.Page cho Java không?**  
A: Có, bạn có thể khám phá bản dùng thử miễn phí [đây](https://releases.aspose.com/).

**Q: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Page cho Java?**  
A: Truy cập [liên kết này](https://purchase.aspose.com/temporary-license/) để nhận giấy phép tạm thời.

## Kết luận
Chúc mừng! Bạn đã học thành công **cách thêm kết cấu** các mẫu lát vào tài liệu Java PostScript bằng Aspose.Page cho Java. Hãy tự do thử nghiệm với các gạch bitmap khác nhau, các hệ số tỷ lệ và các thao tác hợp thành để khai thác tối đa tiềm năng sáng tạo của việc tô kết cấu.

---

**Last Updated:** 2026-05-05  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}