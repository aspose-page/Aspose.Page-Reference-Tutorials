---
title: Thêm độ dốc ngang trong Java XPS
linktitle: Thêm độ dốc ngang trong Java XPS
second_title: API Java Aspose.Page
description: Tìm hiểu cách thêm dải màu ngang tuyệt đẹp vào tài liệu XPS trong Java bằng Aspose.Page. Hãy làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch.
type: docs
weight: 11
url: /vi/java/xps-gradient-addition/horizontal/
---
## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước này về cách thêm dải màu ngang trong Java XPS bằng Aspose.Page cho Java. Aspose.Page cho Java là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc liền mạch với các tài liệu XPS (Đặc tả giấy XML).
Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo ứng dụng Java để thêm dải màu chuyển màu ngang vào tài liệu XPS. Hãy làm theo các bước dưới đây để đạt được điều này một cách dễ dàng.
## Điều kiện tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
1. Môi trường phát triển Java: Đảm bảo rằng bạn đã cài đặt Java trên hệ thống của mình. Nếu không, hãy tải xuống và cài đặt phiên bản Java mới nhất từ[java.com](https://www.java.com).
2.  Aspose.Page for Java Library: Bạn cần có thư viện Aspose.Page for Java. Bạn có thể tải nó xuống từ[Aspose.Page cho tài liệu Java](https://reference.aspose.com/page/java/).
## Gói nhập khẩu
Bắt đầu bằng cách nhập các gói cần thiết cho ứng dụng Java của bạn. Đưa thư viện Aspose.Page cho Java vào dự án của bạn. Bạn có thể làm điều này bằng cách thêm các dòng mã sau:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## Bước 1: Khởi tạo tài liệu
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
//Khởi tạo tài liệu
XpsDocument doc = new XpsDocument();
```
## Bước 2: Tạo gradient ngang
```java
// Độ dốc ngang
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## Bước 3: Thêm đường dẫn với gradient
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## Bước 4: Lưu tài liệu
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
Lặp lại các bước này nếu cần, điều chỉnh các tham số dựa trên yêu cầu cụ thể của bạn.
## Phần kết luận
Chúc mừng! Bạn đã thêm thành công dải màu ngang vào tài liệu XPS bằng Aspose.Page cho Java. Hướng dẫn này cung cấp hướng dẫn toàn diện cho các nhà phát triển đang tìm cách nâng cao ứng dụng Java của họ bằng hiệu ứng chuyển màu.
## Câu hỏi thường gặp
### Câu hỏi: Tôi có thể áp dụng nhiều dải màu trong một tài liệu XPS không?
Có, bạn có thể thêm nhiều đường dẫn với độ dốc khác nhau để tạo ra các thiết kế phức tạp.
### Câu hỏi: Aspose.Page có tương thích với các phiên bản Java mới nhất không?
Aspose.Page dành cho Java được cập nhật thường xuyên để đảm bảo khả năng tương thích với các bản phát hành Java mới nhất.
### Câu hỏi: Có các loại chuyển màu khác có sẵn trong Aspose.Page không?
Có, bên cạnh các gradient tuyến tính, Aspose.Page còn hỗ trợ các gradient xuyên tâm để có các hiệu ứng đa dạng hơn.
### Câu hỏi: Tôi có thể tùy chỉnh màu sắc và vị trí của các điểm dừng chuyển màu không?
Tuyệt đối! Bạn có toàn quyền kiểm soát màu sắc và vị trí của từng điểm chuyển màu.
### Câu hỏi: Có diễn đàn cộng đồng nào dành cho Aspose.Page để tôi có thể tìm kiếm trợ giúp không?
 Có, bạn có thể ghé thăm[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để kết nối với cộng đồng và nhận được sự trợ giúp.