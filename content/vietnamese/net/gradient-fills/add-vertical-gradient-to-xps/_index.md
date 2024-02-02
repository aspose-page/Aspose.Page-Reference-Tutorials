---
title: Thêm gradient dọc vào XPS với Aspose.Page for .NET
linktitle: Thêm độ dốc dọc vào XPS
second_title: API Aspose.Page .NET
description: Tìm hiểu cách nâng cao tài liệu XPS bằng độ dốc dọc bằng Aspose.Page cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch.
type: docs
weight: 15
url: /vi/net/gradient-fills/add-vertical-gradient-to-xps/
---
## Giới thiệu

Chào mừng bạn đến với hướng dẫn từng bước này về cách thêm dải màu dọc vào tài liệu XPS bằng Aspose.Page cho .NET. Aspose.Page là một API mạnh mẽ cho phép bạn làm việc với các tệp XPS (Đặc tả giấy XML) trong các ứng dụng .NET của bạn. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình tạo tài liệu XPS mới, thêm dải màu dọc vào đường dẫn và lưu kết quả.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

-  Aspose.Page for .NET Library: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Page for .NET trong môi trường phát triển của mình. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/page/net/).

- Môi trường phát triển: Thiết lập môi trường phát triển .NET với IDE ưa thích của bạn, chẳng hạn như Visual Studio.

Bây giờ, hãy bắt đầu với việc thêm dải màu dọc vào tài liệu XPS bằng Aspose.Page cho .NET.

## Nhập không gian tên

Trong ứng dụng .NET của bạn, hãy bao gồm các vùng tên cần thiết để truy cập các lớp và phương thức Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Bước 1: Thiết lập thư mục tài liệu của bạn

Trước khi bắt đầu, hãy đặt đường dẫn đến thư mục tài liệu nơi bạn muốn lưu tài liệu XPS thu được.

```csharp
// Bắt đầu:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Bước 2: Tạo tài liệu XPS mới

Khởi tạo một tài liệu XPS mới bằng mã sau:

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Bước 3: Xác định điểm dừng chuyển màu

Tạo danh sách các điểm dừng chuyển màu, chỉ định màu sắc và vị trí cho mỗi điểm dừng. Trong ví dụ này, chúng tôi xác định một gradient dọc có năm điểm dừng.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Bước 4: Tạo đường dẫn với gradient

Xác định một đường dẫn bằng cách chỉ định hình dạng của nó và áp dụng cọ chuyển màu tuyến tính cho nó.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Bước 5: Lưu tài liệu XPS kết quả

Lưu tài liệu XPS đã sửa đổi vào thư mục được chỉ định của bạn.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

Chúc mừng! Bạn đã thêm thành công dải màu dọc vào tài liệu XPS bằng Aspose.Page cho .NET.

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá cách tận dụng Aspose.Page cho .NET để cải thiện các tài liệu XPS với độ dốc dọc. Aspose.Page đơn giản hóa các tác vụ phức tạp, cung cấp cho các nhà phát triển một cách liền mạch để thao tác với các tệp XPS trong ứng dụng .NET của họ.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Page có tương thích với Visual Studio 2019 không?

Câu trả lời 1: Có, Aspose.Page tương thích với Visual Studio 2019. Đảm bảo bạn đã cài đặt đúng phiên bản thư viện.

### Câu 2: Tôi có thể sử dụng Aspose.Page cho các dự án thương mại không?

 Câu trả lời 2: Có, Aspose.Page có thể được sử dụng cho các dự án thương mại. Thăm nom[đây](https://purchase.aspose.com/buy) để khám phá các lựa chọn cấp phép.

### Câu 3: Có bản dùng thử miễn phí không?

 Câu trả lời 3: Có, bạn có thể dùng thử miễn phí Aspose.Page[đây](https://releases.aspose.com/).

### Câu hỏi 4: Tôi có thể tìm tài liệu Aspose.Page ở đâu?

 A4: Tài liệu có sẵn[đây](https://reference.aspose.com/page/net/).

### Câu hỏi 5: Làm cách nào tôi có thể nhận được hỗ trợ hoặc đặt câu hỏi?

 A5: Tham quan[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để hỗ trợ cộng đồng.