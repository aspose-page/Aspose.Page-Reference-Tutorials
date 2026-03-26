---
date: 2026-03-26
description: Học cách tạo tài liệu PostScript trong .NET với các mẫu lát kết cấu bằng
  Aspose.Page. Hãy làm theo hướng dẫn từng bước của chúng tôi để thêm các kết cấu
  phong phú vào tệp PS của bạn.
linktitle: Create PostScript .NET document with texture tiling
second_title: Aspose.Page .NET API
title: Tạo tài liệu PostScript .NET với việc lát kết cấu
url: /vi/net/texture-handling/apply-texture-tiling-pattern-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo tài liệu PostScript .NET với mẫu lát kết cấu

## Cách tạo tài liệu PostScript .NET với mẫu lát kết cấu

Trong hướng dẫn này, bạn sẽ học cách **tạo tài liệu PostScript .NET** và làm phong phú nó bằng một mẫu lát kết cấu sử dụng thư viện Aspose.Page. Chúng tôi sẽ hướng dẫn từng bước, từ việc thiết lập dự án đến việc tô màu và viền văn bản bằng cọ kết cấu, để bạn có thể tạo các tệp PS hấp dẫn chỉ trong vài phút.

## Câu trả lời nhanh
- **Thư viện nào được sử dụng?** Aspose.Page for .NET  
- **Có thể dùng .NET Core không?** Có, thư viện hỗ trợ .NET Core và .NET 5/6  
- **Định dạng ảnh nào phù hợp cho kết cấu?** Bất kỳ định dạng nào được System.Drawing hỗ trợ (BMP, PNG, JPEG, v.v.)  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút cho một ví dụ cơ bản  
- **Cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; cần giấy phép cho môi trường sản xuất  

## Yêu cầu trước

