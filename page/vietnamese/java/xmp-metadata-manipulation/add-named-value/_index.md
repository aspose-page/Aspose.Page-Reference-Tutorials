---
date: 2026-09-19
description: Tìm hiểu cách thêm các giá trị có tên XMP vào tệp EPS bằng Aspose.Page
  for Java – hướng dẫn từng bước kèm ví dụ mã.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Thêm Giá Trị Có Tên trong XMP bằng Java
og_description: Cách thêm các giá trị có tên XMP vào tệp EPS bằng Aspose.Page for
  Java. Tham khảo hướng dẫn ngắn gọn này để chèn siêu dữ liệu tùy chỉnh trong vài
  phút.
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: Cách thêm giá trị có tên XMP vào tệp EPS bằng Java
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: Cách thêm giá trị có tên XMP vào tệp EPS bằng Java
url: /vi/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm giá trị có tên vào siêu dữ liệu XMP bằng Java

## Giới thiệu
Trong phát triển Java hiện đại, việc học **cách thêm XMP** vào siêu dữ liệu trong các tệp EPS là cần thiết để bảo tồn nguồn gốc tài liệu và cải thiện khả năng tìm kiếm. Với **Aspose.Page for Java**, bạn có thể dễ dàng chèn các giá trị có tên tùy chỉnh vào gói XMP. Hướng dẫn này sẽ đưa bạn qua các bước chính xác—kèm đầy đủ các đoạn mã—để bạn có thể bắt đầu thêm siêu dữ liệu XMP vào tài liệu EPS của mình ngay hôm nay.

## Câu trả lời nhanh
- **Thư viện cần thiết?** Aspose.Page for Java (Aspose)  
- **Loại tệp được nhắm tới?** EPS files containing XMP metadata  
- **Trường hợp sử dụng chính?** Thêm các giá trị có tên tùy chỉnh (ví dụ: giới hạn kích thước trang) vào XMP  
- **Yêu cầu tiên quyết?** JDK 8+ và thư viện Aspose.Page for Java  
- **Thời gian triển khai điển hình?** 5–10 phút một khi đã cài đặt thư viện  

## Asp là gì?
Aspose là viết tắt của Aspose, một bộ API cho phép các nhà phát triển tạo, chỉnh sửa, chuyển đổi và hiển thị đa dạng các định dạng tài liệu mà không cần phần mềm bên ngoài. Thành phần Aspose.Page for Java tập trung đặc biệt vào việc xử lý PostScript và EPS, cung cấp quyền truy cập lập trình vào nội dung trang, đồ họa và siêu dữ liệu như XMP.

## Tại sao thêm các giá trị có tên vào siêu dữ liệu XMP?
Các giá trị có tên cho phép bạn lưu trữ các cặp khóa‑giá trị tùy ý trực tiếp trong gói XMP, khiến chúng có thể được các công cụ hạ nguồn đọc ngay lập tức. Điều này cải thiện tính thân thiện với công cụ tìm kiếm, cho phép tự động hoá quy trình làm việc, và đáp ứng các yêu cầu tuân thủ bằng cách nhúng thông tin quy định mà không thay đổi nội dung hình ảnh.

## Tại sao điều này quan trọng
Việc thêm các giá trị có tên vào XMP cho phép bạn lưu trữ các cặp khóa‑giá trị tùy ý có thể được đọc mà không cần phân tích toàn bộ tệp EPS. Khả năng này đặc biệt có giá trị trong các quy trình xuất bản tự động, hệ thống quản lý tài sản kỹ thuật số và quy trình làm việc dựa trên tuân thủ, nơi siêu dữ liệu điều khiển các hành động hạ nguồn.

## Yêu cầu tiên quyết
Trước khi bắt đầu, hãy đảm bảo bạn có những thứ sau:

