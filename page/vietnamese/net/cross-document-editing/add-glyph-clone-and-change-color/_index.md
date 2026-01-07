---
date: 2026-01-07
description: Tìm hiểu cách tạo tài liệu XPS, thêm các bản sao glyph, sử dụng bút vẽ
  màu đặc và lưu tệp XPS bằng Aspose.Page cho .NET.
linktitle: Add Glyph Clone and Change Color
second_title: Aspose.Page .NET API
title: Tạo tài liệu XPS – Thêm bản sao glyph và thay đổi màu sắc với Aspose.Page cho
  .NET
url: /vi/net/cross-document-editing/add-glyph-clone-and-change-color/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Tài liệu XPS – Thêm Bản sao Glyph & Thay đổi Màu với Aspose.Page cho .NET

## Giới thiệu

Chào mừng bạn đến với hướng dẫn từng bước này, cho thấy **cách tạo tệp tài liệu XPS**, sao chép glyph và thay đổi màu của chúng bằng Aspose.Page cho .NET. Dù bạn đang xây dựng báo cáo động, hoá đơn hay đồ họa tùy chỉnh, việc thành thạo các kỹ thuật này sẽ giúp bạn tạo ra đầu ra XPS giàu hình ảnh mà không rời khỏi hệ sinh thái .NET.

## Câu trả lời nhanh
- **Mục tiêu chính là gì?** Tạo một tài liệu XPS, thêm các bản sao glyph và thay đổi màu của chúng.  
- **Thư viện nào được sử dụng?** Aspose.Page cho .NET.  
- **Có cần giấy phép không?** Một giấy phép tạm thời có sẵn để đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Làm sao lưu kết quả?** Sử dụng phương thức `Save` để ghi tệp XPS ra đĩa.

## Yêu cầu trước

Trước khi bắt đầu tutorial, hãy chắc chắn bạn đã có các yêu cầu sau:

- Hiểu biết cơ bản về ngôn ngữ lập trình C#.  
- Visual Studio hoặc bất kỳ môi trường phát triển C# nào bạn ưa thích đã được cài đặt.  
- Thư viện Aspose.Page cho .NET. Bạn có thể tải xuống [tại đây](https://releases.aspose.com/page/net/).  
- Quen thuộc với định dạng tài liệu XPS.

## Nhập các Namespace

Để bắt đầu, bao gồm các namespace cần thiết trong dự án C# của bạn:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Cách tạo tài liệu XPS và thêm bản sao Glyph

### Bước 1: Thiết lập thư mục tài liệu của bạn

Bắt đầu bằng cách thiết lập thư mục nơi các tài liệu sẽ được lưu:

```csharp
string dataDir = "Your Document Directory";
```

### Bước 2: Tạo tài liệu XPS đầu tiên

Bây giờ, hãy tạo tài liệu XPS đầu tiên:

```csharp
XpsDocument doc1 = new XpsDocument();
```

### Bước 3: Thêm Glyph vào tài liệu đầu tiên

Thêm glyph vào tài liệu đầu tiên bằng các tham số đã chỉ định:

```csharp
XpsGlyphs glyphs = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Bước 4: Đổ màu Glyph bằng một Solid Color Brush

Đổ màu cho các glyph trong tài liệu đầu tiên bằng **solid color brush**, ví dụ, màu xanh lá cây:

```csharp
glyphs.Fill = doc1.CreateSolidColorBrush(Color.Green);
```

### Bước 5: Tạo tài liệu XPS thứ hai

Tiếp theo, tạo tài liệu XPS thứ hai:

```csharp
XpsDocument doc2 = new XpsDocument();
```

### Bước 6: Cách thêm bản sao Glyph vào tài liệu khác

Sao chép glyph từ tài liệu đầu tiên và thêm chúng vào tài liệu thứ hai:

```csharp
glyphs = doc2.Add(glyphs.Clone());
```

### Bước 7: Cách thay đổi màu của Glyph đã sao chép

Thay đổi màu của các glyph đã sao chép trong tài liệu thứ hai, ví dụ, sang màu đỏ. Điều này minh họa **cách thay đổi màu** của một glyph sau khi sao chép:

```csharp
((XpsSolidColorBrush)glyphs.Fill).Color = doc2.CreateColor(Color.Red);
```

### Bước 8: Lưu tệp XPS – Tài liệu đầu tiên

Lưu tài liệu XPS đầu tiên vào thư mục bạn đã định nghĩa ở trên:

```csharp
doc1.Save(dataDir + "out1.xps");
```

### Bước 9: Lưu tệp XPS – Tài liệu thứ hai

Lưu tài liệu XPS thứ hai:

```csharp
doc2.Save(dataDir + "out2.xps");
```

Chúc mừng! Bạn đã thành công **tạo các tệp tài liệu XPS**, thêm bản sao glyph và thay đổi màu của chúng bằng Aspose.Page cho .NET.

## Tại sao nên sử dụng sao chép Glyph và thay đổi màu?

- **Tái sử dụng:** Sao chép các glyph hiện có để tái dùng các hình vector phức tạp mà không cần định nghĩa lại.  
- **Hiệu năng:** Giảm thời gian xử lý so với việc tạo lại glyph từ đầu.  
- **Linh hoạt trong thiết kế:** Áp dụng các instance `SolidColorBrush` khác nhau cho cùng một glyph để đạt được các chủ đề hình ảnh đa dạng.  
- **Chỉnh sửa chéo tài liệu:** Sao chép glyph giữa nhiều tệp XPS, giúp duy trì thương hiệu nhất quán trong các báo cáo.

## Các vấn đề thường gặp & Khắc phục

| Vấn đề | Giải pháp |
|-------|----------|
| **Clone trả về null** | Đảm bảo glyph nguồn (`glyphs`) đã được thêm vào tài liệu đầu tiên trước khi sao chép. |
| **Màu không thay đổi** | Ép kiểu `glyphs.Fill` sang `XpsSolidColorBrush` trước khi đặt thuộc tính `Color` (như trong Bước 7). |
| **Tệp không được lưu** | Kiểm tra `dataDir` trỏ tới thư mục hợp lệ, có quyền ghi và bạn có đủ quyền hệ thống tập tin. |
| **Kích thước glyph không mong muốn** | Điều chỉnh tham số kích thước phông chữ (đối số thứ hai trong `AddGlyphs`) để phóng to/thu nhỏ glyph phù hợp. |

## Câu hỏi thường gặp

**Q1: Tôi có thể dùng Aspose.Page cho .NET với các định dạng tài liệu khác không?**  
A1: Aspose.Page cho .NET được thiết kế đặc biệt để làm việc với tài liệu XPS. Nếu bạn cần thao tác các định dạng khác, hãy khám phá các thư viện Aspose khác phù hợp với những định dạng đó.

**Q2: Có giấy phép tạm thời cho Aspose.Page cho .NET không?**  
A2: Có, bạn có thể nhận giấy phép tạm thời để thử nghiệm. Truy cập [tại đây](https://purchase.aspose.com/temporary-license/) để biết thêm chi tiết.

**Q3: Làm sao tôi có thể nhận hỗ trợ hoặc trợ giúp cho các vấn đề?**  
A3: Hãy truy cập diễn đàn [Aspose.Page](https://forum.aspose.com/c/page/39) để kết nối với cộng đồng và nhận trợ giúp.

**Q4: Có bất kỳ hạn chế nào đối với phiên bản dùng thử miễn phí không?**  
A4: Phiên bản dùng thử miễn phí có một số hạn chế; bạn nên xem tài liệu để biết chi tiết trước khi sử dụng.

**Q5: Tôi có thể tìm tài liệu chi tiết cho Aspose.Page cho .NET ở đâu?**  
A5: Tham khảo tài liệu [tại đây](https://reference.aspose.com/page/net/) để có thông tin chi tiết và các ví dụ.

**Q6: Làm sao thay đổi màu viền (stroke) của glyph thay vì màu nền (fill)?**  
A6: Sử dụng `glyphs.Stroke = doc.CreateSolidColorBrush(Color.Blue);` để đặt brush cho viền.

**Q7: Tôi có thể thêm nhiều bản sao glyph vào cùng một tài liệu không?**  
A7: Có, gọi `doc2.Add(glyphs.Clone());` nhiều lần, điều chỉnh vị trí cho phù hợp.

---

**Cập nhật lần cuối:** 2026-01-07  
**Đã kiểm tra với:** Aspose.Page 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}