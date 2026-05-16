---
date: 2026-02-15
description: Tìm hiểu cách tạo tài liệu PostScript bằng Java và tạo các tệp tài liệu
  PostScript với việc dịch chuyển và xoay hình ảnh bằng Aspose.Page cho Java.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Tạo PostScript bằng Java – Thêm ảnh vào PostScript Java
url: /vi/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo PostScript Java – Thêm Hình Ảnh trong Java PostScript

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách **create postscript java** tài liệu và nhúng hình ảnh bằng thư viện Aspose.Page for Java. Chúng tôi sẽ hướng dẫn từng bước, từ khởi tạo một tệp PostScript mới đến việc áp dụng các biến đổi **translate and rotate image**. Khi hoàn thành, bạn sẽ có thể tạo tệp PostScript một cách lập trình và kiểm soát vị trí hình ảnh với độ chính xác pixel‑perfect — lý tưởng cho báo cáo tự động, quy trình in ấn, hoặc bất kỳ tình huống nào bạn cần **generate postscript document** từ Java.

## Câu trả lời nhanh
- **What library is required?** Aspose.Page for Java  
- **Can I add multiple images?** Yes – repeat the transform and draw steps  
- **Do I need a license for development?** A free trial works for testing; a license is required for production  
- **Which Java version is supported?** Java 8 and later  
- **Is image rotation supported?** Absolutely – use `AffineTransform.rotate()`

## Create postscript java là gì?
Một thao tác **create postscript java** tạo ra một tệp mô tả trang PostScript chứa văn bản, đồ họa vector và hình ảnh raster. Với Aspose.Page, bạn có thể xây dựng các tệp này trực tiếp từ mã Java, cho phép kiểm soát hoàn toàn về bố cục, tỷ lệ và quay mà không cần trình thông dịch PostScript riêng.

## Tại sao nên sử dụng Aspose.Page để thao tác hình ảnh?
- **High‑level API:** Trừu tượng các lệnh PostScript cấp thấp thành các phương thức Java đơn giản.  
- **Cross‑platform:** Chạy trên bất kỳ hệ điều hành nào hỗ trợ Java.  
- **Full graphics‑state control:** Lưu, khôi phục, dịch, tỷ lệ và quay đồ họa theo ý muốn.  
- **No external dependencies:** Xử lý tải hình ảnh, chuyển đổi định dạng và nhúng nội bộ.

## Yêu cầu trước
- Bộ công cụ phát triển Java (JDK) đã được cài đặt trên hệ thống của bạn.  
- Thư viện Aspose.Page for Java. Bạn có thể tải xuống [tại đây](https://releases.aspose.com/page/java/).  
- Kiến thức cơ bản về lập trình Java.  

## Nhập khẩu các gói
Để bắt đầu, nhập các gói cần thiết vào dự án Java của bạn. Sử dụng đoạn mã sau làm tham khảo:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Bước 1: Ghi Lệnh Lưu Đồ Họa
Bước đầu tiên là ghi lệnh lưu đồ họa vào tài liệu. Điều này đảm bảo bất kỳ biến đổi hoặc sửa đổi nào thực hiện sau này có thể được hoàn tác nếu cần.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## Bước 2: Dịch và Biến Đổi (translate and rotate image)
Tiếp theo, dịch tài liệu và tạo một đối tượng `BufferedImage` từ tệp hình ảnh. Áp dụng một loạt các biến đổi như tỷ lệ và quay bằng `AffineTransform`. Đây là nơi thực hiện thao tác **translate and rotate image**.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## Bước 3: Thêm Hình Ảnh vào Tài Liệu
Bây giờ, thêm hình ảnh đã biến đổi vào tài liệu.

```java
document.drawImage(image, transform, null);
```

## Bước 4: Ghi Lệnh Khôi Phục Đồ Họa
Sau khi thêm hình ảnh, ghi lệnh khôi phục đồ họa để hoàn thiện các thay đổi đã thực hiện.

```java
document.writeGraphicsRestore();
```

## Bước 5: Đóng Trang Hiện Tại và Lưu
Đóng trang hiện tại và lưu tài liệu.

```java
document.closePage();
document.save();
```

Bạn có thể lặp lại các bước này để thêm nhiều hình ảnh hoặc tùy chỉnh các biến đổi dựa trên yêu cầu của mình.

## Các Vấn Đề Thường Gặp và Giải Pháp
- **FileNotFoundException:** Đảm bảo đường dẫn `dataDir` kết thúc bằng dấu phân cách thư mục (`/` hoặc `\\`) và tên tệp hình ảnh khớp chính xác.  
- **ImageIO.read returns null:** Kiểm tra định dạng hình ảnh có được hỗ trợ không (ví dụ: JPEG, PNG).  
- **Incorrect rotation angle:** `AffineTransform.rotate` yêu cầu góc tính bằng radian. Chuyển đổi độ sang radian (`Math.toRadians(degrees)`) nếu cần.  

## Câu Hỏi Thường Gặp

**Q: Tôi có thể sử dụng Aspose.Page for Java với các ngôn ngữ lập trình khác không?**  
A: Aspose.Page chủ yếu hỗ trợ Java, nhưng cũng có các phiên bản cho các ngôn ngữ lập trình khác.

**Q: Có bản dùng thử miễn phí cho Aspose.Page for Java không?**  
A: Có, bạn có thể truy cập bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

**Q: Làm thế nào để lấy giấy phép tạm thời cho Aspose.Page for Java?**  
A: Bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể tìm hỗ trợ cộng đồng và các cuộc thảo luận liên quan đến Aspose.Page for Java ở đâu?**  
A: Ghé thăm [Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để nhận hỗ trợ cộng đồng.

**Q: Có tài nguyên bổ sung nào để mua Aspose.Page for Java không?**  
A: Bạn có thể mua thư viện [tại đây](https://purchase.aspose.com/buy).

## Kết luận
Chúc mừng! Bạn đã học cách **create postscript java** tài liệu và nhúng hình ảnh bằng Aspose.Page for Java. Khám phá [tài liệu](https://reference.aspose.com/page/java/) để biết thêm các tính năng và chức năng nâng cao, chẳng hạn như đồ họa vector, render văn bản và kích thước trang tùy chỉnh.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}