- **Java Development Kit (JDK):** Một JDK mới (phiên bản 8 trở lên) đã được cài đặt trên máy của bạn.  
- **Aspose.Page for Java Library:** Tải xuống từ [Aspose.Page for Java download](https://releases.aspose.com/page/java/). Thêm tệp JAR vào classpath của dự án.  
- **Tệp EPS** đã chứa siêu dữ liệu XMP hoặc sẽ được tạo tự động.

## Nhập các gói
Bắt đầu bằng việc nhập các gói Java cần thiết. Các import này cung cấp cho bạn quyền truy cập vào các luồng tệp, mô hình tài liệu EPS và các lớp xử lý XMP.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Cách thêm giá trị có tên XMP vào tệp EPS bằng Java
Để thêm một giá trị có tên, tải tệp EPS bằng `FileInputStream`, lấy hoặc tạo đối tượng `XmpMetadata` của nó, chèn `NamedValue` mong muốn vào không gian tên thích hợp, và sau đó ghi tài liệu đã sửa lại bằng `FileOutputStream`. Aspose.Page tự động xử lý việc tạo gói XMP nếu thiếu, đảm bảo siêu dữ liệu mới được nhúng đúng cách.

### Bước 1: Khởi tạo luồng tệp EPS đầu vào
**FileInputStream** là một lớp I/O của Java đọc các byte thô từ một tệp. Tải tệp EPS nguồn vào một `FileInputStream`. Luồng này cung cấp tài liệu cho API của Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Mẹo:** Giữ biến `dataDir` có thể cấu hình để cùng một đoạn mã hoạt động trên mọi môi trường.

### Bước 2: Lấy siêu dữ liệu XMP
**XmpMetadata** đại diện cho gói XMP liên kết với tài liệu EPS. Lấy gói XMP hiện có; nếu tệp EPS không có, Aspose sẽ tạo một đối tượng XMP mới được điền từ các chú thích PS.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Bước 3: Thêm giá trị có tên
**NamedValue** là một cặp khóa‑giá trị được lưu trong không gian tên siêu dữ liệu XMP. Chèn một giá trị có tên tùy chỉnh vào cấu trúc XMP. Trong ví dụ này chúng tôi thêm một khóa mới dưới không gian tên `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Tại sao điều này quan trọng:** Các giá trị có tên cho phép bạn lưu trữ các cặp khóa‑giá trị tùy ý mà các ứng dụng hạ nguồn có thể đọc mà không cần phân tích toàn bộ tài liệu.

### Bước 4: Khởi tạo luồng tệp EPS đầu ra
**FileOutputStream** là một lớp I/O của Java ghi các byte thô vào một tệp. Chuẩn bị một `FileOutputStream` để lưu tệp EPS đã sửa.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Bước 5: Lưu tài liệu
Phương thức `save` lưu lại các thay đổi. Nó ghi gói XMP đã cập nhật trở lại tệp EPS, đảm bảo rằng giá trị có tên mới trở thành một phần của siêu dữ liệu tài liệu.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Bước 6: Đóng luồng EPS đầu vào
Đóng handle tệp gốc ngăn ngừa rò rỉ tài nguyên và đảm bảo tệp không bị khóa cho các thao tác tiếp theo.

```java
psStream.close();
```

Bằng cách thực hiện sáu bước này, bạn đã thành công **thêm một giá trị có tên vào siêu dữ liệu XMP** bằng **Aspose.Page for Java**.

## Các vấn đề thường gặp & giải pháp
| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| `NullPointerException` on `xmp` | Tệp EPS không có XMP và Aspose không tạo được | Đảm bảo EPS chứa ít nhất một chú thích PS hoặc tạo thủ công một đối tượng `XmpMetadata` mới. |
| Tệp đầu ra rỗng | Luồng đầu ra không được flush/đóng | Kiểm tra `outPsStream.close()` được gọi trong khối `finally` (như minh họa). |
| Lỗi khóa trùng lặp | Cùng một giá trị có tên được thêm hai lần | Kiểm tra xem khóa đã tồn tại bằng `xmp.containsNamedValue(...)` trước khi thêm. |

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng Aspose.Page for Java cùng với các thư viện Java khác không?**  
A: Có, Aspose.Page for Java được thiết kế để hoạt động liền mạch với các thư viện Java khác, cung cấp tính linh hoạt trong môi trường phát triển của bạn.

**Q: Có bản dùng thử miễn phí cho Aspose.Page for Java không?**  
A: Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.Page for Java trên [trang phát hành của Aspose](https://releases.aspose.com/).

**Q: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Page for Java?**  
A: Truy cập [trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) để nhận giấy phép tạm thời cho Aspose.Page for Java.

**Q: Tôi có thể tìm thêm các hướng dẫn và ví dụ cho Aspose.Page for Java ở đâu?**  
A: Khám phá [tài liệu](https://reference.aspose.com/page/java/) để có các hướng dẫn và ví dụ toàn diện.

**Q: Aspose.Page for Java có phù hợp cho các dự án quy mô lớn không?**  
A: Chắc chắn, Aspose.Page for Java được thiết kế để xử lý các dự án quy mô lớn một cách hiệu quả, cung cấp khả năng thao tác tài liệu mạnh mẽ.

## Kết luận
Trong hướng dẫn này, chúng tôi đã chứng minh cách **Aspose.Page for Java** giúp **thêm các giá trị có tên vào siêu dữ liệu XMP** trong các tệp EPS một cách dễ dàng. Với các bước trên, bạn có thể làm phong phú tài liệu của mình bằng siêu dữ liệu tùy chỉnh, cải thiện khả năng tìm kiếm và cho phép xử lý hạ nguồn thông minh hơn.

---

**Cập nhật lần cuối:** 2026-09-19  
**Đã kiểm tra với:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách Thêm Không Gian Tên XMP trong Tệp EPS Sử Dụng Aspose.Page – Hướng Dẫn Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Thêm Siêu Dữ Liệu XMP vào Tệp EPS Sử Dụng Java](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [Đọc XMP bằng Aspose.Page – Hướng Dẫn Java](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}