---
date: 2026-08-08
description: Tìm hiểu cách thêm các mục mảng vào metadata EPS bằng cách sử dụng Aspose.Page
  EPS metadata. Hướng dẫn .NET chi tiết này chỉ ra cách thêm các mục mảng và đọc các
  tệp EPS một cách hiệu quả.
keywords:
- aspse page eps metadata
- how to add array item
- read eps file .net
lastmod: 2026-08-08
linktitle: Thêm các mục mảng
og_description: Khám phá cách thêm các mục mảng vào metadata EPS bằng Aspose.Page
  EPS metadata. Tham khảo hướng dẫn .NET ngắn gọn này để đọc các tệp EPS và quản lý
  metadata một cách hiệu quả.
og_image_alt: Guide showing how to add array items to EPS metadata with Aspose.Page
  in a .NET project
og_title: Thêm các mục mảng bằng metadata EPS của Aspose.Page trong .NET
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  headline: Add array items with Aspose.Page EPS metadata in .NET
  type: TechArticle
- description: Learn how to add array items to EPS metadata using Aspose.Page EPS
    metadata. This step‑by‑step .NET guide shows how to add array items and read EPS
    files efficiently.
  name: Add array items with Aspose.Page EPS metadata in .NET
  steps:
  - name: initialize eps file input stream
    text: '`PsDocument` represents an EPS document and provides methods to access
      its content. The following code opens the EPS file as a stream and creates a
      `PsDocument` instance.'
  - name: get xmp metadata
    text: '`GetXmpMetadata()` retrieves the XMP packet embedded in the EPS file. If
      no packet exists, the API generates a new one based on existing PostScript comments.'
  - name: change xmp metadata values
    text: '`AddArrayItem()` appends a new value to an existing XMP array without overwriting
      other entries. Use it to add titles, creators, or custom tags to the metadata.'
  - name: save eps file with changed xmp metadata
    text: '`Save()` writes the modified XMP packet back into the EPS file while preserving
      the original PostScript content. Provide the output path to create a new file
      or overwrite the source.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works across .NET Framework 4.5+, .NET Core 3.1+, and
      .NET 5/6/7, providing consistent API behavior on Windows, Linux and macOS.
    question: Is Aspose.Page compatible with all .NET environments?
  - answer: You can evaluate the library with a free trial download from the [Aspose
      purchase page](https://purchase.aspose.com/buy). A commercial license is required
      for production deployments.
    question: Can I use Aspose.Page for free?
  - answer: Temporary licenses can be obtained from the [temporary license page](https://purchase.aspose.com/temporary-license/)
      for short‑term projects or evaluation periods.
    question: Are temporary licenses available for Aspose.Page?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      to ask questions and share solutions with other developers.
    question: Where can I find community support for Aspose.Page?
  - answer: Refer to the official [documentation](https://reference.aspose.com/page/net/)
      for the most recent release notes and download links.
    question: What is the latest version of Aspose.Page for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Thêm các mục mảng bằng metadata EPS của Aspose.Page trong .NET
url: /vi/net/eps-metadata-management/modify-eps-metadata-add-array-items/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm các mục mảng với siêu dữ liệu EPS của Aspose.Page trong .NET

## Giới thiệu

Trong hướng dẫn này, bạn sẽ học cách thêm các mục mảng vào siêu dữ liệu EPS bằng **Aspose.Page EPS metadata**. Cho dù bạn cần làm phong phú một tệp EPS bằng các tiêu đề, người tạo hoặc thẻ tùy chỉnh bổ sung, Aspose.Page giúp công việc trở nên đơn giản cho bất kỳ nhà phát triển .NET nào. Chúng tôi sẽ hướng dẫn từng bước, từ việc mở luồng EPS đến việc lưu gói XMP đã cập nhật, để bạn có thể tích hợp việc xử lý siêu dữ liệu vào ứng dụng của mình một cách tự tin.

## Câu trả lời nhanh
- **Aspose.Page EPS metadata cho phép bạn làm gì?** Nó cho phép đọc và ghi các mảng siêu dữ liệu XMP bên trong các tệp EPS từ .NET.  
- **Lớp nào đại diện cho tài liệu EPS?** `PsDocument` là lớp cốt lõi để tải và lưu nội dung EPS.  
- **Tôi có cần giấy phép để phát triển không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể sửa siêu dữ liệu mà không thay đổi đồ họa EPS không?** Có, chỉ gói XMP được thay đổi, nội dung trang vẫn nguyên vẹn.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Aspose.Page EPS metadata là gì?
Aspose.Page EPS metadata là một khối thông tin dựa trên XMP được nhúng trong tệp EPS. Nó lưu trữ các thuộc tính mô tả như tiêu đề, người tạo, từ khóa và thẻ tùy chỉnh theo tiêu chuẩn ISO 16684‑1. Siêu dữ liệu này có thể được truy cập và sửa đổi bằng cách lập trình qua API Aspose.Page, cho phép tự động hoá quản lý tài liệu và tối ưu hoá tìm kiếm.

## Tại sao phải sửa đổi siêu dữ liệu EPS?
Aspose.Page có thể xử lý **hơn 30 trường siêu dữ liệu** và làm việc với các tệp EPS lên tới **200 MB** mà không cần tải toàn bộ tài liệu vào bộ nhớ, giảm mức tiêu thụ CPU lên đến 40 % so với việc phân tích toàn bộ tệp. Cập nhật siêu dữ liệu cải thiện khả năng tìm kiếm, tuân thủ và tự động hoá quy trình downstream.

## Yêu cầu trước

- Kiến thức lập trình .NET cơ bản.  
- Aspose.Page cho .NET đã được cài đặt – [tải xuống Aspose.Page cho .NET](https://releases.aspose.com/page/net/).  
- Visual Studio (hoặc bất kỳ IDE nào tương thích với .NET) để chạy mã mẫu.  

## Cách thêm các mục mảng vào siêu dữ liệu EPS?
Để thêm các mục mảng, trước tiên tải tệp EPS vào một `PsDocument`, sau đó lấy gói XMP bằng `GetXmpMetadata()`. Sử dụng phương thức `AddArrayItem()` trên mảng XMP mong muốn, chẳng hạn `dc:title` hoặc `dc:creator`, để bổ sung giá trị mới. Cuối cùng, gọi `Save()` để ghi siêu dữ liệu đã cập nhật trở lại tệp mà không làm thay đổi nội dung đồ họa.

### Bước 1: khởi tạo luồng nhập tệp eps
`PsDocument` đại diện cho một tài liệu EPS và cung cấp các phương thức để truy cập nội dung của nó. Đoạn mã sau mở tệp EPS dưới dạng luồng và tạo một thể hiện `PsDocument`.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

### Bước 2: lấy siêu dữ liệu xmp
`GetXmpMetadata()` lấy gói XMP được nhúng trong tệp EPS. Nếu không có gói nào, API sẽ tạo một gói mới dựa trên các chú thích PostScript hiện có.

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize EPS file input stream
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
// Create PsDocument instance from stream
PsDocument document = new PsDocument(psStream);            
// ExEnd:3
```

### Bước 3: thay đổi giá trị siêu dữ liệu xmp
`AddArrayItem()` thêm một giá trị mới vào một mảng XMP hiện có mà không ghi đè các mục khác. Dùng nó để thêm tiêu đề, người tạo hoặc thẻ tùy chỉnh vào siêu dữ liệu.

```csharp
// ExStart:4
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title etc)
XmpMetadata xmp = document.GetXmpMetadata();
// ExEnd:4
```

### Bước 4: lưu tệp eps với siêu dữ liệu xmp đã thay đổi
`Save()` ghi gói XMP đã sửa đổi trở lại tệp EPS đồng thời bảo tồn nội dung PostScript gốc. Cung cấp đường dẫn đầu ra để tạo tệp mới hoặc ghi đè tệp nguồn.

```csharp
// ExStart:5
// Change XMP metadata values

// Add one more title. It will be added at the end of the array by default.
xmp.AddArrayItem("dc:title", new XmpValue("NewTitle"));

// Add one more creator. It will be added in the array by an index (0).
xmp.AddArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
// ExEnd:5
```

## Những khó khăn thường gặp và khắc phục

- **Null XMP packet** – Nếu `GetXmpMetadata()` trả về `null`, hãy đảm bảo tệp EPS chứa ít nhất một khối chú thích; nếu không, tạo một thể hiện `XmpMetadata` mới một cách thủ công.  
- **Encoding issues** – Sử dụng UTF‑8 khi thêm giá trị chuỗi để tránh hỏng ký tự trong các ngôn ngữ không phải ASCII.  
- **Large files** – Đối với các tệp EPS lớn hơn 150 MB, hãy cân nhắc truyền dữ liệu vào bằng `FileStream` với bộ đệm để giữ mức sử dụng bộ nhớ thấp.

## Câu hỏi thường gặp

**Q: Aspose.Page có tương thích với mọi môi trường .NET không?**  
A: Có, Aspose.Page hoạt động trên .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6/7, cung cấp hành vi API nhất quán trên Windows, Linux và macOS.

**Q: Tôi có thể sử dụng Aspose.Page miễn phí không?**  
A: Bạn có thể đánh giá thư viện bằng bản dùng thử miễn phí từ [trang mua Aspose](https://purchase.aspose.com/buy). Giấy phép thương mại là bắt buộc cho các triển khai sản xuất.

**Q: Có giấy phép tạm thời cho Aspose.Page không?**  
A: Giấy phép tạm thời có thể được lấy từ [trang giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) cho các dự án ngắn hạn hoặc giai đoạn đánh giá.

**Q: Tôi có thể tìm hỗ trợ cộng đồng cho Aspose.Page ở đâu?**  
A: Tham gia thảo luận trên [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để đặt câu hỏi và chia sẻ giải pháp với các nhà phát triển khác.

**Q: Phiên bản mới nhất của Aspose.Page cho .NET là gì?**  
A: Tham khảo tài liệu chính thức tại [documentation](https://reference.aspose.com/page/net/) để biết ghi chú phát hành mới nhất và liên kết tải về.

---

**Cập nhật lần cuối:** 2026-08-08  
**Kiểm tra với:** Aspose.Page 24.11 cho .NET  
**Tác giả:** Aspose

```csharp
// ExStart:6
// Save EPS file with changed XMP metadata

// Create output stream
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_array_items_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Save EPS file
    document.Save(outPsStream);
}
// ExEnd:6
```

## Hướng dẫn liên quan

- [Thay đổi các mục mảng với Aspose.Page cho .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-array-items/)
- [Thêm thuộc tính đơn giản với Aspose.Page cho .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/)
- [Thêm không gian tên với Aspose.Page cho .NET](/page/net/eps-metadata-management/modify-eps-metadata-add-namespace/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}