---
date: 2026-01-20
description: Tìm hiểu cách tạo tài liệu XPS, thêm một hình chữ nhật và lưu tệp XPS
  bằng Aspose.Page cho .NET trong hướng dẫn từng bước này.
linktitle: Add Rectangle to XPS Document
second_title: Aspose.Page .NET API
title: 'Tạo tài liệu XPS: Thêm hình chữ nhật với Aspose.Page cho .NET'
url: /vi/net/drawing-shapes/add-rectangle-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Tài liệu XPS: Thêm Hình chữ nhật với Aspose.Page cho .NET

## Giới thiệu

Trong hướng dẫn này, bạn sẽ **tạo tài liệu XPS** và vẽ một hình chữ nhật bên trong chúng trả lời gìose.Page cho .NET (có bản dùng thử miễn phí).  
- **Mất bao lâu?** Khoảng 5‑10 phút để triển khai và chạy.  
- **Tôi có cần giấy phép không?** Cần một giấy phép tạm thời cho việc sử dụng trong môi trường sản xuất.  
- **Tôi có thể lưu kết quả dưới dạng tệp XPS không?** Có – phương thức `Save` ghi một **tệp XPS đã lưu** vào đĩa.

## Xây dựng tài liệu XPS là gì?

Tạo một tài liệu XPS có nghĩa là xây dựng mô tả trang, .6+.  
- **API vẽ phong phú – mọi thứ chạy trong cùng tiến trình mà không cần Office hay Acrobat.  

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có những thứ sau:

1. **Aspose.Page cho .NET** – tải xuống [tại đây](https://releases.aspose.com/page/net/).  
2. **Một thư mục có quyền ghi** nơi các tệp XPS được tạo sẽ được lưu.

## Nhập không gian tên

Trong dự án .NET của bạn, nhập các không gian tên cần thiết:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Bước 1: Đặt thư mục tài liệu

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

> **Mẹo chuyên nghiệp:** Sử dụng đường dẫn tuyệt đối hoặc `Path.Combine` để tránh các vấn đề về ký tự phân tách đường dẫn trên các hệ điều hành khác nhau.

## Bước 2: Tạo tài liệu XPS mới

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

Tại thời điểm này, bạn đã **tạo một đối tượng tài liệu XPS** sẽ chứa tất cả các phần tử vẽ.

## Bước 3: Thêm hình chữ nhật (sử dụng tạo hình học đường dẫn)

```csharp
// ExStart:5
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.Stroke = doc.CreateSolidColorBrush(
    doc.CreateColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f));
path.StrokeThickness = 12f;
// ExEnd:5
```

Lệnh `CreatePathGeometry` **tạo hình học đường dẫn** xác định đường viền của hình chữ nhật. Bạn có thể chỉnh sửa chuỗi lệnh dạng SVG‑like để vẽ các hình dạng khác.

## Bước 4: Lưu tài liệu (lưu tệp XPS)

```csharp
// ExStart:6
// Save resultant XPS document
doc.Save(dataDir + "AddRectangleXPS_out.xps");
// ExEnd:6
```

Gọi `Save` sẽ ghi **tệp XPS đã lưu** vào vị trí bạn chỉ định.

Chúc mừng! Bạn đã **tạo thành công một tài liệu XPS**, thêm một hình chữ nhật và lưu tệp.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|----------|
| `FileNotFoundException` on `doc.Save` | Thư mục `dataDir` không tồn tại | Đảm bảo thư mục tồn tại hoặc tạo nó bằng `Directory.CreateDirectory(dataDir)`. |
| Hình chữ nhật không hiển thị | Thiếu hồ sơ màu Stroke hoặc hình học đường dẫn bị sai | Kiểm tra đường dẫn tệp ICC và chuỗi hình học (`M … Z`). |
| Hiệu suất chậm khi tài liệu lớn | Quá nhiều lời gọi `AddPath` riêng lẻ | Thực hiện vẽ hàng loạt hoặc tái sử dụng các đối tượng brush/pen. |

## Câu hỏi thường gặp

**Q: Aspose.Page có tương thích với mọi ứng dụng .NET không?**  
A: Có, Aspose.Page được thiết kế để hoạt động liền mạch với mọi ứng dụng .NET.

**Q: Tôi có thể tìm tài liệu cho Aspose.Page cho .NET ở đâu?**  
A: Tài liệu có sẵn [tại đây](https://reference.aspose.com/page/net/).

**Q: Tôi có thể dùng thử Aspose.Page cho .NET miễn phí trước khi mua không?**  
A: Có, bạn có thể nhận bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

**Q: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.Page cho .NET?**  
A: Truy cập [liên kết này](https://purchase.aspose.com/temporary-license/) để nhận giấy phép tạm thời.

**Q: Tôi có thể tìm hỗ trợ cộng đồng hoặc đặt câu hỏi liên quan đến Aspose.Page cho .NET ở đâu?**  
A: Truy cập [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để nhận hỗ trợ cộng đồng.

---

**Cập nhật lần cuối:** 2026-01-20  
**Kiểm tra với:** Aspose.Page 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}