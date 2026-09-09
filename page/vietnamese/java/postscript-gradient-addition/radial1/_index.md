---
date: 2026-09-09
description: Tìm hiểu cách tạo radial gradient trong Java PostScript bằng Aspose.Page.
  Hướng dẫn từng bước này chỉ cho bạn cách thêm color stops gradient, thiết lập radii
  và tạo tệp PS nhanh chóng.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Làm chủ radial gradients trong Java
og_description: Tìm hiểu cách tạo radial gradient trong Java PostScript bằng Aspose.Page.
  Hướng dẫn này giải thích cách thêm color stops gradient, thiết lập radii và tạo
  tệp PS trong vài phút.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Cách tạo radial gradient trong Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Cách tạo radial gradient trong Java PostScript
url: /vi/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo gradient dạng tròn trong Java PostScript với Aspose.Page

## Giới thiệu
Nếu bạn cần **tạo một gradient dạng tròn** trong một tệp PostScript, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ đi qua từng bước cần thiết để tạo một tài liệu PostScript chứa gradient dạng tròn mượt mà, sử dụng **Aspose.Page for Java**. Khi hoàn thành, bạn sẽ hiểu API, xem một ví dụ chạy được đầy đủ, và biết cách điều chỉnh màu sắc, vị trí và bán kính cho bất kỳ kịch bản thiết kế nào.

## Câu trả lời nhanh
- **Thư viện nào tạo gradient dạng tròn trong PostScript?** Aspose.Page for Java.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút cho ví dụ cơ bản.  
- **Tôi có cần giấy phép để chạy mã không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần cho môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 hoặc cao hơn.  
- **Tôi có thể thay đổi hình dạng của gradient không?** Có – điều chỉnh bán kính và điểm trung tâm trong hàm khởi tạo `RadialGradientPaint`.

## Cách tạo gradient dạng tròn trong Java

Tải dự án Java của bạn, nhập các lớp cần thiết, và làm theo hướng dẫn từng bước dưới đây. Câu trả lời cốt lõi là bạn khởi tạo một `RadialGradientPaint` với các màu dừng và sau đó áp dụng nó cho một hình chữ nhật được vẽ trên `PsDocument`. Cách tiếp cận hai đối tượng này xử lý tất cả các lệnh PostScript cấp thấp cho bạn.

## Gradient dạng tròn là gì?
`RadialGradientPaint` là một lớp Java AWT định nghĩa chuyển đổi màu vòng tròn từ một điểm trung tâm ra ngoài. Nó tạo ra sự pha trộn mượt mà của nhiều màu dừng, rất thích hợp cho ánh sáng chiếu, nền mềm, hoặc bất kỳ hiệu ứng nào mà màu sắc lan tỏa từ một điểm tiêu điểm.

## Tại sao nên sử dụng Aspose.Page cho gradient dạng tròn?
Aspose.Page cung cấp cho bạn kiểm soát lập trình đầy đủ đối với đầu ra PostScript trong khi xử lý phần nặng của cú pháp PS cấp thấp. Nó hỗ trợ **hơn 50 định dạng nhập và xuất**, có thể render tài liệu hàng trăm trang mà không cần tải toàn bộ tệp vào bộ nhớ, và chạy trên bất kỳ hệ điều hành nào hỗ trợ Java 8+. Khả năng định lượng này khiến nó trở thành lựa chọn đáng tin cậy cho việc tạo đồ họa cấp doanh nghiệp.

