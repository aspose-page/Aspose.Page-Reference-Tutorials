---
date: 2026-09-04
description: Tìm hiểu cách thêm gradient trong Java PostScript với Aspose.Page Java,
  tạo chuyển đổi màu chéo bằng LinearGradientPaint cho tài liệu sống động.
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'Cách thêm gradient: gradient chéo trong Java PostScript sử dụng Aspose.Page
  Java'
og_description: Tìm hiểu cách thêm gradient trong Java PostScript bằng Aspose.Page
  Java. Hướng dẫn này cho bạn biết cách tạo gradient chéo với LinearGradientPaint
  chỉ trong vài bước.
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: Cách thêm gradient trong Java PostScript với Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'Cách thêm gradient: gradient chéo trong Java PostScript sử dụng Aspose.Page
  Java'
url: /vi/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm gradient chéo trong Java PostScript bằng Aspose.Page Java

## Giới thiệu
Nếu bạn muốn làm phong phú một tệp PostScript bằng một chuyển đổi màu chéo mượt mà, **Aspose.Page Java** làm cho việc này trở nên bất ngờ dễ dàng. Trong hướng dẫn này, bạn sẽ học **cách thêm gradient** theo từng bước, sử dụng lớp `LinearGradientPaint` từ Java 2D. Khi hoàn thành, bạn sẽ có một đoạn mã sẵn sàng chạy tạo tài liệu PostScript với gradient chéo sống động, và bạn sẽ hiểu tại sao cách tiếp cận này dễ bảo trì hơn so với việc viết tay các lệnh PostScript thô.

## Cách thêm gradient trong Java PostScript
Thêm một gradient có thể nghe như một nhiệm vụ chỉ dành cho đồ họa, nhưng với Aspose.Page bạn có được kiểm soát đầy đủ các lệnh PostScript bên dưới trong khi vẫn làm việc bằng Java thuần. Phần này giải thích tại sao cách tiếp cận này hoạt động và những lợi ích bạn nhận được so với việc viết tay các lệnh PostScript thô.

## Câu trả lời nhanh
- **Thư viện nào được yêu cầu?** Aspose.Page for Java.  
- **Lớp nào tạo gradient?** `LinearGradientPaint`.  
- **Có thể thay đổi màu không?** Có – sửa đổi mảng `Color[]`.  
- **Cần giấy phép cho môi trường sản xuất không?** Cần giấy phép thương mại; bản dùng thử miễn phí có sẵn.  
- **Thời gian triển khai mất bao lâu?** Khoảng 10 phút cho một gradient cơ bản.

## Aspose.Page Java là gì?
Aspose.Page Java là một API đầy đủ tính năng cho phép các nhà phát triển tạo, chỉnh sửa và chuyển đổi các tệp PostScript và PDF mà không cần phần mềm bên ngoài. Thư viện hỗ trợ **hơn 50 định dạng đầu vào và đầu ra** và có thể xử lý tài liệu với **hơn 500 trang** trong khi giữ mức sử dụng bộ nhớ dưới 100 MB.

## Tại sao nên sử dụng gradient chéo?
Gradient chéo tạo độ sâu và thu hút thị giác cho biểu đồ, banner hoặc bất kỳ yếu tố đồ họa nào cần vẻ hiện đại. Vì gradient chạy từ một góc đến góc đối diện, nó phù hợp cho nền, lớp nền nút và các hình dạng trang trí, mang lại kết quả chuyên nghiệp mà không cần tài nguyên hình ảnh bổ sung.

