---
title: Aspose.Page Thao tác văn bản Java
linktitle: Thêm văn bản trong Java PostScript
second_title: API Java Aspose.Page
description: Khám phá sức mạnh của Aspose.Page cho Java trong hướng dẫn của chúng tôi về cách thêm văn bản vào tài liệu PostScript. Tìm hiểu cách sử dụng phông chữ hệ thống và tùy chỉnh một cách dễ dàng.
weight: 10
url: /vi/java/postscript-text-manipulation/add-text/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Page Thao tác văn bản Java

## Giới thiệu
Chào mừng bạn đến với hướng dẫn từng bước của chúng tôi về cách thêm văn bản trong Java PostScript bằng Aspose.Page cho Java. Aspose.Page cho Java là một thư viện mạnh mẽ cho phép các nhà phát triển thao tác với các tài liệu PostScript một cách dễ dàng. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thêm văn bản, sử dụng phông chữ hệ thống và phông chữ tùy chỉnh, phác thảo văn bản và kết hợp các nét để có kết quả hấp dẫn trực quan.
## Điều kiện tiên quyết
Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:
- Kiến thức cơ bản về lập trình Java.
-  Aspose.Page cho thư viện Java đã được cài đặt. Bạn có thể tải nó xuống từ[Trang tải xuống Aspose.Page cho Java](https://releases.aspose.com/page/java/).
-  Phông chữ cần thiết có sẵn trong thư mục được chỉ định. Bạn có thể tìm thêm thông tin trong[Aspose.Page cho tài liệu Java](https://reference.aspose.com/page/java/).
## Gói nhập khẩu
Trong dự án Java của bạn, hãy nhập các gói cần thiết cho Aspose.Page cho Java:
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
```java
// Đường dẫn đến thư mục tài liệu.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Tạo luồng đầu ra cho tài liệu PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Tạo tùy chọn lưu với khổ A4
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// Một văn bản để ghi vào tập tin PS
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Tạo tài liệu PS 1 trang mới
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Bước 2: Sử dụng phông chữ hệ thống để điền văn bản
```java
// Sử dụng phông chữ hệ thống để điền văn bản
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Điền vào văn bản với màu mặc định hoặc đã được xác định (màu đen)
document.fillText(str, font, 50, 100);
// Đổ văn bản với màu xanh lam
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Bước 3: Sử dụng phông chữ tùy chỉnh để điền văn bản
```java
// Sử dụng phông chữ tùy chỉnh để điền văn bản
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Điền vào văn bản với màu mặc định hoặc đã được xác định (màu đen)
document.fillText(str, drFont, 50, 200);
// Đổ văn bản với màu xanh lam
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Bước 4: Phác thảo văn bản bằng phông chữ hệ thống
```java
// Sử dụng phông chữ hệ thống để phác thảo văn bản
document.outlineText(str, font, 50, 300);
// Phác thảo văn bản bằng bút rộng 2 điểm màu xanh tím
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Tô văn bản bằng màu cam và nét vẽ bằng bút rộng 2 điểm màu xanh lam
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Bước 5: Phác thảo văn bản với phông chữ tùy chỉnh
```java
// Sử dụng phông chữ tùy chỉnh cho văn bản phác thảo
document.outlineText(str, drFont, 50, 450);
// Phác thảo văn bản bằng bút rộng 2 điểm màu xanh tím
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Tô văn bản bằng màu cam và nét vẽ bằng bút rộng 2 điểm màu xanh lam
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Bước 6: Lưu tài liệu
```java
// Đóng trang hiện tại
document.closePage();
// Lưu tài liệu
document.save();
```
## Phần kết luận
Chúc mừng! Bạn đã học thành công cách thêm văn bản trong Java PostScript bằng Aspose.Page cho Java. Thử nghiệm với các phông chữ, màu sắc và tùy chọn đường viền khác nhau để cải thiện tài liệu của bạn hơn nữa.
## Các câu hỏi thường gặp
### Tôi có thể sử dụng phông chữ tùy chỉnh của riêng mình với Aspose.Page cho Java không?
 Có, bạn có thể sử dụng phông chữ tùy chỉnh bằng cách chỉ định tên và kích thước phông chữ trong phần`DrFont` lớp học.
### Làm cách nào để thay đổi màu của văn bản?
 Bạn có thể đặt màu mong muốn bằng cách sử dụng`Color` lớp khi điền hoặc phác thảo văn bản.
### Có thể thêm nhiều trang vào tài liệu PostScript không?
Tuyệt đối! Bạn có thể tạo nhiều trang bằng cách lặp lại các bước tạo và lưu tài liệu.
###  Mục đích của việc này là gì`ExternalFontCache` class?
`ExternalFontCache` được sử dụng để tìm nạp các phông chữ tùy chỉnh, đảm bảo chúng có sẵn để thao tác văn bản.
### Tôi có thể áp dụng các nét khác nhau cho văn bản được phác thảo không?
 Có, bạn có thể tùy chỉnh độ rộng và màu sắc của nét vẽ bằng cách sử dụng`Stroke` lớp học và`Color` lớp tương ứng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
