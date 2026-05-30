---
date: 2026-05-30
description: Tìm hiểu cách tạo tài liệu XPS trong Java bằng Aspose.Page và thêm hình
  ảnh lặp lại một cách dễ dàng với hướng dẫn từng bước này. Cách tạo tệp XPS nhanh
  chóng.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Thêm hình ảnh lặp lại trong Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Cách tạo tài liệu XPS với hình ảnh lặp lại trong Java
url: /vi/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo tài liệu XPS với hình ảnh lặp lại trong Java

## Giới thiệu
Tạo tài liệu XPS một cách lập trình là kỹ năng cốt lõi cho các nhà phát triển Java cần đầu ra có thể in, độc lập với thiết bị. **How to create XPS** được giải đáp bởi Aspose.Page for Java, công cụ trừu tượng hoá các chi tiết cấp thấp của XML Paper Specification và cho phép bạn tập trung vào thiết kế trực quan. Trong hướng dẫn này, bạn sẽ thấy cách tạo tài liệu XPS, thêm hình ảnh lặp lại làm nền hoặc mẫu, và lưu kết quả — tất cả bằng mã ngắn gọn, sẵn sàng cho môi trường sản xuất.

## Câu trả lời nhanh
- **What does Aspose.Page do?** Nó cung cấp một API cấp cao để tạo và thao tác các tài liệu XPS trong Java.  
- **Can I tile an image?** Có – sử dụng `XpsImageBrush` với `XpsTileMode.Tile`.  
- **Do I need a license?** Cần một giấy phép tạm thời hoặc thương mại cho việc sử dụng trong môi trường sản xuất.  
- **What Java version is supported?** Bất kỳ JDK 8+ nào cũng tương thích.  
- **How long does implementation take?** Khoảng 10–15 phút cho kịch bản hình ảnh lặp lại cơ bản.

## “create XPS document” là gì?
`XpsDocument` là đối tượng cấp cao của Aspose.Page đại diện cho một tệp XPS duy nhất trong bộ nhớ. Nó bao gồm các trang, tài nguyên và siêu dữ liệu, cho phép bạn xây dựng tài liệu một cách lập trình. Tạo tài liệu XPS có nghĩa là khởi tạo lớp này, thêm các yếu tố trực quan, và cuối cùng gọi `save` để ghi tệp bố cục cố định ra đĩa. Cách tiếp cận này loại bỏ việc xử lý XML thủ công và đảm bảo tuân thủ XML Paper Specification.

## Tại sao lại thêm hình ảnh lặp lại?
Việc lặp lại (tiling) làm cho một đồ họa xuất hiện nhiều lần trên một khu vực xác định, rất thích hợp cho nền, dấu nước hoặc các mẫu lấp đầy. Khi sử dụng `XpsTileMode.Tile`, hình ảnh sẽ tự động lặp lại mà không cần sao chép thủ công, giúp tiết kiệm thời gian phát triển và đảm bảo việc hiển thị nhất quán trên mọi thiết bị. Hình ảnh lặp lại cũng giữ kích thước tệp thấp vì cùng một tài nguyên bitmap được tái sử dụng thay vì nhúng nhiều lần.

