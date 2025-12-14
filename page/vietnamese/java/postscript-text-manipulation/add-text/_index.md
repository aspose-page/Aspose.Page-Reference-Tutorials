---
date: 2025-12-14
description: Tìm hiểu cách đặt màu văn bản trong Java bằng Aspose.Page for Java, thêm
  văn bản vào PostScript và áp dụng viền cho văn bản để tạo kiểu tài liệu phong phú.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Đặt màu văn bản trong Java với Aspose.Page – Hướng dẫn thao tác văn bản
url: /vi/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đặt Màu Văn Bản Java với Aspose.Page – Hướng Dẫn Thao Tác Văn Bản

## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước của chúng tôi về **set text color java** khi làm việc với các tệp PostScript bằng Aspose.Page cho Java. Aspose.Page cho Java là một thư viện mạnh mẽ cho phép các nhà phát triển tạo và **generate postscript file** tài liệu, thao tác phông chữ và tạo kiểu văn bản một cách chính xác. Trong tutorial này, bạn sẽ học cách thêm văn bản, thay đổi màu sắc, điều chỉnh kích thước và thậm chí **apply stroke text** để có một giao diện chuyên nghiệp.

## Câu trả lời nhanh
- **Thư viện nào cho phép tôi đặt màu văn bản trong Java?** Aspose.Page cho Java.  
- **Tôi có thể sử dụng phông chữ hệ thống và phông chữ tùy chỉnh không?** Có, cả hai đều được hỗ trợ.  
- **Làm sao để thay đổi kích thước văn bản?** Bằng cách chỉ định kích thước phông chữ khi tạo `Font` hoặc `DrFont`.  
- **Có thể đồng thời viền và tô đầy văn bản không?** Chắc chắn – sử dụng `fillAndStrokeText`.  
- **Định dạng đầu ra của tutorial này là gì?** Một tài liệu PostScript (`.ps`).

## “set text color java” là gì?
Đặt màu văn bản trong Java có nghĩa là xác định đối tượng `Color` mà engine render (ở đây là Aspose.Page) sử dụng khi vẽ các ký tự lên trang. Thao tác này rất quan trọng để tạo ra các tài liệu có sự phân biệt trực quan, đặc biệt khi tạo **postscript documents** một cách lập trình.

## Tại sao nên sử dụng Aspose.Page cho Java?
- **Kiểm soát đầy đủ** việc tạo PostScript mà không cần trình thông dịch PostScript gốc.  
- **Hỗ trợ cả phông chữ hệ thống và phông chữ bên ngoài**, cho phép bạn nhúng bất kỳ kiểu chữ nào cần thiết.  
- **API dễ dùng** để tô đầy, viền, và **fill and stroke text**, mang lại sự linh hoạt trong việc tạo kiểu.  
- **Tương thích đa nền tảng** – viết một lần, chạy ở mọi nơi Java chạy.

## Yêu cầu trước
Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- Kiến thức cơ bản về lập trình Java.  
- Thư viện Aspose.Page cho Java đã được cài đặt. Bạn có thể tải xuống từ [trang tải Aspose.Page cho Java](https://releases.aspose.com/page/java/).  
- Các phông chữ cần thiết có sẵn trong thư mục được chỉ định. Thông tin chi tiết nằm trong [tài liệu Aspose.Page cho Java](https://reference.aspose.com/page/java/).

## Nhập các gói
Trong dự án Java của bạn, nhập các gói cần thiết cho Aspose.Page cho Java:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```

## Bước 1: Thiết lập tài liệu
Đầu tiên, chúng ta tạo một **tài liệu PostScript** mới và cấu hình các tùy chọn đầu ra.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Cách Đặt Màu Văn Bản Java Sử dụng Font Hệ Thống
Bây giờ chúng ta sẽ minh họa **set text color java** với một phông chữ được cung cấp bởi hệ thống.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Mẹo:** Phương thức `fillText` tự động sử dụng màu hiện tại nếu bạn không truyền đối số `Color`, mặc định là màu đen.

## Sử dụng Font Tùy Chỉnh và Thay Đổi Kích Thước Văn Bản
Bạn cũng có thể **change text size** và sử dụng một phông chữ tùy chỉnh được lưu trong thư mục phông chữ của bạn.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Đánh viền (Stroke) Văn Bản – Áp dụng Stroke Text
Đánh viền văn bản giúp nó có đường viền sắc nét. Ở đây chúng ta **apply stroke text** bằng một `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Đánh viền Văn Bản với Font Tùy Chỉnh
Kỹ thuật tương tự cũng áp dụng cho các phông chữ tùy chỉnh.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Bước 6: Lưu tài liệu
Cuối cùng, đóng trang và ghi tệp ra đĩa.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Các vấn đề thường gặp & Giải pháp
| Vấn đề | Giải pháp |
|-------|----------|
| **Font không tìm thấy** | Đảm bảo tệp phông chữ được đặt trong `necessary_fonts` và đường dẫn thư mục được thêm đúng qua `options.setAdditionalFontsFolders`. |
| **Màu không được áp dụng** | Kiểm tra bạn đang gọi overload của `fillText` hoặc `outlineText` có bao gồm đối số `Color`. |
| **Viền quá mỏng** | Tăng độ rộng của `BasicStroke` (ví dụ: `new BasicStroke(3)`). |
| **Tài liệu không mở được** | Xác nhận tệp `.ps` được lưu với phần mở rộng đúng và trình xem của bạn hỗ trợ PostScript. |

## Câu hỏi thường gặp

**Hỏi:** Tôi có thể sử dụng phông chữ tùy chỉnh của mình với Aspose.Page cho Java không?  
**Đáp:** Có, bạn có thể sử dụng phông chữ tùy chỉnh bằng cách chỉ định tên và kích thước phông chữ trong lớp `DrFont`.

**Hỏi:** Làm sao để thay đổi màu của văn bản?  
**Đáp:** Bạn có thể đặt màu mong muốn bằng lớp `Color` khi tô đầy hoặc viền văn bản.

**Hỏi:** Có thể thêm nhiều trang vào một tài liệu PostScript không?  
**Đáp:** Chắc chắn! Bạn có thể tạo nhiều trang bằng cách lặp lại các bước tạo tài liệu và lưu.

**Hỏi:** Mục đích của lớp `ExternalFontCache` là gì?  
**Đáp:** `ExternalFontCache` được dùng để lấy các phông chữ tùy chỉnh, đảm bảo chúng có sẵn cho việc thao tác văn bản.

**Hỏi:** Tôi có thể áp dụng các kiểu viền khác nhau cho văn bản đã được viền không?  
**Đáp:** Có, bạn có thể tùy chỉnh độ rộng và màu của viền bằng lớp `Stroke` và lớp `Color` tương ứng.

## Kết luận
Chúc mừng! Bạn đã biết cách **set text color java**, thay đổi kích thước phông chữ, **apply stroke text**, và **create postscript document** bằng Aspose.Page cho Java. Hãy thử nghiệm với các phông chữ, màu sắc và kiểu viền khác nhau để tạo ra các đầu ra PostScript chuyên nghiệp.

---

**Cập nhật lần cuối:** 2025-12-14  
**Kiểm tra với:** Aspose.Page cho Java 23.12 (phiên bản mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}