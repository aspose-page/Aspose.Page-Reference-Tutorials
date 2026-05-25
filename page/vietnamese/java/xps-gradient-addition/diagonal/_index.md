---
date: 2026-05-25
description: Tìm hiểu cách thêm gradient vào tài liệu XPS trong Java bằng Aspose.Page.
  Hướng dẫn chi tiết này chỉ ra cách thêm diagonal gradient, áp dụng linear gradient
  brushes và tạo ra các tệp XPS chuyên nghiệp.
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: Thêm Diagonal Gradient trong Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'Cách Thêm Gradient: Diagonal Gradient trong Java XPS'
url: /vi/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Gradient: Gradient Đường Chéo trong Java XPS

## Giới thiệu
Trong phát triển Java hiện đại, việc nắm vững **cách thêm gradient** vào tài liệu XPS giúp báo cáo của bạn có giao diện mượt mà, bắt mắt và nổi bật. Hướng dẫn này sẽ dẫn bạn qua quá trình tạo một tệp XPS từ đầu, thêm gradient đường chéo và lưu kết quả — tất cả đều sử dụng Aspose.Page cho Java. Bạn sẽ hiểu tại sao gradient quan trọng, xem các lời gọi API chính xác và nhận được các mẹo thực tế để tránh những lỗi thường gặp.

## Câu trả lời nhanh
- **Thư viện chính là gì?** Aspose.Page for Java  
- **Phương thức nào thêm gradient?** `createLinearGradientBrush` with gradient stops  
- **Tôi có cần giấy phép không?** Bản dùng thử hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất  
- **Thời gian triển khai mất bao lâu?** Khoảng 10‑15 phút cho một gradient đường chéo cơ bản  
- **Tôi có thể sử dụng với các framework Java khác không?** Có, API không phụ thuộc vào framework  

## Gradient đường chéo trong tài liệu XPS là gì?
Gradient đường chéo là một chuyển đổi màu mượt mà chạy từ một góc của hình tới góc đối diện, tạo hiệu ứng thị giác nghiêng. Trong XPS, hiệu ứng này được định nghĩa bằng một brush gradient tuyến tính chứa các gradient stop được sắp xếp, xác định màu sắc và vị trí tương đối dọc theo đường chéo.

## Tại sao thêm gradient đường chéo với Aspose.Page?
Aspose.Page cung cấp **độ chính xác render 100 %** cho gradient trên hơn 20 trình xem XPS, và hỗ trợ **hơn 30 tính năng XPS** như văn bản, hình ảnh và hình dạng vector. API trừu tượng hoá markup XPS phức tạp, cho phép bạn tập trung vào thiết kế đồng thời đảm bảo tệp giống hệt nhau trên các nền tảng Windows, macOS và Linux.

