---
date: 2026-05-25
description: Tìm hiểu cách đọc XMP bằng Aspose.Page với Java. Hướng dẫn từng bước
  này trình bày cách trích xuất metadata XMP, creator info, timestamps, thumbnails
  và nhiều hơn nữa.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Cách đọc metadata XMP bằng Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Đọc XMP bằng Aspose.Page – Hướng dẫn Java
url: /vi/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Lấy siêu dữ liệu từ XMP bằng Java

## Cách đọc XMP bằng Aspose.Page (Java)?

Tải tệp EPS bằng `new Document("file.eps")` — lớp `Document` đại diện cho một tệp đã được tải. Gọi `getXmpMetadata()`, hàm này trích xuất gói XMP, và sau đó truy vấn đối tượng `XmpMetadata` trả về — một giao diện kiểu bản đồ cho các thuộc tính XMP — để lấy các khóa bạn cần. Đây là tất cả những gì cần thiết để đọc XMP bằng Aspose.Page. API trừu tượng hoá việc phân tích cấp thấp, vì vậy bạn nhận được một bản đồ các thuộc tính đã sẵn sàng sử dụng chỉ trong hai dòng mã.

Chào mừng bạn đến với hướng dẫn từng bước của chúng tôi, trình bày **cách đọc XMP** siêu dữ liệu bằng Java và thư viện Aspose.Page. XMP (Extensible Metadata Platform) là một tiêu chuẩn được áp dụng rộng rãi để nhúng siêu dữ liệu phong phú vào trong tài liệu. Khi hoàn thành hướng dẫn này, bạn sẽ có thể đọc XMP của định dạng tài liệu, trích xuất thông tin người tạo, dấu thời gian, hình thu nhỏ và nhiều hơn nữa — giúp bạn xây dựng các giải pháp phân tích tài liệu thông minh hơn.

