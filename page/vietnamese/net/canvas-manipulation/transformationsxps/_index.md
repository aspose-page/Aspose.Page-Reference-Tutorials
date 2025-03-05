---
title: Chuyển đổi XPS với Aspose.Page cho .NET
linktitle: Chuyển đổi XPS
second_title: API Aspose.Page .NET
description: Chuyển đổi tài liệu XPS dễ dàng với Aspose.Page cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để chuyển đổi liền mạch.
type: docs
weight: 13
url: /vi/net/canvas-manipulation/transformationsxps/
---
## Giới thiệu

Chào mừng bạn đến với thế giới của Aspose.Page dành cho .NET, một thư viện mạnh mẽ cho phép bạn thực hiện nhiều phép biến đổi khác nhau trên tài liệu XPS một cách dễ dàng. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình chuyển đổi tài liệu XPS bằng Aspose.Page cho .NET. Cho dù bạn là nhà phát triển dày dạn hay mới bắt đầu, hướng dẫn này sẽ hướng dẫn bạn từng bước, đảm bảo bạn nắm bắt các khái niệm một cách dễ dàng.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu, hãy đảm bảo bạn có những điều sau:

-  Aspose.Page for .NET Library: Tải xuống và cài đặt thư viện từ[Aspose.Page cho Tài liệu .NET](https://reference.aspose.com/page/net/).

- Môi trường phát triển: Thiết lập môi trường phát triển tương thích, chẳng hạn như Visual Studio hoặc bất kỳ công cụ phát triển .NET nào khác.

- Thư mục tài liệu của bạn: Thay thế trình giữ chỗ trong mã bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

Bây giờ chúng ta hãy chuyển sang phần hướng dẫn!

## Nhập không gian tên

Trước tiên, hãy đảm bảo bạn nhập các không gian tên cần thiết để cung cấp các chức năng Aspose.Page cho .NET trong mã của bạn. Thêm các không gian tên sau vào đầu tập lệnh của bạn:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Bước 1: Tạo tài liệu XPS mới

```csharp
// Bắt đầu:1
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";

// Tạo tài liệu XPS mới
XpsDocument doc = new XpsDocument();
```

## Bước 2: Tạo Canvas chính

```csharp
// Tạo canvas chính, chung cho tất cả các thành phần trang
XpsCanvas canvas1 = doc.AddCanvas();

// Tạo các offset bên trái và trên cùng trong khung vẽ chính
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Bước 3: Tạo hình học đường dẫn hình chữ nhật

```csharp
// Tạo hình học đường dẫn hình chữ nhật
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

## Bước 4: Thêm màu tô cho hình chữ nhật

```csharp
// Tạo màu tô cho hình chữ nhật
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Bước 5: Thêm Canvas mới mà không cần chuyển đổi

```csharp
// Thêm canvas mới mà không có bất kỳ chuyển đổi nào vào canvas chính
XpsCanvas canvas2 = canvas1.AddCanvas();

// Tạo hình chữ nhật trong khung vẽ này và tô màu nó
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Bước 6: Thêm Canvas mới với Translate Transformation

```csharp
// Thêm canvas mới với chuyển đổi dịch sang canvas chính
XpsCanvas canvas3 = canvas1.AddCanvas();

// Dịch khung vẽ này để định vị một hình chữ nhật mới bên dưới hình chữ nhật trước đó
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Dịch canvas này sang bên phải của trang
canvas3.RenderTransform.Translate(500, 0);

// Tạo hình chữ nhật trong khung vẽ này và tô màu nó
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

## Bước 7: Thêm Canvas mới với chuyển đổi tỷ lệ kép

```csharp
//Thêm canvas mới với chuyển đổi tỷ lệ kép vào canvas chính
XpsCanvas canvas4 = canvas1.AddCanvas();

// Dịch khung vẽ này để định vị một hình chữ nhật mới bên dưới hình chữ nhật trước đó
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Chia tỷ lệ khung vẽ này
canvas4.RenderTransform.Scale(2, 2);

// Tạo hình chữ nhật trong khung vẽ này và tô màu nó
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

## Bước 8: Thêm Canvas mới với phép xoay quanh phép biến đổi điểm

```csharp
// Thêm khung vẽ mới có tính năng xoay quanh chuyển đổi điểm vào khung vẽ chính
XpsCanvas canvas5 = canvas1.AddCanvas();

// Dịch khung vẽ này để định vị một hình chữ nhật mới bên dưới hình chữ nhật trước đó
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Xoay khung vẽ này quanh một điểm trên 45 độ
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Tạo hình chữ nhật trong khung vẽ này và tô màu nó
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

## Bước 9: Lưu tài liệu XPS kết quả

```csharp
// Lưu tài liệu XPS kết quả
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

## Phần kết luận

Chúc mừng! Bạn đã chuyển đổi thành công tài liệu XPS bằng Aspose.Page cho .NET. Hướng dẫn này bao gồm các bước thiết yếu, từ thiết lập các điều kiện tiên quyết đến thực hiện các phép chuyển đổi khác nhau. Hãy thử nghiệm những kỹ thuật này và khai thác toàn bộ tiềm năng của Aspose.Page cho .NET trong các dự án của bạn.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Page cho .NET có tương thích với tất cả các môi trường phát triển .NET không?

Câu trả lời 1: Có, Aspose.Page dành cho .NET được thiết kế để hoạt động liền mạch với nhiều môi trường phát triển .NET khác nhau, bao gồm cả Visual Studio.

### Câu hỏi 2: Tôi có thể tìm thêm ví dụ và tài liệu về Aspose.Page cho .NET ở đâu?

 A2: Tham quan[Aspose.Page cho Tài liệu .NET](https://reference.aspose.com/page/net/) để có tài liệu và ví dụ đầy đủ.

### Câu hỏi 3: Tôi có thể dùng thử Aspose.Page cho .NET trước khi mua không?

 Câu trả lời 3: Có, bạn có thể khám phá phiên bản dùng thử miễn phí bằng cách truy cập[Aspose.Page Dùng thử miễn phí](https://releases.aspose.com/).

### Câu hỏi 4: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page cho .NET?

 A4: Nhận giấy phép tạm thời bằng cách truy cập[Giấy phép tạm thời](https://purchase.aspose.com/temporary-license/).

### Câu hỏi 5: Tôi có thể mua Aspose.Page cho .NET ở đâu?

 Câu trả lời 5: Mua Aspose.Page cho .NET tại[Aspose.Page Mua](https://purchase.aspose.com/buy).