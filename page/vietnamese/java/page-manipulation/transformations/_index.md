---
date: 2026-02-07
description: Tìm hiểu cách phóng to hình chữ nhật bằng Aspose.Page cho Java, cách
  dịch chuyển hình dạng và áp dụng biến đổi affine để tạo tài liệu PostScript.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Cách thu phóng hình chữ nhật bằng Aspose.Page cho Java
url: /vi/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thu Phóng Hình Chữ Nhật với Aspose.Page cho Java

## Giới thiệu
Chào mừng đến với hướng dẫn toàn diện về việc sử dụng các tính năng mạnh mẽ của **Aspose.Page for Java** để thực hiện đa dạng các phép biến đổi trang. Trong tutorial này, bạn sẽ học **how to scale rectangle**, dịch chuyển các hình, xoay các đối tượng, và **apply affine transform** khi tạo **PostScript document**. Những khả năng này cho phép bạn xây dựng các ứng dụng Java giàu đồ họa mà không cần xử lý mã render cấp thấp.

## Câu trả lời nhanh
- **Làm thế nào để thu phóng một hình chữ nhật trong Java với Aspose.Page?** Sử dụng phương thức `document.scale()` trước khi vẽ hình.  
- **Tôi có thể di chuyển (dịch chuyển) một hình mà không ảnh hưởng đến các đồ họa khác không?** Có — lưu trạng thái đồ họa, gọi `document.translate(x, y)`, vẽ, sau đó khôi phục trạng thái.  
- **Lớp nào tạo file PostScript?** `PsDocument` cùng với `PsSaveOptions`.  
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Cần có giấy phép Aspose.Page hợp lệ cho các triển khai thương mại.  
- **Phiên bản Java nào được hỗ trợ?** Aspose.Page hoạt động với Java 8 trở lên.

## Yêu cầu trước
Trước khi chúng ta đi sâu vào hướng dẫn từng bước, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:

