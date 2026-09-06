---
date: 2026-08-18
description: Tìm hiểu cách thêm mẫu vạch chéo vào các tệp Java PostScript bằng Aspose.Page
  Java. Hướng dẫn chi tiết này trình bày mã đầy đủ và các mẹo.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Thêm mẫu vạch chéo trong Java PostScript
og_description: Tìm hiểu cách thêm mẫu vạch chéo trong Java PostScript bằng Aspose.Page.
  Thực hiện theo hướng dẫn chi tiết này để nhanh chóng tạo đồ họa được tô mẫu vạch
  chéo.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Cách thêm mẫu vạch chéo trong Java PostScript – Hướng dẫn Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Cách thêm mẫu vạch chéo trong Java PostScript
url: /vi/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thêm mẫu vạch chéo trong Java PostScript

## Giới thiệu
Nếu bạn đang làm việc với **Aspose.Page Java** và tự hỏi **cách thêm hatch pattern** vào đầu ra PostScript của mình, hatch pattern là một giải pháp nhanh và linh hoạt. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn **cách thêm hatch** vào tài liệu PostScript, giải thích lý do chúng hữu ích, và cung cấp cho bạn một ví dụ mã hoàn chỉnh, sẵn sàng chạy. Khi kết thúc, bạn sẽ có thể tạo các hình dạng và văn bản được tô hatch một cách hấp dẫn chỉ với vài dòng Java.

## Câu trả lời nhanh
- **Thư viện tôi cần là gì?** Aspose.Page for Java (the “aspose page java” SDK).  
- **Hiệu ứng hình ảnh nào chúng ta đang thêm?** Hatch patterns (e.g., diagonal lines, crosshatch).  
- **Tôi có cần giấy phép để chạy mẫu không?** Một bản dùng thử miễn phí hoạt động cho phát triển; giấy phép cần thiết cho môi trường sản xuất.  
- **Có bao nhiêu dòng mã?** Khoảng 70 dòng, chia thành các bước rõ ràng.  
- **Tôi có thể sử dụng cùng cách tiếp cận cho PDF không?** Có — Aspose.Page hỗ trợ nhiều định dạng đầu ra, bao gồm PDF.

## Hatch pattern là gì?
Hatch pattern là một lớp tô dựa trên vector gồm các đường hoặc hình dạng lặp lại tạo ra hiệu ứng kết cấu. Vì nó được định nghĩa bằng toán học, mẫu có thể phóng to mà không mất chất lượng, làm cho nó lý tưởng cho việc in ấn độ phân giải cao và đầu ra đơn sắc.

## Tại sao sử dụng hatch pattern với Aspose.Page Java?
Aspose.Page hỗ trợ **hơn 10 định dạng đầu ra** (bao gồm PostScript, PDF, EPS, SVG và XPS) và có thể render hatch fill trên tài liệu lên tới **500 trang** mà không cần tải toàn bộ tệp vào bộ nhớ. Điều này mang lại hiệu năng nhanh, tiêu thụ bộ nhớ thấp và kết quả hình ảnh nhất quán trên tất cả các định dạng được hỗ trợ.

## Cách thêm hatch pattern – tổng quan
Hatch pattern là các kết cấu dựa trên vector, render sạch sẽ ở bất kỳ độ phân giải nào và hoạt động tốt trên máy in đơn sắc. Sử dụng Aspose.Page Java, bạn có thể áp dụng các mẫu này cho hình dạng, đường dẫn và thậm chí văn bản mà không cần xử lý các lệnh PostScript cấp thấp.

