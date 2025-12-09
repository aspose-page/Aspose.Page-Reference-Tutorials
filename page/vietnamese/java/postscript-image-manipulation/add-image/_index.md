---
date: 2025-12-09
description: Tìm hiểu cách tạo tài liệu PostScript bằng Java và dịch chuyển, xoay
  hình ảnh bằng Aspose.Page để thao tác hình ảnh một cách liền mạch.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Tạo tài liệu PostScript bằng Java – Thêm hình ảnh trong PostScript Java
url: /vi/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Tài liệu PostScript Java – Thêm Hình ảnh trong PostScript Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách **tạo một tài liệu PostScript Java** và nhúng hình ảnh bằng thư viện Aspose.Page for Java. Chúng tôi sẽ hướng dẫn từng bước, từ việc thiết lập tài liệu đến áp dụng các biến đổi như **dịch và xoay hình ảnh**. Khi hoàn thành, bạn sẽ có thể tạo các tệp PostScript phong phú một cách lập trình và tùy chỉnh vị trí hình ảnh sao cho phù hợp với bố cục mong muốn.

## Câu trả lời nhanh
- **Thư viện cần thiết là gì?** Aspose.Page for Java  
- **Có thể thêm nhiều hình ảnh không?** Có – lặp lại các bước biến đổi và vẽ  
- **Có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; cần giấy phép cho môi trường sản xuất  
- **Phiên bản Java nào được hỗ trợ?** Java 8 trở lên  
- **Có hỗ trợ xoay hình ảnh không?** Chắc chắn – sử dụng `AffineTransform.rotate()`  

## Tạo tài liệu PostScript trong Java là gì?
Một tài liệu PostScript là tệp ngôn ngữ mô tả trang, chứa thông tin về văn bản, đồ họa và hình ảnh. Sử dụng Aspose.Page, bạn có thể tạo ra các tệp này một cách lập trình trong Java, cho phép kiểm soát toàn diện bố cục, trạng thái đồ họa và xử lý hình ảnh mà không cần một trình thông dịch PostScript.

## Tại sao nên sử dụng Aspose.Page cho việc xử lý hình ảnh?
- **API cấp cao:** Đơn giản hoá các lệnh PostScript phức tạp.  
- **Đa nền tảng:** Hoạt động trên bất kỳ hệ điều hành nào hỗ trợ Java.  
- **Kiểm soát trạng thái đồ họa đầy đủ:** Dễ dàng lưu, khôi phục, dịch, co giãn và xoay đồ họa.  
- **Không phụ thuộc bên ngoài:** Xử lý tải và chuyển đổi hình ảnh nội bộ.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- Java Development Kit (JDK) được cài đặt trên hệ thống.  
- Thư viện Aspose.Page for Java. Bạn có thể tải xuống [tại đây](https://releases.aspose.com/page/java/).  
- Kiến thức cơ bản về lập trình Java.  

## Nhập các gói
Để bắt đầu, nhập các gói cần thiết vào dự án Java của bạn. Sử dụng đoạn mã mẫu dưới đây làm tham chiếu:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Bước 1: Ghi Lệnh Lưu Đồ họa
Bước đầu tiên là ghi lệnh lưu đồ họa vào tài liệu. Điều này đảm bảo rằng bất kỳ biến đổi hoặc sửa đổi nào được thực hiện sau này có thể được hoàn tác nếu cần.

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

## Bước 2: Dịch và Biến đổi (dịch và xoay hình ảnh)
Tiếp theo, dịch tài liệu và tạo một đối tượng `BufferedImage` từ tệp hình ảnh. Áp dụng một loạt các biến đổi như co giãn và xoay bằng `AffineTransform`. Đây là nơi thực hiện thao tác **dịch và xoay hình ảnh**.

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

## Bước 3: Thêm Hình ảnh vào Tài liệu
Bây giờ, thêm hình ảnh đã được biến đổi vào tài liệu.

```java
document.drawImage(image, transform, null);
```

## Bước 4: Ghi Lệnh Khôi phục Đồ họa
Sau khi thêm hình ảnh, ghi lệnh khôi phục đồ họa để hoàn thiện các thay đổi đã thực hiện.

```java
document.writeGraphicsRestore();
```

## Bước 5: Đóng Trang Hiện tại và Lưu
Đóng trang hiện tại và lưu tài liệu.

```java
document.closePage();
document.save();
```

Bạn có thể lặp lại các bước này để thêm nhiều hình ảnh hoặc tùy chỉnh các biến đổi dựa trên yêu cầu của mình.

## Các vấn đề thường gặp và giải pháp
- **FileNotFoundException:** Đảm bảo đường dẫn `dataDir` kết thúc bằng ký tự phân tách thư mục (`/` hoặc `\\`) và tên tệp hình ảnh khớp chính xác.  
- **ImageIO.read trả về null:** Kiểm tra định dạng hình ảnh có được hỗ trợ không (ví dụ: JPEG, PNG).  
- **Góc xoay không đúng:** `AffineTransform.rotate` yêu cầu góc tính bằng radian. Chuyển đổi độ sang radian (`Math.toRadians(degrees)`) nếu cần.  

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Page for Java với các ngôn ngữ lập trình khác không?**  
A: Aspose.Page chủ yếu hỗ trợ Java, nhưng cũng có các phiên bản cho các ngôn ngữ lập trình khác.

**Q: Có bản dùng thử miễn phí cho Aspose.Page for Java không?**  
A: Có, bạn có thể truy cập bản dùng thử [tại đây](https://releases.aspose.com/).

**Q: Làm sao để lấy giấy phép tạm thời cho Aspose.Page for Java?**  
A: Bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể tìm cộng đồng hỗ trợ và thảo luận về Aspose.Page for Java ở đâu?**  
A: Ghé thăm [Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để nhận hỗ trợ từ cộng đồng.

**Q: Có nguồn tài nguyên nào khác để mua Aspose.Page for Java không?**  
A: Bạn có thể mua thư viện [tại đây](https://purchase.aspose.com/buy).

## Kết luận
Chúc mừng! Bạn đã học cách **tạo một tài liệu PostScript Java** và nhúng hình ảnh bằng Aspose.Page for Java. Khám phá [tài liệu hướng dẫn](https://reference.aspose.com/page/java/) để tìm hiểu các tính năng nâng cao hơn, như đồ họa vector, render văn bản và kích thước trang tùy chỉnh.

---

**Cập nhật lần cuối:** 2025-12-09  
**Đã kiểm tra với:** Aspose.Page for Java 23.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}