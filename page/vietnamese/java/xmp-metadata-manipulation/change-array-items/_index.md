---
date: 2026-05-15
description: Khám phá hướng dẫn aspose.page xmp cho Java—tìm hiểu cách thay đổi các
  mục trong mảng metadata XMP, cập nhật tiêu đề EPS, người tạo và hơn thế nữa chỉ
  trong vài dòng mã.
keywords:
- aspose.page xmp tutorial
- change array items java
- xmp metadata java
linktitle: Thay đổi các mục trong mảng XMP bằng Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  headline: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  type: TechArticle
- description: Explore the aspose.page xmp tutorial for Java—learn how to change array
    items in XMP metadata, update EPS titles, creators, and more in just a few lines
    of code.
  name: 'aspose.page xmp tutorial: Change Array Items in XMP using Java'
  steps:
  - name: Get XMP Metadata
    text: Call `document.getXmpMetadata()` to retrieve the XMP metadata object associated
      with the EPS file.
  - name: Set "dc:title" Array Item
    text: Use `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` to replace the
      first title entry.
  - name: Set "dc:creator" Array Item
    text: Similarly, `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` updates
      the first creator entry.
  - name: Initialize Output EPS File Stream
    text: Create a `FileOutputStream` pointing to the destination EPS file to write
      the updated document.
  - name: Save Document with Changed XMP Metadata
    text: The `PsDocument` class represents an EPS document and provides the `save`
      method to write changes to a stream.
  type: HowTo
- questions:
  - answer: No. You must invoke `setArrayItem` for each index you wish to modify;
      the API does not provide a bulk‑update method.
    question: Can I update multiple array items in one call?
  - answer: Yes. Provide the full prefix (e.g., `myNS:customProp`) when calling `setArrayItem`
      or `removeArrayItem`.
    question: Does aspose.page xmp java support custom namespaces?
  - answer: Reload the EPS with `PsDocument`, call `getXmpMetadata()`, and inspect
      the returned values, or open the file in an XMP viewer.
    question: How do I verify that the metadata was updated correctly?
  - answer: Use `removeArrayItem(namespace, index)` to delete a specific entry from
      an XMP array.
    question: Is it possible to remove an array item entirely?
  - answer: No. XMP metadata is stored separately from the graphic content and does
      not alter how the EPS renders.
    question: Will the changes affect the visual appearance of the EPS?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'aspose.page xmp tutorial: Thay đổi các mục trong mảng XMP bằng Java'
url: /vi/java/xmp-metadata-manipulation/change-array-items/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page xmp tutorial: Thay đổi các mục mảng trong XMP bằng Java

## Giới thiệu
Chào mừng bạn đến với **aspose.page xmp tutorial** toàn diện của chúng tôi. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn từng bước cách thay đổi các mục mảng trong siêu dữ liệu XMP bên trong các tệp EPS bằng cách sử dụng Aspose.Page cho Java. Cho dù bạn cần cập nhật tiêu đề tài liệu, danh sách tác giả, hoặc bất kỳ mảng XMP nào khác, quy trình này đơn giản, hoàn toàn lập trình và hoạt động với Java 8 +.

## Câu trả lời nhanh
- **aspose.page xmp java làm gì?** Nó đọc và ghi siêu dữ liệu XMP trong các tệp EPS trực tiếp từ Java.  
- **Tôi có cần giấy phép để thử không?** Có — một bản dùng thử miễn phí 30 ngày có sẵn; giấy phép thương mại là bắt buộc cho môi trường sản xuất.  
- **Phiên bản JDK nào được hỗ trợ?** Java 8 hoặc mới hơn (bao gồm Java 11, 17 và 21).  
- **Tôi có thể sửa đổi các trường siêu dữ liệu khác không?** Chắc chắn — bất kỳ thuộc tính XMP nào, bao gồm các không gian tên tùy chỉnh, đều có thể được đọc hoặc cập nhật.  
- **API có an toàn với đa luồng không?** Hầu hết các thao tác đọc/ghi đều an toàn khi mỗi luồng làm việc với một thể hiện `PsDocument` riêng.

## aspose.page xmp java là gì?
`aspose.page xmp java` là thành phần của Aspose.Page cho Java, trừu tượng hoá Extensible Metadata Platform (XMP) thành các đối tượng Java dễ sử dụng. Nó cho phép bạn thao tác các mảng, bag và các thuộc tính có cấu trúc mà không cần xử lý XML thô. Trong thực tế, bạn sẽ làm việc với các phương thức cấp cao như `setArrayItem` và `removeArrayItem` để chỉnh sửa siêu dữ liệu ngay lập tức.

## Tại sao nên sử dụng aspose.page xmp java cho siêu dữ liệu EPS?
Bạn nên sử dụng thư viện này khi cần kiểm soát chính xác, tự động đối với siêu dữ liệu EPS ở quy mô lớn. Aspose.Page hỗ trợ **hơn 30 trường schema XMP** và có thể xử lý các tệp lên tới **500 MB** mà không cần tải toàn bộ tài liệu vào bộ nhớ, mang lại tốc độ và dung lượng bộ nhớ thấp. API cũng đảm bảo rằng các thay đổi giữ nguyên đồ họa gốc, vì vậy việc hiển thị hình ảnh không bị ảnh hưởng.

