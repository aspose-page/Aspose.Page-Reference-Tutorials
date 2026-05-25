---
date: 2026-01-20
description: Dễ dàng thêm số trang PDF khi hợp nhất tài liệu XPS thành các tệp PDF
  chất lượng cao bằng Aspose.Page cho .NET. Hãy làm theo hướng dẫn từng bước của chúng
  tôi để chuyển đổi XPS sang PDF.
linktitle: Merge XPS Documents into PDF
second_title: Aspose.Page .NET API
title: Thêm số trang vào PDF – Chuyển XPS sang PDF bằng Aspose.Page
url: /vi/net/document-merging/merge-xps-documents-into-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm số trang PDF – Gộp XPS sang PDF bằng Aspose.Page

## Introduction

Nếu bạn cần **thêm số trang PDF** khi gộp các tệp XPS, Aspose.Page cho .NET giúp quá trình trở nên dễ dàng. Trong hướng dẫn này, chúng tôi sẽ đi qua một ví dụ hoàn chỉnh, sẵn sàng cho sản xuất, chuyển đổi tài liệu XPS sang PDF chất lượng cao, cho phép bạn kiểm soát nén hình ảnh và tự động chèn số trang vào PDF cuối cùng. Khi hoàn thành, bạn sẽ có một đoạn mã có thể tái sử dụng trong bất kỳ dự án C# nào.

## Quick Answers
- **Tôi có thể thêm số trang khi gộp XPS sang PDF không?** Có – thuộc tính `PdfSaveOptions.PageNumbers` thực hiện đúng điều đó.  
- **Thư viện nào thực hiện việc chuyển đổi?** Aspose.Page cho .NET.  
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Cần một giấy phép Aspose.Page hợp lệ; giấy phép tạm thời có sẵn cho mục đích thử nghiệm.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6+.  
- **Có thể xuất hình ảnh chất lượng cao không?** Chắc chắn – đặt `JpegQualityLevel` thành 100 và chọn `PdfImageCompression.Jpeg`.

## Prerequisites

Trước khi bắt đầu hướng dẫn, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:

- Aspose.Page cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Page. Bạn có thể tải xuống từ [here](https://releases.aspose.com/page/net/).

- Tệp tài liệu: Đảm bảo tệp XPS (`input.xps`) đã sẵn sàng trong thư mục bạn chỉ định.

## Import Namespaces

Trong dự án .NET của bạn, bao gồm các namespace cần thiết để làm việc với Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Bước này đảm bảo bạn có quyền truy cập vào các lớp và phương thức cần thiết cho việc chuyển đổi tài liệu.

## How to add page numbers PDF when merging XPS documents

`Bộ sưu tập PdfSaveOptions.PageNumbers` cho phép bạn chỉ định chính xác những trang (hoặc phạm vi trang) sẽ xuất hiện trong PDF đầu ra. Bằng cách điền các số trang bạn muốn, Aspose.Page sẽ tự động chèn số thứ tự phù hợp.

### Step 1: Initialize Streams

Bước 1: Khởi tạo các luồng

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Initialize PDF output stream
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Bước này liên quan đến việc thiết lập các luồng đầu vào và đầu ra cho các tệp XPS và PDF. Đảm bảo sử dụng đúng đường dẫn và tên tệp.

### Step 2: Load XPS Document

Bước 2: Tải tài liệu XPS

```csharp
// ExStart:4
// Load XPS document form the stream
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// or load XPS document directly from file. No xpsStream is needed then.
// XpsDocument document = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

Ở đây, chúng ta tải tài liệu XPS vào đối tượng `XpsDocument`, chuẩn bị cho các bước xử lý tiếp theo.

### Step 3: Initialize Save Options (merge xps to pdf)

Bước 3: Khởi tạo tùy chọn lưu (gộp XPS sang PDF)

```csharp
// ExStart:5
// Initialize options object with necessary parameters.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }   // <-- adds page numbers PDF
};
// ExEnd:5
```

Tùy chỉnh đối tượng `PdfSaveOptions` theo sở thích của bạn, chỉ định các tham số như nén hình ảnh, nén văn bản và **số trang** bạn muốn xuất hiện trong PDF cuối cùng. Đặt `JpegQualityLevel` thành 100 đảm bảo **hình ảnh PDF chất lượng cao**.

### Step 4: Create Rendering Device

Bước 4: Tạo thiết bị render

```csharp
// ExStart:6
// Create rendering device for PDF format
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

