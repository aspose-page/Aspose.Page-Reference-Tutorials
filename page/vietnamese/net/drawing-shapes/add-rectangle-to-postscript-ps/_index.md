---
date: 2026-01-18
description: Tìm hiểu cách tạo tài liệu PostScript trong .NET và thêm các hình chữ
  nhật bằng Aspose.Page cho .NET. Hướng dẫn chi tiết từng bước kèm ví dụ mã.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Tạo tài liệu PostScript .NET – Thêm hình chữ nhật với Aspose.Page
url: /vi/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Hình Chữ Nhật vào PostScript (PS) với Aspose.Page cho .NET

## Giới thiệu

Nếu bạn đang muốn **tạo tài liệu postscript .net**, Aspose.Page cung cấp một giải pháp mạnh mẽ để xử lý các tệp PostScript. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn cách thêm các hình chữ nhật vào tài liệu PostScript bằng Aspose.Page cho .NET, giúp bạn có nền tảng vững chắc để tạo đồ họa phong phú hơn.

## Câu trả lời nhanh
- **Thư viện tôi cần là gì?** Aspose.Page for .NET.
- **Tôi có thể tạo tài liệu PostScript từ đầu không?** Có – API cho phép bạn xây dựng các tệp PS bằng chương trình.
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc kiểm tra; cần giấy phép cho môi trường sản xuất.
- **Thời gian triển khai mất bao lâu?** Thông thường dưới 10 phút cho các hình cơ bản.

## Tạo tài liệu postscript .net là gì?
Tạo một tài liệu PostScript trong .NET có nghĩa là tạo ra một tệp .ps một cách lập trình, mô tả nội dung trang — văn bản, đồ họa hoặc hình dạng — bằng cách sử dụng API Aspose.Page. Cách tiếp cận này lý tưởng cho việc tạo đồ họa phía máy chủ, tạo báo cáo tự động, hoặc bất kỳ trường hợp nào bạn cần kiểm soát chính xác định dạng đầu ra.

## Tại sao nên sử dụng Aspose.Page cho .NET?
- **Kiểm soát đầy đủ đồ họa** – vẽ các hình, đặt màu và áp dụng nét vẽ mà không phải xử lý cú pháp PS cấp thấp.
- **Đa nền tảng** – hoạt động trên Windows, Linux và macOS.
- **Không phụ thuộc bên ngoài** – thư viện xử lý toàn bộ việc tạo PS nội bộ.
- **Tài liệu & ví dụ phong phú** – giúp bạn nhanh chóng bắt đầu.

## Yêu cầu trước

- **Thư viện Aspose.Page cho .NET** – tải xuống và cài đặt từ [here](https://releases.aspose.com/page/net/).
- **Môi trường phát triển** – Visual Studio, VS Code, hoặc bất kỳ IDE nào tương thích với .NET.

## Nhập không gian tên

Trước khi bắt đầu viết mã, nhập các không gian tên cung cấp các lớp cần thiết:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Bây giờ chúng ta sẽ chia ví dụ thành các bước rõ ràng, có số thứ tự.

## Bước 1: Thiết lập Thư mục Tài liệu của Bạn

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Thay thế `"Your Document Directory"` bằng thư mục mà bạn muốn lưu tệp PS kết quả.

## Bước 2: Tạo Luồng Đầu ra cho Tài liệu PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Luồng này trỏ tới **AddRectangle_outPS.ps**. Bạn có thể đổi tên tệp hoặc thay đổi vị trí tùy ý.

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

Chúng ta định nghĩa một hình chữ nhật tại (250, 100) với chiều rộng 150 và chiều cao 100, đặt một brush màu cam và tô đầy hình.

## Bước 5: Thêm Hình Chữ Nhật Được Viền

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Một hình chữ nhật thứ hai được tạo ở vị trí thấp hơn trên trang, lần này với nét viền màu đỏ dày 3 điểm.

## Bước 6: Đóng Trang và Lưu Tài liệu

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Đóng trang sẽ hoàn thiện việc vẽ, và `Save()` ghi tệp PS ra đĩa.

## Các vấn đề thường gặp & Mẹo

- **Đường dẫn tệp không đúng** – Đảm bảo `dataDir` kết thúc bằng dấu phân tách đường dẫn (`\\` hoặc `/`) hoặc sử dụng `Path.Combine`.
- **Thiếu giấy phép** – Trong môi trường sản xuất, áp dụng giấy phép Aspose của bạn trước khi tạo tài liệu để tránh dấu bản quyền đánh giá.
- **Màu không hiển thị** – Nếu hình chữ nhật xuất hiện trống, kiểm tra màu brush hoặc pen có độ tương phản với nền trang hay không.

## Câu hỏi thường gặp

**Q:** Tôi có thể tùy chỉnh màu của các hình chữ nhật không?  
**A:** Chắc chắn. Thay đổi các giá trị `Color.Orange` hoặc `Color.Red` trong các hàm khởi tạo `SolidBrush` và `Pen` thành bất kỳ `System.Drawing.Color` nào bạn muốn.

**Q:** Aspose.Page có tương thích với các định dạng tài liệu khác không?  
**A:** Có. Ngoài PostScript, Aspose.Page còn hỗ trợ tạo XPS và EPS.

**Q:** Làm thế nào tôi có thể thêm văn bản vào cùng một tài liệu?  
**A:** Sử dụng lớp `TextFragment` để đặt văn bản tại tọa độ mong muốn, sau đó gọi `document.Draw(textFragment)`.

**Q:** Tôi có thể tìm các ví dụ bổ sung và tài liệu tham khảo API đầy đủ ở đâu?  
**A:** Khám phá tài liệu [here](https://reference.aspose.com/page/net/) và tham gia cộng đồng tại [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Tôi có thể dùng thử Aspose.Page trước khi mua không?  
**A:** Có, tải xuống bản dùng thử miễn phí [here](https://releases.aspose.com/). Để đánh giá kéo dài, hãy xem xét một [temporary license](https://purchase.aspose.com/temporary-license/).

---

**Cập nhật lần cuối:** 2026-01-18  
**Kiểm tra với:** Aspose.Page 24.12 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}