---
date: 2026-05-15
description: Tìm hiểu cách chỉnh sửa siêu dữ liệu XMP và cách thay đổi giá trị XMP
  trong các tệp EPS bằng Aspose.Page for Java – hướng dẫn rõ ràng từng bước
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Thay đổi giá trị có tên trong XMP bằng Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: cách chỉnh sửa XMP – Thay đổi giá trị có tên trong XMP bằng Java
url: /vi/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# cách chỉnh sửa xmp – Thay đổi Giá trị Được Đặt Tên trong XMP bằng Java

Trong các quy trình tài liệu hiện đại, **Aspose.Page for Java** giúp dễ dàng đọc, chỉnh sửa và ghi siêu dữ liệu XMP trong các tệp EPS. **Hướng dẫn này cho thấy cách chỉnh sửa xmp** siêu dữ liệu trong tài liệu EPS bằng API Aspose.Page, để bạn có thể giữ thông tin tài liệu chính xác, có thể tìm kiếm và tuân thủ các tiêu chuẩn ngành. Dù bạn đang cập nhật kích thước trang, thông tin tác giả, hay các thẻ tùy chỉnh, các bước dưới đây sẽ hướng dẫn bạn quy trình bằng Java.

## Câu trả lời nhanh
- **Nội dung của hướng dẫn này là gì?** Changing a named XMP value in an EPS file with Aspose.Page for Java.  
- **Phiên bản thư viện nào được yêu cầu?** Any recent Aspose.Page for Java release (the API has been stable for several years).  
- **Tôi có cần giấy phép không?** A temporary or full license is required for production; a free trial works for testing.  
- **Thời gian thực hiện dự kiến là bao lâu?** Roughly 10‑15 minutes for a developer familiar with Java I/O.  
- **Tôi có thể sử dụng với các định dạng tệp khác không?** The XMP API is also available for PDF, SVG, and other formats supported by Aspose.Page.

## XMP metadata là gì?
XMP (Extensible Metadata Platform) là một định dạng chuẩn dựa trên XML để nhúng siêu dữ liệu phong phú—như người tạo, tiêu đề và các thuộc tính tùy chỉnh—trực tiếp vào các tệp. Trong tài liệu EPS, XMP tồn tại cùng với các chú thích PostScript truyền thống, cho phép các ứng dụng đọc và sửa đổi siêu dữ liệu mà không làm thay đổi nội dung hình ảnh.

## Tại sao nên sử dụng Aspose.Page for Java để chỉnh sửa XMP?
Aspose.Page cung cấp cho bạn **toàn quyền kiểm soát hơn 150 thuộc tính schema XMP** và hoạt động nhất quán trên các định dạng EPS, PDF và SVG. Nó xử lý các tệp lên tới **500 MB** mà không cần tải toàn bộ tài liệu vào bộ nhớ, và bao gồm tính năng xác thực tích hợp đảm bảo EPS tạo ra vẫn tuân thủ tiêu chuẩn. Không cần bộ phân tích XML bên ngoài hay thư viện gốc.

## Giới thiệu
Aspose.Page for Java là một thư viện mạnh mẽ giúp thực hiện việc thao tác và xử lý các tệp EPS. Khi làm việc với siêu dữ liệu XMP trong các tệp này, Aspose.Page cung cấp cho các nhà phát triển một bộ tính năng toàn diện. Trong hướng dẫn này, chúng ta sẽ tập trung vào việc thay đổi một giá trị được đặt tên trong XMP, cung cấp một hướng dẫn rõ ràng và ngắn gọn cho các nhà phát triển muốn nâng cao khả năng xử lý tài liệu.

