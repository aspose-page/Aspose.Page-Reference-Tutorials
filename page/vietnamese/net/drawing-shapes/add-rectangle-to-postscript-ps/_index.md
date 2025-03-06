---
title: Thêm hình chữ nhật vào PostScript (PS) bằng Aspose.Page for .NET
linktitle: Thêm hình chữ nhật vào PostScript (PS)
second_title: API Aspose.Page .NET
description: Nâng cao khả năng tạo tài liệu trong .NET với Aspose.Page. Tìm hiểu cách thêm hình chữ nhật vào tệp PostScript (PS) theo từng bước.
weight: 12
url: /vi/net/drawing-shapes/add-rectangle-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm hình chữ nhật vào PostScript (PS) bằng Aspose.Page for .NET

## Giới thiệu

Nếu bạn đang tìm cách nâng cao khả năng tạo tài liệu của mình trong .NET, Aspose.Page cung cấp một giải pháp mạnh mẽ để xử lý các tài liệu PostScript. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình thêm hình chữ nhật vào tài liệu PostScript bằng Aspose.Page cho .NET.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo rằng bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.Page for .NET Library: Tải xuống và cài đặt thư viện Aspose.Page cho .NET từ[đây](https://releases.aspose.com/page/net/).

- Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển .NET trên máy của mình.

## Nhập không gian tên

Trước khi bạn bắt đầu viết mã, hãy đảm bảo nhập các không gian tên cần thiết để truy cập các lớp và phương thức được yêu cầu:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Bây giờ, hãy chia ví dụ thành nhiều bước:

## Bước 1: Thiết lập thư mục tài liệu của bạn

```csharp
// Bắt đầu:1
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";
```

Ở bước này, hãy thay thế "Thư mục tài liệu của bạn" bằng đường dẫn bạn muốn lưu tài liệu PostScript của mình.

## Bước 2: Tạo luồng đầu ra cho tài liệu PostScript

```csharp
//Tạo luồng đầu ra cho tài liệu PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Ở đây, chúng tôi tạo luồng đầu ra cho tài liệu PostScript và chỉ định tên tệp ("AddRectangle_outPS.ps"). Điều chỉnh tên tập tin và vị trí theo sở thích của bạn.

## Bước 3: Đặt tùy chọn lưu và tạo tài liệu PS

```csharp
//Tạo tùy chọn lưu với khổ A4
PsSaveOptions options = new PsSaveOptions();

// Tạo tài liệu PS 1 trang mới
PsDocument document = new PsDocument(outPsStream, options, false);
```

Đặt các tùy chọn lưu, chỉ định kích thước trang mong muốn (trong trường hợp này là A4). Sau đó, tạo một tài liệu PostScript một trang mới.

## Bước 4: Thêm hình chữ nhật và tô màu

```csharp
//Tạo đường dẫn đồ họa từ hình chữ nhật đầu tiên
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Đặt sơn
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Điền vào hình chữ nhật
document.Fill(path);
```

Ở đây, chúng ta tạo một đường dẫn đồ họa đại diện cho hình chữ nhật đầu tiên, đặt màu sơn (trong trường hợp này là màu cam) và tô màu cho hình chữ nhật.

## Bước 5: Thêm một hình chữ nhật và nét viền khác

```csharp
//Tạo đường dẫn đồ họa từ hình chữ nhật thứ hai
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Đặt nét
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (phác thảo) hình chữ nhật
document.Draw(path);
```

Tương tự như bước trước, chúng ta tạo đường dẫn đồ họa cho hình chữ nhật thứ hai, đặt màu nét (màu đỏ với độ dày là 3) và phác thảo hình chữ nhật.

## Bước 6: Đóng trang và lưu tài liệu

```csharp
//Đóng trang hiện tại
document.ClosePage();

//Lưu tài liệu
document.Save();
```

Cuối cùng, đóng trang hiện tại và lưu toàn bộ tài liệu.

## Phần kết luận

Chúc mừng! Bạn đã thêm thành công hình chữ nhật vào tài liệu PostScript bằng Aspose.Page cho .NET. Hướng dẫn này bao gồm các bước thiết yếu, từ thiết lập môi trường phát triển của bạn đến lưu tài liệu cuối cùng.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể tùy chỉnh màu sắc của hình chữ nhật không?

A1: Có, bạn có thể tùy chỉnh màu sắc bằng cách điều chỉnh các thông số trong`SolidBrush` Và`Pen` các lớp học.

### Câu hỏi 2: Aspose.Page có tương thích với các định dạng tài liệu khác không?

Câu trả lời 2: Có, Aspose.Page hỗ trợ nhiều định dạng tài liệu khác nhau, bao gồm XPS và PostScript.

### Câu hỏi 3: Làm cách nào để thêm văn bản vào tài liệu?

 A3: Bạn có thể sử dụng`TextFragment` lớp trong Aspose.Page để thêm văn bản vào tài liệu của bạn.

### Câu hỏi 4: Tôi có thể tìm thêm ví dụ và tài liệu ở đâu?

 A4: Khám phá tài liệu[đây](https://reference.aspose.com/page/net/) và thăm quan[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để hỗ trợ cộng đồng.

### Câu 5: Tôi có thể dùng thử Aspose.Page trước khi mua không?

 Câu trả lời 5: Có, bạn có thể tải phiên bản dùng thử miễn phí[đây](https://releases.aspose.com/) và để sử dụng lâu dài, hãy xem xét một[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
