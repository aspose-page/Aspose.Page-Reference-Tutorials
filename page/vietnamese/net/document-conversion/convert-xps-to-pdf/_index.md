---
title: Chuyển đổi XPS sang PDF bằng Aspose.Page cho .NET
linktitle: Chuyển XPS sang PDF
second_title: API Aspose.Page .NET
description: Dễ dàng chuyển đổi XPS sang PDF trong .NET bằng Aspose.Page. Tải xuống thư viện, khám phá tài liệu và dùng thử miễn phí.
weight: 11
url: /vi/net/document-conversion/convert-xps-to-pdf/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chuyển đổi XPS sang PDF bằng Aspose.Page cho .NET

## Giới thiệu

Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình chuyển đổi tài liệu XPS (Đặc tả giấy XML) sang PDF (Định dạng tài liệu di động) bằng cách sử dụng thư viện Aspose.Page cho .NET mạnh mẽ. Aspose.Page for .NET cung cấp một bộ tính năng mạnh mẽ để làm việc với các tệp XPS, cho phép các nhà phát triển chuyển đổi chúng sang định dạng PDF một cách liền mạch với nhiều tùy chọn tùy chỉnh khác nhau.

## Điều kiện tiên quyết

Trước khi chúng ta bắt đầu hành trình chuyển đổi này, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.Page for .NET Library: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Page for .NET trong môi trường phát triển của mình. Bạn có thể tải nó xuống từ[Tài liệu Aspose.Page](https://reference.aspose.com/page/net/).

- Môi trường phát triển: Thiết lập môi trường phát triển .NET với Visual Studio hoặc bất kỳ IDE tương thích nào khác.

- Tài liệu XPS: Chuẩn bị tài liệu XPS mà bạn muốn chuyển đổi sang PDF. Đây có thể là tệp XPS mẫu của bạn được lưu trữ trong một thư mục được chỉ định.

## Nhập không gian tên

Trước khi đi sâu vào mã, hãy nhập các không gian tên cần thiết để làm cho các chức năng Aspose.Page cho .NET có thể truy cập được trong mã của chúng tôi:

```csharp
using Aspose.Page.XPS;
```

## Bước 1: Khởi tạo thư mục tài liệu

```csharp
string dataDir = "Your Document Directory";
```

Thay thế "Thư mục tài liệu của bạn" bằng đường dẫn đến thư mục chứa tài liệu XPS của bạn.

## Bước 2: Khởi tạo luồng PDF và XPS

```csharp
using (System.IO.Stream pdfStream = System.IO.File.Open(dataDir + "XPStoPDF_out.pdf", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
using (System.IO.Stream xpsStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

Mở luồng cho cả tệp PDF đầu ra và tệp XPS đầu vào. Đảm bảo bạn đã đặt đường dẫn tệp thích hợp.

## Bước 3: Tải tài liệu XPS

```csharp
XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
```

Tải tài liệu XPS bằng thư viện Aspose.Page for .NET.

## Bước 4: Khởi tạo tùy chọn lưu PDF

```csharp
PdfSaveOptions options = new PdfSaveOptions()
{
    JpegQualityLevel = 100,
    ImageCompression = PdfImageCompression.Jpeg,
    TextCompression = PdfTextCompression.Flate,
    PageNumbers = new int[] { 1, 2, 6 }
};
```

Thiết lập các tùy chọn lưu PDF, bao gồm các thông số như mức chất lượng JPEG, nén hình ảnh, nén văn bản và số trang cụ thể cần đưa vào.

## Bước 5: Tạo thiết bị kết xuất PDF

```csharp
PdfDevice device = new PdfDevice(pdfStream);
```

Tạo một thiết bị hiển thị cho định dạng PDF bằng thư viện Aspose.Page cho .NET.

## Bước 6: Lưu tài liệu sang PDF

```csharp
document.Save(device, options);
```

Lưu tài liệu XPS thành PDF bằng cách sử dụng các tùy chọn và thiết bị kết xuất được chỉ định.

## Phần kết luận

Chúc mừng! Bạn đã chuyển đổi thành công tài liệu XPS sang PDF bằng Aspose.Page for .NET. Thư viện đa năng này cung cấp cho các nhà phát triển một bộ công cụ mạnh mẽ để xử lý các định dạng tài liệu khác nhau một cách dễ dàng.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể chuyển đổi nhiều tệp XPS thành một tệp PDF bằng Aspose.Page cho .NET không?

Câu trả lời 1: Có, bạn có thể lặp qua nhiều tệp XPS và làm theo các bước tương tự để hợp nhất chúng thành một tệp PDF duy nhất.

### Câu hỏi 2: Có các định dạng đầu ra nào khác được Aspose.Page hỗ trợ cho .NET không?

Câu trả lời 2: Có, Aspose.Page for .NET hỗ trợ nhiều định dạng đầu ra khác nhau, bao gồm TIFF, JPEG, PNG, v.v.

### Câu hỏi 3: Làm cách nào tôi có thể tùy chỉnh giao diện của tài liệu PDF đã chuyển đổi?

Câu trả lời 3: Bạn có thể điều chỉnh các tham số đối tượng tùy chọn, chẳng hạn như nén hình ảnh và nén văn bản, để đạt được giao diện mong muốn.

### Câu hỏi 4: Có phiên bản dùng thử cho Aspose.Page cho .NET không?

 Câu trả lời 4: Có, bạn có thể khám phá các khả năng của Aspose.Page dành cho .NET bằng cách nhận bản dùng thử miễn phí từ[đây](https://releases.aspose.com/).

### Câu hỏi 5: Tôi có thể nhận hỗ trợ cộng đồng cho Aspose.Page cho .NET ở đâu?

 A5: Tham quan[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để thảo luận và hỗ trợ cộng đồng.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
