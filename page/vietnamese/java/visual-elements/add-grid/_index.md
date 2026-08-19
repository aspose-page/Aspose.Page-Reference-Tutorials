---
date: 2026-03-05
description: Tìm hiểu cách thêm lưới bằng Visual Brush trong Java với Aspose.Page.
  Thực hiện theo hướng dẫn từng bước để nâng cao hình ảnh tài liệu một cách dễ dàng.
linktitle: Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Cách thêm lưới bằng Visual Brush trong Java
url: /vi/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Lưới bằng Visual Brush trong Java

## Giới thiệu
Nếu bạn đang muốn **cách thêm lưới** vào các tài liệu được tạo bằng Java, tính năng Visual Brush của Aspose.Page giúp thực hiện một cách bất ngờ đơn giản. Trong hướng dẫn này chúng ta sẽ đi qua từng bước, giải thích tại sao Visual Brush là lựa chọn lý tưởng cho các mẫu lưới, và cung cấp cho bạn một ví dụ hoàn chỉnh, có thể chạy được.

## Câu trả lời nhanh
- **Visual Brush là gì?** Một phần tử hình ảnh có thể tái sử dụng, có thể lặp lại hoặc kéo dài để lấp đầy một khu vực.  
- **Tại sao lại dùng lưới?** Lưới giúp cấu trúc bố cục, tạo mẫu nền, hoặc làm nổi bật các phần trong tài liệu XPS.  
- **Yêu cầu trước?** Java JDK, Aspose.Page for Java, và hiểu biết cơ bản về đồ họa Java.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút sau khi đã cài đặt thư viện.  
- **Có thể tùy chỉnh màu sắc không?** Có – bạn kiểm soát màu nền, độ trong suốt và kích thước ô trực tiếp trong mã.

## Tại sao sử dụng Visual Brush để thêm lưới?
Visual Brush cho phép bạn định nghĩa một hình ảnh nhỏ (gọi là “ô”) một lần và sau đó lặp lại nó trên bất kỳ hình dạng nào. Cách tiếp cận này tiết kiệm bộ nhớ và giữ cho mã của bạn sạch sẽ, đặc biệt khi bạn cần áp dụng cùng một mẫu cho nhiều canvas.

## Yêu cầu trước
Trước khi chúng ta đi vào mã, hãy chắc chắn rằng bạn đã có các yêu cầu sau:
- Hiểu biết cơ bản về lập trình Java.  
- Thư viện Aspose.Page đã được cài đặt. Bạn có thể tải xuống từ [tài liệu Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Java Development Kit (JDK) đã được cài đặt trên máy tính của bạn.

## Nhập các gói
Đảm bảo bạn đã nhập các gói cần thiết trong dự án Java của mình:
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

### Bước 1: Thiết lập dự án
Đầu tiên, tạo một thể hiện `XpsDocument` và chỉ định thư mục sẽ lưu kết quả.
```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Bước 2: Tạo Visual Brush Lưới Màu Magenta
Chúng ta sẽ xây dựng một ô màu magenta nhỏ sẽ được lặp lại. Đường hình học (path geometry) xác định hình dạng của ô.
```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Bước 3: Định nghĩa Geometry cho Visual Brush Lưới Màu Magenta
Ở đây chúng ta mô tả khu vực sẽ nhận brush lặp lại.
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Bước 4: Tạo Canvas mới
Một canvas mới được thêm vào tài liệu, và chúng ta áp dụng phép biến đổi dịch (translation transform) để lưới xuất hiện ở vị trí mong muốn.
```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Bước 5: Thêm Lưới vào Canvas
Bây giờ chúng ta gắn visual brush vào geometry và thiết lập chế độ lặp (tiling mode).
```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Bước 6: Thêm Hình chữ nhật Đỏ Trong Suốt
Để minh họa việc lớp phủ, chúng ta đặt một hình chữ nhật đỏ bán trong suốt lên trên lưới.
```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Bước 7: Lưu Tài liệu XPS Kết quả
Cuối cùng, ghi tệp XPS ra đĩa.
```java
doc.save(dataDir + "AddGrid_out.xps");
```

Thực hiện các bước này, và bạn sẽ thành công trong việc thêm một lưới hấp dẫn bằng Visual Brush trong ứng dụng Java của mình với Aspose.Page.

## Các trường hợp sử dụng phổ biến
- **Nền báo cáo:** Thêm các mẫu lưới nhẹ nhàng vào báo cáo tài chính hoặc kỹ thuật để cải thiện khả năng đọc.  
- **Mẫu thiết kế:** Tạo các mẫu trang có thể tái sử dụng, nơi cùng một lưới lặp lại trên nhiều trang.  
- **Làm nổi bật các phần:** Đặt lưới màu lên để thu hút sự chú ý đến các khu vực cụ thể trong tài liệu.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Lưới bị kéo dài** | Kiểm tra `TileMode` đã được đặt thành `XpsTileMode.Tile` và các hình chữ nhật nguồn và đích có cùng kích thước. |
| **Màu sắc không đúng** | Đảm bảo bạn sử dụng giá trị RGBA chính xác khi tạo brush màu rắn (`createColor(alpha, red, green, blue)`). |
| **Tài liệu không được lưu** | Kiểm tra `dataDir` trỏ tới một thư mục có thể ghi được và bạn có quyền truy cập hệ thống tập tin phù hợp. |

## Kết luận
Chúc mừng! Bạn đã học **cách thêm lưới** bằng Visual Brush của Aspose.Page trong Java. Kỹ thuật này cho phép bạn kiểm soát chi tiết việc hiển thị mẫu trong khi giữ cho mã sạch sẽ và dễ bảo trì.

## Câu hỏi thường gặp
### Aspose.Page có phù hợp cho việc tạo tài liệu chuyên nghiệp không?
Có, Aspose.Page là một thư viện mạnh mẽ được thiết kế cho việc tạo tài liệu chuyên nghiệp trong Java.

### Tôi có thể tùy chỉnh màu lưới bằng Visual Brush không?
Chắc chắn! Visual Brush cho phép bạn vẽ với nhiều màu sắc khác nhau, cung cấp sự linh hoạt trong việc tùy chỉnh.

### Tôi có thể tìm hỗ trợ bổ sung cho Aspose.Page ở đâu?
Truy cập [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để nhận hỗ trợ cộng đồng và thảo luận.

### Có bản dùng thử miễn phí cho Aspose.Page không?
Có, bạn có thể truy cập [bản dùng thử miễn phí](https://releases.aspose.com/) để khám phá các tính năng của Aspose.Page.

### Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Page?
Nhận [giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để thử nghiệm.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-05  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose  

---