`PdfDevice` là công cụ chịu trách nhiệm chuyển đổi tài liệu XPS sang định dạng PDF.

### Step 5: Save the Document (c# xps to pdf)

Bước 5: Lưu tài liệu (C# XPS sang PDF)

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Cuối cùng, lưu tài liệu bằng thiết bị render và các tùy chọn đã chỉ định. PDF đầu ra sẽ chứa các trang đã chọn với số trang được tự động thêm.

## Why use Aspose.Page for this conversion?

Tại sao nên sử dụng Aspose.Page cho việc chuyển đổi này?

- **Độ tin cậy** – Xử lý các tính năng phức tạp của XPS mà không mất độ chính xác.  
- **Hiệu suất** – Xử lý dựa trên luồng tránh việc tải toàn bộ tệp vào bộ nhớ.  
- **Linh hoạt** – Kiểm soát chi tiết chất lượng hình ảnh, nén và đánh số trang.  
- **Đa nền tảng** – Hoạt động trên Windows, Linux và macOS với .NET Core.

## Common Issues and Solutions

Các vấn đề thường gặp và giải pháp

| Vấn đề | Giải pháp |
|-------|----------|
| **PDF đầu ra trống** | Xác minh rằng đường dẫn tệp XPS là đúng và tệp không bị hỏng. |
| **Số trang không hiển thị** | Đảm bảo `PageNumbers` được đặt đúng chỉ số trang dựa trên zero (ví dụ, `new int[] {1,2,6}`). |
| **Hình ảnh chất lượng thấp** | Tăng `JpegQualityLevel` và chọn `PdfImageCompression.Jpeg`. |
| **Các tệp XPS lớn gây áp lực bộ nhớ** | Xử lý XPS thành các phần nhỏ hơn hoặc tăng giới hạn bộ nhớ của ứng dụng. |

## Frequently Asked Questions

Câu hỏi thường gặp

### Q1: Tôi có thể gộp nhiều tệp XPS thành một PDF duy nhất không?

A1: Có, bạn có thể. Chỉ cần điều chỉnh tham số `PageNumbers` trong `PdfSaveOptions` để bao gồm các trang mong muốn từ các tệp XPS khác nhau, hoặc tải từng XPS theo thứ tự và gọi `document.Save` trên cùng một `PdfDevice`.

### Q2: Có giấy phép tạm thời cho Aspose.Page cho .NET không?

A2: Có, bạn có thể nhận giấy phép tạm thời [here](https://purchase.aspose.com/temporary-license/) để thử nghiệm.

### Q3: Có giới hạn nào về kích thước tệp khi sử dụng Aspose.Page để chuyển đổi tài liệu không?

A3: Aspose.Page cho .NET không áp đặt giới hạn nghiêm ngặt về kích thước tệp, nhưng hiệu suất tối ưu đạt được với các tệp có kích thước hợp lý. Đối với các tài liệu XPS rất lớn, hãy cân nhắc xử lý chúng bằng luồng để giảm tiêu thụ bộ nhớ.

### Q4: Tôi có thể tùy chỉnh thêm PDF đầu ra, chẳng hạn thêm watermark hoặc chú thích không?

A4: Có, Aspose.Page cho .NET cung cấp các tính năng phong phú cho việc thao tác PDF. Sau khi chuyển đổi, bạn có thể sử dụng thư viện Aspose.PDF để thêm watermark, chú thích hoặc các cải tiến khác.

### Q5: Aspose.Page cho .NET có hỗ trợ phát triển đa nền tảng không?

A5: Có, Aspose.Page cho .NET được thiết kế để hoạt động liền mạch trên nhiều nền tảng, bao gồm Windows, Linux và macOS, khi sử dụng với .NET Core hoặc .NET 5/6.

---

**Cập nhật lần cuối:** 2026-01-20  
**Được kiểm tra với:** Aspose.Page 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}