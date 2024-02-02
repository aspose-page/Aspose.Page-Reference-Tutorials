---
title: Thêm hình ảnh xếp chồng vào tài liệu XPS bằng Aspose.Page for .NET
linktitle: Thêm hình ảnh xếp chồng vào tài liệu XPS
second_title: API Aspose.Page .NET
description: Khám phá cách thêm hình ảnh xếp chồng vào tài liệu XPS một cách dễ dàng với Aspose.Page for .NET. Tăng cường sự hấp dẫn trực quan và tạo ra các tài liệu tuyệt đẹp.
type: docs
weight: 12
url: /vi/net/image-management/add-tiled-image-to-xps-document/
---
## Giới thiệu

Bạn đang tìm cách nâng cao tài liệu XPS của mình bằng cách thêm các hình ảnh xếp chồng hấp dẫn trực quan? Aspose.Page for .NET trao quyền cho các nhà phát triển để đạt được điều này một cách liền mạch. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình thêm hình ảnh xếp kề vào tài liệu XPS bằng Aspose.Page cho .NET.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.Page for .NET: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Page. Bạn có thể tìm tài liệu chi tiết và tải về thư viện[đây](https://reference.aspose.com/page/net/).
- Môi trường phát triển: Thiết lập môi trường phát triển .NET ưa thích của bạn, chẳng hạn như Visual Studio.

## Nhập không gian tên

Để bắt đầu, hãy nhập các không gian tên cần thiết vào dự án của bạn. Điều này đảm bảo rằng bạn có quyền truy cập vào các lớp và phương thức cần thiết để làm việc với Aspose.Page. Thêm các không gian tên sau vào đầu mã của bạn:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Bây giờ, hãy chia ví dụ thành nhiều bước.

## Bước 1: Xác định thư mục tài liệu

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";
```

Đảm bảo thay thế "Thư mục tài liệu của bạn" bằng đường dẫn thực tế nơi bạn muốn lưu tài liệu XPS của mình.

## Bước 2: Tạo tài liệu XPS mới

```csharp
// Tạo tài liệu XPS mới
XpsDocument doc = new XpsDocument();
```

 Khởi tạo một tài liệu XPS mới bằng cách sử dụng`XpsDocument` lớp học.

## Bước 3: Thêm hình ảnh xếp cạnh

```csharp
// Hình ảnh ngói
// Hình chữ nhật đầy ImageBrush ở trên cùng bên phải bên dưới
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.Fill = doc.CreateImageBrush(dataDir + "R08LN_NN.jpg", new RectangleF(0f, 0f, 128f, 96f), new RectangleF(0f, 0f, 64f, 48f));
((XpsImageBrush)path.Fill).TileMode = XpsTileMode.Tile;
path.Fill.Opacity = 0.5f;
```

Bước này thêm hình ảnh xếp kề vào tài liệu XPS. Điều chỉnh tọa độ và đường dẫn tệp hình ảnh theo yêu cầu của bạn.

## Bước 4: Lưu tài liệu XPS kết quả

```csharp
// Lưu tài liệu XPS kết quả
doc.Save(dataDir + "AddTiledImage_outXPS.xps");
```

Lưu tài liệu XPS đã sửa đổi vào thư mục được chỉ định.

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách thêm hình ảnh xếp kề vào tài liệu XPS bằng Aspose.Page cho .NET. Tính năng đơn giản nhưng mạnh mẽ này cho phép bạn nâng cao sự hấp dẫn trực quan của tài liệu một cách dễ dàng.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Page có tương thích với tất cả môi trường phát triển .NET không?

Câu trả lời 1: Có, Aspose.Page được thiết kế để hoạt động liền mạch với nhiều môi trường phát triển .NET khác nhau, bao gồm cả Visual Studio.

### Câu hỏi 2: Tôi có thể điều chỉnh độ mờ của hình ảnh xếp kề không?

Câu trả lời 2: Chắc chắn, như được minh họa trong ví dụ, bạn có thể đặt độ mờ của hình chữ nhật được tô màu bằng cách sử dụng`Opacity` tài sản.

### Câu hỏi 3: Có các chế độ ô xếp khác có sẵn trong Aspose.Page cho .NET không?

 Câu trả lời 3: Có, Aspose.Page cung cấp các chế độ xếp khác nhau. Trong hướng dẫn này, chúng tôi đã sử dụng`XpsTileMode.Tile`, nhưng bạn có thể khám phá các tùy chọn khác trong tài liệu.

### Câu hỏi 4: Làm cách nào để xử lý giấy phép tạm thời cho Aspose.Page?

 A4: Hãy tham khảo[giấy phép tạm thời](https://purchase.aspose.com/temporary-license/) trên trang web Aspose để được hướng dẫn cách lấy và triển khai giấy phép tạm thời.

### Câu hỏi 5: Tôi có thể tìm kiếm trợ giúp hoặc kết nối với cộng đồng Aspose.Page ở đâu?

 A5: Tham quan[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để tương tác với cộng đồng, đặt câu hỏi và tìm giải pháp.