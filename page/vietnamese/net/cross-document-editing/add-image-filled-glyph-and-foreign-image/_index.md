---
date: 2026-06-30
description: Tìm hiểu cách tạo tài liệu XPS .NET và thêm image‑filled glyphs hoặc
  foreign images bằng Aspose.Page cho .NET trong vài bước đơn giản.
keywords:
- create xps document .net
- image filled glyph
- foreign image
linktitle: Thêm Image Filled Glyph & Foreign Image
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create XPS document .NET and add image‑filled glyphs or
    foreign images using Aspose.Page for .NET in a few easy steps.
  headline: Create XPS Document .NET – Add Image Filled Glyph & Foreign Image with
    Aspose.Page
  type: TechArticle
- questions:
  - answer: Over 25 image formats and the ability to process XPS files up to 500 MB
      without full memory loading.
    question: What does Aspose.Page support?
  - answer: 'Just two lines: create an `ImageBrush` and assign it to a `Glyph`.'
    question: How many lines of code to add an image‑filled glyph?
  - answer: Yes, a commercial license removes evaluation watermarks.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are compatible?
  - answer: Absolutely – you can import the font collection from the first document
      into the second.
    question: Can I reuse fonts from another XPS?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Tạo tài liệu XPS .NET – Thêm Image Filled Glyph & Foreign Image với Aspose.Page
url: /vi/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Tài liệu XPS .NET – Thêm Glyph Được Điền Hình Ảnh & Hình Ảnh Ngoại với Aspose.Page

## Giới thiệu

Trong phát triển .NET, các nhiệm vụ **create XPS document .NET** thường gặp khi bạn cần đồ họa chất lượng cao, độc lập độ phân giải. Aspose.Page cho .NET giúp thực hiện điều này một cách đơn giản và cho phép bạn làm phong phú các tệp XPS bằng các glyph được điền hình ảnh hoặc kéo hình ảnh từ tài liệu XPS khác. Khi kết thúc hướng dẫn này, bạn sẽ biết cách tạo hai tài liệu XPS, điền glyph bằng hình ảnh và tái sử dụng những hình ảnh đó qua các tài liệu — lý tưởng cho việc tạo hoá đơn, chứng chỉ hoặc bất kỳ đầu ra nào giàu hình ảnh.

## Câu trả lời nhanh

- **Aspose.Page hỗ trợ gì?** Hơn 25 định dạng hình ảnh và khả năng xử lý các tệp XPS lên đến 500 MB mà không cần tải toàn bộ vào bộ nhớ.  
- **Cần bao nhiêu dòng mã để thêm glyph được điền hình ảnh?** Chỉ hai dòng: tạo một `ImageBrush` và gán nó cho một `Glyph`.  
- **Có cần giấy phép cho môi trường sản xuất không?** Có, giấy phép thương mại loại bỏ các watermark đánh giá.  
- **Phiên bản .NET nào tương thích?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Có thể tái sử dụng phông chữ từ XPS khác không?** Chắc chắn – bạn có thể nhập bộ sưu tập phông chữ từ tài liệu đầu tiên vào tài liệu thứ hai.

## Làm thế nào để tạo tài liệu XPS bằng Aspose.Page .NET?

Tải thư viện Aspose.Page, khởi tạo một `XpsDocument`, thêm một trang và gọi `Save` – đó là quy trình hoàn chỉnh chỉ trong ba câu lệnh ngắn gọn. API tự động xử lý kích thước trang, DPI và quản lý tài nguyên, vì vậy bạn không cần tự quản lý các cấu trúc XPS cấp thấp. Cách tiếp cận này mở rộng từ tờ rơi một trang đến các danh mục hàng trăm trang.

## Yêu cầu trước

Trước khi bắt đầu, hãy đảm bảo bạn có:

