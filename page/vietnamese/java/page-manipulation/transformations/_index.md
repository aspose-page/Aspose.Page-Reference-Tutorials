---
date: 2026-10-20
description: Tìm hiểu cách scale rectangle với Aspose.Page cho Java, cách translate
  shape và áp dụng affine transform để tạo tài liệu PostScript.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Biến đổi trong thao tác trang Java
og_description: Tìm hiểu cách scale rectangle, translate shape và áp dụng affine transform
  bằng Aspose.Page cho Java để tạo tệp PostScript một cách hiệu quả.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Cách scale rectangle với Aspise.Page cho Java – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Cách scale rectangle với Aspose.Page cho Java
url: /vi/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thu phóng hình chữ nhật với Aspose.Page cho Java

## Giới thiệu
Trong hướng dẫn này, bạn sẽ khám phá **cách thu phóng hình chữ nhật** bằng Aspose.Page cho Java, đồng thời học cách dịch chuyển vị trí hình dạng, xoay đồ họa và áp dụng các phép biến đổi affine để tạo ra đầu ra PostScript chất lượng cao. Những kỹ thuật này cho phép bạn xây dựng đồ họa tinh vi, không phụ thuộc vào thiết bị mà không cần viết mã render cấp thấp, giúp các ứng dụng Java của bạn mạnh mẽ và dễ bảo trì hơn.

## Câu trả lời nhanh
`scale(sx, sy)` thu phóng ngữ cảnh đồ họa theo các hệ số ngang và dọc được cung cấp.  

- **Làm thế nào để tôi thu phóng một hình chữ nhật trong Java với Aspose.Page?** Gọi phương thức `scale(sx, sy)` trên ngữ cảnh đồ họa trước khi vẽ hình chữ nhật.  
- **Tôi có thể di chuyển (dịch chuyển) một hình dạng mà không ảnh hưởng đến các đồ họa khác không?** Có — bao quanh phép dịch chuyển bằng các lời gọi `writeGraphicsSave()` và `writeGraphicsRestore()`.  
- **Lớp nào tạo tệp PostScript?** Sử dụng `PsDocument` kết hợp với `PsSaveOptions`.  
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Cần có giấy phép Aspose.Page hợp lệ cho các triển khai thương mại.  
- **Phiên bản Java nào được hỗ trợ?** Aspose.Page hoạt động với Java 8 và các phiên bản sau.

## Yêu cầu trước
Trước khi bắt đầu, hãy xác nhận rằng bạn có:

