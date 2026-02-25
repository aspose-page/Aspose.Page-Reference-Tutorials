---
date: 2026-02-25
description: Tìm hiểu cách sử dụng brush gradient tuyến tính trong C# để thêm gradient
  vào các tệp PS và tô hình chữ nhật bằng gradient bằng Aspose.Page cho .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# Linear Gradient Brush – Thêm Độ Trơn Dọc vào PostScript (PS) bằng Aspose.Page
url: /vi/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

 craft translation.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# c# Linear Gradient Brush – Thêm Độ Trơn Dọc vào PostScript (PS) với Aspose.Page

## Giới thiệu

Trong lĩnh vực thao tác và tạo tài liệu, **Aspose.Page for .NET** nổi bật như một công cụ mạnh mẽ cho các nhà phát triển. Trong hướng dẫn này, bạn sẽ khám phá cách **thêm gradient vào file PS** bằng cách sử dụng **c# linear gradient brush** để **đổ hình chữ nhật bằng gradient**. Khi kết thúc tutorial, bạn sẽ nắm rõ quy trình từng bước và lý do kỹ thuật này tạo ra một gradient dọc mượt mà trong đầu ra PostScript của bạn.

## Câu trả lời nhanh
- **Brush gradient tuyến tính trong C# làm gì?** Nó tạo ra một chuyển đổi mượt mà giữa nhiều màu sắc trên một hình dạng.
- **Có thể dùng với bất kỳ phiên bản .NET nào không?** Có, Aspose.Page hỗ trợ .NET Framework 4.5+ và .NET Core/5+.
- **Cần giấy phép cho môi trường sản xuất không?** Cần giấy phép thương mại cho các bản không phải đánh giá.
- **Gradient thực sự dọc không?** Brush được xoay 90°, đảm bảo luồng màu dọc.
- **Đầu ra được lưu ở đâu?** Ở đường dẫn bạn chỉ định trong `dataDir` (ví dụ, `VerticalGradient_outPS.ps`).

## Brush Gradient Tuyến Tính trong C# là gì?
**C# linear gradient brush** là một đối tượng GDI+ (`LinearGradientBrush`) vẽ chuyển đổi màu tuyến tính giữa các điểm đã định. Khi kết hợp với API vẽ của Aspose.Page, nó cho phép bạn render các gradient tinh vi trực tiếp vào tài liệu PostScript (PS).

## Tại sao nên dùng Linear Gradient Brush cho PostScript?
- **Đầu ra chất lượng cao:** Gradient được render ở mức độ máy in, giữ nguyên độ trung thực.
- **Kiểm soát toàn diện:** Bạn có thể đặt các điểm dừng màu tùy chỉnh, góc quay và tỉ lệ.
- **Mã tái sử dụng:** Logic brush này hoạt động cho PDF, SVG và các định dạng khác được Aspose.Page hỗ trợ.

## Yêu cầu trước

Trước khi bắt đầu tutorial, hãy chắc chắn rằng bạn đã chuẩn bị:

- Aspose.Page for .NET: Đảm bảo đã cài đặt thư viện Aspose.Page. Bạn có thể tìm tài nguyên và tài liệu cần thiết [tại đây](https://reference.aspose.com/page/net/).
- Môi trường phát triển: Thiết lập môi trường phát triển phù hợp, bao gồm một Integrated Development Environment (IDE) cho .NET.
- Kiến thức cơ bản: Nắm vững các kiến thức cơ bản về phát triển .NET, bao gồm làm việc với streams, graphics paths và thao tác màu sắc.

## Nhập các Namespace

Trong dự án C# của bạn, thêm các namespace cần thiết ở đầu file mã:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Bước 1: Thiết lập Thư mục Tài liệu

Xác định đường dẫn tới thư mục tài liệu của bạn. Đây là vị trí sẽ lưu file PS.

```csharp
string dataDir = "Your Document Directory";
```

## Bước 2: Tạo Output Stream cho Tài liệu PostScript

Tạo một output stream cho tài liệu PostScript bằng lớp `FileStream`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Bước 3: Tạo Save Options và Tài liệu PS

Tạo các tùy chọn lưu với kích thước A4 và khởi tạo một tài liệu PS 1 trang.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Bước 4: Định nghĩa Kích thước Hình chữ nhật

Xác định kích thước và vị trí của hình chữ nhật sẽ áp dụng gradient dọc.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Bước 5: Tạo Graphics Path

Xây dựng một graphics path từ hình chữ nhật đã định nghĩa.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Bước 6: Định nghĩa Các Màu Nội suy

Thiết lập một mảng các màu nội suy và vị trí cho gradient.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Bước 7: Tạo Linear Gradient Brush

Tạo một linear gradient brush với hình chữ nhật làm giới hạn, màu bắt đầu và màu kết thúc.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Bước 8: Đặt Transform cho Brush

Thiết lập một transform cho brush, đảm bảo các thành phần tỉ lệ X và Y khớp với chiều rộng và chiều cao của hình chữ nhật.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Bước 9: Đặt Paint và Đổ Hình chữ nhật

Đặt paint cho tài liệu, và **đổ hình chữ nhật bằng gradient** bằng cách sử dụng path đã tạo trước đó.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Bước 10: Đóng Trang hiện tại và Lưu Tài liệu

Đóng trang hiện tại và lưu tài liệu PostScript.

```csharp
document.ClosePage();
document.Save();
```

Chúc mừng! Bạn đã thành công **thêm gradient dọc vào tài liệu PostScript** bằng **c# linear gradient brush** với Aspose.Page for .NET. Hãy thử nghiệm với các tham số và màu sắc khác nhau để đạt được các hiệu ứng hình ảnh đa dạng trong tài liệu của bạn.

## Các vấn đề thường gặp và Giải pháp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| Gradient xuất hiện ngang | Brush chưa được xoay | Đảm bảo gọi `brushTransform.Rotate(90);` trước khi gán cho `brush.Transform`. |
| Màu sắc bị nhạt | Output stream độ phân giải thấp | Sử dụng `PsSaveOptions` có độ phân giải cao hơn hoặc tăng kích thước tài liệu. |
| File đầu ra rỗng | Stream chưa được flush | Kiểm tra rằng `document.Save();` được gọi bên ngoài khối `using`. |

## Câu hỏi thường gặp

**Q1: Tôi có thể áp dụng nhiều gradient cho các vùng khác nhau trong cùng một tài liệu không?**  
A: Có, bạn chỉ cần lặp lại các bước cho mỗi vùng với kích thước và bảng màu riêng.

**Q2: Làm sao tích hợp đoạn mã này vào dự án .NET hiện có?**  
A: Sao chép và dán mã vào file dự án của bạn và đảm bảo đã tham chiếu thư viện Aspose.Page.

**Q3: Aspose.Page cho .NET có hỗ trợ các loại gradient khác không?**  
A: Aspose.Page hỗ trợ nhiều loại gradient, bao gồm radial và path gradients. Tham khảo tài liệu để biết chi tiết.

**Q4: Tôi có thể dùng Aspose.Page cho các dự án thương mại không?**  
A: Có, bạn có thể. Truy cập [tại đây](https://purchase.aspose.com/buy) để khám phá các tùy chọn giấy phép.

**Q5: Có diễn đàn cộng đồng nào cho Aspose.Page để tôi có thể hỏi đáp không?**  
A: Chắc chắn! Ghé thăm [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để kết nối với các nhà phát triển khác và nhận hỗ trợ.

---

**Cập nhật lần cuối:** 2026-02-25  
**Đã kiểm tra với:** Aspose.Page 24.11 for .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}