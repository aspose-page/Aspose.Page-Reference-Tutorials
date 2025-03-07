---
title: Đặt mặt nạ độ mờ trong Java XPS
linktitle: Đặt mặt nạ độ mờ trong Java XPS
second_title: API Java Aspose.Page
description: Khám phá sức mạnh của việc thiết lập mặt nạ độ mờ trong Java XPS với Aspose.Page. Hãy làm theo hướng dẫn từng bước của chúng tôi để có trải nghiệm tài liệu được nâng cao về mặt trực quan.
weight: 11
url: /vi/java/xps-transparency/set-opacity-mask/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt mặt nạ độ mờ trong Java XPS

## Giới thiệu
Chào mừng bạn đến với hướng dẫn toàn diện của chúng tôi về cách đặt mặt nạ độ mờ trong Java XPS bằng Aspose.Page. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo tài liệu XPS, thêm khung vẽ và áp dụng mặt nạ độ mờ cho hình chữ nhật bằng cách sử dụng các tính năng mạnh mẽ của Aspose.Page cho Java.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn này, hãy đảm bảo bạn có những điều sau:
- Hiểu biết cơ bản về lập trình Java.
-  Aspose.Page cho thư viện Java đã được cài đặt. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/page/java/).
-  Giấy phép hợp lệ cho Aspose.Page. Nếu bạn không có, bạn có thể xin giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
- Một môi trường phát triển được thiết lập để chạy các ứng dụng Java.
## Gói nhập khẩu
Bắt đầu bằng cách nhập các gói cần thiết vào dự án Java của bạn. Đảm bảo rằng bạn đã tích hợp thư viện Aspose.Page đúng cách. Dưới đây là đoạn trích để hướng dẫn bạn:
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Bây giờ, hãy chia mã ví dụ thành nhiều bước:
## Bước 1: Tạo tài liệu XPS mới
```java
// Tạo một tài liệu XPS mới
XpsDocument doc = new XpsDocument();
```
## Bước 2: Thêm Canvas
```java
// Canvas mới
XpsCanvas canvas = doc.addCanvas();
```
## Bước 3: Thêm hình chữ nhật với Opacity Mask
```java
// Hình chữ nhật ở giữa bên trái với độ mờ được che bởi ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## Bước 4: Đặt mặt nạ độ mờ bằng ImageBrush
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## Bước 5: Lưu tài liệu XPS kết quả
```java
// Lưu tài liệu XPS kết quả
doc.save(dataDir + "OpacityMask_out.xps"); 
```
Hãy thực hiện cẩn thận các bước sau để kết hợp mặt nạ độ mờ vào tài liệu Java XPS của bạn bằng Aspose.Page.
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách đặt mặt nạ độ mờ trong Java XPS bằng Aspose.Page. Tính năng này bổ sung thêm một lớp hình ảnh phong phú cho tài liệu của bạn, khiến chúng trở nên hấp dẫn và năng động hơn.
## Câu hỏi thường gặp
### Aspose.Page có tương thích với tất cả các môi trường phát triển Java không?
Có, Aspose.Page được thiết kế để hoạt động trơn tru với nhiều môi trường phát triển Java khác nhau.
### Tôi có thể sử dụng Aspose.Page mà không cần giấy phép không?
Mặc dù bạn có thể sử dụng Aspose.Page mà không cần giấy phép, nhưng bạn nên có giấy phép để có đầy đủ các tính năng và hỗ trợ.
### Có bất kỳ hạn chế nào đối với phiên bản dùng thử không?
Phiên bản dùng thử có thể có một số hạn chế về tính năng. Đó là khuyến khích để kiểm tra tài liệu để biết chi tiết.
### Làm cách nào tôi có thể nhận được hỗ trợ cho Aspose.Page?
 Bạn có thể ghé thăm[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để được hỗ trợ cộng đồng hoặc mua giấy phép để được hỗ trợ cao cấp.
### Có đảm bảo hoàn lại tiền cho Aspose.Page không?
 Tham khảo đến[trang mua hàng](https://purchase.aspose.com/buy) để biết thông tin về chính sách hoàn trả.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