## Yêu cầu trước
1. **Java Development Kit (JDK)** – JDK 8 hoặc mới hơn đã được cài đặt.  
2. **Aspose.Page for Java** – tải xuống từ [website](https://releases.aspose.com/page/java/).  
3. **A writable directory** – nơi tệp XPS được tạo sẽ được lưu.

## Nhập gói
Trong dự án Java của bạn, nhập các lớp cần thiết:

`XpsDocument` là đối tượng chính đại diện cho một tệp XPS.  
`XpsImageBrush` vẽ các hình dạng bằng nguồn ảnh.  
`XpsTileMode` xác định cách ảnh được lặp lại.  
`Rectangle2D` mô tả một vùng hình chữ nhật để định vị.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Hướng dẫn từng bước

### Bước 1: Thiết lập dự án của bạn
Thêm các file JAR của Aspose.Page vào classpath của dự án và xác nhận các câu lệnh import biên dịch mà không có lỗi.

### Bước 2: Tạo tài liệu XPS
`XpsDocument` là container cốt lõi chứa các trang, đường dẫn và tài nguyên. Khởi tạo nó với kích thước trang mong muốn, sau đó bạn có thể bắt đầu thêm các yếu tố đồ họa.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Bước 3: Xác định đường dẫn hình ảnh lặp lại
Đặt hình ảnh bạn muốn lặp lại (ví dụ, `R08LN_NN.jpg`) vào thư mục được tham chiếu bởi `dataDir`. Hình ảnh sẽ được sử dụng làm mẫu brush.

### Bước 4: Thêm hình ảnh lặp lại
Tạo một đường dẫn hình chữ nhật và tô đầy nó bằng `XpsImageBrush`. Bằng cách đặt chế độ lặp lại thành `Tile`, hình ảnh sẽ lặp lại trên toàn bộ hình chữ nhật. Điều chỉnh các hình chữ nhật nguồn và đích để kiểm soát kích thước và vị trí của các ô lặp.

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
Lưu tệp XPS vào đĩa. Tệp đầu ra sẽ chứa hình ảnh lặp lại mà bạn vừa định nghĩa và có thể mở bằng bất kỳ trình xem XPS nào.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Lặp lại các bước này bất cứ khi nào bạn cần **thêm hình ảnh lặp lại** vào các trang hoặc hình dạng khác trong cùng một tài liệu XPS.

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| Hình ảnh không hiển thị | Xác minh đường dẫn tệp (`dataDir + "R08LN_NN.jpg"`) là đúng và hình ảnh có thể truy cập. |
| Mẫu lặp lại bị kéo dãn | Điều chỉnh các giá trị `Rectangle2D` nguồn và đích để kiểm soát kích thước ô lặp. |
| Độ trong suốt không có hiệu lực | Đảm bảo độ trong suốt của brush được đặt **sau** khi cấu hình chế độ lặp lại. |

## Câu hỏi thường gặp

**Q:** Aspose.Page có tương thích với tất cả các phiên bản Java không?  
**A:** Aspose.Page hỗ trợ Java 8 đến Java 21; bạn có thể xem ma trận tương thích đầy đủ [tại đây](https://reference.aspose.com/page/java/).

**Q:** Tôi có thể sử dụng Aspose.Page cho các dự án thương mại không?  
**A:** Có, cần có giấy phép thương mại cho việc sử dụng trong môi trường sản xuất. Các tùy chọn mua được liệt kê [tại đây](https://purchase.aspose.com/buy).

**Q:** Có bản dùng thử miễn phí không?  
**A:** Bản dùng thử đầy đủ chức năng có thể tải xuống từ trang phát hành của Aspose [tại đây](https://releases.aspose.com/).

**Q:** Tôi có thể nhận hỗ trợ cộng đồng ở đâu?  
**A:** Tham gia diễn đàn cộng đồng Aspose.Page tại [forum](https://forum.aspose.com/c/page/39) để đặt câu hỏi và chia sẻ ví dụ.

**Q:** Làm thế nào để tôi có được giấy phép tạm thời để đánh giá?  
**A:** Giấy phép tạm thời được cung cấp theo yêu cầu qua cổng thông tin Aspose [tại đây](https://purchase.aspose.com/temporary-license/).

## Kết luận
Bây giờ bạn đã có quy trình hoàn chỉnh, sẵn sàng cho môi trường sản xuất để **how to create XPS** tài liệu với hình ảnh lặp lại bằng Aspose.Page for Java. Bằng cách tận dụng `XpsImageBrush` và `XpsTileMode.Tile`, bạn có thể tạo ra các đồ họa phong phú, có thể lặp lại mà không làm tăng kích thước tệp. Hãy thử nghiệm với các kích thước ô lặp khác nhau, mức độ trong suốt và các hình dạng để xây dựng bố cục tài liệu tinh vi. Trong bước tiếp theo, hãy khám phá việc thêm các hình dạng vector hoặc lớp phủ văn bản để nâng cao hơn nữa các tệp XPS của bạn.

---

**Cập nhật lần cuối:** 2026-05-30  
**Kiểm tra với:** Aspose.Page for Java 24.12 (latest)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Cách thêm hình ảnh vào tài liệu XPS Java – Hướng dẫn đơn giản với Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - Hướng dẫn thêm trang vào XPS](/page/java/xps-page-manipulation/add-page/)
- [Chuyển đổi XPS sang PDF trong Java bằng Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}