## Yêu cầu trước
- **Java Development Kit (JDK) 8+** – kiểm tra bằng `java -version`.  
- **Aspose.Page for Java** – tải JAR mới nhất từ trang tải [Aspose.Page](https://releases.aspose.com/page/java/).  
- **IDE bạn chọn** – Eclipse, IntelliJ IDEA, hoặc VS Code với các phần mở rộng Java.  
- **Thư mục có quyền ghi** – nơi file `.ps` được tạo sẽ được lưu.

## Nhập các gói
Đầu tiên, nhập các lớp chúng ta sẽ cần. Gói `java.awt` cung cấp các đối tượng gradient paint, trong khi `com.aspose.eps` chứa các lớp xử lý tài liệu PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Hướng dẫn từng bước

### Bước 1: tạo hình chữ nhật và mở tài liệu PS
`PsDocument` là lớp của Aspose.Page đại diện cho một tài liệu PostScript và cung cấp các phương thức để vẽ hình dạng, văn bản và hình ảnh. Chúng ta bắt đầu bằng việc tạo một luồng xuất, cấu hình kích thước trang (A4 mặc định), và xác định một hình chữ nhật sẽ chứa gradient.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Mẹo chuyên nghiệp:** Điều chỉnh tọa độ của hình chữ nhật (`200, 100, 200, 200`) để đặt gradient ở bất kỳ vị trí nào trên trang.

### Bước 2: xác định màu và tỉ lệ
Một gradient dạng tròn được xây dựng từ *color stops* (các màu) và *fractions* (vị trí tương đối của các màu). Ở đây chúng ta tạo một mảng gồm sáu màu và các tỉ lệ tương ứng.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Tại sao điều này quan trọng:** Bằng cách điều chỉnh `fractions` bạn kiểm soát cách màu chuyển đổi nhanh hay chậm, cho phép tạo ra hiệu ứng tinh tế hoặc mạnh mẽ.

### Bước 3: tạo đối tượng RadialGradientPaint
`RadialGradientPaint` là lớp cốt lõi mô tả gradient màu dạng tròn, bao gồm điểm trung tâm, bán kính, điểm tiêu điểm, fractions, colors, cycle method và color space. Bây giờ chúng ta xây dựng đối tượng `RadialGradientPaint` bằng các mảng đã định nghĩa ở trên.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Lưu ý:** `transform` có thể là `null` nếu bạn không cần thêm việc co giãn hoặc xoay. Tự do thử nghiệm với `AffineTransform` để tạo gradient nghiêng.

### Bước 4: đặt màu và tô đầy hình chữ nhật
Khi đã có gradient paint, chúng ta yêu cầu `PsDocument` sử dụng nó và sau đó tô đầy hình chữ nhật đã định nghĩa trước đó.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

Tại thời điểm này, trang PostScript chứa một hình chữ nhật được tô đầy gradient dạng tròn một cách mượt mà theo cấu hình của chúng ta.

### Bước 5: đóng và lưu tài liệu
Cuối cùng, đóng trang hiện tại và ghi file ra đĩa.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Mở `RadialGradient1_outPS.ps` trong bất kỳ trình xem PostScript nào (ví dụ: Ghostscript) và bạn sẽ thấy gradient được render chính xác như đã định nghĩa.

## Vấn đề thường gặp & giải pháp
| Triệu chứng | Nguyên nhân có thể | Cách khắc phục |
|------------|-------------------|----------------|
| Gradient xuất hiện dưới dạng màu đồng nhất | Mảng `fractions` không bắt đầu ở `0.0f` hoặc không kết thúc ở `1.0f` | Đảm bảo fraction đầu tiên là `0.0f` và fraction cuối cùng là `1.0f`. |
| Màu sắc bị nhạt | Sử dụng `ColorSpaceType` không đúng | Chuyển sang `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` để có đầu ra sống động hơn. |
| Không tạo được file đầu ra | Đường dẫn `FileOutputStream` không hợp lệ hoặc không ghi được | Kiểm tra `dataDir` tồn tại và ứng dụng có quyền ghi. |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Page cho Java trong các dự án thương mại không?**  
A: Có. Cần có giấy phép thương mại cho việc sử dụng trong môi trường sản xuất. Bạn có thể mua tại [trang giấy phép Aspose](https://purchase.aspose.com/buy).

**Q: Tôi có thể tìm tài liệu API chính thức ở đâu?**  
A: Tài liệu đầy đủ có sẵn tại [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Có bản dùng thử miễn phí để thử nghiệm không?**  
A: Chắc chắn. Tải phiên bản dùng thử từ [trang phát hành Aspose.Page](https://releases.aspose.com/).

**Q: Làm thế nào để tôi có được giấy phép tạm thời để đánh giá?**  
A: Có thể yêu cầu giấy phép tạm thời tại [trang yêu cầu giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể nhận hỗ trợ cộng đồng ở đâu?**  
A: Tham gia diễn đàn cộng đồng Aspose.Page tại [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Kết luận
Bạn giờ đã biết **cách tạo gradient dạng tròn** trong tài liệu Java PostScript bằng Aspose.Page. Bằng cách điều chỉnh kích thước hình chữ nhật, các màu dừng và bán kính gradient, bạn có thể tạo ra vô số hiệu ứng hình ảnh—từ nền nền nhẹ nhàng đến đồ họa chiếu sáng mạnh mẽ. Hãy tự do thử nghiệm với các giá trị `AffineTransform` khác nhau để xoay hoặc nghiêng gradient, và kết hợp kỹ thuật này với văn bản và hình ảnh để có đầu ra PDF hoặc EPS phong phú hơn.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Page for Java latest (as of writing)  
**Author:** Aspose

## Hướng dẫn liên quan

- [Điền hình dạng bằng Gradient: Ví dụ Radial Java PostScript](/page/java/postscript-gradient-addition/radial2/)
- [Tạo Gradient PostScript trong Java – Thêm Gradient Dọc](/page/java/postscript-gradient-addition/vertical/)
- [Hướng dẫn Transparency Aspose.Page – Thêm Transparency trong Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}