## Yêu cầu trước
- Kiến thức lập trình Java cơ bản.  
- JDK đã được cài đặt trên máy của bạn.  
- Thư viện Aspose.Page cho Java – tải xuống **[tại đây](https://releases.aspose.com/page/java/)**.  
- Một IDE như IntelliJ IDEA hoặc Eclipse.

## Nhập các gói
Bắt đầu bằng việc nhập các lớp cần thiết. Các import này cho phép bạn truy cập vào hình học, xử lý gradient và tạo tài liệu XPS.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## Bước 1: Thiết lập dự án của bạn
Tạo một dự án Java mới trong IDE ưa thích của bạn và thêm các tệp JAR của Aspose.Page vào đường dẫn biên dịch của dự án.

## Bước 2: Xác định thư mục tài liệu
Xác định vị trí sẽ lưu tệp XPS được tạo.

```java
String dataDir = "Your Document Directory";
```

## Bước 3: Tạo tài liệu XPS
`XpsDocument` là đối tượng cốt lõi đại diện cho một tệp XPS trong bộ nhớ. Khi khởi tạo, nó cung cấp cho bạn một canvas để thêm các trang, hình dạng và brush.

```java
XpsDocument doc = new XpsDocument();
```

## Bước 4: Thêm đường gradient đường chéo
Tạo một đường hình chữ nhật sẽ nhận gradient. Hình học đường dùng lệnh di chuyển‑đường‑đóng đơn giản.  
XpsPath định nghĩa một hình dạng vector trong tài liệu XPS, như hình chữ nhật hoặc hình học tùy chỉnh.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Bước 5: Định nghĩa các điểm dừng gradient tuyến tính
Cài đặt các màu và vị trí của chúng. Mỗi điểm dừng xác định một vị trí trong gradient nơi một màu cụ thể xuất hiện.  
XpsGradientStop đại diện cho một điểm dừng màu duy nhất trong gradient, chỉ định màu và độ lệch của nó.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Bước 6: Áp dụng gradient tuyến tính lên đường
`XpsLinearGradientBrush` là loại brush của Aspose.Page cho các chuyển đổi màu tuyến tính. Nó nhận hai điểm xác định hướng gradient và một tập hợp các gradient stop quyết định màu sắc dọc theo đường đó.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Bước 7: Lưu tài liệu
Lưu tệp XPS vào đĩa. Tệp sẽ chứa hình chữ nhật được tô đầy gradient đường chéo mà bạn đã định nghĩa.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## Cách thêm gradient trong Java XPS?
Tải XpsDocument, tạo một `XpsLinearGradientBrush` với điểm bắt đầu `(0,0)` và điểm kết thúc `(width,height)`, gắn các gradient stop, gán brush cho thuộc tính `Fill` của hình dạng, và cuối cùng gọi `save`. Quy trình ngắn gọn này cho phép bạn nhúng gradient đường chéo chỉ với một vài lời gọi API, giữ cho mã nguồn sạch sẽ và dễ bảo trì.

## Những lỗi thường gặp & Mẹo
- **Hướng gradient** – đảm bảo các điểm bắt đầu và kết thúc của brush phản ánh đường chéo mong muốn; hoán đổi chúng sẽ đảo ngược gradient.  
- **Độ chính xác màu** – Aspose sử dụng ARGB; bao gồm kênh alpha nếu bạn cần độ trong suốt.  
- **Đường dẫn tệp** – luôn sử dụng đường dẫn tuyệt đối hoặc xác minh rằng đường dẫn tương đối trỏ tới một thư mục có thể ghi được.

## Câu hỏi thường gặp bổ sung

**Q: Làm thế nào tôi **cách thêm gradient** vào một hình dạng XPS hiện có?**  
A: Tạo một `XpsLinearGradientBrush`, định nghĩa các gradient stop, và gán nó cho thuộc tính `Fill` của hình dạng như đã trình bày ở Bước 6.

**Q: **apply linear gradient** thực sự làm gì phía sau?**  
A: Nó tạo ra một định nghĩa brush trong gói XPS mà tham chiếu tới các điểm bắt đầu/kết thúc và một tập hợp các gradient stop, mà trình xem sẽ render thành một chuyển đổi màu mượt mà.

**Q: Có cách nhanh để **cách sử dụng aspose** cho các tính năng XPS khác không?**  
A: Có, API Aspose.Page bao gồm các phương thức để thêm hình ảnh, văn bản và hình dạng tùy chỉnh — chỉ cần khám phá lớp `XpsDocument` để tìm các trợ giúp bổ sung.

**Q: Tôi có thể **thêm đường gradient** vào các hình dạng không phải hình chữ nhật không?**  
A: Chắc chắn. Định nghĩa bất kỳ hình học nào bằng `createPathGeometry` và sau đó đặt `Fill` của nó thành một gradient brush.

**Q: Gradient có ảnh hưởng đáng kể đến kích thước tệp không?**  
A: Chỉ ảnh hưởng nhẹ; định nghĩa gradient là các mục XML nhẹ trong gói XPS.

---

**Cập nhật lần cuối:** 2026-05-25  
**Kiểm tra với:** Aspose.Page for Java 24.11  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Thêm Gradient XPS bằng Aspose Page](/page/java/xps-gradient-addition/)
- [Thêm Văn bản XPS Java - Hướng dẫn Aspose.Page](/page/java/xps-text-manipulation/add-text/)
- [Cách Thêm Hình ảnh vào Tài liệu XPS Java – Hướng dẫn đơn giản với Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}