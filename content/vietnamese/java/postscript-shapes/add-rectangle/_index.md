---
title: Tùy chỉnh Java PostScript - Thêm hình chữ nhật với Aspose.Page
linktitle: Thêm hình chữ nhật trong Java PostScript
second_title: API Java Aspose.Page
description: Khám phá hướng dẫn từng bước về cách thêm hình chữ nhật sống động vào tài liệu Java PostScript bằng Aspose.Page cho Java. Tăng cường tùy chỉnh tài liệu của bạn một cách dễ dàng!
type: docs
weight: 11
url: /vi/java/postscript-shapes/add-rectangle/
---
## Giới thiệu
Bạn đang tìm cách nâng cao tài liệu Java PostScript của mình bằng các hình chữ nhật sống động? Đừng tìm đâu xa! Trong hướng dẫn từng bước này, chúng ta sẽ khám phá cách sử dụng Aspose.Page cho Java để thêm hình chữ nhật vào tài liệu PostScript của bạn. Aspose.Page là một thư viện mạnh mẽ cung cấp các tính năng mạnh mẽ để làm việc với các tệp PostScript, khiến nó trở thành lựa chọn lý tưởng cho các nhà phát triển đang tìm cách thao tác và tùy chỉnh tài liệu của họ.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Hiểu biết cơ bản về lập trình Java.
-  Aspose.Page cho thư viện Java đã được cài đặt. Nếu không, hãy tải xuống từ[Aspose.Page cho tài liệu Java](https://reference.aspose.com/page/java/).
- Môi trường phát triển Java được thiết lập trên máy của bạn.
## Gói nhập khẩu
Trong dự án Java của bạn, hãy bắt đầu bằng cách nhập các gói cần thiết:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Hướng dẫn: Thêm hình chữ nhật trong Java PostScript
## Bước 1: Đặt màu tô cho hình chữ nhật
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo luồng đầu ra cho tài liệu PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Tạo tùy chọn lưu với khổ A4
PsSaveOptions options = new PsSaveOptions();
// Tạo Tài liệu PS mới với trang đã mở
PsDocument document = new PsDocument(outPsStream, options, false);
// Đặt sơn để tô hình chữ nhật
document.setPaint(Color.ORANGE);        
// Điền vào hình chữ nhật đầu tiên
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## Bước 2: Đặt màu cho hình chữ nhật vuốt ve
```java
// Đặt sơn cho hình chữ nhật vuốt ve
document.setPaint(Color.RED);
// Đặt nét
document.setStroke(new BasicStroke(3));
// Stroke (phác thảo) hình chữ nhật thứ hai
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## Bước 3: Đóng trang hiện tại và lưu tài liệu
```java
// Đóng trang hiện tại
document.closePage();
// Lưu tài liệu
document.save();
```
Chúc mừng! Bạn đã thêm thành công các hình chữ nhật sống động vào tài liệu Java PostScript của mình bằng Aspose.Page.
## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá quy trình nâng cao tài liệu Java PostScript của bạn bằng hình chữ nhật bằng cách sử dụng Aspose.Page cho Java. Thư viện mạnh mẽ này mở ra một thế giới khả năng cho các nhà phát triển đang tìm cách tùy chỉnh và thao tác tài liệu của họ một cách dễ dàng.
Hãy vui vẻ thử nghiệm với các hình dạng và màu sắc khác nhau để làm cho tài liệu của bạn trở nên hấp dẫn về mặt hình ảnh!
## Các câu hỏi thường gặp

### Tôi có thể sử dụng Aspose.Page cho Java với các ngôn ngữ lập trình khác không?
Aspose.Page chủ yếu hỗ trợ Java, nhưng các thư viện tương tự cũng có sẵn cho các ngôn ngữ khác.
### Có phiên bản dùng thử của Aspose.Page cho Java không?
 Có, bạn có thể khám phá các tính năng của Aspose.Page dành cho Java bằng[phiên bản dùng thử miễn phí](https://releases.aspose.com/).
### Tôi có thể tìm thêm trợ giúp và thảo luận ở đâu?
 Tham quan[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để hòa nhập với cộng đồng và nhận được sự trợ giúp.
### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page cho Java?
 Nhận giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Tôi có thể mua phiên bản Aspose.Page được cấp phép cho Java ở đâu?
 Mua phiên bản được cấp phép[đây](https://purchase.aspose.com/buy).