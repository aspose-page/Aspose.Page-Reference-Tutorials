---
title: Làm chủ các gradient xuyên tâm trong Java PostScript với Aspose.Page
linktitle: Làm chủ các gradient xuyên tâm trong Java
second_title: API Java Aspose.Page
description: Tìm hiểu cách thêm độ dốc xuyên tâm tuyệt đẹp trong Java PostScript bằng cách sử dụng Aspose.Page cho Java. Nâng cao tài liệu PostScript của bạn bằng hướng dẫn từng bước này.
weight: 12
url: /vi/java/postscript-gradient-addition/radial1/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Làm chủ các gradient xuyên tâm trong Java PostScript với Aspose.Page

## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước của chúng tôi về cách thêm gradient xuyên tâm trong Java PostScript bằng Aspose.Page. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo tài liệu PostScript với độ dốc xuyên tâm đẹp mắt. Aspose.Page cho Java là một thư viện mạnh mẽ cho phép bạn làm việc liền mạch với các tệp PostScript.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Bộ công cụ phát triển Java (JDK): Đảm bảo rằng bạn đã cài đặt Java trên hệ thống của mình.
-  Aspose.Page dành cho Java: Tải xuống và cài đặt thư viện Aspose.Page từ[đây](https://releases.aspose.com/page/java/).
- Môi trường phát triển tích hợp (IDE): Chọn Java IDE ưa thích của bạn, chẳng hạn như Eclipse hoặc IntelliJ.
## Gói nhập khẩu
Bắt đầu bằng cách nhập các gói cần thiết để bắt đầu với dự án Java PostScript của bạn:
```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Bước 1: Tạo hình chữ nhật
Hãy bắt đầu bằng cách tạo một hình chữ nhật trong tài liệu PostScript của chúng ta:
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo luồng đầu ra cho tài liệu PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Tạo tùy chọn lưu với khổ A4
PsSaveOptions options = new PsSaveOptions();
// Tạo Tài liệu PS mới với trang đã mở
PsDocument document = new PsDocument(outPsStream, options, false);
//Tạo một hình chữ nhật
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```
## Bước 2: Xác định màu sắc và phân số
Xác định mảng màu và phân số cho gradient xuyên tâm:
```java
// Tạo mảng màu và phân số cho gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```
## Bước 3: Tạo sơn chuyển màu xuyên tâm
Tạo một lớp sơn gradient xuyên tâm cho hình chữ nhật:
```java
// Tạo sơn gradient xuyên tâm
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(300, 200), 100, new Point2D.Float(300, 200),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Bước 4: Đặt màu và tô màu cho hình chữ nhật
Đặt màu và tô hình chữ nhật với gradient xuyên tâm:
```java
// Đặt sơn
document.setPaint(paint);
// Điền vào hình chữ nhật
document.fill(rectangle);
```
## Bước 5: Đóng và lưu
Cuối cùng, đóng trang hiện tại và lưu tài liệu:
```java
// Đóng trang hiện tại
document.closePage();
// Lưu tài liệu
document.save();
```
Điều này hoàn tất quá trình thêm gradient xuyên tâm vào tài liệu Java PostScript của bạn bằng Aspose.Page.
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách nâng cao tài liệu PostScript của mình bằng các gradient xuyên tâm bằng Aspose.Page cho Java. Thử nghiệm với các màu sắc và cấu hình khác nhau để tạo hiệu ứng hình ảnh ấn tượng.
## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Page cho Java trong các dự án thương mại không?
 Có, bạn có thể sử dụng Aspose.Page cho Java trong các dự án thương mại. Để biết chi tiết cấp phép, hãy truy cập[đây](https://purchase.aspose.com/buy).
### Tôi có thể tìm tài liệu về Aspose.Page cho Java ở đâu?
 Tài liệu có sẵn[đây](https://reference.aspose.com/page/java/).
### Có bản dùng thử miễn phí không?
 Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Làm thế nào tôi có thể nhận được giấy phép tạm thời?
 Nhận giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Cần sự hỗ trợ của cộng đồng?
 Tham gia cộng đồng Aspose.Page[diễn đàn](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
