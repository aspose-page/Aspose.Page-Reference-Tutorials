---
title: Thêm hình ảnh đầy Glyph & hình ảnh nước ngoài với Aspose.Page .NET
linktitle: Thêm hình ảnh đầy Glyph & hình ảnh nước ngoài
second_title: API Aspose.Page .NET
description: Khai phá sức mạnh xử lý tài liệu trong .NET với Aspose.Page. Thêm glyph chứa đầy hình ảnh một cách dễ dàng. Nâng cao hình ảnh và hợp lý hóa quy trình làm việc của bạn.
weight: 11
url: /vi/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm hình ảnh đầy Glyph & hình ảnh nước ngoài với Aspose.Page .NET

## Giới thiệu

Trong thế giới phát triển .NET, Aspose.Page nổi bật như một bộ công cụ mạnh mẽ để xử lý các tác vụ xử lý tài liệu. Hướng dẫn này sẽ hướng dẫn bạn quy trình thêm các ký tự chứa đầy hình ảnh và kết hợp các hình ảnh nước ngoài bằng Aspose.Page cho .NET. Đến cuối hướng dẫn này, bạn sẽ hiểu rõ về cách nâng cao khả năng xử lý tài liệu của mình.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.Page for .NET: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Page. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/page/net/).

- Môi trường phát triển: Thiết lập môi trường phát triển .NET hoạt động với Visual Studio hoặc bất kỳ IDE ưa thích nào khác.

- Thư mục Tài liệu: Tạo một thư mục nơi bạn sẽ lưu trữ tài liệu của mình. Điều này sẽ được gọi là "Thư mục tài liệu của bạn" trong các ví dụ về mã.

## Nhập không gian tên

Trong ứng dụng .NET của bạn, hãy bắt đầu bằng cách nhập các vùng tên cần thiết để truy cập các lớp và phương thức do Aspose.Page cung cấp:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Bước 1: Tạo tài liệu XPS đầu tiên

Bắt đầu bằng cách tạo tài liệu XPS đầu tiên bằng Aspose.Page. Tài liệu này sẽ đóng vai trò là nền tảng để thêm các hình tượng chứa đầy hình ảnh.

```csharp
// Bắt đầu:1
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";

// Tạo tài liệu XPS đầu tiên
XpsDocument doc1 = new XpsDocument();
```

## Bước 2: Thêm Glyph vào tài liệu đầu tiên

Thêm glyph vào tài liệu đầu tiên, chỉ định phông chữ, kích thước, kiểu dáng và vị trí.

```csharp
// Thêm glyph vào tài liệu đầu tiên
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Bước 3: Tô màu Glyph bằng Image Brush

Điền vào các glyph bằng cọ hình ảnh, sử dụng hình ảnh từ thư mục dữ liệu của bạn.

```csharp
// Điền vào các glyph bằng cọ hình ảnh
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Bước 4: Tạo tài liệu XPS thứ hai

Bây giờ, hãy tạo tài liệu XPS thứ hai sẽ kết hợp các hình tượng từ tài liệu đầu tiên.

```csharp
// Tạo tài liệu XPS thứ hai
XpsDocument doc2 = new XpsDocument();
```

## Bước 5: Thêm Glyph với Phông chữ từ Tài liệu Đầu tiên

Thêm glyph vào tài liệu thứ hai, sử dụng phông chữ từ tài liệu đầu tiên.

```csharp
// Thêm glyphs với phông chữ từ tài liệu đầu tiên vào tài liệu thứ hai
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Bước 6: Tạo Image Brush từ phần tô của tài liệu đầu tiên

Tạo một cọ vẽ hình ảnh từ phần tô của tài liệu đầu tiên và sử dụng nó để tô các nét tượng hình trong tài liệu thứ hai.

```csharp
// Tạo một cọ hình ảnh từ phần tô của tài liệu đầu tiên và điền glyphs vào tài liệu thứ hai
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Bước 7: Lưu tài liệu

Lưu cả tài liệu XPS thứ nhất và thứ hai.

```csharp
// Lưu tài liệu XPS đầu tiên
doc1.Save(dataDir + "out1.xps");

// Lưu tài liệu XPS thứ hai
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Phần kết luận

Chúc mừng! Bạn đã thêm thành công các ký tự chứa đầy hình ảnh và kết hợp các hình ảnh nước ngoài bằng Aspose.Page cho .NET. Hướng dẫn này cung cấp nền tảng để nâng cao khả năng xử lý tài liệu của bạn, mở ra những khả năng mới cho các tài liệu sáng tạo và hấp dẫn về mặt hình ảnh.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng các định dạng hình ảnh khác nhau để tô hình tượng không?

Câu trả lời 1: Có, Aspose.Page hỗ trợ nhiều định dạng hình ảnh khác nhau. Đảm bảo khả năng tương thích với định dạng hình ảnh đã chọn.

### Câu hỏi 2: Làm cách nào tôi có thể tùy chỉnh thêm hình thức của glyph?

Câu trả lời 2: Khám phá tài liệu Aspose.Page để biết các thuộc tính và phương pháp bổ sung nhằm tinh chỉnh giao diện glyph.

### Câu hỏi 3: Aspose.Page có phù hợp để xử lý các tập tài liệu lớn không?

Câu trả lời 3: Aspose.Page được thiết kế để xử lý cả tập tài liệu nhỏ và lớn một cách hiệu quả.

### Câu hỏi 4: Tôi có thể áp dụng các kiểu khác nhau cho từng hình tượng không?

Câu trả lời 4: Có, bạn có thể tùy chỉnh các kiểu cho từng hình tượng một cách độc lập, mang lại mức độ linh hoạt cao.

### Câu hỏi 5: Lợi ích của việc sử dụng Aspose.Page so với các công cụ xử lý tài liệu khác là gì?

Câu trả lời 5: Aspose.Page cung cấp một bộ tính năng toàn diện, hiệu suất tuyệt vời và tài liệu phong phú, khiến nó trở thành lựa chọn ưa thích của nhiều nhà phát triển.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
