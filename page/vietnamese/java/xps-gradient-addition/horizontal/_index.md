---
date: 2025-12-25
description: Tìm hiểu cách thêm gradient vào tài liệu XPS trong Java bằng Aspose.Page
  và cách tùy chỉnh các điểm dừng gradient để tạo hiệu ứng ngang ấn tượng.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Cách Thêm Độ Dốc – Độ Dốc Ngang trong Java XPS
url: /vi/java/xps-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Gradient – Gradient Ngang trong Java XPS

## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước **cách thêm gradient** vào tài liệu XPS bằng Java. Trong tutorial này, bạn sẽ học cách thêm gradient ngang, tại sao nó quan trọng đối với việc hoàn thiện hình ảnh, và cách **tùy chỉnh các điểm dừng gradient** để kiểm soát màu sắc một cách chính xác. Aspose.Page for Java giúp làm việc với tài liệu XPS (XML Paper Specification) trở nên đơn giản, cho phép bạn tập trung vào thiết kế thay vì xử lý tệp ở mức độ thấp.

## Câu trả lời nhanh
- **Thư viện cần thiết là gì?** Aspose.Page for Java  
- **Phiên bản Java nào hỗ trợ?** Bất kỳ runtime Java 8+ nào  
- **Có cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần cho môi trường sản xuất  
- **Có thể thay đổi hướng gradient không?** Có – chỉ cần sửa các điểm bắt đầu/kết thúc của brush tuyến tính  
- **Có thể thêm nhiều gradient không?** Chắc chắn – lặp lại các bước tạo đường dẫn với các brush khác nhau  

## Gradient ngang trong XPS là gì?
Gradient ngang là sự chuyển đổi màu mượt mà từ trái sang phải trên một hình dạng. Trong XPS, nó được biểu diễn bằng một brush gradient tuyến tính, nội suy giữa các **điểm dừng gradient** đã định nghĩa. Hiệu ứng này thường được dùng cho banner, nút bấm và nền màu.

## Tại sao nên dùng Aspose.Page for Java?
- **Hỗ trợ XPS đầy đủ** – tạo, chỉnh sửa và render mà không cần công cụ bên thứ ba.  
- **API đơn giản** – các đối tượng cấp cao như `XpsDocument`, `XpsPath` và `XpsGradientBrush` ẩn đi sự phức tạp của XML.  
- **Hiệu năng** – tối ưu cho tài liệu lớn và xử lý hàng loạt.  

## Yêu cầu trước
Trước khi bắt đầu, hãy đảm bảo bạn có:

1. **Môi trường phát triển Java** – Cài đặt JDK mới nhất từ [java.com](https://www.java.com).  
2. **Thư viện Aspose.Page for Java** – Tải JAR từ [tài liệu Aspose.Page for Java](https://reference.aspose.com/page/java/).  

## Nhập các gói
Bắt đầu bằng việc nhập các lớp cần thiết. Những import này cho phép bạn truy cập vào việc tạo tài liệu, xử lý gradient và hình học cơ bản.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Bước 1: Khởi tạo tài liệu XPS
Tạo một thể hiện `XpsDocument` mới và chỉ định thư mục nơi bạn muốn lưu kết quả.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Bước 2: Tạo Gradient ngang
Xác định danh sách **điểm dừng gradient** để kiểm soát màu sắc và vị trí của mỗi điểm chuyển đổi. Ví dụ dưới đây tạo một gradient giống cầu vồng sống động.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### Cách tùy chỉnh các điểm dừng gradient
- **Màu** – Dùng `doc.createColor(alpha, red, green, blue)` để đặt bất kỳ giá trị ARGB nào.  
- **Vị trí** – Tham số thứ hai (`float` từ `0` đến `1`) xác định điểm dừng xuất hiện trên đường gradient. Điều chỉnh các giá trị này để dịch màu sang trái hoặc phải.

## Bước 3: Thêm Path với Gradient
Tạo một path hình chữ nhật, áp dụng biến đổi nếu cần, và tô đầy nó bằng brush gradient tuyến tính. Brush sử dụng hai điểm (`(10,0)` đến `(228,0)`) để tạo hiệu ứng ngang.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Mẹo chuyên nghiệp:** Việc tái sử dụng cùng một danh sách `stops` cho nhiều path có thể cải thiện hiệu năng, nhưng nhớ gọi `clear()` trước khi thêm các điểm dừng mới.

## Bước 4: Lưu tài liệu
Ghi tệp XPS ra đĩa. Bây giờ bạn có thể mở nó bằng bất kỳ trình xem XPS nào để xem gradient ngang hoạt động.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Các vấn đề thường gặp & Giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|--------|-------------|----------------|
| Gradient hiển thị thành màu đồng nhất | Không có điểm dừng gradient được thêm hoặc brush chưa được đặt | Đảm bảo `path.setFill(...)` sử dụng `LinearGradientBrush` và các điểm dừng được thêm qua `getGradientStops().addAll(stops)`. |
| Màu sắc bị nhạt | Giá trị alpha (tham số đầu) không đúng | Dùng `255` cho màu hoàn toàn không trong suốt trừ khi bạn muốn độ trong suốt. |
| Kích thước path sai | Giá trị ma trận biến đổi không đúng | Điều chỉnh các tham số ma trận (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Câu hỏi thường gặp

**H: Tôi có thể áp dụng nhiều gradient trong một tài liệu XPS không?**  
Đ: Có, bạn có thể thêm nhiều path, mỗi path có brush gradient riêng, để tạo các thiết kế lớp phức tạp.

**H: Aspose.Page có tương thích với các phiên bản Java mới nhất không?**  
Đ: Aspose.Page for Java được cập nhật thường xuyên và hoạt động với Java 8 và các phiên bản mới hơn.

**H: Có các loại gradient khác nào trong Aspose.Page không?**  
Đ: Ngoài gradient tuyến tính, Aspose.Page còn hỗ trợ gradient bán kính cho các chuyển đổi màu vòng tròn.

**H: Tôi có thể tùy chỉnh màu sắc và vị trí của các điểm dừng gradient không?**  
Đ: Hoàn toàn có thể! Bạn có toàn quyền kiểm soát màu ARGB và vị trí tương đối (khoảng 0‑1) của mỗi điểm dừng.

**H: Có diễn đàn cộng đồng nào cho Aspose.Page để tôi có thể hỏi đáp không?**  
Đ: Có, bạn có thể truy cập [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để kết nối với cộng đồng và nhận hỗ trợ.

---

**Cập nhật lần cuối:** 2025-12-25  
**Đã kiểm tra với:** Aspose.Page for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}