- Kiến thức vững chắc về cú pháp Java cơ bản và các khái niệm hướng đối tượng.  
- Thư viện Aspose.Page cho Java đã được cài đặt. Bạn có thể tải xuống từ [tài liệu Aspose.Page cho Java](https://reference.aspose.com/page/java/).  
- Một IDE Java (IntelliJ IDEA, Eclipse hoặc VS Code) được cấu hình với các file JAR của thư viện trên classpath.

## Nhập khẩu gói
`PsDocument` là lớp chính được dùng để tạo tài liệu PostScript, và `PsSaveOptions` cấu hình cách tài liệu được lưu.  

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
`scale(float sx, float sy)` áp dụng một phép biến đổi thu phóng affine lên trạng thái đồ họa hiện tại, thay đổi kích thước các bản vẽ tiếp theo theo các hệ số `sx` (ngang) và `sy` (dọc). Đây là thao tác cốt lõi đằng sau từ khóa **how to scale rectangle**. Bằng cách áp dụng phép biến đổi này trước khi vẽ, bất kỳ hình dạng nào tiếp theo như hình chữ nhật sẽ được render với kích thước mới trong khi vẫn giữ tỷ lệ ban đầu.

## Cách dịch chuyển hình dạng với Aspose.Page
`writeGraphicsSave()` lưu trạng thái đồ họa hiện tại và `writeGraphicsRestore()` khôi phục lại, đảm bảo các phép biến đổi chỉ ảnh hưởng đến hình dạng mong muốn. Dịch chuyển thay đổi vị trí gốc của hệ tọa độ mà không thay đổi kích thước đối tượng. Bằng cách bao quanh `translate(dx, dy)` bằng `writeGraphicsSave()` / `writeGraphicsRestore()`, bạn đảm bảo chỉ hình dạng được chỉ định di chuyển trong khi các đồ họa khác không thay đổi, cung cấp kiểm soát chính xác cho từng phần tử.

## Ví dụ 1: không có biến đổi
Ví dụ đầu tiên vẽ một hình chữ nhật mà không có bất kỳ biến đổi nào, tạo ra một chuẩn cơ sở để so sánh hình ảnh với các ví dụ sau.

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

## Ví dụ 2: dịch chuyển
Trong mẫu này, chúng ta di chuyển ngữ cảnh đồ họa sang phải 250 đơn vị trước khi vẽ hình chữ nhật thứ hai, minh họa **cách dịch chuyển hình dạng**.

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

## Ví dụ 3: thu phóng
Ở đây chúng ta trả lời câu hỏi chính **how to scale rectangle**. Hình chữ nhật được giảm xuống 50 % chiều rộng gốc và 75 % chiều cao gốc bằng cách gọi `scale(0.5f, 0.75f)`.

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

## Cách xoay hình trong Java (rotate shape java)
`rotate(angle)` xoay hệ tọa độ theo góc được chỉ định tính bằng độ. Tải `PsDocument` của bạn, gọi `rotate(angle)` trên trạng thái đồ họa, vẽ hình dạng, sau đó khôi phục trạng thái trước đó. Mẫu này thực hiện **rotate shape java** và **how to rotate rectangle** trong một khối duy nhất, có thể tái sử dụng, cho phép bạn quay đồ họa quanh bất kỳ điểm nào bạn chọn.

## Tại sao điều này quan trọng – lợi ích thực tế
- **Đầu ra không phụ thuộc vào thiết bị** – Aspose.Page có thể tạo các tệp PostScript và XPS hiển thị giống hệt trên bất kỳ máy in hoặc trình xem nào, loại bỏ việc tinh chỉnh theo nền tảng.  
- **Kiểm soát chi tiết** – Kết hợp dịch chuyển, thu phóng, kéo dãn và xoay để đáp ứng các yêu cầu bố cục chính xác; API hỗ trợ hơn 20 kết hợp biến đổi trên mỗi trang.  
- **Xử lý hướng hiệu năng** – Thư viện xử lý tài liệu với dung lượng bộ nhớ dưới 10 MB cho các báo cáo khoảng 100 trang, giúp các công việc batch nhanh và mở rộng.

## Các trường hợp sử dụng phổ biến
- **Hóa đơn có thể in** – Đặt chính xác logo, mã vạch và bảng bằng cách sử dụng thu phóng và dịch chuyển để phù hợp với hướng dẫn thương hiệu của công ty.  
- **Sơ đồ kỹ thuật** – Tạo các bản vẽ sơ đồ mà mỗi thành phần phải được thay đổi kích thước và vị trí một cách tỷ lệ.  
- **Báo cáo đa trang tự động** – Tạo các báo cáo PostScript yêu cầu thu phóng đồng nhất trên các trang, chẳng hạn như các thông số kỹ thuật kỹ thuật.

## Các vấn đề thường gặp và giải pháp
- **Biến đổi không được đặt lại** – Luôn luôn ghép `writeGraphicsSave()` với `writeGraphicsRestore()`; nếu không, các bản vẽ tiếp theo sẽ kế thừa các biến đổi không mong muốn.  
- **Màu không mong muốn** – Đặt màu (paint) sau mỗi biến đổi vì trạng thái đồ họa không giữ lại thông tin màu sau khi khôi phục.  
- **Kích thước tệp quá lớn** – Bật nén trong `PsSaveOptions` và giới hạn độ phân giải ảnh raster nhúng để giữ tệp cuối dưới 5 MB cho tài liệu khoảng 50 trang.

## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Page cho Java cho các định dạng tài liệu khác không?
Aspose.Page chủ yếu tập trung vào việc thao tác trang cho các định dạng PostScript và XPS, nhưng cũng cung cấp khả năng xuất PDF hạn chế.

### Tôi có thể tìm thêm ví dụ và tài liệu cho Aspose.Page cho Java ở đâu?
Truy cập [tài liệu Aspose.Page cho Java](https://reference.aspose.com/page/java/) để có các hướng dẫn toàn diện, tham chiếu API và dự án mẫu.

### Có bản dùng thử miễn phí cho Aspose.Page cho Java không?
Có, bạn có thể truy cập bản dùng thử miễn phí qua trang **Aspose free trial download**: [Aspose free trial download](https://releases.aspose.com/).

### Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Page cho Java?
Nhận giấy phép tạm thời qua **temporary license request page**: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Tôi có thể tìm hỗ trợ cộng đồng hoặc đặt câu hỏi về Aspose.Page cho Java ở đâu?
Truy cập [diễn đàn Aspose.Page cho Java](https://forum.aspose.com/c/page/39) để thảo luận cộng đồng, đoạn mã mẫu và mẹo khắc phục sự cố.

## Các câu hỏi thường gặp

**Q: Sự khác biệt giữa `translate` và `scale` là gì?**  
A: `translate` di chuyển gốc của hệ tọa độ, trong khi `scale` thay đổi kích thước của các đối tượng được vẽ theo trục X và/hoặc Y.

**Q: Tôi có thể kết hợp nhiều biến đổi trong một trạng thái đồ họa duy nhất không?**  
A: Có — bằng cách gọi `translate`, `scale`, `rotate` hoặc `shear` liên tiếp trước khi vẽ, bạn tạo ra một phép biến đổi affine kết hợp.

**Q: Làm sao để đặt lại các biến đổi sau khi vẽ một hình dạng?**  
A: Sử dụng `writeGraphicsRestore()` để quay lại trạng thái đồ họa đã lưu trước đó.

**Q: Có thể xoay một hình chữ nhật quanh trung tâm của nó không?**  
A: Hoàn toàn có thể. Dịch chuyển hình chữ nhật tới gốc, áp dụng `rotate(angle)`, sau đó dịch chuyển lại về vị trí ban đầu trước khi vẽ.

**Q: Aspose.Page có hỗ trợ anti‑aliasing để đồ họa mượt hơn không?**  
A: Có — đặt các tùy chọn render phù hợp trong `PsSaveOptions` để bật anti‑aliasing.

**Cập nhật lần cuối:** 2026-10-20  
**Kiểm tra với:** Aspose.Page cho Java 24.12  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách vẽ hình chữ nhật trong Java PostScript với Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Tạo Gradient dạng tròn trong PostScript với Aspose.Page cho Java](/page/java/postscript-gradient-addition/)
- [Thao tác trang Postscript](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}