- [Visual Studio](https://visualstudio.microsoft.com/) đã được cài đặt trên máy của bạn.  
- Kiến thức cơ bản về lập trình C#.  
- Tải và cài đặt [thư viện Aspose.Page for .NET](https://releases.aspose.com/page/net/).  
- Một tệp ảnh cho mẫu kết cấu (ví dụ: **TestTexture.bmp**).

## Nhập không gian tên

Trong tệp C# của bạn, nhập các không gian tên cần thiết để trình biên dịch biết nơi tìm các kiểu chúng ta sẽ dùng:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Bước 1: Thiết lập thư mục tài liệu

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Thay **Your Document Directory** bằng thư mục mà bạn muốn lưu tệp PS được tạo.

## Bước 2: Tạo luồng xuất cho tài liệu PS

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddTextureTilingPattern_outPS.ps", FileMode.Create))
{
    // Create save options with A4 size
    PsSaveOptions options = new PsSaveOptions();

    // Create new 1-paged PS Document
    PsDocument document = new PsDocument(outPsStream, options, false);
```

Khối này mở một luồng tệp, cấu hình kích thước trang (mặc định A4), và tạo một thể hiện **PsDocument** mới mà chúng ta sẽ vẽ lên.

## Bước 3: Áp dụng mẫu lát kết cấu

```csharp
// Create a Bitmap object from the image file
using (Bitmap image = new Bitmap(dataDir + "TestTexture.bmp"))
{
    // Create texture brush from the image
    TextureBrush brush = new TextureBrush(image, WrapMode.Tile);

    // Add scaling in X direction to the pattern
    Matrix transform = new Matrix(2, 0, 0, 1, 0, 0);
    brush.Transform = transform;

    // Set this texture brush as the current paint
    document.SetPaint(brush);
}
```

Ở đây chúng ta tải bitmap, bọc nó trong một **TextureBrush**, tùy chọn kéo dài theo chiều ngang, và yêu cầu **PsDocument** sử dụng cọ này cho các thao tác vẽ tiếp theo.

## Bước 4: Tạo đường dẫn hình chữ nhật và tô màu

```csharp
// Create rectangle path
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(0, 0, 200, 100));

// Fill rectangle
document.Fill(path);
```

Một hình chữ nhật đơn giản được định nghĩa và được tô bằng cọ kết cấu mà chúng ta đã thiết lập trước đó.

## Bước 5: Đặt nét viền và vẽ

```csharp
// Get current paint
Brush paint = document.GetPaint();

// Set red stroke
document.SetStroke(new Pen(new SolidBrush(Color.Red), 2));

// Stroke the rectangle
document.Draw(path);
```

Chúng ta lấy màu hiện tại (cọ kết cấu), tạo một bút đỏ cho viền, và vẽ đường viền của hình chữ nhật.

## Bước 6: Tô và viền văn bản bằng mẫu kết cấu

```csharp
// Fill text with texture pattern                
Font font = new Font("Arial", 96, FontStyle.Bold);
document.FillAndStrokeText("ABC", font, 200, 300, paint, new Pen(Color.Black, 2));

// Outline text with texture pattern
document.OutlineText("ABC", font, 200, 400, new Pen(paint, 5));
```

Bước này minh họa khả năng **tô và viền văn bản**: các ký tự “ABC” được tô bằng cọ kết cấu và sau đó được viền, tạo hiệu ứng hình ảnh ấn tượng.

## Bước 7: Lưu và đóng tài liệu

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Đóng trang sẽ hoàn thiện các lệnh vẽ, và `Save()` ghi tệp PostScript ra đĩa.

## Các vấn đề thường gặp và giải pháp

- **Kết cấu bị kéo dài không đúng** – Điều chỉnh các giá trị `Matrix` để kiểm soát tỉ lệ trong các hướng X/Y.  
- **Không tìm thấy ảnh** – Kiểm tra `dataDir` trỏ đúng thư mục và tên tệp khớp chính xác, kể cả chữ hoa/thường.  
- **Màu sắc không đúng** – Nhớ rằng PostScript sử dụng không gian màu độc lập với thiết bị; đảm bảo bạn dùng các đối tượng `Color` được ánh xạ chính xác.

## Câu hỏi thường gặp

**Hỏi:** Tôi có thể dùng các định dạng ảnh khác cho mẫu kết cấu không?  
**Đáp:** Có, bất kỳ định dạng nào được `System.Drawing.Bitmap` hỗ trợ (BMP, PNG, JPEG, GIF, v.v.) đều hoạt động.

**Hỏi:** Aspose.Page có tương thích với .NET Core không?  
**Đáp:** Hoàn toàn. Thư viện chạy trên .NET Framework, .NET Core và .NET 5/6.

**Hỏi:** Làm sao thay đổi kích thước của hình chữ nhật có kết cấu?  
**Đáp:** Sửa các giá trị `RectangleF` trong bước tạo hình chữ nhật (ví dụ, `new RectangleF(0, 0, 300, 150)`).

**Hỏi:** Tôi có thể áp dụng nhiều mẫu kết cấu trong một tài liệu không?  
**Đáp:** Có. Chỉ cần tạo một `TextureBrush` mới với ảnh khác và gọi `SetPaint` lại trước khi vẽ hình hoặc văn bản tiếp theo.

**Hỏi:** Tôi có thể tìm thêm ví dụ và tài liệu API ở đâu?  
**Đáp:** Truy cập [Aspose.Page Forum](https://forum.aspose.com/c/page/39) để nhận hỗ trợ cộng đồng và [tài liệu chính thức](https://reference.aspose.com/page/net/) để xem chi tiết cách dùng API.

## Kết luận

Bây giờ bạn đã biết cách **tạo tài liệu PostScript .NET** và áp dụng mẫu lát kết cấu, bao gồm cách **tô và viền văn bản** bằng kết cấu đó. Hãy thử nghiệm với các ảnh khác nhau, ma trận co giãn và các primitive vẽ để tạo ra các tệp PS tùy chỉnh cho báo cáo, tờ rơi hoặc bất kỳ đầu ra đồ họa nào.

---

**Cập nhật lần cuối:** 2026-03-26  
**Kiểm tra với:** Aspose.Page 24.11 for .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}