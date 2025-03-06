---
title: Thêm hình ảnh lát gạch trong Java XPS
linktitle: Thêm hình ảnh lát gạch trong Java XPS
second_title: API Java Aspose.Page
description: Khám phá thao tác tài liệu Java XPS liền mạch với Aspose.Page. Tìm hiểu cách thêm hình ảnh xếp chồng một cách dễ dàng bằng hướng dẫn từng bước này.
weight: 11
url: /vi/java/xps-image-manipulation/add-tiled-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm hình ảnh lát gạch trong Java XPS

## Giới thiệu
Trong thế giới năng động của phát triển Java, nhu cầu thao tác và tạo tài liệu hiệu quả ngày càng tăng. Aspose.Page dành cho Java nổi lên như một công cụ mạnh mẽ, cung cấp cho các nhà phát triển khả năng làm việc liền mạch với các tài liệu XPS. Hướng dẫn này tập trung vào một tác vụ cụ thể – thêm hình ảnh xếp kề vào tài liệu Java XPS.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo rằng bạn có sẵn các điều kiện tiên quyết sau:
1. Bộ công cụ phát triển Java (JDK): Đảm bảo bạn đã cài đặt JDK trên hệ thống của mình.
2.  Aspose.Page cho Java: Tải xuống và cài đặt Aspose.Page cho Java từ[trang mạng](https://releases.aspose.com/page/java/).
3. Thư mục tài liệu của bạn: Chọn hoặc tạo thư mục nơi bạn muốn lưu tài liệu XPS của mình.
## Gói nhập khẩu
Trong dự án Java của bạn, hãy nhập các gói cần thiết để sử dụng các chức năng của Aspose.Page:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Bây giờ, hãy chia nhỏ quy trình thêm hình ảnh xếp kề vào tài liệu Java XPS thành các bước rõ ràng, dễ quản lý.
## Bước 1: Thiết lập dự án của bạn
Bắt đầu bằng cách thiết lập dự án Java của bạn, đảm bảo rằng Aspose.Page for Java được tích hợp đúng cách.
## Bước 2: Tạo tài liệu XPS
Khởi tạo một tài liệu XPS mới bằng mã sau:
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
// Tạo tài liệu XPS mới
XpsDocument doc = new XpsDocument();
```
## Bước 3: Xác định đường dẫn hình ảnh xếp kề
Chỉ định đường dẫn đến hình ảnh xếp kề mà bạn muốn thêm vào tài liệu XPS.
## Bước 4: Thêm hình ảnh xếp cạnh
Sử dụng đoạn mã bên dưới để thêm hình ảnh xếp kề vào tài liệu XPS:
```java
// Hình ảnh ngói
// Hình chữ nhật đầy ImageBrush ở trên cùng bên phải bên dưới
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## Bước 5: Lưu tài liệu
Cuối cùng, lưu tài liệu XPS thu được bằng mã bên dưới:
```java
// Lưu tài liệu XPS kết quả
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Lặp lại các bước này để dễ dàng kết hợp hình ảnh xếp kề vào tài liệu Java XPS của bạn bằng Aspose.Page.
## Phần kết luận
Aspose.Page dành cho Java hợp lý hóa quy trình làm việc với tài liệu XPS, cung cấp cho nhà phát triển giải pháp hiệu quả để thao tác tài liệu. Bằng cách làm theo hướng dẫn từng bước này, bạn có thể dễ dàng thêm hình ảnh xếp kề vào tài liệu Java XPS của mình.

## Câu hỏi thường gặp
### Aspose.Page có tương thích với tất cả các phiên bản Java không?
 Aspose.Page được thiết kế để hoạt động với nhiều phiên bản Java khác nhau. Đảm bảo tính tương thích bằng cách kiểm tra tài liệu[đây](https://reference.aspose.com/page/java/).
### Tôi có thể sử dụng Aspose.Page cho các dự án thương mại không?
Có, Aspose.Page cung cấp giấy phép thương mại. Mua chúng[đây](https://purchase.aspose.com/buy).
### Có bản dùng thử miễn phí không?
 Có, khám phá các tính năng của Aspose.Page với bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Tôi có thể tìm sự hỗ trợ và thảo luận của cộng đồng ở đâu?
 Tương tác với cộng đồng Aspose.Page trên[diễn đàn](https://forum.aspose.com/c/page/39).
### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page?
 Nhận giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
