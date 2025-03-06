---
title: Thêm hình chữ nhật vào tài liệu XPS bằng Aspose.Page for .NET
linktitle: Thêm hình chữ nhật vào tài liệu XPS
second_title: API Aspose.Page .NET
description: Tăng cường việc tạo tài liệu với Aspose.Page cho .NET. Tìm hiểu cách thêm hình chữ nhật vào tài liệu XPS trong hướng dẫn từng bước này.
weight: 13
url: /vi/net/drawing-shapes/add-rectangle-to-xps-document/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm hình chữ nhật vào tài liệu XPS bằng Aspose.Page for .NET

## Giới thiệu

Aspose.Page for .NET là một thư viện mạnh mẽ cung cấp nhiều tính năng khác nhau để làm việc với tài liệu XPS (Đặc tả giấy XML) trong các ứng dụng .NET. Trong hướng dẫn này, chúng tôi sẽ tập trung vào việc thêm hình chữ nhật vào tài liệu XPS bằng Aspose.Page cho .NET. Hãy làm theo hướng dẫn từng bước này để nâng cao quá trình tạo tài liệu của bạn.

## Điều kiện tiên quyết

Trước khi bạn bắt đầu với hướng dẫn này, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1.  Aspose.Page for .NET Library: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Page for .NET trong môi trường phát triển của mình. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/page/net/).

2. Thư mục Tài liệu: Thiết lập thư mục nơi bạn muốn lưu trữ tài liệu XPS của mình.

## Nhập không gian tên

Trong ứng dụng .NET của bạn, hãy bao gồm các vùng tên cần thiết để sử dụng các chức năng của Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Bước 1: Đặt thư mục tài liệu

```csharp
// Bắt đầu:3
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Bước 2: Tạo tài liệu XPS mới

```csharp
// ExStart:4
// Tạo tài liệu XPS mới
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Bước 3: Thêm hình chữ nhật

```csharp
// ExStart:5
// Hình chữ nhật có nét đồng màu CMYK (xanh lam) ở phía dưới bên trái
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

## Bước 4: Lưu tài liệu

```csharp
// ExStart:6
// Lưu tài liệu XPS kết quả
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Chúc mừng! Bạn đã thêm thành công hình chữ nhật vào tài liệu XPS bằng Aspose.Page for .NET.

## Phần kết luận

Aspose.Page for .NET đơn giản hóa các tác vụ thao tác tài liệu, cho phép các nhà phát triển tạo và sửa đổi tài liệu XPS một cách dễ dàng. Hướng dẫn từng bước này trình bày cách thêm hình chữ nhật vào tài liệu XPS của bạn, cung cấp nền tảng vững chắc để khám phá thêm.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Page có tương thích với tất cả các ứng dụng .NET không?

Câu trả lời 1: Có, Aspose.Page được thiết kế để hoạt động trơn tru với tất cả các ứng dụng .NET.

### Câu hỏi 2: Tôi có thể tìm tài liệu về Aspose.Page cho .NET ở đâu?

 A2: Tài liệu có sẵn[đây](https://reference.aspose.com/page/net/).

### Câu hỏi 3: Tôi có thể dùng thử Aspose.Page cho .NET miễn phí trước khi mua không?

 A3: Có, bạn có thể dùng thử miễn phí[đây](https://releases.aspose.com/).

### Câu hỏi 4: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page cho .NET?

 A4: Thăm quan[liên kết này](https://purchase.aspose.com/temporary-license/) để có được giấy phép tạm thời.

### Câu hỏi 5: Tôi có thể tìm kiếm sự hỗ trợ của cộng đồng hoặc đặt câu hỏi liên quan đến Aspose.Page cho .NET ở đâu?

 A5: Tham quan[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để hỗ trợ cộng đồng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
