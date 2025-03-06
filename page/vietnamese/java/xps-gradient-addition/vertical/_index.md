---
title: Thêm gradient dọc trong Java XPS
linktitle: Thêm gradient dọc trong Java XPS
second_title: API Java Aspose.Page
description: Tìm hiểu cách thêm dải màu dọc vào tài liệu Java XPS bằng Aspose.Page. Tăng cường sự hấp dẫn thị giác một cách dễ dàng. Hướng dẫn từng bước bên trong.
weight: 12
url: /vi/java/xps-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm gradient dọc trong Java XPS

## Giới thiệu
Trong hướng dẫn này, chúng ta sẽ khám phá cách thêm gradient dọc trong Java XPS bằng Aspose.Page cho Java. Việc thêm độ chuyển màu vào tài liệu XPS có thể nâng cao sức hấp dẫn trực quan cho nội dung của bạn, khiến nội dung đó trở nên hấp dẫn và thẩm mỹ hơn.
## Điều kiện tiên quyết
Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Một môi trường phát triển Java đang hoạt động.
-  Aspose.Page cho thư viện Java. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/page/java/).
- Hiểu biết cơ bản về lập trình Java.
## Gói nhập khẩu
Bắt đầu bằng cách nhập các gói cần thiết cho dự án Java của bạn. Đảm bảo rằng bạn đã đưa thư viện Aspose.Page dành cho Java vào các phần phụ thuộc của dự án.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
        
// Nhập Aspose.Page cho Java
```
## Bước 1: Khởi tạo tài liệu
Bắt đầu bằng cách khởi tạo tài liệu XPS. Điều này đặt nền tảng cho việc thêm các phần tử như đường dẫn và độ dốc vào tài liệu của bạn.
```java
// Khởi tạo tài liệu
XpsDocument doc = new XpsDocument();
```
## Bước 2: Tạo đường dẫn với độ dốc dọc
Bây giờ, hãy tạo một đường dẫn có độ dốc dọc. Điều này liên quan đến việc xác định hình dạng đường dẫn và chỉ định các điểm dừng chuyển màu.
```java
// Tạo một đường dẫn với hình học
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Xác định điểm dừng gradient dọc
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//Áp dụng gradient dọc cho đường dẫn
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Bước 3: Lưu tài liệu
Cuối cùng, lưu tài liệu XPS có thêm gradient dọc vào thư mục bạn muốn.
```java
// Lưu tài liệu
doc.save(dataDir + "VerticalGradient.xps");
```
Chúc mừng! Bạn đã thêm thành công dải màu dọc vào tài liệu Java XPS của mình bằng Aspose.Page.
## Phần kết luận
Cải thiện tài liệu XPS của bạn bằng độ chuyển màu có thể cải thiện đáng kể sức hấp dẫn trực quan của chúng. Aspose.Page dành cho Java đơn giản hóa quy trình này, cho phép bạn tạo các tài liệu tuyệt đẹp một cách dễ dàng.

### Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Page cho Java trong các dự án thương mại không?
 Có, Aspose.Page dành cho Java có sẵn cho mục đích thương mại. Bạn có thể mua nó[đây](https://purchase.aspose.com/buy).
### Có bản dùng thử miễn phí cho Aspose.Page cho Java không?
 Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/).
### Tôi có thể tìm tài liệu về Aspose.Page cho Java ở đâu?
 Tài liệu có sẵn[đây](https://reference.aspose.com/page/java/).
### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page cho Java?
 Nhận giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Cần giúp hoặc có câu hỏi?
 Truy cập cộng đồng Aspose.Page[diễn đàn](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
