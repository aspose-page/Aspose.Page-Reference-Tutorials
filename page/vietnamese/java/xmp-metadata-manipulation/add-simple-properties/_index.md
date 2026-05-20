---
date: 2026-05-20
description: Tìm hiểu cách thêm siêu dữ liệu XMP vào tệp EPS với Aspose.Page for Java.
  Hướng dẫn từng bước để nhúng các thuộc tính XMP đơn giản một cách lập trình.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Thêm các thuộc tính đơn giản trong XMP bằng Java
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Thêm siêu dữ liệu XMP vào tệp EPS bằng Java
url: /vi/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm siêu dữ liệu XMP vào tệp EPS bằng Java

## Giới thiệu
Trong các quy trình đồ họa hiện đại, khả năng **thêm siêu dữ liệu XMP** vào các tệp EPS một cách lập trình cho phép bạn kiểm soát hoàn toàn cách mô tả, tìm kiếm và lưu trữ các minh họa của mình. Với Aspose.Page for Java, bạn có thể đọc, sửa đổi và ghi các gói XMP bên trong tài liệu EPS mà không rời khỏi môi trường Java. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn từng bước để thêm các thuộc tính XMP đơn giản vào tệp EPS, giúp bạn làm phong phú đồ họa với siêu dữ liệu tùy chỉnh một cách nhanh chóng và đáng tin cậy.

## Câu trả lời nhanh
- **What does “add XMP metadata to EPS” mean?** Nhúng một gói XMP (siêu dữ liệu dựa trên XML) vào bên trong tệp EPS.  
- **Which library is required?** Thư viện Aspose.Page for Java (có thể tải xuống từ trang Aspose).  
- **Do I need a license for testing?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **How many lines of code?** Ít hơn 30 dòng Java cộng với một vài câu lệnh import.  
- **Can I add other data types?** Có – ngày tháng, số nguyên, số thực, chuỗi và thậm chí mảng đều được hỗ trợ.

## Cách thêm siêu dữ liệu XMP vào tệp EPS bằng Java?
Tải tệp EPS bằng `new PsDocument("input.eps")`, lấy hoặc tạo gói XMP của nó, chèn các thuộc tính mong muốn, và sau đó lưu tài liệu trở lại đĩa – tất cả trong dưới mười dòng mã Java. Cách tiếp cận này cho phép bạn nhúng siêu dữ liệu có thể tìm kiếm, tuân thủ tiêu chuẩn mà không cần chỉnh sửa thủ công nguồn EPS.

## Siêu dữ liệu XMP trong EPS là gì?
Siêu dữ liệu XMP trong EPS là một gói XML nằm bên trong tệp EPS và lưu trữ thông tin như tác giả, ngày tạo và các thẻ tùy chỉnh. Nhúng gói này cho phép các công cụ hạ nguồn đọc và xử lý dữ liệu mà không cần các tệp phụ riêng biệt.

## Tại sao nên thêm siêu dữ liệu XMP vào tệp EPS?
Nhúng siêu dữ liệu XMP làm cho tài sản EPS có thể tìm kiếm ngay lập tức, đảm bảo tuân thủ bằng cách lưu thông tin cấp phép bên trong tệp, cho phép các quy trình tự động đưa ra quyết định dựa trên các thẻ nhúng, và đảm bảo siêu dữ liệu đi cùng đồ họa trên mọi nền tảng. Aspose.Page có thể xử lý các tệp lên tới 500 MB mà không cần tải toàn bộ tài liệu vào bộ nhớ, mang lại hiệu năng nhanh cho khối lượng công việc quy mô lớn.

## Yêu cầu trước
- Kiến thức cơ bản về lập trình Java.  
- Thư viện Aspose.Page for Java đã được cài đặt. Bạn có thể tải xuống **[tại đây](https://releases.aspose.com/page/java/)**.  
- Một tệp EPS mẫu chứa siêu dữ liệu. Nếu bạn chưa có, hãy sử dụng tệp **`xmp3.eps`** được cung cấp.

## Nhập gói
Đầu tiên, nhập các lớp bạn sẽ cần. Các câu lệnh import giữ nguyên như trong ví dụ gốc:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Bước 1: Tải tài liệu EPS và lấy siêu dữ liệu XMP
Lớp `PsDocument` đại diện cho một tệp EPS và cung cấp các phương thức để truy cập nội dung và siêu dữ liệu của nó.  
Đối tượng `XmpMetadata` chứa gói XMP liên kết với tài liệu.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Bước 2: Thêm thuộc tính Date
Lớp `Date` đại diện cho một thời điểm cụ thể trong thời gian, với độ chính xác mili giây.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Bước 3: Thêm thuộc tính Integer
Lớp `Integer` bọc một giá trị nguyên primitive `int` dưới dạng đối tượng.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Bước 4: Thêm thuộc tính Double
Lớp `Double` bọc một giá trị primitive `double` dưới dạng đối tượng.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Bước 5: Thêm thuộc tính String
Lớp `String` đại diện cho một chuỗi ký tự.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Bước 6: Lưu tệp EPS đã cập nhật
Phương thức `save` ghi tài liệu đã sửa đổi trở lại đĩa, giữ nguyên cấu trúc EPS.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Bước 7: Dọn dẹp tài nguyên
Luôn đóng các luồng để tránh rò rỉ handle tệp và đảm bảo mọi bộ đệm được flush.

```java
// Close input EPS stream
psStream.close();
```

## Các vấn đề thường gặp và giải pháp
| Vấn đề | Lý do | Cách khắc phục |
|-------|--------|----------------|
| **Null XMP metadata** | Tệp EPS không có gói XMP và thư viện không thể suy ra các chú thích PS. | Đảm bảo EPS nguồn chứa ít nhất một chú thích PS (ví dụ, `%%Creator`). Thư viện sẽ tự động tạo một gói XMP tối thiểu. |
| **Time zone mismatch** | Ngày tháng bị lệch khi mở trong ứng dụng khác. | Đặt `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` trước khi tạo đối tượng `Date`, như trong Bước 2. |
| **License exception** | Runtime ném `LicenseException`. | Áp dụng giấy phép Aspose.Page hợp lệ trước khi sử dụng API, hoặc chạy ở chế độ dùng thử để đánh giá. |

## Câu hỏi thường gặp
**Q: Can I use Aspose.Page for Java with other programming languages?**  
A: Aspose.Page chủ yếu hỗ trợ Java, nhưng các thư viện tương đương có sẵn cho .NET, C++, và Python.

**Q: Is a free trial available for Aspose.Page for Java?**  
A: Có, bạn có thể khám phá các tính năng của Aspose.Page bằng cách nhận bản dùng thử miễn phí **[tại đây](https://releases.aspose.com/)**.

**Q: Where can I find detailed documentation for Aspose.Page for Java?**  
A: Tài liệu có sẵn **[tại đây](https://reference.aspose.com/page/java/)**.

**Q: How can I obtain a temporary license for Aspose.Page for Java?**  
A: Giấy phép tạm thời có thể được mua **[tại đây](https://purchase.aspose.com/temporary-license/)**.

**Q: Where can I purchase Aspose.Page for Java?**  
A: Bạn có thể mua sản phẩm **[tại đây](https://purchase.aspose.com/buy)**.

---

**Cập nhật lần cuối:** 2026-05-20  
**Kiểm tra với:** Aspose.Page for Java 24.12 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Cách đọc siêu dữ liệu XMP bằng Java – Hướng dẫn Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp tutorial – Thêm Namespace trong XMP bằng Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Thêm mục mảng trong siêu dữ liệu XMP bằng Java](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}