---
date: 2026-03-21
description: Tìm hiểu cách thêm văn bản Unicode vào tài liệu XPS bằng Aspose.Page
  cho .NET. Hướng dẫn này chỉ cho bạn cách tạo tài liệu XPS bằng C# và Aspose.Page
  để chèn văn bản với các chuỗi Unicode.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Cách Thêm Văn Bản Unicode vào Tài Liệu XPS với Aspose.Page
url: /vi/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Văn Bản Unicode vào Tài Liệu XPS với Aspose.Page

## Giới thiệu

Nếu bạn cần **cách thêm unicode** vào một tệp XPS, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ đi qua các bước chính xác để **tạo tài liệu XPS kiểu C#** bằng Aspose.Page cho .NET và trình diễn khả năng **aspose page add text** với một chuỗi Unicode. Khi hoàn thành, bạn sẽ có một tài liệu XPS hoạt động đầy đủ, hiển thị đúng văn bản Unicode từ phải sang trái (RTL).

## Câu trả lời nhanh
- **Hướng dẫn này đề cập đến gì?** Thêm văn bản Unicode vào tài liệu XPS với Aspose.Page cho .NET.  
- **Ngôn ngữ được sử dụng?** C# (tương thích với .NET Framework và .NET Core).  
- **Có cần giấy phép không?** Bản dùng thử miễn phí đủ cho việc phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Có thể thay đổi phông chữ hoặc kích thước không?** Có – ví dụ sử dụng Arial 20 pt, nhưng bất kỳ phông chữ đã cài đặt nào cũng được.  
- **Có hỗ trợ RTL không?** Đặt `BidiLevel = 1` sẽ bật chế độ hiển thị từ phải sang trái cho các chuỗi Unicode.

## “cách thêm unicode” trong XPS là gì?

Thêm văn bản Unicode có nghĩa là chèn các ký tự từ bất kỳ ngôn ngữ nào—Arabic, Hebrew, Chinese, v.v.—vào tài liệu XPS. Lớp `XpsGlyphs` của Aspose.Page xử lý việc đặt glyph ở mức thấp, trong khi thuộc tính `BidiLevel` kiểm soát hướng văn bản cho các script RTL.

## Tại sao nên dùng Aspose.Page để thêm văn bản?

- **Tích hợp đầy đủ .NET** – hoạt động với .NET Framework, .NET Core, .NET 5/6+.  
- **Không phụ thuộc bên ngoài** – mã quản lý thuần, không cần COM interop.  
- **Hỗ trợ typogra­phy phong phú** – phông chữ, kiểu, màu sắc và văn bản hai chiều.  
- **Hiệu năng cao** – tạo và lưu tệp XPS nhanh chóng, lý tưởng cho việc tạo trên server.

## Yêu cầu trước

- Kiến thức cơ bản về C# và phát triển .NET.  
- Visual Studio (bất kỳ phiên bản mới nào).  
- Thư viện Aspose.Page cho .NET – tải về từ [here](https://releases.aspose.com/page/net/).

## Nhập không gian tên

Đầu tiên, nhập các không gian tên cho phép bạn truy cập mô hình XPS và các tiện ích vẽ.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Bước 1: Thiết lập tài liệu – tạo XPS document C#

Tạo một tài liệu XPS mới sẽ chứa văn bản Unicode.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Bước 2: Thêm Văn Bản Unicode – aspose page add text

Bây giờ chúng ta thêm chuỗi Unicode thực tế. Trong ví dụ này, chúng tôi sử dụng phông Arial, kích thước 20, và đặt văn bản tại (400 f, 200 f). `BidiLevel` bằng 1 báo cho bộ render xử lý chuỗi như văn bản từ phải sang trái.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Bước 3: Lưu tài liệu

Cuối cùng, ghi tệp XPS ra đĩa.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Chúc mừng! Bạn đã thành công **cách thêm unicode** vào tài liệu XPS bằng Aspose.Page cho .NET.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|-----------|
| Văn bản bị lỗi | Phông chữ không hỗ trợ dải Unicode cần thiết | Sử dụng phông chữ có chứa glyph cần thiết (ví dụ, Arial Unicode MS). |
| Văn bản RTL vẫn hiển thị trái‑sang‑phải | `BidiLevel` chưa được đặt hoặc đặt thành 0 | Đảm bảo `glyphs.BidiLevel = 1;` cho các script RTL. |
| Không lưu được tệp | Đường dẫn `dataDir` không hợp lệ | Kiểm tra thư mục tồn tại và ứng dụng có quyền ghi. |

## Câu hỏi thường gặp

**H: Aspose.Page có tương thích với các framework .NET mới nhất không?**  
Đ: Có, Aspose.Page được cập nhật thường xuyên để hỗ trợ .NET Framework, .NET Core và .NET 5/6+.

**H: Tôi có thể tùy chỉnh kiểu và kích thước phông chữ khi thêm văn bản không?**  
Đ: Chắc chắn! Phương thức `AddGlyphs` cho phép bạn chỉ định bất kỳ họ phông, kích thước và `FontStyle` nào bạn cần.

**H: Tôi có thể tìm tài liệu bổ sung cho Aspose.Page ở đâu?**  
Đ: Tham khảo tài liệu [here](https://reference.aspose.com/page/net/) để biết chi tiết API toàn diện.

**H: Có nguồn tài nguyên miễn phí nào để bắt đầu với Aspose.Page không?**  
Đ: Có, khám phá diễn đàn cộng đồng tại [Aspose.Page forum](https://forum.aspose.com/c/page/39) để nhận mẹo, ví dụ và hỗ trợ từ người dùng khác.

**H: Có phiên bản dùng thử trước khi mua không?**  
Đ: Tất nhiên! Tải bản dùng thử miễn phí từ [here](https://releases.aspose.com/) để đánh giá thư viện.

---

**Cập nhật lần cuối:** 2026-03-21  
**Kiểm tra với:** Aspose.Page 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}