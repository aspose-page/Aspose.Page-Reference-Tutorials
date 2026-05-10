---
date: 2026-02-13
description: Học cách tạo gradient PostScript với gradient dừng màu dạng tròn bằng
  Aspose.Page cho Java. Hướng dẫn chi tiết này sẽ chỉ cho bạn cách thêm gradient dừng
  màu vào tài liệu của mình.
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: Tạo Gradient PostScript – Gradient Tia trong Java
url: /vi/java/postscript-gradient-addition/radial1/
weight: 12
---

 keep the "## Conclusion".

We need to keep the "## Introduction" etc.

We need to ensure we translate "Radial Gradient" maybe keep as "gradient dạng tròn" but keep term "Radial Gradient" maybe keep as is? The rule: keep technical terms in English, but "radial gradient" is a technical term, maybe keep as is. But we can translate surrounding text.

Let's proceed.

We'll produce the final content.

Make sure to keep all shortcodes at beginning and end.

Let's write translation.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Gradient Hình Tròn trong Java PostScript bằng Aspose.Page

## Giới thiệu
Nếu bạn từng cần **tạo một gradient PostScript** với chuyển đổi màu mượt mà, bắt mắt, việc học cách thêm gradient hình tròn là điểm khởi đầu hoàn hảo. Trong hướng dẫn này, chúng ta sẽ đi qua từng bước cần thiết để tạo một tệp PostScript chứa gradient hình tròn đẹp mắt, sử dụng thư viện **Aspose.Page for Java**. Khi hoàn thành, bạn sẽ hiểu API, xem một ví dụ đầy đủ có thể chạy, và biết cách điều chỉnh màu sắc, vị trí và bán kính để phù hợp với bất kỳ thiết kế nào.

## Câu trả lời nhanh
- **Thư viện nào tạo gradient hình tròn trong PostScript?** Aspose.Page for Java.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút cho một ví dụ cơ bản.  
- **Có cần giấy phép để chạy mã không?** Bản dùng thử miễn phí đủ cho phát triển; giấy phép thương mại cần cho môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 hoặc cao hơn.  
- **Tôi có thể thay đổi hình dạng của gradient không?** Có – điều chỉnh bán kính và điểm trung tâm trong hàm khởi tạo `RadialGradientPaint`.

## Cách Tạo Gradient PostScript với Đổ Bổ Sung Hình Tròn
Dưới đây là hướng dẫn ngắn gọn, từng bước, cho thấy cách **tạo nội dung gradient PostScript** bằng cách đổ màu hình tròn. Mỗi bước bao gồm một giải thích ngắn và sau đó là khối mã gốc (không thay đổi).

## Gradient Hình Tròn là gì?
Gradient hình tròn tô màu lan tỏa ra từ một điểm trung tâm, dần dần hòa quyện về phía các cạnh. Khác với gradient tuyến tính, chuyển đổi màu theo một mẫu vòng tròn (hoặc elip), rất thích hợp cho các điểm nhấn, ánh sáng spot, hoặc nền nền mềm mại.

## Tại sao nên dùng Aspose.Page cho Gradient Hình Tròn?
- **Kiểm soát đầy đủ đầu ra PostScript** – không cần tự viết các lệnh PS cấp thấp.  
- **Đa nền tảng** – hoạt động trên bất kỳ hệ điều hành nào chạy Java.  
- **Quản lý màu sắc phong phú** – hỗ trợ nhiều điểm dừng màu, các không gian màu khác nhau và các phương pháp lặp.  
- **Sẵn sàng tích hợp** – kết hợp với các tính năng khác của Aspose.Page như văn bản, hình ảnh và hình dạng vector.

## Yêu cầu trước
Trước khi chúng ta bắt đầu với mã, hãy chắc chắn bạn đã chuẩn bị sẵn:

- **Java Development Kit (JDK) 8+** – kiểm tra bằng `java -version`.  
- **Aspose.Page for Java** – tải JAR mới nhất từ trang [trang tải Aspose.Page](https://releases.aspose.com/page/java/).  
- **IDE yêu thích** – Eclipse, IntelliJ IDEA, hoặc VS Code với các extension Java.  
- **Thư mục có quyền ghi** – nơi sẽ lưu tệp `.ps` được tạo.

## Nhập khẩu các Gói
Đầu tiên, nhập các lớp cần thiết. Gói `java.awt` cung cấp các đối tượng gradient paint, trong khi `com.aspose.eps` chứa các lớp xử lý tài liệu PostScript.

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

## Hướng Dẫn Từng Bước

### Bước 1: Tạo một Hình Chữ Nhật và Mở Tài liệu PS
Chúng ta bắt đầu bằng việc tạo một luồng xuất, cấu hình kích thước trang (mặc định A4), và định nghĩa một hình chữ nhật sẽ chứa gradient.

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

### Bước 2: Định Nghĩa Màu Sắc và Tỷ Lệ
Gradient hình tròn được xây dựng từ *các điểm dừng màu* (colors) và *các tỷ lệ* (fractions). Ở đây chúng ta tạo một mảng gồm sáu màu và các tỷ lệ tương ứng.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Tại sao điều này quan trọng:** Bằng cách tinh chỉnh `fractions` bạn kiểm soát tốc độ chuyển đổi màu, cho phép tạo hiệu ứng nhẹ nhàng hoặc mạnh mẽ.

### Thêm Gradient Điểm Dừng Màu vào Đổ Bổ Sung Hình Tròn
Khi bạn cần **thêm gradient điểm dừng màu**, các mảng `colors` và `fractions` là chìa khóa. Bạn có thể sắp xếp lại, thêm hoặc xóa các mục để phù hợp với thiết kế của mình.

### Bước 3: Tạo Đối Tượng RadialGradientPaint
Bây giờ chúng ta xây dựng đối tượng `RadialGradientPaint`. Hàm khởi tạo nhận điểm trung tâm của gradient, bán kính, điểm tiêu điểm, các tỷ lệ, màu sắc, phương pháp lặp, không gian màu và một phép biến đổi tùy chọn.

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

> **Lưu ý:** `transform` có thể để `null` nếu bạn không cần phép co dãn hoặc quay bổ sung. Hãy thử nghiệm với `AffineTransform` để tạo gradient nghiêng.

### Bước 4: Đặt Paint và Đổ Bổ Sung Hình Chữ Nhật
Khi paint đã sẵn sàng, chúng ta yêu cầu `PsDocument` sử dụng nó và sau đó đổ màu vào hình chữ nhật đã định nghĩa trước đó.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

Tại thời điểm này, trang PostScript chứa một hình chữ nhật được đổ đầy gradient hình tròn mượt mà mà chúng ta đã cấu hình.

### Bước 5: Đóng và Lưu Tài liệu
Cuối cùng, đóng trang hiện tại và ghi tệp ra đĩa.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Mở `RadialGradient1_outPS.ps` bằng bất kỳ trình xem PostScript nào (ví dụ: Ghostscript) và bạn sẽ thấy gradient được hiển thị chính xác như đã định nghĩa.

## Các Vấn Đề Thường Gặp & Giải Pháp
| Triệu chứng | Nguyên nhân có thể | Cách khắc phục |
|------------|--------------------|----------------|
| Gradient hiển thị thành màu đồng nhất | Mảng `fractions` không bắt đầu ở `0.0f` hoặc không kết thúc ở `1.0f` | Đảm bảo phần tử đầu tiên là `0.0f` và phần tử cuối cùng là `1.0f`. |
| Màu sắc bị nhạt | Sử dụng sai `ColorSpaceType` | Chuyển sang `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` để có màu sắc sống động hơn. |
| Không tạo được tệp đầu ra | Đường dẫn `FileOutputStream` không hợp lệ hoặc không có quyền ghi | Kiểm tra `dataDir` tồn tại và ứng dụng có quyền ghi. |

## Câu Hỏi Thường Gặp

**H: Tôi có thể dùng Aspose.Page for Java trong dự án thương mại không?**  
Đ: Có. Cần giấy phép thương mại cho môi trường sản xuất. Bạn có thể mua tại trang [trang giấy phép Aspose](https://purchase.aspose.com/buy).

**H: Tôi có thể tìm tài liệu API chính thức ở đâu?**  
Đ: Tài liệu đầy đủ có sẵn [tại đây](https://reference.aspose.com/page/java/).

**H: Có bản dùng thử miễn phí để thử nghiệm không?**  
Đ: Chắc chắn. Tải phiên bản dùng thử từ [trang phát hành Aspose.Page](https://releases.aspose.com/).

**H: Làm sao để lấy giấy phép tạm thời để đánh giá?**  
Đ: Bạn có thể yêu cầu giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

**H: Tôi có thể nhận hỗ trợ cộng đồng ở đâu?**  
Đ: Tham gia diễn đàn cộng đồng Aspose.Page tại [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Kết luận
Bây giờ bạn đã biết **cách thêm gradient hình tròn** vào tài liệu Java PostScript bằng Aspose.Page. Bằng cách điều chỉnh kích thước hình chữ nhật, các điểm dừng màu và bán kính gradient, bạn có thể tạo vô số hiệu ứng hình ảnh—from nền nền nhẹ nhàng đến các đồ họa spot sáng mạnh. Hãy thử nghiệm với các giá trị `AffineTransform` khác nhau để quay hoặc nghiêng gradient, và kết hợp kỹ thuật này với văn bản và hình ảnh để có đầu ra PDF hoặc EPS phong phú hơn.

---

**Cập nhật lần cuối:** 2026-02-13  
**Kiểm thử với:** Aspose.Page for Java phiên bản mới nhất (tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}