---
date: 2026-07-19
description: Tìm hiểu cách tạo tài liệu XPS .NET và thêm một hình chữ nhật bằng Aspose.Page
  cho .NET trong hướng dẫn ngắn gọn từng bước.
keywords:
- create xps document .net
- add rectangle xps
- aspose.page .net
lastmod: 2026-07-19
linktitle: Thêm hình chữ nhật vào tài liệu XPS
og_description: Tạo tài liệu XPS .NET nhanh chóng. Bài hướng dẫn này chỉ cách thêm
  một hình chữ nhật vào tệp XPS bằng Aspose.Page cho .NET, kèm mã nguồn rõ ràng và
  mẹo hữu ích.
og_image_alt: Guide to adding a rectangle to an XPS document using Aspose.Page for
  .NET
og_title: Tạo tài liệu XPS .NET – Thêm hình chữ nhật với Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-07-19'
  description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  headline: Create XPS Document .NET – Add Rectangle with Aspose.Page
  type: TechArticle
- description: Learn how to create XPS document .NET and add a rectangle using Aspose.Page
    for .NET in a concise step‑by‑step guide.
  name: Create XPS Document .NET – Add Rectangle with Aspose.Page
  steps:
  - name: Create a New XPS Document
    text: The `XpsDocument` class represents the XPS file you are building and provides
      methods to add pages, graphics, and other resources.
  - name: Add a Rectangle
    text: '`XpsPath` defines a drawable path object within the XPS document, allowing
      you to set geometry, stroke, fill, and other visual properties.'
  - name: Save the Document
    text: The `Save` method writes the constructed XPS document to the specified file
      path on disk. Congratulations! You have successfully added a rectangle to an
      XPS document using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works seamlessly with desktop, web, and cloud .NET applications.
    question: Is Aspose.Page compatible with all .NET applications?
  - answer: The full API reference is available [here](https://reference.aspose.com/page/net/).
    question: Where can I find the documentation for Aspose.Page for .NET?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Can I try Aspose.Page for .NET for free before purchasing?
  - answer: Visit [this link](https://purchase.aspose.com/temporary-license/) to obtain
      a temporary license.
    question: How can I obtain a temporary license for Aspose.Page for .NET?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support.
    question: Where can I seek community support or ask questions related to Aspose.Page
      for .NET?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- xps document
- aspose.page
- .net drawing
title: Tạo tài liệu XPS .NET – Thêm hình chữ nhật với Aspose.Page
url: /vi/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo tài liệu XPS .NET – Thêm hình chữ nhật với Aspose.Page

## Giới thiệu

Trong hướng dẫn này, bạn sẽ học cách **create XPS document .NET** và vẽ một hình chữ nhật bên trong nó bằng Aspose.Page cho .NET. Dù bạn đang xây dựng một engine báo cáo, một hoá đơn có thể in, hoặc một lớp đồ họa tùy chỉnh, khả năng tạo file XPS một cách lập trình cho phép bạn kiểm soát hoàn toàn bố cục và độ chính xác. Hãy làm theo các bước dưới đây và bạn sẽ có một file XPS sẵn sàng sử dụng trong vài phút.

## Câu trả lời nhanh
- **What is the primary goal?** Tạo một tài liệu XPS .NET và thêm một hình dạng hình chữ nhật.  
- **Which library is required?** Aspose.Page cho .NET (có thể tải xuống từ trang chính thức).  
- **Do I need a license for testing?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **What .NET versions are supported?** .NET Framework 4.6+, .NET Core 3.1+, .NET 5/6/7.  
- **How long does implementation take?** Khoảng 5‑10 phút cho một hình chữ nhật cơ bản.

## Aspose.Page cho .NET là gì?
Aspose.Page cho .NET là một API hiệu suất cao, được quản lý hoàn toàn, cho phép các nhà phát triển tạo, chỉnh sửa và render tài liệu XPS (XML Paper Specification) một cách lập trình mà không cần phụ thuộc vào các thành phần bên ngoài. Nó cung cấp một mô hình đối tượng phong phú để vẽ các hình dạng, văn bản và hình ảnh, và hỗ trợ các tính năng nâng cao như quản lý màu sắc, nén và chuyển đổi PDF, làm cho nó phù hợp với nhiều kịch bản tạo tài liệu.

## Tại sao nên sử dụng Aspose.Page để tạo tài liệu XPS .NET?
Aspose.Page hỗ trợ **30+ XPS features** — bao gồm đồ họa vector, bố cục văn bản và quản lý màu sắc — và có thể tạo các tệp lên tới **500 MB** mà không cần tải toàn bộ tài liệu vào bộ nhớ. Khả năng định lượng này đảm bảo hiệu suất mượt mà ngay cả với các công việc in ấn quy mô lớn.

## Yêu cầu trước

Trước khi bắt đầu với hướng dẫn này, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:

1. Thư viện Aspose.Page cho .NET: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Page cho .NET trong môi trường phát triển của mình. Bạn có thể tải xuống [tại đây](https://releases.aspose.com/page/net/).

2. Thư mục tài liệu: Thiết lập một thư mục nơi bạn muốn lưu trữ các tài liệu XPS của mình.

## Nhập không gian tên

Trong ứng dụng .NET của bạn, bao gồm các không gian tên cần thiết để sử dụng các chức năng của Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Làm thế nào để thêm một hình chữ nhật vào tài liệu XPS trong .NET?

Tải tài liệu XPS, tạo một đối tượng `Graphics`, định nghĩa một `RectangleF` với kích thước mong muốn, và gọi `DrawRectangle`. Trình tự này vẽ một hình chữ nhật trong một dòng lệnh duy nhất và tự động xử lý việc scaling DPI. Đối với các trang kích thước A4 tiêu chuẩn, một hình chữ nhật 200 × 100 pt sẽ xuất hiện ở giữa mà không cần tính toán thêm.

### Bước 1: Đặt thư mục tài liệu

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

### Bước 2: Tạo tài liệu XPS mới

Lớp `XpsDocument` đại diện cho file XPS mà bạn đang xây dựng và cung cấp các phương thức để thêm trang, đồ họa và các tài nguyên khác.

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

### Bước 3: Thêm một hình chữ nhật

`XpsPath` định nghĩa một đối tượng đường dẫn có thể vẽ được trong tài liệu XPS, cho phép bạn thiết lập hình học, nét viền, màu nền và các thuộc tính hiển thị khác.

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

### Bước 4: Lưu tài liệu

Phương thức `Save` ghi tài liệu XPS đã xây dựng vào đường dẫn file được chỉ định trên đĩa.

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Chúc mừng! Bạn đã thêm thành công một hình chữ nhật vào tài liệu XPS bằng Aspose.Page cho .NET.

## Các vấn đề thường gặp và mẹo

- **Missing fonts:** Đảm bảo các phông chữ bạn tham chiếu đã được cài đặt trên máy chủ; nếu không, Aspose.Page sẽ thay thế bằng phông mặc định, có thể làm thay đổi bố cục.  
- **Large documents:** Khi tạo các tệp lớn hơn 200 MB, hãy xem xét gọi `document.SaveOptions.Compress = true` để giảm việc sử dụng bộ nhớ.  
- **Coordinate system:** XPS sử dụng đơn vị điểm (1/72 inch). Hãy nhớ chuyển đổi pixel sang điểm nếu bạn đang làm việc với kích thước dựa trên màn hình.

## Câu hỏi thường gặp

**Q: Aspose.Page có tương thích với mọi ứng dụng .NET không?**  
A: Có, Aspose.Page hoạt động liền mạch với các ứng dụng .NET trên desktop, web và cloud.

**Q: Tôi có thể tìm tài liệu cho Aspose.Page cho .NET ở đâu?**  
A: Tham khảo đầy đủ API tại [đây](https://reference.aspose.com/page/net/).

**Q: Tôi có thể dùng thử Aspose.Page cho .NET miễn phí trước khi mua không?**  
A: Có, bạn có thể nhận bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

**Q: Làm thế nào để lấy giấy phép tạm thời cho Aspose.Page cho .NET?**  
A: Truy cập [liên kết này](https://purchase.aspose.com/temporary-license/) để nhận giấy phép tạm thời.

**Q: Tôi có thể tìm hỗ trợ cộng đồng hoặc đặt câu hỏi liên quan đến Aspose.Page cho .NET ở đâu?**  
A: Truy cập [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để được hỗ trợ cộng đồng.

---

**Cập nhật lần cuối:** 2026-07-19  
**Kiểm tra với:** Aspose.Page cho .NET 24.9  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo tài liệu XPS với Aspose.Page cho .NET](/page/net/document-creation/create-xps-document/)
- [Aspose.Page .NET – Vẽ hình dạng](/page/net/drawing-shapes/)
- [Thêm văn bản vào tài liệu XPS với Aspose.Page cho .NET](/page/net/text-manipulation/add-text-to-xps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}