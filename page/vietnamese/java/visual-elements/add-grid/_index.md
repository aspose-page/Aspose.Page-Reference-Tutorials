---
date: 2025-12-18
description: Học cách thêm lưới và thêm hình chữ nhật trong suốt trong tài liệu XPS
  Java với Aspose.Page. Hướng dẫn từng bước để lưu tài liệu XPS một cách hiệu quả.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Cách Thêm Lưới bằng Visual Brush trong Java
url: /vi/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Lưới bằng Visual Brush trong Java

## Giới thiệu
Nếu bạn đang tìm cách **thêm lưới** vào các tài liệu XPS được tạo bằng Java, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách thêm lưới bằng Visual Brush, lớp hình chữ nhật trong suốt, và cuối cùng **lưu tài liệu XPS** bằng API Aspose.Page Java. Khi hoàn thành, bạn sẽ có một hình ảnh hoàn thiện có thể tái sử dụng trong báo cáo, hoá đơn, hoặc bất kỳ ứng dụng nào có nhiều tài liệu.

## Câu trả lời nhanh
- **Visual Brush làm gì?** Nó tô màu một khu vực đã định nghĩa bằng nội dung hình ảnh có thể tái sử dụng, rất phù hợp cho các mẫu lặp lại như lưới.  
- **Tôi có thể thay đổi màu lưới không?** Có – chỉnh sửa cài đặt brush màu đặc.  
- **Làm sao để thêm một hình chữ nhật trong suốt lên trên lưới?** Sử dụng `setOpacity` trên một đường (path) được tô màu đặc.  
- **Phương thức nào lưu file?** `doc.save(...)` ghi tệp XPS vào đĩa.  
- **Tôi có cần giấy phép không?** Cần một giấy phép tạm thời hoặc đầy đủ cho việc sử dụng trong môi trường sản xuất.

## Visual Brush Grid là gì?
Visual Brush cho phép bạn định nghĩa một hình ảnh nhỏ (mẫu lưới) và sau đó lặp lại nó trên một khu vực lớn hơn. Cách tiếp cận này tiết kiệm bộ nhớ hơn so với việc vẽ từng đường riêng lẻ và mang lại khả năng lặp lại chính xác từng pixel.

## Tại sao nên sử dụng Aspose.Page cho nhiệm vụ này?
- **Đa nền tảng** – Hoạt động trên bất kỳ hệ điều hành nào hỗ trợ Java.  
- **Kết xuất độ chính xác cao** – Kiểm soát chính xác màu sắc, độ trong suốt và việc lặp lại.  
- **Không phụ thuộc bên ngoài** – Mọi thứ được xử lý qua thư viện Aspose.Page.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- Kiến thức lập trình Java cơ bản.  
- Thư viện Aspose.Page đã được cài đặt – bạn có thể tải xuống từ [tài liệu Aspose.Page cho Java](https://reference.aspose.com/page/java/).  
- JDK 8 trở lên đã được cài đặt trên máy phát triển của bạn.

## Nhập các gói
Đầu tiên, nhập các lớp cần thiết để trình biên dịch biết nơi tìm các kiểu chúng ta sẽ sử dụng:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Hướng dẫn từng bước

### Bước 1: Thiết lập dự án của bạn
Tạo một thể hiện mới của `XpsDocument` và chỉ đến thư mục nơi bạn muốn lưu tệp đầu ra.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Bước 2: Tạo Visual Brush lưới màu Đỏ tươi
Chúng tôi định nghĩa một hình dạng màu hồng tươi nhỏ sẽ được lặp lại trên khu vực lưới.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Bước 3: Định nghĩa hình học cho Brush lưới
Thiết lập khu vực hình chữ nhật sẽ nhận hình ảnh được lặp lại.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Bước 4: Tạo Canvas mới cho tài liệu
Thêm một canvas vào tài liệu và đặt vị trí nơi lưới sẽ xuất hiện.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Bước 5: Thêm lưới vào Canvas
Áp dụng visual brush lên hình học, cho phép lặp lại.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Bước 6: Thêm hình chữ nhật đỏ trong suốt (Tính năng phụ)
Ở đây chúng tôi minh họa **thêm hình chữ nhật trong suốt** lên trên lưới để nhấn mạnh.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Bước 7: Lưu tài liệu XPS kết quả
Cuối cùng, ghi tài liệu ra đĩa—đây là bước **lưu tài liệu XPS**.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Thực hiện các bước này, bạn sẽ có một lưới trông chuyên nghiệp với lớp phủ trong suốt, tất cả được tạo ra bằng chương trình.

## Các vấn đề thường gặp & Mẹo

- **Kích thước lặp không đúng:** Đảm bảo `Rectangle2D` được sử dụng cho brush khớp với kích thước lặp mong muốn; nếu không mẫu có thể bị kéo dài.  
- **Độ trong suốt không áp dụng:** Nhớ gọi `setOpacity` trên đường (path) bạn muốn trong suốt; nó sẽ không ảnh hưởng tới brush.  
- **File không được lưu:** Kiểm tra `dataDir` trỏ tới thư mục tồn tại và ứng dụng của bạn có quyền ghi.

## Câu hỏi thường gặp

**H: Aspose.Page có phù hợp cho việc tạo tài liệu chuyên nghiệp không?**  
Đ: Có, Aspose.Page là một thư viện mạnh mẽ được thiết kế cho việc tạo XPS và PDF chất lượng cao trong Java.

**H: Tôi có thể tùy chỉnh màu lưới bằng Visual Brush không?**  
Đ: Chắc chắn! Thay đổi các tham số của `createColor` trong lời gọi `setFill` của brush thành bất kỳ giá trị RGBA nào bạn cần.

**H: Tôi có thể tìm hỗ trợ bổ sung cho Aspose.Page ở đâu?**  
Đ: Truy cập [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để nhận trợ giúp từ cộng đồng và câu trả lời chính thức.

**H: Có bản dùng thử miễn phí cho Aspose.Page không?**  
Đ: Có, bạn có thể truy cập [bản dùng thử miễn phí](https://releases.aspose.com/) để khám phá tất cả tính năng trước khi mua.

**H: Làm sao tôi có thể nhận giấy phép tạm thời để thử nghiệm?**  
Đ: Lấy một [giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) phù hợp cho việc phát triển và đánh giá.

**Last Updated:** 2025-12-18  
**Tested With:** Aspose.Page for Java 23.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}