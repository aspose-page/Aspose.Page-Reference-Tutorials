---
title: Thêm chuyển màu dọc trong Java PostScript
linktitle: Thêm chuyển màu dọc trong Java PostScript
second_title: API Java Aspose.Page
description: Khám phá hướng dẫn từng bước để thêm độ dốc dọc trong Java PostScript với Aspose.Page cho Java. Dễ dàng nâng cao tài liệu của bạn bằng hình ảnh sống động.
type: docs
weight: 14
url: /vi/java/postscript-gradient-addition/vertical/
---
## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước này về cách thêm dải màu dọc trong Java PostScript bằng Aspose.Page cho Java. Nếu bạn muốn cải thiện tài liệu của mình bằng các chuyển màu bắt mắt, hướng dẫn này là dành cho bạn. Aspose.Page dành cho Java cung cấp các công cụ mạnh mẽ để thao tác các tài liệu PostScript một cách liền mạch.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên máy của bạn.
-  Aspose.Page cho thư viện Java. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/page/java/).
## Gói nhập khẩu
Trong dự án Java của bạn, hãy nhập các gói cần thiết để bắt đầu:
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
Bây giờ, hãy chia nhỏ quá trình thêm dải màu dọc trong Java PostScript thành nhiều bước.
## Bước 1: Thiết lập thư mục tài liệu của bạn
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
```
## Bước 2: Tạo luồng đầu ra cho tài liệu PostScript
```java
// Tạo luồng đầu ra cho tài liệu PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```
## Bước 3: Tạo tùy chọn lưu với khổ A4
```java
// Tạo tùy chọn lưu với khổ A4
PsSaveOptions options = new PsSaveOptions();
```
## Bước 4: Tạo tài liệu PS mới
```java
// Tạo Tài liệu PS mới với trang đã mở
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Bước 5: Tạo hình chữ nhật
```java
//Tạo một hình chữ nhật
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Bước 6: Thiết lập màu sắc và phân số cho gradient
```java
// Tạo mảng màu sắc và phân số cho gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```
## Bước 7: Tạo chuyển đổi gradient
```java
// Tạo phép biến đổi gradient. Các thành phần tỷ lệ trong phép biến đổi phải bằng chiều rộng và chiều cao của hình chữ nhật.
// Các thành phần dịch là phần bù của hình chữ nhật.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Xoay gradient 90 độ xung quanh điểm gốc
transform.rotate(90 * (Math.PI / 180));
```
## Bước 8: Tạo sơn chuyển màu tuyến tính dọc
```java
// Tạo sơn gradient tuyến tính dọc.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Bước 9: Đặt màu và tô màu cho hình chữ nhật
```java
// Đặt sơn
document.setPaint(paint);
// Điền vào hình chữ nhật
document.fill(rectangle);
```
## Bước 10: Đóng trang hiện tại và lưu tài liệu
```java
// Đóng trang hiện tại
document.closePage();
// Lưu tài liệu
document.save();
```
Chúc mừng! Bạn đã thêm thành công dải màu dọc vào tài liệu Java PostScript bằng Aspose.Page cho Java.
## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá quy trình nâng cao tài liệu của bạn bằng các dải màu dọc sống động bằng cách sử dụng Aspose.Page cho Java. Giờ đây, bạn có thể đưa các thao tác tài liệu của mình lên một tầm cao mới bằng cách kết hợp các hình ảnh tuyệt đẹp.
## Các câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Page cho Java với các thư viện Java khác không?
Có, Aspose.Page dành cho Java được thiết kế để hoạt động liền mạch với các thư viện Java khác.
### Có bản dùng thử miễn phí cho Aspose.Page cho Java không?
 Có, bạn có thể dùng thử miễn phí[đây](https://releases.aspose.com/).
### Tôi có thể tìm tài liệu bổ sung ở đâu?
 Tài liệu chi tiết có sẵn[đây](https://reference.aspose.com/page/java/).
### Làm cách nào tôi có thể mua Aspose.Page cho Java?
 Bạn có thể mua Aspose.Page cho Java[đây](https://purchase.aspose.com/buy).
### Có diễn đàn nào để thảo luận về Aspose.Page không?
 Có, bạn có thể tham gia diễn đàn cộng đồng[đây](https://forum.aspose.com/c/page/39).