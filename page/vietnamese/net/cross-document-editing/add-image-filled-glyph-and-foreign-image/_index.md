---
date: 2026-01-07
description: Tìm hiểu cách tạo tài liệu XPS .NET bằng Aspose.Page. Hướng dẫn này cho
  thấy cách thêm các glyph được lấp đầy bằng hình ảnh và các hình ảnh ngoại vi để
  tạo hình ảnh tài liệu phong phú hơn.
linktitle: Add Image Filled Glyph & Foreign Image
second_title: Aspose.Page .NET API
title: Tạo tài liệu XPS .NET với Aspose.Page – Glyph được lấp đầy bằng hình ảnh và
  hình ảnh ngoại
url: /vi/net/cross-document-editing/add-image-filled-glyph-and-foreign-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo tài liệu XPS .NET với Aspose.Page – Glyph được lấp đầy bằng hình ảnh & Hình ảnh ngoại vi

## Introduction

Nếu bạn cần **create XPS document .NET** cho các ứng dụng trông chuyên nghiệp và tinh tế, Aspose.Page cung cấp các công cụ để nhúng hình ảnh trực tiếp vào glyphs và tái sử dụng tài nguyên đồ họa giữa các tài liệu. Trong hướng dẫn này, chúng ta sẽ xây dựng hai tệp XPS, lấp đầy glyphs bằng một image brush, và sau đó tái sử dụng brush đó trong tài liệu thứ hai. Khi hoàn thành, bạn sẽ hiểu tại sao cách tiếp cận này giúp tiết kiệm bộ nhớ, đơn giản hoá việc tạo kiểu, và mở ra nhiều khả năng sáng tạo cho báo cáo, hoá đơn hoặc bất kỳ nội dung có thể in nào.

## Quick Answers
- **What does this tutorial cover?** Thêm glyphs được lấp đầy bằng hình ảnh và tái sử dụng chúng trong các tài liệu XPS với Aspose.Page cho .NET.  
- **Which primary keyword is targeted?** `create xps document .net`.  
- **Prerequisites?** Môi trường phát triển .NET, Aspose.Page cho .NET, và một thư mục cho các tệp XPS của bạn.  
- **How long does implementation take?** Khoảng 10‑15 phút để có một nguyên mẫu hoạt động.  
- **Can I use other image formats?** Có – bất kỳ định dạng nào được .NET `System.Drawing.Image` hỗ trợ.

## Prerequisites

Trước khi bắt đầu viết mã, hãy đảm bảo bạn đã chuẩn bị sẵn các mục sau:

- **Aspose.Page for .NET** – tải thư viện mới nhất từ [here](https://releases.aspose.com/page/net/).  
- **Development Environment** – Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ .NET 6+).  
- **Document Directory** – tạo một thư mục trên máy tính của bạn để chứa các hình ảnh đầu vào và các tệp XPS được tạo; chúng tôi sẽ gọi nó là **Your Document Directory** trong các đoạn mã.

## Import Namespaces

Bắt đầu bằng cách import các namespace cần thiết để làm việc với các đối tượng XPS và các tiện ích vẽ.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Step‑by‑Step Guide

### Step 1: Create the First XPS Document

