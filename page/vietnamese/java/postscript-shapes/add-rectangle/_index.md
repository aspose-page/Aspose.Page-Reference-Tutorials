---
date: 2026-02-18
description: Học cách vẽ các hình chữ nhật trong Java PostScript bằng Aspose.Page.
  Hướng dẫn từng bước này chỉ ra cách thiết lập màu vẽ, thiết lập màu cho hình chữ
  nhật trong Java và tạo đồ họa sống động đồng thời giải thích cách vẽ hình chữ nhật
  một cách hiệu quả.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Cách vẽ hình chữ nhật trong Java PostScript bằng Aspose.Page
url: /vi/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Vẽ Hình Chữ Nhật trong Java PostScript với Aspose.Page

## Giới thiệu
Nếu bạn cần **cách vẽ hình chữ nhật** trong một tệp Java PostScript, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ trình bày cách sử dụng Aspose.Page for Java để thêm các hình chữ nhật màu sắc, kiểm soát màu nền và viền, và lưu kết quả dưới dạng tài liệu PostScript. Bạn sẽ thấy **cách đặt màu vẽ**, cách xác định hình học của hình chữ nhật, và lý do tại sao cách tiếp cận này lý tưởng cho việc tạo đồ họa có thể in một cách tự động. Khi kết thúc hướng dẫn, bạn cũng sẽ hiểu bối cảnh rộng hơn của các kỹ thuật **draw rectangle java** và cách chúng phù hợp với quy trình **java awt rectangle drawing**.

## Câu trả lời nhanh
- **Thư viện cần thiết là gì?** Aspose.Page for Java  
- **Tôi có thể thay đổi màu của hình chữ nhật không?** Có – sử dụng `setPaint` với bất kỳ `java.awt.Color` nào  
- **Có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép cần thiết cho môi trường sản xuất  
- **Kích thước trang được sử dụng trong ví dụ là gì?** A4 (mặc định `PsSaveOptions`)  
- **Mã có tương thích với Java 8+ không?** Hoàn toàn – nó sử dụng các lớp AWT tiêu chuẩn  

## “How to Draw Rectangle” trong PostScript là gì?
Vẽ một hình chữ nhật trong tài liệu PostScript có nghĩa là xác định một vùng hình chữ nhật và hoặc tô đầy, hoặc vẽ viền, hoặc cả hai. Với Aspose.Page, bạn có thể thực hiện điều này bằng các lớp **java awt rectangle drawing** quen thuộc, giúp mã dễ đọc và bảo trì.

## Tại sao nên dùng Aspose.Page cho đồ họa hình chữ nhật?
- **Đa nền tảng**: Tạo PostScript tiêu chuẩn hoạt động trên mọi máy in.  
- **Kiểm soát chi tiết**: Bạn có thể đặt màu nền, màu viền và độ rộng đường viền một cách độc lập.  
- **Không phụ thuộc bên ngoài**: Chỉ sử dụng các lớp hình học AWT có sẵn, không cần thư viện đồ họa bổ sung.  