## Yêu cầu trước
- Java Development Kit (JDK) 8 hoặc mới hơn đã được cài đặt.  
- Thư viện Aspose.Page cho Java. Tải JAR mới nhất từ [here](https://releases.aspose.com/page/java/).  
- Tệp giấy phép Aspose hợp lệ (hoặc giấy phép dùng thử) được đặt trên classpath.

## Cách thay đổi các mục mảng với aspose.page xmp java
Phần này trình bày quy trình làm việc đầy đủ: mở tệp EPS, lấy đối tượng siêu dữ liệu XMP của nó, sửa đổi các mục mảng cụ thể, và cuối cùng ghi tài liệu đã cập nhật trở lại đĩa. Mỗi bước được minh họa bằng mã Java ngắn gọn, giúp dễ dàng tích hợp vào ứng dụng của bạn.

### Bước 1: Lấy siêu dữ liệu XMP
Gọi `document.getXmpMetadata()` để lấy đối tượng siêu dữ liệu XMP liên kết với tệp EPS.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

### Bước 2: Đặt mục mảng "dc:title"
Sử dụng `xmpMetadata.setArrayItem("dc:title", 0, "New Title")` để thay thế mục tiêu đề đầu tiên.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one will be filled with values from PS metadata comments.
XmpMetadata xmp = document.getXmpMetadata();
```

### Bước 3: Đặt mục mảng "dc:creator"
Tương tự, `xmpMetadata.setArrayItem("dc:creator", 0, "New Author")` cập nhật mục tạo giả đầu tiên.

```java
// Set "dc:title" array item by index 0 
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```

### Bước 4: Khởi tạo luồng tệp EPS đầu ra
Tạo một `FileOutputStream` trỏ tới tệp EPS đích để ghi tài liệu đã cập nhật.

```java
// Set "dc:creator" array item by index 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```

### Bước 5: Lưu tài liệu với siêu dữ liệu XMP đã thay đổi
Lớp `PsDocument` đại diện cho một tài liệu EPS và cung cấp phương thức `save` để ghi các thay đổi vào một luồng.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

## Những lỗi thường gặp & Mẹo
- **Chỉ mục ngoài phạm vi:** Xác minh rằng chỉ mục mục tiêu tồn tại; nếu không, Aspose sẽ ném ra ngoại lệ `ArrayIndexOutOfBoundsException`.  
- **Quản lý luồng:** Luôn luôn đóng các luồng trong khối `finally` hoặc sử dụng try‑with‑resources để ngăn chặn khóa tệp.  
- **Kích hoạt giấy phép:** Quên áp dụng giấy phép hợp lệ sẽ dẫn đến tệp EPS có dấu nước ở chế độ dùng thử.  
- **Tệp lớn:** Đối với các tệp EPS lớn hơn 200 MB, hãy cân nhắc tăng kích thước heap JVM (`-Xmx2g`) để tránh áp lực bộ nhớ.

## Câu hỏi thường gặp

**Q: Tôi có thể cập nhật nhiều mục mảng trong một lần gọi không?**  
A: Không. Bạn phải gọi `setArrayItem` cho mỗi chỉ mục bạn muốn sửa đổi; API không cung cấp phương thức cập nhật hàng loạt.

**Q: aspose.page xmp java có hỗ trợ không gian tên tùy chỉnh không?**  
A: Có. Cung cấp tiền tố đầy đủ (ví dụ: `myNS:customProp`) khi gọi `setArrayItem` hoặc `removeArrayItem`.

**Q: Làm thế nào để tôi xác minh rằng siêu dữ liệu đã được cập nhật đúng?**  
A: Tải lại EPS bằng `PsDocument`, gọi `getXmpMetadata()`, và kiểm tra các giá trị trả về, hoặc mở tệp trong một trình xem XMP.

**Q: Có thể xóa hoàn toàn một mục mảng không?**  
A: Sử dụng `removeArrayItem(namespace, index)` để xóa một mục cụ thể khỏi mảng XMP.

**Q: Các thay đổi có ảnh hưởng đến giao diện hình ảnh của EPS không?**  
A: Không. Siêu dữ liệu XMP được lưu trữ riêng biệt khỏi nội dung đồ họa và không thay đổi cách EPS được hiển thị.

## Kết luận
Bây giờ bạn đã thành thạo **aspose.page xmp tutorial** cho Java và có thể tự tin thay đổi các mục mảng trong siêu dữ liệu XMP của EPS. Khả năng này cho phép tự động hoá quy trình tài liệu, cập nhật siêu dữ liệu hàng loạt, và quản lý tài sản tốt hơn mà không ảnh hưởng đến dữ liệu hình ảnh.

---

**Cập nhật lần cuối:** 2026-05-15  
**Kiểm tra với:** Aspose.Page for Java 24.11 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

```java
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Hướng dẫn liên quan

- [Thêm mục mảng trong siêu dữ liệu XMP bằng Java](/page/java/xmp-metadata-manipulation/add-array-items/)
- [aspose page xmp tutorial – Thay đổi giá trị có tên trong XMP bằng Java](/page/java/xmp-metadata-manipulation/change-named-value/)
- [Cách đọc siêu dữ liệu XMP bằng Java – Hướng dẫn Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}