Chúng ta khởi tạo một tài liệu XPS trống sẽ chứa glyph được lấp đầy bằng hình ảnh.

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create the first XPS Document
XpsDocument doc1 = new XpsDocument();
```

### Step 2: Add Glyphs to the First Document

Tiếp theo, thêm một glyph (một ký tự văn bản) mà chúng ta sẽ lấp đầy bằng image brush.

```csharp
// Add glyphs to the first document
XpsGlyphs glyphs1 = doc1.AddGlyphs("Times New Roman", 200, FontStyle.Bold, 50, 250, "Test");
```

### Step 3: Fill Glyphs with an Image Brush

Ở đây chúng ta tạo một `ImageBrush` từ tệp TIFF nằm trong thư mục dữ liệu và áp dụng nó cho glyph. Brush được đặt ở chế độ tile để hình ảnh lặp lại nếu khu vực glyph lớn hơn kích thước hình ảnh.

```csharp
// Fill the glyphs with an image brush
glyphs1.Fill = doc1.CreateImageBrush(dataDir + "R08SY_NN.tif", new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 64f, 96f));
((XpsImageBrush)glyphs1.Fill).TileMode = XpsTileMode.Tile;
```

### Step 4: Create the Second XPS Document

Bây giờ chúng ta tạo một tài liệu XPS thứ hai sẽ tái sử dụng kiểu glyph và image brush từ tài liệu đầu tiên.

```csharp
// Create the second XPS Document
XpsDocument doc2 = new XpsDocument();
```

### Step 5: Add Glyphs with the Font from the First Document

Chúng ta thêm một glyph vào tài liệu thứ hai, tái sử dụng đối tượng font chính xác từ tài liệu đầu tiên. Điều này đảm bảo tính nhất quán về hình ảnh giữa hai tệp.

```csharp
// Add glyphs with the font from the first document to the second document
XpsGlyphs glyphs2 = doc2.AddGlyphs(glyphs1.Font, 200, 50, 250, "Test");
```

### Step 6: Create an Image Brush from the Fill of the First Document

Thay vì tải lại hình ảnh, chúng ta sao chép brush từ `glyphs1` và gán cho `glyphs2`. Điều này minh họa cách bạn có thể **create XPS document .NET** với quy trình chia sẻ tài nguyên một cách hiệu quả.

```csharp
// Create an image brush from the fill of the first document and fill glyphs in the second document
glyphs2.Fill = doc2.CreateImageBrush(((XpsImageBrush)glyphs1.Fill).Image, new RectangleF(0f, 0f, 128f, 192f),
    new RectangleF(0f, 0f, 128f, 192f));
((XpsImageBrush)glyphs2.Fill).TileMode = XpsTileMode.Tile;
```

### Step 7: Save the Documents

Cuối cùng, lưu cả hai tệp XPS vào đĩa. Bạn có thể mở chúng bằng bất kỳ trình xem XPS nào để xem hiệu ứng glyph được lấp đầy bằng hình ảnh.

```csharp
// Save the first XPS document
doc1.Save(dataDir + "out1.xps");

// Save the second XPS document
doc2.Save(dataDir + "out2.xps");
// ExEnd:1
```

## Why use image‑filled glyphs when you create XPS document .NET?

- **Visual Impact** – Biến văn bản thuần thành các yếu tố đồ họa phong phú mà không cần raster hoá toàn bộ trang.  
- **Resource Reuse** – Chia sẻ brushes và fonts giữa nhiều tài liệu, giảm lượng bộ nhớ tiêu thụ.  
- **Flexibility** – Tile, stretch, hoặc rotate image brush để tạo ra các mẫu tùy chỉnh hoặc thương hiệu.

## Common Issues & Tips

- **File Path Errors** – Đảm bảo `dataDir` kết thúc bằng dấu phân tách đường dẫn (`\` hoặc `/`) phù hợp với hệ điều hành của bạn.  
- **Unsupported Image Formats** – Aspose.Page hoạt động tốt nhất với TIFF, PNG và JPEG. Chuyển đổi các định dạng khác trước khi sử dụng.  
- **TileMode Not Applied** – Kiểm tra bạn đã ép kiểu thành `XpsImageBrush` trước khi đặt `TileMode`; nếu không, thuộc tính sẽ bị bỏ qua.

## Frequently Asked Questions

### Q1: Can I use different image formats for filling glyphs?

**A:** Có, Aspose.Page hỗ trợ TIFF, PNG, JPEG, BMP và GIF. Chỉ cần cung cấp phần mở rộng tệp đúng trong lời gọi `CreateImageBrush`.

### Q2: How can I customize the appearance of glyphs further?

**A:** Khám phá các thuộc tính bổ sung trên `XpsGlyphs` như `Opacity`, `RenderTransform`, và `Stroke` để tinh chỉnh việc render.

### Q3: Is Aspose.Page suitable for handling large document sets?

**A:** Chắc chắn. Thư viện được tối ưu cho các kịch bản hiệu năng cao và có thể xử lý hàng ngàn tệp XPS trong các công việc batch.

### Q4: Can I apply different styles to individual glyphs?

**A:** Có. Mỗi thể hiện `XpsGlyphs` có thể có fill, stroke và transformation riêng, cho phép bạn kiểm soát chi tiết từng glyph.

### Q5: What are the benefits of using Aspose.Page over other document processing tools?

**A:** Aspose.Page cung cấp một API hoàn chỉnh, không cần giấy phép cho việc tạo, thao tác và chuyển đổi XPS, kèm tài liệu chi tiết và hỗ trợ 24/7.

---

**Last Updated:** 2026-01-07  
**Tested With:** Aspose.Page 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}