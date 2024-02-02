---
title: Thêm hình elip gradient xuyên tâm với Aspose.Page
linktitle: Thêm hình elip trong Java XPS
second_title: API Java Aspose.Page
description: Khám phá hướng dẫn từng bước về cách thêm hình elip có nét chuyển động hướng tâm trong Java XPS bằng cách sử dụng Aspose.Page cho Java. Tăng cường việc tạo tài liệu của bạn một cách dễ dàng.
type: docs
weight: 10
url: /vi/java/xps-shapes/add-ellipse/
---
## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước của chúng tôi về cách thêm hình elip trong Java XPS bằng Aspose.Page cho Java. Aspose.Page là một thư viện Java mạnh mẽ cho phép các nhà phát triển làm việc với các tài liệu XPS một cách dễ dàng. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo một hình elip có nét chuyển động hướng tâm và lưu nó dưới dạng tài liệu XPS.
## Điều kiện tiên quyết
Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Bộ công cụ phát triển Java (JDK) được cài đặt trên máy của bạn.
-  Đã tải xuống thư viện Aspose.Page cho Java. Bạn có thể lấy nó[đây](https://releases.aspose.com/page/java/).
- Trình soạn thảo mã bạn chọn (Eclipse, IntelliJ, v.v.) để viết và thực thi mã Java.
## Gói nhập khẩu
Đảm bảo bạn đã nhập các gói cần thiết vào dự án Java của mình để sử dụng Aspose.Page. Thêm các câu lệnh nhập sau vào đầu tệp Java của bạn:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## Bước 1: Thiết lập thư mục tài liệu
Xác định đường dẫn đến thư mục tài liệu của bạn nơi tài liệu XPS sẽ được lưu:
```java
String dataDir = "Your Document Directory";
```
## Bước 2: Tạo tài liệu XPS
Khởi tạo một tài liệu XPS mới bằng mã sau:
```java
XpsDocument doc = new XpsDocument();
```
## Bước 3: Xác định các điểm dừng xuyên tâm
Tạo danh sách các điểm dừng chuyển màu cho hình elip có nét chuyển động hướng tâm:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## Bước 4: Tạo hình học đường dẫn
Xác định một hình elip có nét chuyển động hướng tâm bằng cách sử dụng hình học đường dẫn:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## Bước 5: Thêm Canvas và Đường dẫn
Thêm canvas mới vào tài liệu và nối thêm đường dẫn với hình dạng đã xác định:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## Bước 6: Đặt nét và chuyển màu
Định cấu hình nét của đường dẫn bằng cọ chuyển màu xuyên tâm:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## Bước 7: Đặt độ dày nét
Chỉ định độ dày nét của đường dẫn:
```java
path.setStrokeThickness(12f);
```
## Bước 8: Lưu tài liệu
Lưu tài liệu XPS kết quả:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Chúc mừng! Bạn đã thêm thành công hình elip có nét chuyển động hướng tâm trong Java XPS bằng cách sử dụng Aspose.Page cho Java.
## Phần kết luận
Trong hướng dẫn này, chúng tôi đã khám phá các bước để tạo một tài liệu XPS với hình elip có nét chuyển động xuyên tâm hấp dẫn trực quan. Aspose.Page dành cho Java đơn giản hóa thao tác tài liệu XPS, cung cấp cho các nhà phát triển một bộ công cụ mạnh mẽ.
## Các câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Page cho Java với các thư viện Java khác không?
Có, Aspose.Page cho Java có thể được tích hợp liền mạch với các thư viện Java khác.
### Aspose.Page có phù hợp để xử lý tài liệu quy mô lớn không?
Tuyệt đối! Aspose.Page được thiết kế để xử lý hiệu quả việc xử lý tài liệu quy mô lớn.
### Tôi có thể tìm thêm hướng dẫn và ví dụ về Aspose.Page cho Java ở đâu?
 Tham quan[Aspose.Page cho tài liệu Java](https://reference.aspose.com/page/java/)để có hướng dẫn và ví dụ toàn diện.
### Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page cho Java?
 Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).
### Có diễn đàn cộng đồng nào để thảo luận về Aspose.Page không?
 Vâng, hãy tham gia[Diễn đàn cộng đồng Aspose.Page](https://forum.aspose.com/c/page/39) để tương tác với các nhà phát triển khác và nhận được hỗ trợ.