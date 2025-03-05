---
title: Thay đổi giá trị được đặt tên bằng Aspose.Page cho .NET
linktitle: Thay đổi giá trị được đặt tên
second_title: API Aspose.Page .NET
description: Tìm hiểu cách thay đổi giá trị được đặt tên trong tệp EPS bằng Aspose.Page cho .NET. Tùy chỉnh siêu dữ liệu XMP dễ dàng để xử lý tài liệu phù hợp.
type: docs
weight: 16
url: /vi/net/eps-metadata-management/modify-eps-metadata-change-named-value/
---
## Giới thiệu

Trong thế giới xử lý tài liệu, Aspose.Page for .NET nổi bật như một công cụ mạnh mẽ để thao tác với các tệp EPS. Một trong những chức năng chính mà nó cung cấp là khả năng thay đổi các giá trị được đặt tên trong siêu dữ liệu XMP. Hướng dẫn này sẽ hướng dẫn bạn quy trình thay đổi giá trị được đặt tên bằng Aspose.Page cho .NET, cho phép bạn tùy chỉnh các tệp EPS theo nhu cầu cụ thể của mình.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Aspose.Page for .NET: Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Page for .NET. Nếu không, bạn có thể tải xuống[đây](https://releases.aspose.com/page/net/).

- Thư mục Tài liệu: Có một thư mục được chỉ định cho các tệp EPS của bạn, nơi bạn có thể thực hiện các thay đổi giá trị được đặt tên.

## Nhập không gian tên

Trong dự án .NET của bạn, bạn cần nhập các vùng tên cần thiết để truy cập chức năng do Aspose.Page cung cấp. Thêm các không gian tên sau vào mã của bạn:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

Bây giờ, hãy chia mã thành nhiều bước để hiểu toàn diện:

## Bước 1: Khởi tạo luồng đầu vào tệp EPS

```csharp
// Bắt đầu:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
// ExEnd:1
```

Trong bước này, chúng tôi thiết lập luồng đầu vào cho tệp EPS mà bạn muốn sửa đổi. Đảm bảo thay thế "Thư mục tài liệu của bạn" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Nhận siêu dữ liệu XMP

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

Truy xuất siêu dữ liệu XMP hiện có từ tệp EPS. Nếu tệp EPS không chứa siêu dữ liệu XMP thì một tệp mới sẽ được tạo với các giá trị từ nhận xét siêu dữ liệu PS.

## Bước 3: Thay đổi giá trị siêu dữ liệu XMP

```csharp
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
xmp.SetNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

Ở đây, chúng tôi chứng minh việc thay đổi hai giá trị được đặt tên trong cấu trúc "xmpTPg:MaxPageSize". Bạn có thể tùy chỉnh điều này theo yêu cầu cụ thể của bạn.

## Bước 4: Lưu tệp EPS với siêu dữ liệu XMP đã thay đổi

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

Lưu tệp EPS đã sửa đổi vào luồng đầu ra. Bây giờ tệp sẽ phản ánh những thay đổi được thực hiện đối với siêu dữ liệu XMP.

## Phần kết luận

Với hướng dẫn này, bạn đã học cách tận dụng Aspose.Page cho .NET để thay đổi các giá trị được đặt tên trong siêu dữ liệu XMP trong tệp EPS. Chức năng này mở ra vô số khả năng tùy chỉnh và điều chỉnh tài liệu của bạn để đáp ứng các yêu cầu cụ thể.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng Aspose.Page cho .NET với các định dạng tài liệu khác không?

Câu trả lời 1: Có, Aspose.Page hỗ trợ nhiều định dạng tài liệu khác nhau, bao gồm EPS, XPS và PDF.

### Câu hỏi 2: Có phiên bản dùng thử cho Aspose.Page cho .NET không?

 Câu trả lời 2: Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/).

### Câu hỏi 3: Tôi có thể tìm thêm tài liệu về Aspose.Page cho .NET ở đâu?

 A3: Tham khảo tài liệu[đây](https://reference.aspose.com/page/net/).

### Câu hỏi 4: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page cho .NET?

 A4: Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).

### Câu hỏi 5: Aspose.Page có những tùy chọn hỗ trợ nào dành cho người dùng .NET?

 A5: Truy cập diễn đàn cộng đồng[đây](https://forum.aspose.com/c/page/39) để được hỗ trợ và thảo luận.