## Yêu cầu trước
Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn đã chuẩn bị các yêu cầu sau:
1. **Môi trường phát triển Java** – A JDK (8 or higher) and an IDE or build tool (Maven/Gradle).  
2. **Thư viện Aspose.Page for Java** – Tải xuống và tích hợp thư viện Aspose.Page for Java vào dự án của bạn. Bạn có thể tìm thư viện và tài liệu chi tiết [tại đây](https://reference.aspose.com/page/java/).  
3. **Tệp EPS mẫu** – Chuẩn bị một tệp EPS mẫu để thử nghiệm. Nếu bạn chưa có, hãy sử dụng tệp ví dụ được cung cấp có tên **"xmp4.eps."**

## Nhập gói
Các câu lệnh `import` đưa các lớp Aspose.Page cần thiết vào phạm vi.

Lớp `PsDocument` là đối tượng cốt lõi của Aspose.Page đại diện cho một tài liệu EPS trong bộ nhớ.  
Lớp `XmpMetadata` cung cấp quyền truy cập vào gói XMP được nhúng trong tệp EPS.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Cách chỉnh sửa siêu dữ liệu XMP?
Tải tệp EPS, lấy gói XMP của nó, sửa đổi thuộc tính mong muốn và lưu tài liệu—tất cả trong vài dòng đơn giản. Cách tiếp cận này hoạt động cho bất kỳ giá trị XMP nào được đặt tên, dù là trường Dublin Core tiêu chuẩn hay không gian tên tùy chỉnh mà bạn đã định nghĩa.

## Bước 1: Khởi tạo luồng tệp EPS đầu vào
`FileInputStream` mở một luồng chỉ đọc tới tệp EPS nguồn, cho phép Aspose.Page đọc tài liệu mà không khóa hệ thống tệp.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Bước 2: Khởi tạo PsDocument
`PsDocument` là đối tượng chính bao gồm nội dung EPS và cung cấp quyền truy cập vào siêu dữ liệu, các trang và tài nguyên của nó.

```java
PsDocument document = new PsDocument(psStream);
```

## Bước 3: Lấy siêu dữ liệu XMP
`XmpMetadata` đại diện cho gói XMP trong tệp EPS và cung cấp các phương thức để đọc, sửa đổi hoặc xóa các thuộc tính riêng lẻ.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Bước 4: Đặt giá trị mới trong XMP
`setProperty` đặt giá trị của một thuộc tính XMP được chỉ định trong gói siêu dữ liệu.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Bước 5: Khởi tạo luồng tệp EPS đầu ra
`FileOutputStream` tạo một luồng ghi để lưu tệp EPS đã chỉnh sửa.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Bước 6: Lưu tài liệu với siêu dữ liệu XMP đã thay đổi
`save` ghi đối tượng PsDocument trong bộ nhớ, bao gồm XMP đã cập nhật, vào luồng đầu ra.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Bước 7: Đóng luồng EPS đầu vào
`close` giải phóng tay cầm tệp và giải phóng tài nguyên liên quan đến luồng đầu vào.

```java
// Close input EPS stream
psStream.close();
```

## Các vấn đề thường gặp và giải pháp
- **FileNotFoundException** – Xác minh rằng `dataDir` trỏ tới thư mục đúng và `xmp4.eps` tồn tại.  
- **LicenseException** – Nếu bạn gặp lỗi giấy phép, hãy chắc chắn rằng tệp giấy phép Aspose.Page hợp lệ đã được tải trước khi tạo `PsDocument`.  
- **Metadata Not Updated** – Sau khi lưu, mở EPS kết quả trong một công cụ xem siêu dữ liệu (ví dụ, Adobe Bridge) để xác nhận giá trị mới xuất hiện.

## Câu hỏi thường gặp
**Q: Tôi có thể sử dụng Aspose.Page for Java với các ngôn ngữ lập trình khác không?**  
A: Aspose.Page chủ yếu hỗ trợ Java, nhưng Aspose cung cấp các thư viện tương đương cho .NET, C++ và Python có khả năng thao tác XMP tương tự.

**Q: Có bản dùng thử miễn phí cho Aspose.Page for Java không?**  
A: Có, bạn có thể khám phá bản dùng thử miễn phí của Aspose.Page for Java [tại đây](https://releases.aspose.com/).

**Q: Tôi có thể tìm hỗ trợ và thảo luận bổ sung về Aspose.Page for Java ở đâu?**  
A: Truy cập [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để nhận hỗ trợ cộng đồng và thảo luận.

**Q: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Page for Java?**  
A: Bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể mua Aspose.Page for Java ở đâu?**  
A: Để mua Aspose.Page for Java, hãy truy cập [trang mua hàng](https://purchase.aspose.com/buy).

---

**Cập nhật lần cuối:** 2026-05-15  
**Đã kiểm tra với:** Aspose.Page for Java (latest release)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách Đọc Siêu dữ liệu XMP bằng Java – Hướng dẫn Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Hướng dẫn Aspose Page Java – Thêm Siêu dữ liệu XMP vào Tệp EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – Thay đổi Giá trị trong XMP bằng Java](/page/java/xmp-metadata-manipulation/change-values/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}