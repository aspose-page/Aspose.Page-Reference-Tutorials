---
date: 2026-02-25
description: Nâng cao tài liệu PostScript với hình chữ nhật gradient tuyến tính bằng
  cách sử dụng Aspose.Page cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi
  để học cách tô màu gradient cho văn bản và tạo viền gradient cho văn bản.
linktitle: Add Horizontal Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: Thêm hình chữ nhật gradient tuyến tính vào PostScript (PS) bằng Aspose.Page
url: /vi/net/gradient-fills/add-horizontal-gradient-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Hình Chữ Nhật Gradient Tuyến Tính vào PostScript (PS) với Aspose.Page

## Giới thiệu

Chào mừng bạn đến với hướng dẫn toàn diện về cách thêm **hình chữ nhật gradient tuyến tính** vào tài liệu PostScript (PS) bằng Aspose.Page cho .NET. Aspose.Page là một thư viện mạnh mẽ cho phép bạn tạo, sửa đổi và render tài liệu ở nhiều định dạng, và hôm nay chúng ta sẽ tập trung vào cách đưa các gradient bắt mắt vào các tệp PS của bạn.

### Câu trả lời nhanh
- **Hình chữ nhật gradient tuyến tính làm gì?** Nó lấp đầy một khu vực hình chữ nhật bằng một chuyển đổi màu mượt mà từ phía này sang phía kia.  
- **API nào xử lý việc tô màu gradient cho văn bản?** `LinearGradientBrush` kết hợp với `SetPaint` và `FillAndStrokeText`.  
- **Tôi có thể viền văn bản bằng gradient không?** Có — sử dụng `SetStroke` với một brush gradient và gọi `OutlineText`.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Cần một giấy phép thương mại Aspose.Page cho việc sử dụng không phải để đánh giá.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- Aspose.Page for .NET Library: Đảm bảo thư viện đã được tham chiếu trong dự án của bạn. Bạn có thể tải xuống từ [tài liệu Aspose.Page cho .NET](https://reference.aspose.com/page/net/).
- Document Directory: Tạo một thư mục trên đĩa nơi tệp PS được tạo sẽ được lưu và thay thế **“Your Document Directory”** trong mã bằng đường dẫn đó.

## Nhập không gian tên

Để bắt đầu, nhập các không gian tên cho phép bạn truy cập các lớp vẽ và các lớp đặc thù của PS:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Hình chữ nhật Gradient Tuyến tính là gì?

Một **hình chữ nhật gradient tuyến tính** đơn giản là một hình chữ nhật mà bên trong được tô bằng một gradient tuyến tính — các màu chuyển đổi mượt mà dọc theo một đường thẳng, thường là từ trái sang phải (ngang) hoặc từ trên xuống dưới (dọc). Trong Aspose.Page, bạn đạt được điều này bằng cách kết hợp một `GraphicsPath` định nghĩa hình chữ nhật với một `LinearGradientBrush` mô tả chuyển đổi màu.

## Tại sao nên dùng Gradient cho việc tô Văn bản và Gradient cho viền Văn bản?

- **Thu hút thị giác:** Văn bản được tô gradient tạo độ sâu và phong cách hiện đại cho báo cáo, hoá đơn hoặc tài liệu quảng cáo.  
- **Nhất quán thương hiệu:** Phù hợp màu sắc công ty với các giá trị ARGB chính xác.  
- **Đa năng:** Cùng một brush có thể tái sử dụng cho việc tô hình, tô văn bản và gradient viền, giảm thiểu việc sao chép mã.

## Bước 1: Thiết lập tài liệu

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "HorizontalGradient_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

## Bước 2: Định nghĩa hình chữ nhật Gradient và màu sắc

```csharp
    float offsetX = 200;
    float offsetY = 100;
    float width = 200;
    float height = 100;

    // Create graphics path from the first rectangle
    System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
    path.AddRectangle(new System.Drawing.RectangleF(offsetX, offsetY, width, height));

    // Create linear gradient brush with rectangle as bounds, start, and end colors
    LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.FromArgb(150, 0, 0, 0),
        Color.FromArgb(50, 40, 128, 70), 0f);
```

## Bước 3: Thiết lập biến đổi cho Brush

```csharp
    // Create a transform for brush. X and Y scale component must be equal to width and height of the rectangle correspondingly.
    // Translation components are offsets of the rectangle
    System.Drawing.Drawing2D.Matrix brushTransform = new System.Drawing.Drawing2D.Matrix(width, 0, 0, height, offsetX, offsetY);
    // Set transform
    brush.Transform = brushTransform;
```

## Bước 4: Thiết lập Paint và tô hình chữ nhật

```csharp
    // Set paint
    document.SetPaint(brush);

    // Fill the rectangle
    document.Fill(path);
```

## Cách áp dụng Gradient cho việc tô Văn bản

```csharp
    // Fill text with gradient
    System.Drawing.Font font = new System.Drawing.Font("Arial", 96, FontStyle.Bold);
    document.FillAndStrokeText("ABC", font, 200, 300, brush, new Pen(new SolidBrush(Color.Black), 2));
```

## Sử dụng Gradient cho viền Văn bản

```csharp
    // Set current stroke
    document.SetStroke(new Pen(brush, 5));
    // Outline text with gradient
    document.OutlineText("ABC", font, 200, 400);
```

## Bước 7: Đóng trang hiện tại và lưu tài liệu

```csharp
    // Close current page
    document.ClosePage();

    // Save the document
    document.Save();
}
```

Chúc mừng! Bạn đã thành công thêm một **hình chữ nhật gradient tuyến tính** vào tài liệu PostScript và sử dụng cùng một brush cho **gradient tô văn bản** và **gradient viền văn bản**.

## Các trường hợp sử dụng phổ biến & Mẹo

- **Tiêu đề báo cáo:** Tô các khối văn bản lớn bằng gradient để làm nổi bật tiêu đề phần.  
- **Logo thương hiệu:** Tái tạo các hình dạng logo với các hình dạng được tô gradient để duy trì thương hiệu nhất quán.  
- **Mẹo chuyên nghiệp:** Tái sử dụng cùng một thể hiện `LinearGradientBrush` cho nhiều lời gọi vẽ để giữ màu sắc đồng nhất hoàn hảo trên các hình dạng và văn bản.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể áp dụng gradient cho các hình dạng khác ngoài hình chữ nhật không?
**Đáp:** Có, bạn có thể áp dụng gradient cho bất kỳ hình dạng nào được định nghĩa bằng `GraphicsPath`. Chỉ cần thêm các vòng tròn, đa giác hoặc các đường dẫn tùy chỉnh trước khi gọi `document.Fill(path)`.

### Câu hỏi 2: Làm sao tôi thay đổi màu gradient?
**Đáp:** Sửa đổi các giá trị `Color.FromArgb` khi tạo `LinearGradientBrush`. Màu đầu tiên là màu bắt đầu, màu thứ hai là màu kết thúc của gradient.

### Câu hỏi 3: Aspose.Page có tương thích với các định dạng tài liệu khác nhau không?
**Đáp:** Hoàn toàn. Aspose.Page hỗ trợ XPS, PS, PDF và một số định dạng vector khác. Kiểm tra tài liệu chính thức để biết danh sách đầy đủ.

### Câu hỏi 4: Tôi có thể sử dụng Aspose.Page cho các dự án thương mại không?
**Đáp:** Có, giấy phép thương mại có sẵn. Xem trang mua hàng để biết chi tiết: [here](https://purchase.aspose.com/buy).

### Câu hỏi 5: Tôi có thể tìm hỗ trợ cộng đồng ở đâu?
**Đáp:** Tham gia diễn đàn cộng đồng Aspose.Page: [Aspose.Page Forum](https://forum.aspose.com/c/page/39).

---

**Cập nhật lần cuối:** 2026-02-25  
**Đã kiểm tra với:** Aspose.Page 24.10 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}