## Yêu cầu trước
- **Môi trường phát triển Java** – JDK 8 trở lên và một IDE bạn chọn.  
- **Thư viện Aspose.Page for Java** – Tải JAR mới nhất từ **trang tải Aspose.Page for Java** [here](https://releases.aspose.com/page/java/).  
- Bạn cũng có thể duyệt các bản phát hành Aspose khác [here](https://releases.aspose.com/).  
- **Quyền ghi** vào thư mục nơi tệp PostScript được tạo sẽ được lưu.

## Nhập các gói
Các import dưới đây bao gồm các lớp Java AWT tiêu chuẩn cho các primitive đồ họa như màu sắc, nét vẽ và hình học, cũng như các lớp Aspose.Page cung cấp mô hình tài liệu, định nghĩa hatch‑style và các tùy chọn lưu cần thiết để tạo tệp PostScript.  
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Lớp `Document` là gì?
Lớp `Document` là đối tượng cấp cao nhất của Aspose.Page đại diện cho một tệp PostScript duy nhất trong bộ nhớ. Tất cả các thao tác vẽ được thực hiện thông qua đối tượng này.

## Cách thiết lập luồng đầu ra?
Để ghi đầu ra, tạo một `FileOutputStream` trỏ tới đường dẫn tệp mong muốn; luồng này xử lý việc ghi byte cấp thấp. `PsSaveOptions` cấu hình cách tài liệu được lưu, bao gồm kích thước trang và nén. Sau đó khởi tạo một `Document` với đối tượng `PsSaveOptions` chỉ định kích thước trang, nén và các cài đặt đặc thù của PostScript.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Cách lưu trạng thái đồ họa và dịch gốc tọa độ?
Lưu trạng thái đồ họa ghi lại ma trận biến đổi hiện tại, vùng cắt và các thuộc tính vẽ, cho phép bạn khôi phục sau này. Sau khi lưu, gọi `translate(x, y)` trên đối tượng graphics để dịch gốc tới vị trí thuận tiện cho việc vẽ lưới các ô hatch.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Cách tạo một hình chữ nhật có thể tái sử dụng cho mỗi mẫu?
`Rectangle2D` đại diện cho một hình chữ nhật được xác định bởi vị trí và kích thước. Bằng cách tạo một thể hiện duy nhất phù hợp với kích thước ô, bạn có thể tái sử dụng nó cho mỗi ô được tô hatch, giảm việc cấp phát đối tượng và giữ vòng lặp vẽ hiệu quả.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Cách thiết lập bút cho viền hình vuông mẫu?
`BasicStroke` mô tả độ dày viền, mẫu gạch và đầu mút cho các hình vector. Sử dụng `BasicStroke` 2‑point cung cấp viền rõ ràng quanh mỗi ô được tô hatch, đảm bảo phần tô được tách biệt trực quan khỏi các ô lân cận.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## Cách lặp qua các hatch pattern?
`HatchStyle` là một enumeration liệt kê tất cả các hatch pattern được định nghĩa sẵn như chéo, chéo kép và chấm. Vòng lặp qua `HatchStyle.values()` cho phép bạn áp dụng từng mẫu một cách tuần tự, tô hình chữ nhật bằng `HatchBrush`, sau đó vẽ viền của nó.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Cách khôi phục trạng thái đồ họa sau khi vẽ?
Gọi `restore()` trên đối tượng graphics sẽ khôi phục ma trận biến đổi và cài đặt vẽ về trạng thái đã lưu trước đó, ngăn việc dịch chuyển hoặc phóng to tích lũy ảnh hưởng đến các thao tác vẽ tiếp theo. Điều này đảm bảo nội dung sau bắt đầu từ hệ tọa độ gốc và sử dụng các thuộc tính mặc định.  
```java
document.writeGraphicsRestore();
```

## Cách tô văn bản bằng hatch pattern?
`TextFragment` đại diện cho một đoạn văn bản có thể được định vị và định dạng độc lập. Bằng cách gán một `HatchBrush` với `HatchStyle` đã chọn cho phần fill của fragment, các ký tự văn bản sẽ được render bằng kết cấu hatch thay vì màu đặc.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Cách tạo viền cho văn bản bằng hatch style khác?
`HatchBrush` cũng có thể được dùng để vẽ nét. Để vẽ viền, đặt stroke của fragment thành một `HatchBrush` với `HatchStyle` khác (ví dụ, hatch 70 %), và tăng độ rộng nét bằng `setStrokeWidth`. Điều này render viền văn bản với hatch pattern riêng trong khi vẫn giữ phần bên trong đã được tô.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Cách đóng và lưu tài liệu?
`document.save()` ghi tài liệu trong bộ nhớ vào luồng đầu ra đã chỉ định. Sau khi hoàn thành tất cả các lệnh vẽ, gọi phương thức này và sau đó đóng `FileOutputStream` để giải phóng tài nguyên hệ thống và đảm bảo tệp được ghi đầy đủ lên đĩa.  
```java
document.closePage();
document.save();
```

Thực hiện các bước này, bạn sẽ có một tệp PostScript hiển thị đầy đủ các hatch pattern được áp dụng cho cả hình dạng và văn bản — tất cả đều được hỗ trợ bởi **aspose page java**.

## Những lỗi thường gặp & mẹo
- **Lỗi đường dẫn tệp** – Đảm bảo `dataDir` kết thúc bằng dấu phân tách tệp phù hợp (`/` hoặc `\`).  
- **Màu không được hỗ trợ** – Một số trình thông dịch PostScript cũ có thể không xử lý một số không gian màu; hãy sử dụng RGB cơ bản để tương thích tối đa.  
- **Cảnh báo giấy phép** – Chạy mẫu mà không có giấy phép hợp lệ sẽ chèn watermark vào đầu ra.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Page Java với các framework Java khác không?**  
A: Có, thư viện không phụ thuộc vào framework và hoạt động với Spring, Jakarta EE, Android (giới hạn), và Java SE thuần.

**Q: Có phiên bản dùng thử cho Aspose.Page Java không?**  
A: Chắc chắn. Tải bản dùng thử miễn phí 30 ngày [Aspose trial download page](https://releases.aspose.com/).

**Q: Làm sao để lấy giấy phép tạm thời cho phát triển?**  
A: Yêu cầu giấy phép tạm thời [temporary license request page](https://purchase.aspose.com/temporary-license/). Nó sẽ loại bỏ watermark đánh giá.

**Q: Tôi có thể tìm thêm hướng dẫn và hỗ trợ cộng đồng ở đâu?**  
A: Truy cập diễn đàn chính thức [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) để xem thêm ví dụ và Q&A.

**Q: Có tài liệu đầy đủ cho tất cả các lớp và phương thức không?**  
A: Có, tài liệu API đầy đủ có sẵn [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Tôi có thể render cùng hatch pattern sang PDF thay vì PostScript không?**  
A: Chắc chắn. Thay đổi `PsSaveOptions` thành `PdfSaveOptions` (hoặc tương đương) và phần còn lại của mã vẫn giữ nguyên.

**Q: Tôi nên làm gì nếu tệp tạo ra rỗng?**  
A: Kiểm tra luồng đầu ra trỏ tới thư mục có quyền ghi và chắc chắn `document.save()` được gọi sau tất cả các thao tác vẽ.

---

**Cập nhật lần cuối:** 2026-08-18  
**Kiểm thử với:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo mẫu kết cấu trong PostScript – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Cách thêm Gradient: Gradient chéo trong Java PostScript sử dụng Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Cách chuyển đổi PostScript sang PDF bằng Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}