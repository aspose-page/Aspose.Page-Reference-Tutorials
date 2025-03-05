---
title: Thêm hình chữ nhật trong Java XPS
linktitle: Thêm hình chữ nhật trong Java XPS
second_title: API Java Aspose.Page
description: Tìm hiểu cách thêm hình chữ nhật trong Java XPS bằng Aspose.Page. Thực hiện theo hướng dẫn từng bước của chúng tôi để thao tác tài liệu liền mạch. #JavaXPS #AsposePage
type: docs
weight: 11
url: /vi/java/xps-shapes/add-rectangle/
---
## Giới thiệu
Chào mừng bạn đến với hướng dẫn toàn diện về cách thêm hình chữ nhật trong Java XPS bằng Aspose.Page! Cho dù bạn là nhà phát triển dày dạn hay mới bắt đầu với Java XPS, hướng dẫn này sẽ hướng dẫn bạn qua quy trình với hướng dẫn từng bước, đảm bảo bạn hiểu sâu về chủ đề.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Kiến thức cơ bản về ngôn ngữ lập trình Java.
-  Đã cài đặt thư viện Aspose.Page. Nếu không, bạn có thể tải xuống từ[Tài liệu Java Aspose.Page](https://reference.aspose.com/page/java/).
- Một môi trường phát triển Java đang hoạt động.
## Gói nhập khẩu
Để bắt đầu, hãy nhập các gói cần thiết vào dự án Java của bạn. Đảm bảo rằng thư viện Aspose.Page được thêm chính xác vào đường dẫn lớp của bạn. Đây là một ví dụ cơ bản:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
Bây giờ, hãy chia ví dụ được cung cấp thành nhiều bước để thêm hình chữ nhật trong Java XPS.
## Bước 1: Đặt thư mục tài liệu
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
```
Thay thế "Thư mục tài liệu của bạn" bằng đường dẫn đến thư mục bạn muốn.
## Bước 2: Tạo tài liệu XPS mới
```java
// Tạo tài liệu XPS mới
XpsDocument doc = new XpsDocument();
```
Điều này khởi tạo một tài liệu XPS mới.
## Bước 3: Thêm hình chữ nhật có nét đồng màu CMYK
```java
// Hình chữ nhật có nét đồng màu CMYK (xanh lam) ở phía dưới bên trái
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Bước này thêm một hình chữ nhật có nét với màu đồng nhất CMYK.
## Bước 4: Lưu tài liệu XPS kết quả
```java
// Lưu tài liệu XPS kết quả
doc.save(dataDir + "AddRectangle_out.xps");
```
Cuối cùng, lưu tài liệu XPS đã sửa đổi với hình chữ nhật được thêm vào.
Lặp lại các bước này, điều chỉnh các tham số nếu cần để tùy chỉnh thêm hình chữ nhật của bạn.
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách thêm hình chữ nhật trong Java XPS bằng Aspose.Page. Hướng dẫn này cung cấp nền tảng vững chắc cho nỗ lực thao tác tài liệu XPS của bạn.
## Câu hỏi thường gặp
### Tôi có thể thêm nhiều hình chữ nhật vào một tài liệu XPS không?
Có, bạn có thể thêm bao nhiêu hình chữ nhật nếu cần bằng cách lặp lại các bước được nêu trong hướng dẫn.
### Làm cách nào để thay đổi màu của hình chữ nhật?
 Sửa đổi giá trị màu trong`createColor` phương pháp để đạt được màu sắc mong muốn.
### Aspose.Page có phù hợp để xử lý các thao tác tài liệu XPS phức tạp không?
Tuyệt đối! Aspose.Page cung cấp một bộ tính năng mạnh mẽ để xử lý các tác vụ tài liệu XPS khác nhau.
### Tôi có thể tìm thêm ví dụ và hỗ trợ ở đâu?
 Khám phá cái[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39)để biết thêm ví dụ và tìm kiếm sự hỗ trợ từ cộng đồng.
### Tôi có thể dùng thử Aspose.Page trước khi mua không?
 Có, bạn có thể khám phá một[dùng thử miễn phí](https://releases.aspose.com/) để trải nghiệm các khả năng của Aspose.Page.