## Yêu cầu trước
- Java Development Kit (JDK) 8 hoặc cao hơn.  
- Một IDE như Eclipse, IntelliJ IDEA, hoặc VS Code.  
- **Thư viện Aspose.Page for Java** – tải phiên bản mới nhất từ [trang tải chính thức](https://releases.aspose.com/page/java/).

## Nhập các gói
Gói `java.awt` cung cấp các lớp đồ họa cốt lõi, trong khi gói `com.aspose.page` cho bạn truy cập vào các API đặc thù của PostScript.

Lớp `LinearGradientPaint` là cầu nối của Aspose.Page tới chức năng gradient của Java 2D.  
`AffineTransform` cho phép xoay và thay đổi tỷ lệ của gradient để nó căn chỉnh theo đường chéo.

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

## Bước 1: tạo luồng đầu ra cho tài liệu PostScript
Đầu tiên, xác định thư mục nơi tệp sẽ được lưu và mở một `FileOutputStream`. Luồng này nhận dữ liệu PostScript được tạo.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Bước 2: tạo tùy chọn lưu với kích thước A4
`PsSaveOptions` cho phép bạn chỉ định kích thước trang, độ phân giải và các cài đặt đầu ra khác. Ở đây chúng ta sử dụng kích thước A4 mặc định, là 595 × 842 điểm ở 72 dpi.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Bước 3: tạo tài liệu PS mới
Lớp `PsDocument` đại diện cho một tài liệu PostScript và cung cấp các phương thức để tạo trang và vẽ đồ họa.  
Khởi tạo một `PsDocument` bằng cách sử dụng luồng đầu ra và các tùy chọn lưu. Cờ `false` thông báo cho hàm khởi tạo không tự động mở một trang mới – chúng ta sẽ làm điều này sau.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Bước 4: tạo hình chữ nhật
Xác định hình chữ nhật sẽ nhận màu gradient. Vị trí của hình chữ nhật (200, 100) và kích thước (200 × 100) được chọn để gradient hiển thị rõ ràng.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Bước 5: tạo biến đổi gradient
`AffineTransform` cho phép chúng ta xoay, thay đổi tỷ lệ và dịch chuyển gradient sao cho nó chạy chéo qua hình chữ nhật. Công thức dưới đây tính độ dài đường chéo và điều chỉnh tỷ lệ phóng đại cho phù hợp.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Bước 6: tạo gradient tuyến tính chéo
`LinearGradientPaint` là lớp cốt lõi tạo ra chuyển đổi màu. Nó trải dài từ góc trên‑trái của hình chữ nhật đến góc dưới‑phải, sử dụng biến đổi đã định nghĩa trước. `MultipleGradientPaint.CycleMethod.NO_CYCLE` đảm bảo gradient không lặp lại.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Bước 7: đặt paint và tô hình chữ nhật
Áp dụng gradient paint vào tài liệu và tô hình chữ nhật. Bước này vẽ chuyển đổi màu chéo lên trang PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Bước 8: đóng trang hiện tại và lưu tài liệu
Cuối cùng, đóng trang, xả luồng và lưu tệp. Tệp `DiagonalGradient_outPS.ps` kết quả có thể mở bằng bất kỳ trình xem PostScript nào.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Các vấn đề thường gặp & mẹo
- **Gradient xuất hiện phẳng** – kiểm tra lại góc xoay; góc xoay 45° tạo ra đường chéo thực sự.  
- **Màu sắc trông nhạt** – đảm bảo bạn đang sử dụng `MultipleGradientPaint.ColorSpaceType.SRGB` để hiển thị màu chính xác.  
- **Lỗi không tìm thấy tệp** – xác minh rằng `dataDir` trỏ tới một thư mục tồn tại và ứng dụng có quyền ghi.  
- **Tài liệu lớn gây tăng đột biến bộ nhớ** – sử dụng `PsSaveOptions.setCompress(true)` để giảm lượng bộ nhớ tiêu thụ.

## Câu hỏi thường gặp

**H: Tôi có thể sử dụng thư viện này cho các thao tác đồ họa khác trong Java không?**  
C: Có, Aspose.Page for Java cung cấp đầy đủ các primitive vẽ, render văn bản và khả năng xử lý hình ảnh.

**H: Có bản dùng thử miễn phí cho Aspose.Page Java không?**  
C: Chắc chắn. Bạn có thể tải bản dùng thử đầy đủ chức năng từ [trang dùng thử miễn phí của Aspose](https://releases.aspose.com/).

**H: Tôi có thể tìm tài liệu cho Aspose.Page Java ở đâu?**  
C: Tham chiếu API chính thức có sẵn tại [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**H: Làm thế nào để mua giấy phép cho Aspose.Page Java?**  
C: Giấy phép có thể mua trực tiếp từ [cổng mua Aspose](https://purchase.aspose.com/buy).

**H: Cần hỗ trợ hoặc có câu hỏi?**  
C: Truy cập diễn đàn cộng đồng [Aspose.Page forum](https://forum.aspose.com/c/page/39) để nhận trợ giúp từ các kỹ sư Aspose và các nhà phát triển khác.

---

**Cập nhật lần cuối:** 2026-09-04  
**Đã kiểm tra với:** Aspose.Page for Java 24.12 (latest)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo Gradient Hình Tròn trong PostScript với Aspose.Page cho Java](/page/java/postscript-gradient-addition/)
- [Cách Thêm Gradient trong Java PostScript bằng Linear Gradient Paint](/page/java/postscript-gradient-addition/horizontal/)
- [Tạo Gradient PostScript trong Java – Thêm Gradient Dọc](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}