## Câu trả lời nhanh
- **“Đọc XMP” có nghĩa là gì?** Nó có nghĩa là trích xuất chương trình gói XMP lưu trữ siêu dữ liệu bên trong tệp.  
- **Thư viện nào được yêu cầu?** Aspose.Page for Java (download from the official page [here](https://releases.aspose.com/page/java/)).  
- **Tôi có cần giấy phép không?** Cần một giấy phép tạm thời hoặc đầy đủ cho môi trường sản xuất; bản dùng thử miễn phí đủ cho việc đánh giá.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 hoặc cao hơn.  
- **Tôi có thể đọc XMP từ các định dạng khác không?** Có — Aspose.Page trích xuất XMP từ EPS, PDF, JPEG, PNG và hơn 20 định dạng khác.

## Yêu cầu trước
Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn có:

- **Java Development Kit (JDK)** – Java 8+ đã được cài đặt và cấu hình trên máy của bạn.  
- **Aspose.Page for Java** – Tải thư viện từ trang chính [here](https://releases.aspose.com/page/java/).  
- Một tệp EPS chứa siêu dữ liệu XMP (ví dụ, `xmp1.eps`).  

## Nhập gói
Lớp `XmpMetadata` nằm trong không gian tên `com.aspose.page.xmp`, trong khi lớp `Document` nằm trong `com.aspose.page`. Nhập cả hai để bạn có thể làm việc với tệp EPS và siêu dữ liệu của nó.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Bước 1: Khởi tạo luồng tệp EPS đầu vào
Bắt đầu bằng cách đặt đường dẫn tới thư mục tài liệu của bạn và khởi tạo luồng tệp EPS đầu vào.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Bước 2: Lấy siêu dữ liệu XMP
`XmpMetadata` là đối tượng của Aspose.Page chứa gói XMP được trích xuất từ tài liệu. Lấy nó bằng `document.getXmpMetadata()`. Nếu tệp không có XMP, API sẽ tổng hợp một gói tối thiểu từ các chú thích PostScript hiện có.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Bước 3: Trích xuất thông tin CreatorTool
Khóa `CreatorTool` nằm trong không gian tên `xmp` và ghi lại ứng dụng đã tạo ra tệp. Kiểm tra sự tồn tại của nó và in giá trị.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Bước 4: Trích xuất thông tin CreateDate
`CreateDate` lưu trữ dấu thời gian khi tài liệu được tạo ra ban đầu. Sử dụng cùng mẫu `containsKey`/`get` để đọc nó.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Bước 5: Lấy độ rộng của Thumbnail
Nếu có thumbnail, mảng `xmp:Thumbnails` chứa một hoặc nhiều mục. Mỗi mục có `width`, `height`, và dữ liệu nhị phân. Ví dụ này trích xuất độ rộng của thumbnail đầu tiên.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Bước 6: Trích xuất thông tin Định dạng
Khóa `format` cho bạn biết định dạng tệp gốc (ví dụ, “application/postscript”). Điều này hữu ích khi bạn cần ghi lại hoặc xác thực loại nguồn.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Bước 7: Lấy DocumentID
`DocumentID` là một định danh duy nhất được ứng dụng tạo ra gán. Nó có thể được dùng để loại bỏ trùng lặp trong các thư viện tài sản lớn.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Tại sao điều này quan trọng
Aspose.Page có thể đọc XMP từ **hơn 20** định dạng tệp và xử lý tài liệu lên tới **500 MB** mà không cần tải toàn bộ tệp vào bộ nhớ, cung cấp cho bạn truy cập nhanh, chi phí thấp tới siêu dữ liệu quan trọng. Khả năng này rất quan trọng cho các pipeline xử lý hàng loạt, hệ thống quản lý tài sản kỹ thuật số, và bất kỳ giải pháp nào dựa trên các thuộc tính tài liệu có thể tìm kiếm, máy đọc.

## Những lỗi thường gặp & Mẹo
- **Missing XMP:** Một số tệp EPS có thể không chứa XMP. Lệnh `getXmpMetadata()` sẽ tổng hợp một bộ tối thiểu dựa trên các chú thích PS hiện có, nhưng bạn sẽ không nhận được siêu dữ liệu đầy đủ trừ khi nó được nhúng.  
- **Thumbnail Arrays:** Khóa `xmp:Thumbnails` có thể chứa nhiều mục. Ví dụ chỉ trích xuất mục đầu tiên; lặp qua mảng nếu bạn cần tất cả các thumbnail.  
- **Namespace Awareness:** Các khóa XMP sử dụng không gian tên (ví dụ, `xmp:`, `dc:`). Đảm bảo bạn tham chiếu đúng tên khóa; nếu không `containsKey` sẽ trả về false.  

## Câu hỏi thường gặp
### Tôi có thể sử dụng Aspose.Page cho Java với các ngôn ngữ lập trình khác không?
Có, Aspose.Page hỗ trợ Java, .NET và một số ngôn ngữ khác. Xem danh sách đầy đủ trong [documentation](https://reference.aspose.com/page/java/).

### Có bản dùng thử miễn phí cho Aspose.Page cho Java không?
Có, bạn có thể truy cập bản dùng thử miễn phí [here](https://releases.aspose.com/).

### Tôi có thể tìm hỗ trợ cho Aspose.Page cho Java ở đâu?
Truy cập [Aspose.Page forum](https://forum.aspose.com/c/page/39) để nhận trợ giúp cộng đồng và hỗ trợ chính thức.

### Làm thế nào để tôi nhận được giấy phép tạm thời cho Aspose.Page cho Java?
Bạn có thể nhận giấy phép tạm thời [here](https://purchase.aspose.com/temporary-license/).

### Có tài nguyên bổ sung nào cho Aspose.Page cho Java không?
Khám phá toàn bộ [documentation](https://reference.aspose.com/page/java/) và tải thư viện [here](https://releases.aspose.com/page/java/).

## Câu hỏi bổ sung
**Q: Phương pháp này có hoạt động với các tệp PDF chứa XMP không?**  
A: Có, Aspose.Page có thể đọc XMP từ PDF, EPS và một số định dạng hình ảnh.

**Q: Tôi có thể chỉnh sửa siêu dữ liệu XMP sau khi đọc không?**  
A: Chắc chắn. Đối tượng `XmpMetadata` có thể thay đổi; bạn có thể thêm, cập nhật hoặc xóa các khóa và sau đó lưu tài liệu.

**Q: Có cách nào để trích xuất tất cả hình ảnh thumbnail, không chỉ kích thước không?**  
A: Bạn có thể lấy dữ liệu nhị phân từ thuộc tính `xmpGImg:data` của mỗi mục thumbnail và ghi nó vào tệp.

## Kết luận
Bạn đã nắm vững **cách đọc XMP** siêu dữ liệu bằng Java và Aspose.Page. Bằng cách thực hiện các bước này, bạn có thể trích xuất công cụ tạo, dấu thời gian, thumbnail, thông tin định dạng và Document ID — cung cấp cho bạn cái nhìn toàn diện về siêu dữ liệu nhúng trong các tệp EPS của mình. Hãy tự do thử nghiệm các không gian tên XMP bổ sung để thu thập dữ liệu phong phú hơn cho ứng dụng của bạn.

---

**Cập nhật lần cuối:** 2026-05-25  
**Được kiểm tra với:** Aspose.Page for Java 24.12 (latest)  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Hướng dẫn Aspose Page Java – Thêm siêu dữ liệu XMP vào tệp EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [hướng dẫn aspose.page xmp – Thêm Namespace trong XMP bằng Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [hướng dẫn aspose page xmp – Thay đổi giá trị có tên trong XMP bằng Java](/page/java/xmp-metadata-manipulation/change-named-value/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}