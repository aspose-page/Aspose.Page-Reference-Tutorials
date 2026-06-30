---
date: 2026-06-30
description: Tìm hiểu cách tạo tài liệu postscript .NET và thêm các hình chữ nhật
  bằng Aspose.Page cho .NET. Hướng dẫn chi tiết từng bước kèm mẫu mã.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: Thêm hình chữ nhật vào PostScript (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Tạo tài liệu PostScript .NET – Thêm hình chữ nhật Aspose.Page
url: /vi/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Hình Chữ Nhật vào PostScript (PS) với Aspose.Page cho .NET

## Giới thiệu

Aspose.Page cho .NET là một thư viện cho phép tạo và thao tác các tệp PostScript, EPS và XPS một cách lập trình. Nếu bạn đang muốn **tạo tài liệu postscript .net**, hướng dẫn này sẽ chỉ cho bạn cách thêm hình chữ nhật vào tài liệu PostScript bằng Aspose.Page, giúp bạn có nền tảng vững chắc để tạo đồ họa phong phú hơn.

## Câu trả lời nhanh
- **Thư viện tôi cần là gì?** Aspose.Page cho .NET.  
- **Tôi có thể tạo tài liệu PostScript từ đầu không?** Có – API cho phép bạn xây dựng các tệp PS một cách lập trình.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép cần thiết cho môi trường sản xuất.  
- **Thời gian triển khai mất bao lâu?** Thông thường dưới 10 phút cho các hình dạng cơ bản.

## Tạo tài liệu postscript .net là gì?
Tạo một tài liệu PostScript trong .NET có nghĩa là tạo một tệp `.ps` một cách lập trình, mô tả nội dung trang—văn bản, đồ họa hoặc hình dạng—bằng API Aspose.Page. Cách tiếp cận này lý tưởng cho việc tạo đồ họa phía máy chủ, tự động tạo báo cáo, hoặc bất kỳ kịch bản nào yêu cầu kiểm soát chính xác định dạng đầu ra.

## Tại sao nên dùng Aspose.Page cho .NET?
Aspose.Page hỗ trợ **hơn 30 primitive đồ họa** và có thể tạo các tệp lên đến **500 MB** mà không cần tải toàn bộ tài liệu vào bộ nhớ, mang lại khả năng render hiệu suất cao trên Windows, Linux và macOS. Thư viện cung cấp kiểm soát đầy đủ đối với các hình dạng, màu sắc và nét vẽ, đồng thời loại bỏ nhu cầu viết mã PostScript cấp thấp.

- **Kiểm soát toàn diện đồ họa** – vẽ hình, đặt màu và áp dụng nét vẽ mà không phải lo lắng về cú pháp PS cấp thấp.  
- **Đa nền tảng** – hoạt động trên môi trường Windows, Linux và macOS.  
- **Không phụ thuộc bên ngoài** – thư viện tự xử lý toàn bộ việc tạo PS.  
- **Tài liệu & ví dụ phong phú** – giúp bạn nhanh chóng bắt đầu.

## Yêu cầu trước

- **Thư viện Aspose.Page cho .NET** – tải về và cài đặt từ [tại đây](https://releases.aspose.com/page/net/).  
- **Môi trường phát triển** – Visual Studio, VS Code hoặc bất kỳ IDE nào hỗ trợ .NET.

## Nhập không gian tên

Không gian tên `Aspose.Page` cung cấp các lớp cốt lõi bạn sẽ cần, chẳng hạn như `Document`, `Page`, `SolidBrush` và `Pen`. Nhập nó trước khi bắt đầu viết mã.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Bây giờ chúng ta sẽ chia ví dụ thành các bước rõ ràng, được đánh số.

## Bước 1: Thiết lập Thư mục Tài liệu của Bạn

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Thay `"Your Document Directory"` bằng thư mục nơi bạn muốn lưu tệp PS kết quả.

## Bước 2: Tạo Luồng Đầu ra cho Tài liệu PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Luồng này trỏ tới **AddRectangle_outPS.ps**. Bạn có thể đổi tên tệp hoặc thay đổi vị trí lưu tùy ý.

## Bước 3: Đặt Tùy chọn Lưu và Tạo Tài liệu PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Ở đây chúng ta chỉ định Aspose.Page sử dụng kích thước trang A4 và tạo một tài liệu một trang.

## Bước 4: Thêm Hình Chữ Nhật Được Đổ Màu

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Chúng ta định nghĩa một hình chữ nhật tại (250, 100) với chiều rộng 150 và chiều cao 100, đặt một brush màu cam và đổ màu cho hình.

## Bước 5: Thêm Hình Chữ Nhật Viền

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Một hình chữ nhật thứ hai được tạo ở vị trí thấp hơn trên trang, lần này với nét đỏ dày 3 điểm.

## Bước 6: Đóng Trang và Lưu Tài liệu

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Đóng trang sẽ hoàn thiện việc vẽ, và `Save()` sẽ ghi tệp PS ra đĩa.

## Cách tạo tài liệu postscript .net?
`Document` là lớp chính đại diện cho một tệp PostScript trong Aspose.Page. `SaveOptions` xác định các cài đặt như kích thước trang và định dạng đầu ra cho tài liệu. Tải đối tượng `Document`, cấu hình `SaveOptions` cho trang A4, vẽ các hình dạng bằng `SolidBrush` hoặc `Pen`, sau đó gọi `document.Save()`—toàn bộ quy trình chỉ cần vài dòng mã và chạy trên bất kỳ runtime .NET nào được hỗ trợ. Mô hình này cho phép bạn tạo các tệp PostScript hoàn toàn tuân thủ mà không cần chạm tới cú pháp PS thô.

## Cách tạo tệp postscript
Sử dụng lớp `SaveOptions` của Aspose.Page để chỉ định định dạng đầu ra là PostScript (`SaveFormat.PS`). Thư viện sẽ truyền nội dung trực tiếp tới tệp hoặc luồng bộ nhớ, cho phép bạn tạo các tài liệu lớn một cách hiệu quả mà không tiêu tốn quá nhiều bộ nhớ.

## Các vấn đề thường gặp & Mẹo

- **Đường dẫn tệp không đúng** – Đảm bảo `dataDir` kết thúc bằng ký tự phân tách đường dẫn (`\\` hoặc `/`) hoặc dùng `Path.Combine`.  
- **Thiếu giấy phép** – Trong môi trường sản xuất, áp dụng giấy phép Aspose trước khi tạo tài liệu để tránh dấu nước đánh giá.  
- **Màu sắc không hiển thị** – Nếu hình chữ nhật xuất hiện trắng, kiểm tra xem màu brush hoặc pen có tương phản với nền trang không.

## Câu hỏi thường gặp

**H:** Tôi có thể tùy chỉnh màu của các hình chữ nhật không?  
**Đ:** Chắc chắn. Thay đổi giá trị `Color.Orange` hoặc `Color.Red` trong các hàm khởi tạo `SolidBrush` và `Pen` thành bất kỳ `System.Drawing.Color` nào bạn muốn.

**H:** Aspose.Page có tương thích với các định dạng tài liệu khác không?  
**Đ:** Có. Ngoài PostScript, Aspose.Page còn hỗ trợ tạo XPS và EPS.

**H:** Làm sao để thêm văn bản vào cùng một tài liệu?  
**Đ:** Sử dụng lớp `TextFragment` để đặt văn bản tại tọa độ mong muốn, sau đó gọi `document.Draw(textFragment)`.

**H:** Tôi có thể tìm các ví dụ bổ sung và tài liệu API đầy đủ ở đâu?  
**Đ:** Khám phá tài liệu [tại đây](https://reference.aspose.com/page/net/) và tham gia cộng đồng tại [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39).

**H:** Tôi có thể dùng thử Aspose.Page trước khi mua không?  
**Đ:** Có, tải bản dùng thử miễn phí [tại đây](https://releases.aspose.com/). Để đánh giá kéo dài, bạn có thể xem xét một [giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

---

**Cập nhật lần cuối:** 2026-06-30  
**Kiểm tra với:** Aspose.Page 24.12 cho .NET  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Các hướng dẫn liên quan

- [Cách Tạo Tài liệu PostScript với Aspose.Page cho .NET](/page/net/document-creation/create-postscript-document/)
- [Thêm Hình Ảnh vào Tài liệu PostScript (PS) với Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Thêm Văn bản vào Tài liệu PostScript (PS) với Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}