---
date: 2026-04-24
description: Tìm hiểu cách tạo tài liệu XPS bằng Java với hình ellipse gradient dạng
  radial. Hướng dẫn từng bước này chỉ cách thiết lập độ dày nét vẽ và định nghĩa hình
  học đường dẫn bằng Aspose.Page.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Thêm hình ellipse trong Java XPS
second_title: Aspose.Page Java API
title: Tạo tài liệu XPS Java – Thêm ellipse gradient dạng tròn
url: /vi/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Hình Elip Đường Viền Gradient Tia với Aspose.Page

## Giới thiệu
Trong hướng dẫn này, bạn sẽ học cách **create XPS document Java** với một hình elip đường viền gradient tia đẹp mắt bằng cách sử dụng Aspose.Page cho Java. Aspose.Page là một thư viện mạnh mẽ trừu tượng hoá các chi tiết XPS cấp thấp, cho phép bạn tập trung vào thiết kế thay vì các phức tạp của định dạng tệp. Khi kết thúc hướng dẫn này, bạn sẽ có một tệp XPS sẵn sàng sử dụng mà bạn có thể nhúng vào báo cáo, hoá đơn, hoặc bất kỳ quy trình tạo tài liệu nào.

## Câu trả lời nhanh
- **API chính nào được sử dụng?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, etc.).
- **Tôi có cần giấy phép để chạy mẫu không?** Một giấy phép tạm thời hoạt động cho việc đánh giá; giấy phép đầy đủ là bắt buộc cho môi trường sản xuất.
- **Các thuộc tính chính chúng ta thiết lập là gì?** Brush đường viền (gradient tia), phương pháp lan truyền, các điểm dừng gradient, và độ dày đường viền.
- **Tôi có thể thay đổi kích thước elip không?** Có – chỉnh sửa chuỗi hình học đường dẫn hoặc tọa độ brush gradient.
- **Elip hiển thị phẳng**? Một tệp XPS một trang chứa một hình elip đường viền với gradient tia đa màu.

## “create XPS document Java” là gì?
Tạo một tài liệu XPS trong Java có nghĩa là tạo ra một tệp XML Paper Specification (XPS) — một định dạng tài liệu bố cục cố định tương tự PDF — trực tiếp từ mã Java. Aspose.Page cung cấp một mô hình đối tượng cấp cao (`XpsDocument`, `XpsCanvas`, etc.) trừu tượng hoá markup XML, làm cho quá trình trở nên đơn giản như làm việc với các đối tượng Java tiêu chuẩn.

## Tại sao lại sử dụng elip gradient tia?
Gradient tia tạo cảm giác ba chiều, hoàn hảo cho các điểm nhấn trực quan, logo, hoặc các yếu tố trang trí trong báo cáo. So với đường viền màu đồng nhất, gradient thêm độ sâu mà không làm tăng kích thước tệp đáng kể, và định dạng XPS giữ nguyên chất lượng vector cho bất kỳ việc phóng to nào.

## Yêu cầu trước
- Java Development Kit (JDK) đã được cài đặt trên máy của bạn.
- Thư viện Aspose.Page cho Java đã được tải xuống. Bạn có thể tải nó [tại đây](https://releases.aspose.com/page/java/).
- Trình soạn thảo mã mà bạn lựa chọn (Eclipse, IntelliJ, v.v.) để viết và chạy mã Java.

## Nhập các gói
Đảm bảo bạn đã nhập các gói cần thiết trong dự án Java của mình để sử dụng Aspose.Page. Thêm các câu lệnh import sau vào đầu tệp Java của bạn:

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

## Bước 1: Thiết lập Thư mục Tài liệu
Xác định đường dẫn tới thư mục tài liệu nơi tệp XPS sẽ được lưu:

```java
String dataDir = "Your Document Directory";
```

## Bước 2: Tạo Tài liệu XPS
Khởi tạo một tài liệu XPS mới bằng đoạn mã sau:

```java
XpsDocument doc = new XpsDocument();
```

## Bước 3: Định nghĩa các điểm dừng Gradient Tia
Tạo một danh sách các điểm dừng gradient cho elip đường viền gradient tia:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Bước 4: Tạo Hình học Đường dẫn
Định nghĩa một elip đường viền gradient tia bằng hình học đường dẫn:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Bước 5: Thêm Canvas và Đường dẫn
Thêm một canvas mới vào tài liệu và nối đường dẫn với hình học đã định nghĩa:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Bước 6: Đặt Đường viền và Gradient
Cấu hình đường viền của đường dẫn bằng một brush gradient tia:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Bước 7: Đặt Độ dày Đường viền
Chỉ định **độ dày đường viền** của đường dẫn:

```java
path.setStrokeThickness(12f);
```

## Bước 8: Lưu Tài liệu
Lưu tài liệu XPS đã tạo:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Chúc mừng! Bạn đã thành công thêm một elip đường viền gradient tia trong khi **creating an XPS document Java** với Aspose.Page.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **Elip hiển thị phẳng** | Sử dụng `XpsSpreadMethod.Pad` thay vì `Reflect` | Thay đổi phương pháp lan truyền thành `XpsSpreadMethod.Reflect` như đã minh họa ở Bước 6. |
| **Không có tệp đầu ra** | `dataDir` trỏ tới thư mục không tồn tại | Đảm bảo thư mục tồn tại hoặc sử dụng đường dẫn tuyệt đối. |
| **Màu gradient không đúng** | Thứ tự các điểm dừng gradient không đúng | Kiểm tra các giá trị `offset` (0 → 1) tăng một cách đơn điệu. |
| **Lỗi biên dịch** | Thiếu các JAR của Aspose.Page trong classpath | Thêm `aspose-page-xx.jar` vào các phụ thuộc của dự án. |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Page cho Java cùng với các thư viện Java khác không?**  
A: Có, Aspose.Page cho Java có thể tích hợp với các thư viện Java khác một cách liền mạch.

**Q: Aspose.Page có phù hợp cho việc xử lý tài liệu quy mô lớn không?**  
A: Chắc chắn! Aspose.Page được thiết kế để xử lý tài liệu quy mô lớn một cách hiệu quả.

**Q: Tôi có thể tìm thêm các hướng dẫn và ví dụ cho Aspose.Page cho Java ở đâu?**  
A: Tham khảo [tài liệu Aspose.Page cho Java](https://reference.aspose.com/page/java/) để có các hướng dẫn và ví dụ toàn diện.

**Q: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Page cho Java?**  
A: Bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

**Q: Có diễn đàn cộng đồng cho các thảo luận về Aspose.Page không?**  
A: Có, tham gia [diễn đàn cộng đồng Aspose.Page](https://forum.aspose.com/c/page/39) để giao lưu với các nhà phát triển khác và nhận hỗ trợ.

---

**Cập nhật lần cuối:** 2026-04-24  
**Đã kiểm tra với:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}