- **Aspose.Page for .NET** – tải xuống tại [đây](https://releases.aspose.com/page/net/).  
- **Một IDE .NET** – Visual Studio, Rider, hoặc VS Code với phần mở rộng C#.  
- **Một thư mục cho tài liệu của bạn** – chúng tôi sẽ gọi nó là **Your Document Directory** trong các đoạn mã.

## Nhập không gian tên

The `Aspose.Page.XPS` namespace provides core XPS document classes, while `Aspose.Page.XPS.XpsModel` contains model elements such as glyphs and brushes. Import them at the top of your file:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Glyph được điền hình ảnh là gì?

Một glyph là một hình dạng vector có thể được vẽ bằng màu nền đồng nhất, gradient hoặc một brush hình ảnh. Khi bạn áp dụng một `ImageBrush`, phần bên trong glyph được tô bằng hình ảnh đã cung cấp, cho phép tạo hiệu ứng hình ảnh phức tạp mà không cần raster hoá toàn bộ trang.

## Bước 1: Tạo tài liệu XPS đầu tiên

`XpsDocument` đại diện cho một gói XPS và là điểm khởi đầu để tạo và lưu các tệp XPS. Bắt đầu bằng cách tạo tài liệu XPS đầu tiên sẽ chứa các glyph được điền hình ảnh.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

## Bước 2: Thêm glyph vào tài liệu đầu tiên

`XpsGlyphs` định nghĩa một tập hợp các glyph (ký tự văn bản) có thể được đặt trên một trang. Thêm glyph vào tài liệu đầu tiên, chỉ định phông chữ, kích thước, kiểu và vị trí.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

## Bước 3: Điền glyph bằng Image Brush

`ImageBrush` tô một khu vực bằng hình ảnh, cho phép các mẫu hoặc bức tranh lấp đầy các hình dạng. Điền các glyph bằng một image brush, sử dụng hình ảnh từ thư mục dữ liệu của bạn.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

## Bước 4: Tạo tài liệu XPS thứ hai

`XpsDocument` được sử dụng để tạo một tệp XPS mới có thể chứa các trang, tài nguyên và nội dung. Bây giờ, tạo tài liệu XPS thứ hai sẽ tích hợp các glyph từ tài liệu đầu tiên.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

## Bước 5: Thêm glyph với phông chữ từ tài liệu đầu tiên

`Font` đại diện cho một kiểu chữ được sử dụng để hiển thị văn bản trong tài liệu XPS. Thêm glyph vào tài liệu thứ hai, sử dụng phông chữ được trích xuất từ tài liệu đầu tiên. Bằng cách chia sẻ bộ sưu tập phông chữ, bạn giữ kích thước tệp nhỏ và đảm bảo tính nhất quán về hình ảnh.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

## Bước 6: Tạo Image Brush từ phần Fill của tài liệu đầu tiên

`ImageBrush` có thể được tạo từ một fill hiện có để tái sử dụng cùng một hình ảnh qua các tài liệu. Tạo một image brush từ phần fill của tài liệu đầu tiên và sử dụng nó để điền các glyph trong tài liệu thứ hai. Kỹ thuật “hình ảnh ngoại” này cho phép bạn tái sử dụng tác phẩm mà không cần sao chép lại tệp nguồn.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

## Bước 7: Lưu các tài liệu

`Save` ghi gói XPS vào một tệp, nhúng tất cả các tài nguyên. Lưu cả hai tài liệu XPS đầu tiên và thứ hai vào thư mục đầu ra. Phương thức `Save` ghi gói XPS, nhúng tất cả các tài nguyên và bảo tồn các glyph được điền hình ảnh.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|----------------|-----|
| **Hình ảnh không hiển thị bên trong glyph** | `ImageBrush` được tạo với URI không đúng hoặc kích thước hình ảnh vượt quá giới hạn glyph. | Xác minh đường dẫn hình ảnh, và tùy chọn đặt `ImageBrush.Stretch = Stretch.Uniform`. |
| **Phông chữ thiếu trong tài liệu thứ hai** | Tài nguyên phông chữ không được xuất từ XPS đầu tiên. | Sử dụng `firstDoc.Fonts.SaveTo(secondDoc.Fonts)` trước khi thêm glyph. |
| **Hiệu suất chậm khi xử lý tệp lớn** | Tải hình ảnh lớn vào bộ nhớ cho mỗi glyph. | Tái sử dụng một thể hiện `ImageBrush` duy nhất cho tất cả glyph, hoặc giảm độ phân giải hình ảnh trước khi sử dụng. |

## Câu hỏi thường gặp

### Q1: Tôi có thể sử dụng các định dạng hình ảnh khác nhau để điền glyph không?

A1: Có, Aspose.Page hỗ trợ PNG, JPEG, BMP, GIF, TIFF và hơn nữa — hơn 25 định dạng tổng cộng.

### Q2: Làm sao tôi có thể tùy chỉnh giao diện của glyph hơn nữa?

A2: Khám phá các thuộc tính như `Glyph.Stroke`, `Glyph.FillOpacity`, và `Glyph.Transform` để điều chỉnh viền, độ trong suốt và góc quay.

### Q3: Aspose.Page có phù hợp để xử lý bộ tài liệu lớn không?

A3: Chắc chắn. Thư viện xử lý các tệp XPS hàng trăm trang bằng cách streaming, giữ mức sử dụng bộ nhớ dưới 100 MB ngay cả với tài liệu 500 trang.

### Q4: Tôi có thể áp dụng các kiểu khác nhau cho từng glyph không?

A4: Có, mỗi thể hiện `Glyph` có các thuộc tính `Fill`, `Stroke`, và `Transform` riêng, cho phép tạo kiểu cho từng glyph.

### Q5: Lợi ích của việc sử dụng Aspose.Page so với các công cụ XPS khác là gì?

A5: Aspose.Page hỗ trợ hơn 25 định dạng hình ảnh, xử lý các tệp lên đến 500 MB mà không cần tải toàn bộ vào bộ nhớ, và cung cấp API 100 % .NET‑native — loại bỏ nhu cầu sử dụng COM interop hoặc công cụ bên ngoài.

---

**Cập nhật lần cuối:** 2026-06-30  
**Kiểm tra với:** Aspose.Page 24.11 for .NET  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Các hướng dẫn liên quan

- [Tạo tài liệu XPS – Aspose.Page cho .NET](/page/net/document-creation/)
- [Thêm hình ảnh vào tài liệu XPS với Aspose.Page cho .NET](/page/net/image-management/add-image-to-xps-document/)
- [Thêm bản sao Glyph và thay đổi màu với Aspose.Page cho .NET](/page/net/cross-document-editing/add-glyph-clone-and-change-color/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}