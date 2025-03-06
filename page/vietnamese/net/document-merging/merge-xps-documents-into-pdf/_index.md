---
title: Hợp nhất tài liệu XPS thành PDF bằng Aspose.Page cho .NET
linktitle: Hợp nhất tài liệu XPS thành PDF
second_title: API Aspose.Page .NET
description: Dễ dàng hợp nhất các tài liệu XPS thành các tệp PDF chất lượng cao bằng Aspose.Page cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để có trải nghiệm chuyển đổi tài liệu suôn sẻ.
weight: 11
url: /vi/net/document-merging/merge-xps-documents-into-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hợp nhất tài liệu XPS thành PDF bằng Aspose.Page cho .NET

## Giới thiệu

Trong bối cảnh xử lý tài liệu ngày càng phát triển, Aspose.Page for .NET nổi lên như một công cụ mạnh mẽ để hợp nhất liền mạch các tài liệu XPS thành định dạng PDF. Hướng dẫn này sẽ hướng dẫn bạn thực hiện quy trình, chia nhỏ từng bước để đảm bảo thực hiện suôn sẻ và hiệu quả.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.Page for .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Page. Bạn có thể tải nó xuống từ[đây](https://releases.aspose.com/page/net/).

- Tệp tài liệu: Có tài liệu XPS (`input.xps`) sẵn sàng trong thư mục được chỉ định của bạn.

## Nhập không gian tên

Trong dự án .NET của bạn, hãy bao gồm các vùng tên cần thiết để làm việc với Aspose.Page:

```csharp
using Aspose.Page.XPS;
```

Bước này đảm bảo rằng bạn có quyền truy cập vào các lớp và phương thức cần thiết để chuyển đổi tài liệu.

## Bước 1: Khởi tạo luồng

```csharp
// Bắt đầu:3
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";
// Khởi tạo luồng đầu ra PDF
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Khởi tạo luồng đầu vào XPS
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
{
    // ...
}
// ExEnd:3
```

Bước này liên quan đến việc thiết lập luồng đầu vào và đầu ra cho tệp XPS và PDF. Đảm bảo sử dụng đúng đường dẫn và tên tệp.

## Bước 2: Tải tài liệu XPS

```csharp
// ExStart:4
// Tải tài liệu XPS dưới dạng luồng
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
// hoặc tải tài liệu XPS trực tiếp từ tệp. Khi đó không cần xpsStream.
//Tài liệu XpsDocument = new XpsDocument(inputFileName, new XpsLoadOptions());
// ExEnd:4
```

 Ở đây, chúng tôi tải tài liệu XPS vào`XpsDocument` đối tượng, chuẩn bị cho quá trình xử lý tiếp theo.

## Bước 3: Khởi tạo tùy chọn lưu

```csharp
// ExStart:5
// Khởi tạo đối tượng tùy chọn với các tham số cần thiết.
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
// ExEnd:5
```

 Tùy chỉnh`PdfSaveOptions` đối tượng dựa trên sở thích của bạn, chỉ định các tham số như nén ảnh, nén văn bản và số trang.

## Bước 4: Tạo thiết bị kết xuất

```csharp
// ExStart:6
// Tạo thiết bị kết xuất cho định dạng PDF
PdfDevice device = new PdfDevice(pdfStream);
// ExEnd:6
```

 Các`PdfDevice` là công cụ chịu trách nhiệm hiển thị tài liệu XPS sang định dạng PDF.

## Bước 5: Lưu tài liệu

```csharp
// ExStart:7
document.Save(device, options);
// ExEnd:7
```

Cuối cùng, lưu tài liệu bằng thiết bị kết xuất và các tùy chọn đã chỉ định.

## Phần kết luận

Chúc mừng! Bạn đã hợp nhất thành công các tài liệu XPS thành PDF bằng Aspose.Page for .NET. Quá trình liền mạch này đảm bảo duy trì chất lượng và định dạng tài liệu.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể hợp nhất nhiều tệp XPS thành một tệp PDF không?

 A1: Có, bạn có thể. Đơn giản chỉ cần điều chỉnh`PageNumbers` tham số trong`PdfSaveOptions` để bao gồm các trang mong muốn từ các tệp XPS khác nhau.

### Câu hỏi 2: Giấy phép tạm thời có sẵn cho Aspose.Page cho .NET không?

 A2: Có, bạn có thể xin giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/) cho mục đích thử nghiệm.

### Câu hỏi 3: Có bất kỳ hạn chế nào về kích thước tệp khi sử dụng Aspose.Page để chuyển đổi tài liệu không?

Câu trả lời 3: Aspose.Page for .NET không áp đặt các giới hạn nghiêm ngặt về kích thước tệp nhưng đạt được hiệu suất tối ưu với kích thước tệp hợp lý.

### Câu hỏi 4: Tôi có thể tùy chỉnh thêm tệp PDF đầu ra, chẳng hạn như thêm hình mờ hoặc chú thích không?

Câu trả lời 4: Có, Aspose.Page for .NET cung cấp các tính năng mở rộng để thao tác với PDF. Kiểm tra tài liệu để biết các tùy chọn tùy chỉnh nâng cao.

### Câu hỏi 5: Aspose.Page cho .NET có hỗ trợ phát triển đa nền tảng không?

Câu trả lời 5: Có, Aspose.Page dành cho .NET được thiết kế để hoạt động trơn tru trên nhiều nền tảng khác nhau.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