## Yêu cầu trước
Trước khi bắt đầu tutorial, hãy chắc chắn bạn đã chuẩn bị các yêu cầu sau:
- Hiểu biết cơ bản về lập trình Java.  
- Thư viện Aspose.Page for Java đã được cài đặt. Nếu chưa, tải về từ [tài liệu Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Môi trường phát triển Java đã được thiết lập trên máy tính của bạn.

## Nhập khẩu các gói
Trong dự án Java của bạn, bắt đầu bằng cách nhập các gói cần thiết. Các import này cung cấp quyền truy cập vào các lớp `Color`, `BasicStroke` và `Rectangle2D` của AWT, cũng như các lớp xử lý tài liệu cốt lõi của Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Hướng dẫn từng bước để vẽ hình chữ nhật trong Java PostScript

### Bước 1: Đặt màu vẽ cho việc tô hình chữ nhật  
**Cách đặt màu vẽ** – chúng ta chọn màu cam cho hình chữ nhật đầu tiên. Điều này minh họa khả năng **set rectangle color java**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Bước 2: Đặt màu vẽ cho việc viền hình chữ nhật  
**Set rectangle color java** – bây giờ chúng ta đổi màu vẽ sang màu đỏ và định nghĩa độ rộng nét. Phần này của ví dụ cho thấy cách **draw rectangle java** với độ dày đường tùy chỉnh.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Bước 3: Đóng trang hiện tại và lưu tài liệu  
Sau khi vẽ, chúng ta đóng trang và ghi lại tệp. Đóng trang đảm bảo tất cả các lệnh vẽ được đẩy vào luồng PostScript.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Các trường hợp sử dụng phổ biến cho việc vẽ hình chữ nhật
- **Tạo hoá đơn hoặc biên lai** – hình chữ nhật dùng làm viền hoặc làm nổi bật các phần.  
- **Tạo nhãn** – vẽ các hộp màu để tách thông tin sản phẩm.  
- **Biểu đồ đơn giản** – sử dụng các hình chữ nhật tô đầy làm thành phần của biểu đồ cột.  
- **Mẫu biểu mẫu có thể in** – kết hợp hình chữ nhật với văn bản để xây dựng các trường biểu mẫu.

## Các vấn đề thường gặp & Mẹo
- **Lỗi đường dẫn tệp** – đảm bảo `dataDir` kết thúc bằng dấu phân cách thư mục (`/` hoặc `\\`).  
- **Ngoại lệ giấy phép** – phiên bản dùng thử sẽ thêm watermark; cần mua giấy phép đầy đủ cho môi trường sản xuất.  
- **Khả năng hiển thị màu** – một số máy in có thể diễn giải các giá trị RGB khác nhau; hãy thử với một hình chữ nhật đen đơn giản trước.  
- **Tiêu thụ bộ nhớ** – đối với tài liệu lớn, cân nhắc flush luồng sau mỗi trang (`document.closePage()`).

## Câu hỏi thường gặp

**Hỏi:** *Tôi có thể dùng Aspose.Page for Java với các ngôn ngữ lập trình khác không?*  
**Đáp:** Aspose.Page chủ yếu hỗ trợ Java, nhưng các thư viện tương tự có sẵn cho các ngôn ngữ khác.

**Hỏi:** *Có phiên bản dùng thử của Aspose.Page for Java không?*  
**Đáp:** Có, bạn có thể khám phá các tính năng của Aspose.Page for Java qua [phiên bản dùng thử miễn phí](https://releases.aspose.com/).

**Hỏi:** *Tôi có thể tìm thêm trợ giúp và thảo luận ở đâu?*  
**Đáp:** Truy cập [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để giao lưu với cộng đồng và nhận hỗ trợ.

**Hỏi:** *Làm sao để lấy giấy phép tạm thời cho Aspose.Page for Java?*  
**Đáp:** Nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

**Hỏi:** *Tôi có thể mua phiên bản có giấy phép của Aspose.Page for Java ở đâu?*  
**Đáp:** Mua phiên bản có giấy phép [tại đây](https://purchase.aspose.com/buy).

**Câu hỏi bổ sung**

**Hỏi:** *Tôi có thể thay đổi kích thước hình chữ nhật một cách động không?*  
**Đáp:** Có – chỉ cần sửa các tham số `Rectangle2D.Float(x, y, width, height)` trước khi gọi `fill` hoặc `draw`.

**Hỏi:** *Có thể thêm văn bản vào bên trong hình chữ nhật không?*  
**Đáp:** Chắc chắn. Sau khi vẽ hình chữ nhật, sử dụng `document.drawString(...)` với phông chữ và vị trí mong muốn.

**Hỏi:** *Aspose.Page có hỗ trợ các hình dạng khác như vòng tròn hoặc đa giác không?*  
**Đáp:** Có, API cung cấp các phương thức như `drawEllipse` và `drawPolygon` cho nhiều loại đồ họa vector.

## Kết luận
Trong hướng dẫn này, chúng tôi đã trình bày **cách vẽ hình chữ nhật** trong tài liệu Java PostScript, bao gồm **cách đặt màu vẽ**, và chỉ ra cách **set rectangle color java** bằng Aspose.Page. Giờ đây bạn đã có nền tảng vững chắc để tạo ra các đồ họa in màu sống động, dù bạn đang xây dựng hoá đơn, nhãn, hay biểu mẫu tùy chỉnh. Hãy tự do thử nghiệm với các màu sắc, kiểu đường và các hình dạng AWT bổ sung để làm phong phú hơn kết quả của mình.

---

**Cập nhật lần cuối:** 2026-02-18  
**Kiểm tra với:** Aspose.Page for Java 24.12 (phiên bản mới nhất)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}