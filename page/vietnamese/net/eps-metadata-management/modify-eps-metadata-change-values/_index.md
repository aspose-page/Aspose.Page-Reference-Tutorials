---
title: Thay đổi giá trị bằng Aspose.Page cho .NET
linktitle: Thay đổi giá trị
second_title: API Aspose.Page .NET
description: Thao tác thành thạo tệp EPS với Aspose.Page cho .NET. Thay đổi giá trị siêu dữ liệu XMP một cách dễ dàng.
type: docs
weight: 17
url: /vi/net/eps-metadata-management/modify-eps-metadata-change-values/
---
## Giới thiệu

Trong thế giới xử lý tài liệu năng động, Aspose.Page for .NET nổi bật như một công cụ mạnh mẽ, cung cấp cho các nhà phát triển khả năng thao tác các tệp EPS một cách dễ dàng. Trong hướng dẫn này, chúng ta sẽ đi sâu vào quá trình thay đổi giá trị trong tệp EPS bằng Aspose.Page cho .NET. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay người mới bắt đầu tò mò, hướng dẫn từng bước này sẽ trang bị cho bạn những kỹ năng cần thiết để sửa đổi siêu dữ liệu XMP trong tệp EPS của bạn một cách hiệu quả.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

### 1. Aspose.Page cho Thư viện .NET

Đảm bảo rằng bạn đã cài đặt thư viện Aspose.Page for .NET trong môi trường phát triển của mình. Nếu không, bạn có thể tải xuống[đây](https://releases.aspose.com/page/net/).

### 2. Thư mục tài liệu

Thiết lập một thư mục cho tài liệu của bạn. Đây sẽ là vị trí lưu trữ các tệp EPS của bạn.

Bây giờ chúng ta đã sắp xếp các điều kiện tiên quyết, hãy chuyển sang các bước quan trọng tiếp theo.

## Nhập không gian tên

Trong bất kỳ dự án .NET nào, điều cần thiết là nhập các vùng tên cần thiết để sử dụng các chức năng của Aspose.Page. Đây là cách bạn có thể làm điều đó:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Bước 1: Khởi tạo luồng đầu vào tệp EPS

```csharp
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";
// Khởi tạo luồng đầu vào tệp EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "get_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
```

## Bước 2: Tạo phiên bản PsDocument từ luồng

```csharp
//Tạo phiên bản PsDocument từ luồng
PsDocument document = new PsDocument(psStream);
```

Bây giờ chúng ta đã chuẩn bị sẵn sàng, hãy chuyển sang phần cốt lõi của hướng dẫn - thay đổi giá trị siêu dữ liệu XMP trong tệp EPS.

## Bước 3: Nhận siêu dữ liệu XMP

```csharp
// Nhận siêu dữ liệu XMP. Nếu tệp EPS không chứa siêu dữ liệu XMP, chúng tôi sẽ nhận được tệp mới chứa các giá trị từ nhận xét siêu dữ liệu PS (%%Creator, %%CreatDate, %%Title, v.v.)
XmpMetadata xmp = document.GetXmpMetadata();
```

## Bước 4: Sửa đổi giá trị siêu dữ liệu XMP

Bây giờ, hãy thay đổi một số giá trị chính trong siêu dữ liệu XMP:

### Bước 4.1: Thay đổi giá trị ModifyDate

```csharp
// Thay đổi giá trị ModifyDate
DateTime now = DateTime.UtcNow;
xmp["xmp:ModifyDate"] = now;
```

### Bước 4.2: Thay đổi giá trị Creator

```csharp
// Thay đổi giá trị của Người tạo
XmpValue value = new XmpValue("Aspose.Page");
xmp.Add("dc:creator", value);
```

### Bước 4.3: Thay đổi giá trị Tiêu đề

```csharp
// Thay đổi giá trị Tiêu đề
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.Add("dc:title", value);
```

Sau khi thực hiện những thay đổi này, hãy chuyển sang bước cuối cùng - lưu tệp EPS đã sửa đổi.

## Bước 5: Lưu tệp EPS với siêu dữ liệu XMP đã thay đổi

### Bước 5.1: Tạo luồng đầu ra

```csharp
// Tạo luồng đầu ra
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "change_values_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
```

### Bước 5.2: Lưu file EPS

```csharp
// Lưu tập tin EPS
document.Save(outPsStream);
```

Cuối cùng, đóng luồng đầu vào:

```csharp
finally
{
    psStream.Close();
}
```

Chúc mừng! Bạn đã sửa đổi thành công các giá trị siêu dữ liệu XMP trong tệp EPS bằng Aspose.Page cho .NET.

## Phần kết luận

Trong hướng dẫn này, chúng tôi đã khám phá quy trình thay đổi giá trị liền mạch trong tệp EPS bằng cách sử dụng Aspose.Page cho .NET. Với tư cách là nhà phát triển, giờ đây bạn có thể tùy ý sử dụng một công cụ mạnh mẽ để thao tác tài liệu hiệu quả.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng Aspose.Page cho .NET với các định dạng tệp khác không?

Câu trả lời 1: Aspose.Page chủ yếu tập trung vào thao tác với tệp EPS. Đối với các định dạng khác, hãy khám phá nhiều loại sản phẩm đa dạng của Aspose.

### Q2: Có phiên bản dùng thử không?

 Câu trả lời 2: Có, bạn có thể dùng thử Aspose.Page cho .NET với bản dùng thử miễn phí có sẵn[đây](https://releases.aspose.com/).

### Câu 3: Tôi có thể tìm tài liệu chi tiết ở đâu?

 A3: Có thể tìm thấy tài liệu toàn diện[đây](https://reference.aspose.com/page/net/).

### Câu hỏi 4: Làm cách nào để có được giấy phép tạm thời?

 A4: Bạn có thể nhận được giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/).

### Câu hỏi 5: Tôi có thể mua Aspose.Page cho .NET không?

 A5: Chắc chắn rồi! Truy cập trang mua hàng[đây](https://purchase.aspose.com/buy) cho các tùy chọn cấp phép.