---
date: 2026-03-03
description: Tìm hiểu cách sử dụng Aspose.Page cho .NET để lắp ghép hình ảnh trong
  tài liệu XPS. Hướng dẫn từng bước này chỉ ra cách lắp ghép hình ảnh một cách hiệu
  quả và nâng cao tính thẩm mỹ.
linktitle: Add Tiled Image to XPS Document
second_title: Aspose.Page .NET API
title: Cách sử dụng Aspose.Page để thêm hình ảnh lát gạch vào tài liệu XPS
url: /vi/net/image-management/add-tiled-image-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Sử Dụng Aspose.Page Để Thêm Hình Ảnh Lát Vào Tài Liệu XPS

## Giới thiệu

Nếu bạn đang tự hỏi **how to use Aspose** để mang lại cho các tệp XPS của mình một phong cách hình ảnh phong phú hơn, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn từng bước cần thiết để **tile an image** bên trong tài liệu XPS bằng cách sử dụng Aspose.Page cho .NET. Khi hoàn thành, bạn sẽ có một đoạn mã có thể tái sử dụng mà bạn có thể chèn vào bất kỳ dự án .NET nào để tạo đồ họa hình ảnh lát ngay lập tức.

## Câu trả lời nhanh
- **Thư viện nào cần thiết?** Aspose.Page for .NET  
- **Phương thức nào tạo ra brush lát?** `CreateImageBrush` with `TileMode = XpsTileMode.Tile`  
- **Tôi có thể kiểm soát độ trong suốt không?** Yes – set `path.Fill.Opacity` (e.g., 0.5f)  
- **Tôi có cần giấy phép để thử nghiệm không?** A temporary license works for evaluation; a full license is required for production.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+

## Aspose.Page là gì và Tại sao lại Lát Hình Ảnh?

Aspose.Page là một API mạnh mẽ cho phép các nhà phát triển tạo, chỉnh sửa và render XPS, PDF và các định dạng dựa trên trang khác mà không cần phụ thuộc vào Microsoft Office. Lát một hình ảnh—lặp lại bitmap trên một hình dạng—giúp bạn lấp đầy các khu vực lớn bằng các mẫu, dấu nước hoặc kết cấu nền trong khi giữ kích thước tệp thấp.

## Cách Sử Dụng Aspose.Page Để Lát Hình Ảnh Trong Tài Liệu XPS

Dưới đây bạn sẽ tìm thấy một ví dụ hoàn chỉnh, sẵn sàng chạy. Mỗi bước được giải thích bằng ngôn ngữ đơn giản trước khối mã tương ứng, để bạn có thể thấy **why** mỗi dòng quan trọng.

### Yêu cầu trước

- **Aspose.Page for .NET** – tải xuống và tham chiếu thư viện từ trang chính [here](https://reference.aspose.com/page/net/).  
- **Development environment** – Visual Studio (bất kỳ phiên bản nào) hoặc IDE .NET khác mà bạn thích.

### Nhập Các Namespace

Đầu tiên, đưa các namespace cần thiết vào phạm vi để trình biên dịch biết nơi tìm các lớp XPS.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

### Bước 1: Xác Định Thư Mục Tài Liệu

Xác định vị trí lưu tệp XPS được tạo và hình ảnh nguồn. Thay thế placeholder bằng thư mục thực tế trên máy của bạn.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Bước 2: Tạo Tài Liệu XPS Mới

Khởi tạo một tài liệu XPS trống sẽ chứa đồ họa lát.

```csharp
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Bước 3: Thêm Hình Ảnh Lát

Ở đây chúng ta tạo một đường hình chữ nhật, lấp đầy nó bằng một `ImageBrush`, và đặt brush ở chế độ lát. Thuộc tính `TileMode` cho phép engine lặp lại hình ảnh cả theo chiều ngang và chiều dọc. Điều chỉnh tọa độ hình chữ nhật hoặc hình ảnh nguồn tùy theo nhu cầu của bạn.

```csharp
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

### Bước 4: Lưu Tài Liệu XPS Đã Tạo

Cuối cùng, ghi tài liệu ra đĩa. Tệp đầu ra có thể được mở bằng bất kỳ trình xem XPS nào hoặc tiếp tục xử lý bằng Aspose.Page.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

## Các Vấn Đề Thường Gặp & Mẹo

- **Path errors** – Đảm bảo `dataDir` kết thúc bằng dấu gạch chéo `/` hoặc sử dụng `Path.Combine` để tránh các vấn đề thiếu dấu phân tách.  
- **Image size mismatches** – Hình ảnh nguồn nên đủ lớn cho khu vực lát; nếu không mẫu có thể bị kéo dài.  
- **Opacity not visible** – Một số trình xem bỏ qua độ trong suốt trên XPS; hãy thử với trình xem hỗ trợ đầy đủ việc render XPS (ví dụ, XPS Viewer trên Windows).

## Câu Hỏi Thường Gặp

### Q1: Aspose.Page có tương thích với mọi môi trường phát triển .NET không?
A: Có, Aspose.Page hoạt động với Visual Studio, Rider, VS Code và bất kỳ IDE nào hỗ trợ .NET.

### Q2: Tôi có thể điều chỉnh độ trong suốt của hình ảnh lát không?
A: Chắc chắn. Ví dụ đặt `path.Fill.Opacity = 0.5f;`—bạn có thể thay đổi giá trị float trong khoảng 0 (transparent) và 1 (opaque).

### Q3: Có các chế độ lát khác có sẵn trong Aspose.Page cho .NET không?
A: Có. Ngoài `XpsTileMode.Tile`, bạn có thể sử dụng `FlipX`, `FlipY`, và `FlipXY` để tạo các mẫu phản chiếu.

### Q4: Làm thế nào để tôi xử lý giấy phép tạm thời cho Aspose.Page?
A: Tham khảo trang [temporary license](https://purchase.aspose.com/temporary-license/) trên website Aspose để biết chi tiết về cách lấy và áp dụng giấy phép dùng thử.

### Q5: Tôi có thể tìm kiếm trợ giúp hoặc kết nối với cộng đồng Aspose.Page ở đâu?
A: Truy cập [Aspose.Page forum](https://forum.aspose.com/c/page/39) để đặt câu hỏi, chia sẻ đoạn mã và học hỏi từ các nhà phát triển khác.

### Q6: Tôi có thể sử dụng cách này để tạo hiệu ứng dấu nước không?
A: Có. Bằng cách giảm độ trong suốt và chọn một hình ảnh bán trong suốt, brush lát sẽ hoạt động hoàn hảo như một dấu nước lặp lại.

## Kết luận

Bây giờ bạn đã biết **how to use Aspose** để thêm một hình ảnh lát vào tài liệu XPS, kiểm soát độ trong suốt của nó và lưu kết quả để sử dụng tiếp. Kỹ thuật này lý tưởng cho các mẫu nền, dấu nước, hoặc bất kỳ trường hợp nào mà đồ họa lặp lại tăng tính thẩm mỹ mà không làm tăng kích thước tệp. Hãy thoải mái thử nghiệm với các hình dạng, hình ảnh và chế độ lát khác nhau để phù hợp với nhu cầu dự án của bạn.

---

**Last Updated:** 2026-03-03  
**Tested With:** Aspose.Page for .NET (latest release)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}