- Kiến thức cơ bản về lập trình Java.  
- Thư viện Aspose.Page for Java đã được cài đặt. Bạn có thể tải xuống từ [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Môi trường phát triển tích hợp Java (IDE) đã được thiết lập trên máy của bạn.

## Nhập các gói
Trong dự án Java của bạn, nhập các gói cần thiết để sử dụng Aspose.Page cho Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## “how to scale rectangle” là gì trong Aspose.Page?
Việc thu phóng một hình chữ nhật thay đổi kích thước của nó theo trục X và Y trong khi vẫn giữ nguyên hình dạng. Aspose.Page cung cấp phương thức `scale(float sx, float sy)`, áp dụng một **affine transform** lên trạng thái đồ họa hiện tại. Đây là kỹ thuật cốt lõi phía sau từ khóa **how to scale rectangle**.

## Cách Dịch Chuyển Hình với Aspose.Page
Dịch chuyển di chuyển một hình tới vị trí mới mà không thay đổi kích thước của nó. Đây là bản chất của **how to translate shape**. Bằng cách lưu trạng thái đồ họa, áp dụng `translate(dx, dy)`, vẽ, và sau đó khôi phục trạng thái, bạn giữ các đối tượng khác không bị ảnh hưởng.

## Ví dụ 1: Không có biến đổi
Ví dụ đầu tiên vẽ một hình chữ nhật đơn giản mà không áp dụng bất kỳ biến đổi nào. Điều này làm nền tảng để so sánh với các ví dụ sau.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Ví dụ 2: Dịch chuyển
Ở đây chúng tôi minh họa **how to translate shape** bằng cách di chuyển ngữ cảnh đồ họa 250 đơn vị sang phải trước khi vẽ hình chữ nhật thứ hai.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Ví dụ 3: Thu phóng
Ví dụ này trả lời câu hỏi chính **how to scale rectangle**. Chúng tôi thu nhỏ hình chữ nhật xuống 50 % chiều rộng gốc và 75 % chiều cao gốc.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Cách Xoay Hình Java (rotate shape java)
Xoay là một phép biến đổi affine phổ biến khác. Mặc dù các đoạn mã xoay bị bỏ qua để ngắn gọn, mẫu thực hiện là giống nhau: lưu trạng thái đồ họa, gọi `document.rotate(angle)`, vẽ hình, sau đó khôi phục. Điều này minh họa **rotate shape java** và **how to rotate rectangle** trong thực tế.

## Tại sao điều này quan trọng – Lợi ích thực tế
- **Device‑independent output** – Viết một lần và tạo PostScript hoặc XPS mà không cần tinh chỉnh theo nền tảng.  
- **Fine‑grained control** – Kết hợp dịch chuyển, thu phóng, cắt xén và xoay để đáp ứng yêu cầu bố cục chính xác.  
- **Performance‑oriented** – API nhẹ, lý tưởng cho xử lý hàng loạt tài liệu quy mô lớn.  

## Các trường hợp sử dụng phổ biến
- Tạo hoá đơn có thể in – ví dụ, giải pháp **printable invoice java** đặt logo và mã vạch một cách chính xác.  
- Tạo sơ đồ kỹ thuật nơi cần thu phóng và định vị chính xác.  
- Tự động tạo báo cáo đa trang ở định dạng PostScript.  

## Các vấn đề thường gặp và giải pháp
- **Transformation not resetting** – Luôn luôn ghép `document.writeGraphicsSave()` với `document.writeGraphicsRestore()` để tránh các hiệu ứng kéo theo không mong muốn.  
- **Unexpected colors** – Đảm bảo bạn đặt màu sau mỗi biến đổi; trạng thái đồ họa không giữ lại cài đặt màu trước khi khôi phục.  
- **File size too large** – Sử dụng `PsSaveOptions` để bật nén hoặc giảm độ phân giải ảnh khi nhúng đồ họa raster.  

## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Page cho Java cho các định dạng tài liệu khác không?
Aspose.Page chủ yếu tập trung vào việc thao tác trang cho các định dạng PostScript và XPS.

### Tôi có thể tìm thêm ví dụ và tài liệu cho Aspose.Page cho Java ở đâu?
Truy cập [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) để có thông tin toàn diện.

### Có bản dùng thử miễn phí cho Aspose.Page cho Java không?
Có, bạn có thể truy cập bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### Làm sao tôi có thể nhận giấy phép tạm thời cho Aspose.Page cho Java?
Nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể tìm hỗ trợ cộng đồng hoặc đặt câu hỏi về Aspose.Page cho Java ở đâu?
Truy cập [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) để thảo luận cộng đồng.

## Câu hỏi thường gặp

**Q: Sự khác nhau giữa `translate` và `scale` là gì?**  
A: `translate` di chuyển gốc của hệ tọa độ, trong khi `scale` thay đổi kích thước của các đối tượng được vẽ theo trục X và/hoặc Y.

**Q: Tôi có thể kết hợp nhiều biến đổi trong một trạng thái đồ họa duy nhất không?**  
A: Có — bằng cách gọi `translate`, `scale`, `rotate`, hoặc `shear` liên tiếp trước khi vẽ, bạn tạo ra một phép biến đổi affine kết hợp.

**Q: Làm sao tôi đặt lại các biến đổi sau khi vẽ một hình?**  
A: Sử dụng `document.writeGraphicsRestore()` để quay lại trạng thái đồ họa đã lưu trước đó.

**Q: Có thể xoay một hình chữ nhật quanh trung tâm của nó không?**  
A: Hoàn toàn có thể. Dịch chuyển hình chữ nhật tới gốc, áp dụng `rotate(angle)`, sau đó dịch chuyển lại về vị trí ban đầu trước khi vẽ.

**Q: Aspose.Page có hỗ trợ anti‑aliasing để đồ họa mượt hơn không?**  
A: Có — đặt các tùy chọn render phù hợp trong `PsSaveOptions` để bật anti‑aliasing.

---

**Cập nhật lần cuối:** 2026-02-07  
**Kiểm tra với:** Aspose.Page for Java 24.12  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}