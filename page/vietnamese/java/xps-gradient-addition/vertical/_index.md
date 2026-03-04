---
date: 2025-12-25
description: Tìm hiểu cách thêm gradient dọc trong Java XPS bằng Aspose.Page. Hãy
  làm theo hướng dẫn từng bước này để nâng cao sức hấp dẫn trực quan cho tài liệu
  của bạn.
linktitle: How to Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
title: Cách Thêm Gradient Dọc trong Java XPS
url: /vi/java/xps-gradient-addition/vertical/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Độ Dốc Dọc trong Java XPS

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá **cách thêm độ dốc dọc** vào tài liệu XPS khi làm việc với Java. Áp dụng độ dốc dọc có thể cải thiện đáng kể ảnh hưởng trực quan của báo cáo, hoá đơn hoặc bất kỳ nội dung có thể in nào. Chúng tôi sẽ hướng dẫn từng bước, từ việc thiết lập dự án đến lưu tệp XPS cuối cùng, sử dụng thư viện mạnh mẽ Aspose.Page for Java.

## Câu trả lời nhanh
- **Độ dốc dọc làm gì?** Nó tạo ra một chuyển đổi màu mượt mà từ trên xuống dưới của một hình dạng.  
- **Thư viện nào được yêu cầu?** Aspose.Page for Java (có thể tải xuống từ trang chính thức).  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Có tương thích với Java 8+ không?** Có, API hỗ trợ Java 8 và các phiên bản sau.  
- **Thời gian thực hiện khoảng bao lâu?** Thông thường dưới 10 phút sau khi môi trường đã được thiết lập.

## Yêu cầu trước
Trước khi chúng ta bắt đầu với mã, hãy chắc chắn rằng bạn có những thứ sau:

- Môi trường phát triển Java hoạt động (JDK 8 hoặc mới hơn).  
- Thư viện Aspose.Page for Java. Bạn có thể tải xuống từ [here](https://releases.aspose.com/page/java/).  
- Kiến thức cơ bản về các khái niệm lập trình Java.  

## Nhập các gói
Bắt đầu bằng việc nhập các gói cần thiết cho dự án Java của bạn. Đảm bảo rằng thư viện Aspose.Page for Java đã được thêm vào classpath của dự án.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```

## Bước 1: Khởi tạo tài liệu
Bắt đầu bằng việc tạo một tài liệu XPS mới. Đối tượng này sẽ chứa tất cả các yếu tố vẽ mà bạn sẽ thêm sau này.

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

## Bước 2: Tạo đường dẫn với độ dốc dọc
Tiếp theo, định nghĩa một đường dẫn hình chữ nhật và áp dụng một độ dốc tuyến tính dọc. Các điểm dừng độ dốc xác định màu sắc và vị trí của chúng dọc theo trục dọc.

```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Bước 3: Lưu tài liệu
Cuối cùng, ghi tệp XPS ra đĩa. Tệp kết quả sẽ chứa hình chữ nhật được tô đầy bằng độ dốc dọc mà bạn đã định nghĩa.

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

Chúc mừng! Bạn đã học thành công **cách thêm độ dốc dọc** vào tài liệu Java XPS bằng Aspose.Page.

## Tại sao nên sử dụng độ dốc dọc?
- **Cải thiện thẩm mỹ:** Độ dốc thêm độ sâu và vẻ hiện đại cho các hình dạng tĩnh.  
- **Nhất quán thương hiệu:** Phối màu công ty một cách mượt mà trên các trang.  
- **Dễ tùy chỉnh:** Thay đổi màu sắc hoặc vị trí dừng mà không cần thiết kế lại đồ họa.

## Các vấn đề thường gặp & Khắc phục
- **Độ dốc không hiển thị:** Kiểm tra xem các điểm bắt đầu và kết thúc của `LinearGradientBrush` đã được đặt đúng cho hướng dọc chưa.  
- **Tệp không được lưu:** Đảm bảo `dataDir` trỏ tới thư mục có thể ghi và bạn có quyền ghi tệp.  
- **Không tìm thấy thư viện:** Kiểm tra lại xem JAR Aspose.Page đã được bao gồm trong đường dẫn biên dịch của dự án chưa.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Page for Java trong các dự án thương mại không?**  
A: Có, Aspose.Page for Java có sẵn cho việc sử dụng thương mại. Bạn có thể mua nó [here](https://purchase.aspose.com/buy).

**Q: Có bản dùng thử miễn phí cho Aspose.Page for Java không?**  
A: Có, bạn có thể truy cập bản dùng thử miễn phí [here](https://releases.aspose.com/).

**Q: Tôi có thể tìm tài liệu cho Aspose.Page for Java ở đâu?**  
A: Tài liệu có sẵn [here](https://reference.aspose.com/page/java/).

**Q: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Page for Java?**  
A: Nhận giấy phép tạm thời [here](https://purchase.aspose.com/temporary-license/).

**Q: Cần trợ giúp hoặc có câu hỏi?**  
A: Truy cập cộng đồng Aspose.Page [forum](https://forum.aspose.com/c/page/39).

---

**Cập nhật lần cuối:** 2025-12-25  
**Kiểm tra với:** Aspose.Page for Java 24.12 (mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}