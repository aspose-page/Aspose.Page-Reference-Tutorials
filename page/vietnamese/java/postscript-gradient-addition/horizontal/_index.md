---
title: Thêm chuyển màu ngang trong Java PostScript
linktitle: Thêm chuyển màu ngang trong Java PostScript
second_title: API Java Aspose.Page
description: Tìm hiểu cách thêm dải màu ngang trong Java PostScript bằng Aspose.Page cho Java. Tạo các tài liệu trực quan tuyệt đẹp một cách dễ dàng.
weight: 11
url: /vi/java/postscript-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm chuyển màu ngang trong Java PostScript

## Giới thiệu
Chào mừng bạn đến với hướng dẫn toàn diện này về cách thêm dải màu ngang trong Java PostScript bằng Aspose.Page cho Java. Aspose.Page là một thư viện Java mạnh mẽ cho phép các nhà phát triển làm việc với PostScript và các định dạng tài liệu khác. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo tài liệu PostScript có dải màu ngang bằng cách sử dụng các ví dụ từng bước.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên máy của bạn.
- Aspose.Page cho thư viện Java. Bạn có thể tải nó xuống từ[Tài liệu Java Aspose.Page](https://reference.aspose.com/page/java/).
## Gói nhập khẩu
Bắt đầu bằng cách nhập các gói cần thiết vào dự án Java của bạn. Các gói này rất quan trọng để làm việc với Aspose.Page.
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
## Bước 1: Tạo hình chữ nhật
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo luồng đầu ra cho tài liệu PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Tạo tùy chọn lưu với khổ A4
PsSaveOptions options = new PsSaveOptions();
// Tạo Tài liệu PS mới với trang đã mở
PsDocument document = new PsDocument(outPsStream, options, false);
//Tạo một hình chữ nhật
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Bước 2: Tạo sơn chuyển màu tuyến tính ngang
```java
// Tạo sơn gradient tuyến tính ngang. Các thành phần tỷ lệ trong phép biến đổi phải bằng chiều rộng và chiều cao của hình chữ nhật.
// Các thành phần dịch là phần bù của hình chữ nhật.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Đặt sơn
document.setPaint(paint);
```
## Bước 3: Tô màu hình chữ nhật
```java
// Điền vào hình chữ nhật
document.fill(rectangle);
```
## Bước 4: Tô màu văn bản bằng gradient
```java
// Điền vào văn bản với độ dốc
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Bước 5: Tạo nét cho văn bản bằng gradient
```java
// Tạo nét cho văn bản bằng gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Phần kết luận
Chúc mừng! Bạn đã thêm thành công dải màu ngang trong Java PostScript bằng Aspose.Page cho Java. Hướng dẫn này cung cấp cho bạn hướng dẫn chi tiết từng bước để giúp bạn tạo các tài liệu PostScript hấp dẫn về mặt hình ảnh.
## Các câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Page cho Java trong các dự án thương mại không?
Có, Aspose.Page for Java có thể được sử dụng trong các dự án thương mại. Để biết chi tiết cấp phép, hãy truy cập[Aspose.Purchase](https://purchase.aspose.com/buy).
### Có bản dùng thử miễn phí không?
 Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.Page cho Java[đây](https://releases.aspose.com/).
### Tôi có thể tìm thêm tài liệu và hỗ trợ ở đâu?
 Tham quan[Tài liệu Java Aspose.Page](https://reference.aspose.com/page/java/) để có nguồn tài nguyên toàn diện. Để được cộng đồng hỗ trợ, hãy kiểm tra[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39).
### Làm thế nào tôi có thể có được giấy phép tạm thời?
 Bạn có thể xin giấy phép tạm thời từ[Aspose.Purchase](https://purchase.aspose.com/temporary-license/).
### Yêu cầu hệ thống đối với Aspose.Page cho Java là gì?
 Tham khảo đến[tài liệu](https://reference.aspose.com/page/java/) để biết các yêu cầu chi tiết của hệ thống.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
