---
date: 2025-12-28
description: Tìm hiểu cách tạo tài liệu XPS trong Java bằng Aspose.Page và thêm hình
  ảnh lặp lại một cách dễ dàng với hướng dẫn từng bước này.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Cách tạo tài liệu XPS với hình ảnh lặp lại trong Java
url: /vi/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo tài liệu XPS và Thêm hình ảnh lặp lại trong Java

## Giới thiệu
Trong phát triển Java hiện đại, khả năng **tạo tệp tài liệu XPS** một cách lập trình là một kỹ năng quý giá, đặc biệt khi bạn cần làm phong phú chúng bằng các đồ họa như hình ảnh lặp lại. Aspose.Page for Java giúp quá trình này trở nên đơn giản, cho phép bạn tập trung vào thiết kế trực quan thay vì xử lý tệp ở mức độ thấp. Trong hướng dẫn này, bạn sẽ học cách tạo tài liệu XPS, **thêm hình ảnh lặp lại**, và lưu kết quả, tất cả đều kèm theo các ví dụ mã rõ ràng, từng bước.

## Trả lời nhanh
- **Aspose.Page làm gì?** Nó cung cấp một API cấp cao để tạo và thao tác tài liệu XPS trong Java.  
- **Tôi có thể lặp lại một hình ảnh không?** Có – sử dụng `XpsImageBrush` với `XpsTileMode.Tile`.  
- **Có cần giấy phép không?** Cần một giấy phép tạm thời hoặc thương mại cho việc sử dụng trong môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Bất kỳ JDK 8+ nào cũng tương thích.  
- **Thời gian triển khai mất bao lâu?** Khoảng 10–15 phút cho một kịch bản hình ảnh lặp lại cơ bản.

## “Tạo tài liệu XPS” là gì?
Một tệp XPS (XML Paper Specification) là định dạng tài liệu bố cục cố định tương tự PDF. Tạo tài liệu XPS một cách lập trình cho phép bạn tạo ra các tệp có thể in, độc lập với thiết bị, trực tiếp từ mã Java.

## Tại sao lại thêm hình ảnh lặp lại?
Lặp lại một hình ảnh sẽ sao chép đồ họa trên một khu vực xác định, rất phù hợp cho nền, dấu nước hoặc các mẫu nền. Sử dụng `XpsTileMode.Tile` của Aspose.Page, bạn có thể thực hiện điều này chỉ với vài dòng mã.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

1. **Java Development Kit (JDK)** – JDK 8 hoặc mới hơn đã được cài đặt.  
2. **Aspose.Page for Java** – tải về từ [website](https://releases.aspose.com/page/java/).  
3. **Thư mục có quyền ghi** – nơi sẽ lưu tệp XPS được tạo.

## Nhập gói
Trong dự án Java của bạn, nhập các lớp cần thiết:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Hướng dẫn từng bước

### Bước 1: Thiết lập dự án
Thêm các file JAR của Aspose.Page vào classpath của dự án và xác nhận các câu lệnh import biên dịch không lỗi.

### Bước 2: Tạo tài liệu XPS
Khởi tạo một đối tượng `XpsDocument` mới. Đây là container chính sẽ chứa tất cả các trang, đường dẫn và tài nguyên.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Bước 3: Xác định đường dẫn hình ảnh lặp lại
Đặt hình ảnh bạn muốn lặp lại (ví dụ: `R08LN_NN.jpg`) vào thư mục được tham chiếu bởi `dataDir`. Hình ảnh sẽ được dùng làm mẫu brush.

### Bước 4: Thêm hình ảnh lặp lại
Tạo một đường hình chữ nhật và lấp đầy nó bằng một `XpsImageBrush`. Bằng cách đặt chế độ lặp (`tile mode`) thành `Tile`, hình ảnh sẽ được lặp lại trên toàn bộ hình chữ nhật.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Bước 5: Lưu tài liệu
Ghi tệp XPS ra đĩa. Tệp đầu ra sẽ chứa hình ảnh lặp lại mà bạn vừa định nghĩa.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Lặp lại các bước này bất cứ khi nào bạn cần **thêm hình ảnh lặp lại** vào các trang hoặc hình dạng khác trong cùng một tài liệu XPS.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| Hình ảnh không hiển thị | Kiểm tra lại đường dẫn tệp (`dataDir + "R08LN_NN.jpg"`) có đúng và hình ảnh có thể truy cập được không. |
| Mẫu lặp bị kéo dài | Điều chỉnh các giá trị `Rectangle2D` nguồn và đích để kiểm soát kích thước ô lặp. |
| Độ trong suốt không có hiệu lực | Đảm bảo độ trong suốt của brush được đặt **sau** khi cấu hình chế độ lặp. |

## Câu hỏi thường gặp

### Aspose.Page có tương thích với mọi phiên bản Java không?
Aspose.Page được thiết kế để hoạt động với nhiều phiên bản Java. Kiểm tra tính tương thích bằng cách xem tài liệu [tại đây](https://reference.aspose.com/page/java/).

### Tôi có thể sử dụng Aspose.Page cho dự án thương mại không?
Có, Aspose.Page cung cấp các giấy phép thương mại. Mua chúng [tại đây](https://purchase.aspose.com/buy).

### Có bản dùng thử miễn phí không?
Có, khám phá các tính năng của Aspose.Page với bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### Tôi có thể tìm hỗ trợ cộng đồng và thảo luận ở đâu?
Tham gia cộng đồng Aspose.Page trên [diễn đàn](https://forum.aspose.com/c/page/39).

### Làm sao để có được giấy phép tạm thời cho Aspose.Page?
Nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

---

**Cập nhật lần cuối:** 2025-12-28  
**Kiểm thử với:** Aspose.Page for Java 24.12 (phiên bản mới nhất)  
**Tác giả:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
