---
date: 2025-12-07
description: Tìm hiểu cách co dãn hình chữ nhật, dịch chuyển hình dạng và áp dụng
  biến đổi affine trong Java bằng Aspose.Page để tạo tài liệu PostScript.
language: vi
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Cách thu phóng hình chữ nhật và áp dụng các phép biến đổi với Aspose.Page
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thu Phóng Hình Chữ Nhật và Áp Dụng Biến Đổi với Aspose.Page

## Giới thiệu
Chào mừng bạn đến với hướng dẫn toàn diện về việc sử dụng các tính năng mạnh mẽ của **Aspose.Page for Java** để thực hiện đa dạng các biến đổi trang. Trong tutorial này, bạn sẽ học **cách thu phóng hình chữ nhật**, dịch chuyển các hình dạng, xoay các đối tượng, và **áp dụng kỹ thuật biến đổi affine** khi tạo **tài liệu PostScript**. Những khả năng này cho phép bạn xây dựng các ứng dụng Java giàu đồ họa mà không cần viết mã render cấp thấp.

## Trả lời nhanh
- **Làm sao để thu phóng một hình chữ nhật trong Java với Aspose.Page?** Sử dụng phương thức `document.scale()` trước khi vẽ hình.  
- **Tôi có thể di chuyển (dịch) một hình dạng mà không ảnh hưởng đến các đồ họa khác không?** Có — lưu trạng thái đồ họa, gọi `document.translate(x, y)`, vẽ, rồi khôi phục trạng thái.  
- **Lớp nào tạo file PostScript?** `PsDocument` kết hợp với `PsSaveOptions`.  
- **Có cần giấy phép cho việc sử dụng trong môi trường production không?** Cần một giấy phép Aspose.Page hợp lệ cho các triển khai thương mại.  
- **Phiên bản Java nào được hỗ trợ?** Aspose.Page hoạt động với Java 8 trở lên.

## Điều kiện tiên quyết
Trước khi bắt đầu hướng dẫn chi tiết, hãy chắc chắn bạn đã chuẩn bị các điều kiện sau:

- Kiến thức cơ bản về lập trình Java.  
- Thư viện Aspose.Page for Java đã được cài đặt. Bạn có thể tải xuống từ [tài liệu Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Một môi trường phát triển tích hợp (IDE) cho Java đã được thiết lập trên máy tính của bạn.

## Nhập gói
Trong dự án Java của bạn, nhập các gói cần thiết để sử dụng Aspose.Page for Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## “how to scale rectangle” trong Aspose.Page là gì?
Việc thu phóng một hình chữ nhật thay đổi kích thước của nó theo trục X và Y trong khi vẫn giữ nguyên hình dạng. Aspose.Page cung cấp phương thức `scale(float sx, float sy)`, áp dụng một **biến đổi affine** lên trạng thái đồ họa hiện tại. Đây là kỹ thuật cốt lõi đằng sau từ khóa **how to scale rectangle**.

## Cách Dịch Chuyển Hình Dạng với Aspose.Page
Dịch chuyển di chuyển một hình dạng tới vị trí mới mà không thay đổi kích thước của nó. Đây là bản chất của **how to translate shape**. Bằng cách lưu trạng thái đồ họa, áp dụng `translate(dx, dy)`, vẽ, và sau đó khôi phục trạng thái, bạn giữ cho các đối tượng khác không bị ảnh hưởng.

## Ví dụ 1: Không Có Biến Đổi
Ví dụ đầu tiên vẽ một hình chữ nhật đơn giản mà không áp dụng bất kỳ biến đổi nào. Đây là cơ sở để so sánh với các ví dụ sau.

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

## Ví dụ 2: Dịch Chuyển
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

## Ví dụ 3: Thu Phóng
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

## Cách Xoay Hình Dạng Java (rotate shape java)
Xoay là một thao tác affine phổ biến khác. Mặc dù các đoạn mã xoay bị bỏ qua để ngắn gọn, mẫu thực hiện vẫn giống nhau: lưu trạng thái đồ họa, gọi `document.rotate(angle)`, vẽ hình, rồi khôi phục. Điều này minh họa **rotate shape java** và **how to rotate rectangle** trong thực tế.

## Tại sao nên dùng Aspose.Page cho các biến đổi này?
- **Không phụ thuộc vào thiết bị**: Viết một lần, tạo PostScript hoặc XPS mà không cần mã đặc thù nền tảng.  
- **Kiểm soát chi tiết**: Truy cập trực tiếp vào trạng thái đồ họa cho phép bạn kết hợp dịch chuyển, thu phóng, kéo dãn và xoay.  
- **Hiệu năng**: API nhẹ, phù hợp cho xử lý hàng loạt tài liệu lớn.  

## Các trường hợp sử dụng phổ biến
- Tạo hoá đơn có thể in được với mã vạch và logo động.  
- Thiết kế sơ đồ kỹ thuật yêu cầu độ chính xác cao trong việc thu phóng và định vị.  
- Tự động hoá việc sản xuất báo cáo đa trang ở định dạng PostScript.

## Kết luận
Trong tutorial này, chúng ta đã khám phá các biến đổi khác nhau trong việc thao tác trang Java bằng Aspose.Page for Java, tập trung vào **how to scale rectangle**, **how to translate shape**, và các thao tác affine khác. Bằng cách làm theo các ví dụ này, bạn có thể nâng cao ứng dụng Java của mình với khả năng thao tác trang nâng cao và **tạo tài liệu PostScript** đáp ứng tiêu chuẩn xuất bản chuyên nghiệp.

## Câu hỏi thường gặp
### Tôi có thể dùng Aspose.Page for Java cho các định dạng tài liệu khác không?
Aspose.Page chủ yếu tập trung vào thao tác trang cho định dạng PostScript và XPS.

### Tôi có thể tìm thêm ví dụ và tài liệu cho Aspose.Page for Java ở đâu?
Truy cập [tài liệu Aspose.Page for Java](https://reference.aspose.com/page/java/) để có thông tin chi tiết.

### Có bản dùng thử miễn phí cho Aspose.Page for Java không?
Có, bạn có thể truy cập bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### Làm sao để lấy giấy phép tạm thời cho Aspose.Page for Java?
Nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể tìm hỗ trợ cộng đồng hoặc đặt câu hỏi về Aspose.Page for Java ở đâu?
Tham gia diễn đàn [Aspose.Page for Java](https://forum.aspose.com/c/page/39) để thảo luận với cộng đồng.

## Các câu hỏi thường gặp khác

**H: Sự khác nhau giữa `translate` và `scale` là gì?**  
Đ: `translate` di chuyển gốc của hệ tọa độ, trong khi `scale` thay đổi kích thước của các đối tượng được vẽ theo trục X và/hoặc Y.

**H: Tôi có thể kết hợp nhiều biến đổi trong một trạng thái đồ họa không?**  
Đ: Có — bằng cách gọi `translate`, `scale`, `rotate`, hoặc `shear` liên tiếp trước khi vẽ, bạn tạo ra một biến đổi affine tổng hợp.

**H: Làm sao để đặt lại các biến đổi sau khi vẽ một hình dạng?**  
Đ: Sử dụng `document.writeGraphicsRestore()` để quay lại trạng thái đồ họa đã lưu trước đó.

**H: Có thể xoay một hình chữ nhật quanh trung tâm của nó không?**  
Đ: Chắc chắn. Dịch chuyển hình chữ nhật tới gốc, áp dụng `rotate(angle)`, rồi dịch chuyển lại vị trí ban đầu trước khi vẽ.

**H: Aspose.Page có hỗ trợ anti‑aliasing để làm mịn đồ họa không?**  
Đ: Có — đặt các tùy chọn render phù hợp trong `PsSaveOptions` để bật anti‑aliasing.

---

**Cập nhật lần cuối:** 2025-12-07  
**Đã kiểm tra với:** Aspose.Page for Java 24.12  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}