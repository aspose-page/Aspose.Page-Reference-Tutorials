---
title: Thêm giá trị được đặt tên bằng Aspose.Page
linktitle: Thêm giá trị được đặt tên
second_title: API Aspose.Page .NET
description: Tìm hiểu cách thêm các giá trị được đặt tên vào tệp EPS trong .NET bằng Aspose.Page. Hướng dẫn toàn diện này sẽ hướng dẫn bạn từng bước thực hiện quy trình.
type: docs
weight: 12
url: /vi/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---
## Giới thiệu

Trong lĩnh vực xử lý tài liệu bằng .NET, Aspose.Page nổi bật như một công cụ mạnh mẽ để xử lý các tệp EPS. Aspose.Page trao quyền cho các nhà phát triển thao tác siêu dữ liệu XMP, tạo điều kiện thuận lợi cho các tác vụ như thêm các giá trị được đặt tên. Hướng dẫn này sẽ hướng dẫn bạn quy trình thêm các giá trị được đặt tên vào tệp EPS bằng Aspose.Page theo cách từng bước.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo rằng bạn có sẵn các điều kiện tiên quyết sau:

- Kiến thức cơ bản về ngôn ngữ lập trình C#.
- Một môi trường phát triển tích hợp (IDE) như Visual Studio đã được cài đặt.
-  Aspose.Page cho thư viện .NET. Nếu chưa cài đặt, bạn có thể tải xuống từ[đây](https://releases.aspose.com/page/net/).

## Nhập không gian tên

Đầu tiên, hãy nhập các vùng tên cần thiết vào mã C# của bạn. Các không gian tên này rất quan trọng để truy cập các chức năng do Aspose.Page cung cấp:

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

 Bước đầu tiên liên quan đến việc khởi tạo luồng đầu vào cho tệp EPS. Thay thế`"Your Document Directory"` với đường dẫn đến thư mục tài liệu của bạn:

```csharp
// Bắt đầu:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Bước 2: Nhận siêu dữ liệu XMP

Truy xuất siêu dữ liệu XMP từ tệp EPS. Nếu tệp EPS thiếu siêu dữ liệu XMP thì một tệp mới sẽ được tạo, chứa đầy các giá trị từ nhận xét siêu dữ liệu PS:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Bước 3: Thay đổi giá trị siêu dữ liệu XMP

Bây giờ, hãy thực hiện các thay đổi đối với siêu dữ liệu XMP. Trong ví dụ này, chúng tôi sẽ thêm giá trị được đặt tên vào cấu trúc "xmpTPg:MaxPageSize":

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Bước 4: Lưu tệp EPS với siêu dữ liệu XMP đã thay đổi

Lưu tệp EPS với siêu dữ liệu XMP được cập nhật. Tạo luồng đầu ra và lưu tệp EPS đã sửa đổi:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Phần kết luận

Chúc mừng! Bạn đã thêm thành công giá trị được đặt tên vào tệp EPS bằng Aspose.Page trong .NET. Hướng dẫn này đã hướng dẫn bạn qua các bước thiết yếu, thể hiện tính đơn giản và hiệu quả của Aspose.Page trong thao tác tài liệu.

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.Page có tương thích với các phiên bản tệp EPS khác nhau không?

Câu trả lời 1: Aspose.Page hỗ trợ nhiều phiên bản tệp EPS khác nhau, đảm bảo khả năng tương thích với nhiều loại tài liệu.

### Câu 2: Tôi có thể sử dụng Aspose.Page cho các dự án thương mại không?

 Câu trả lời 2: Có, Aspose.Page có giấy phép thương mại và bạn có thể mua nó[đây](https://purchase.aspose.com/buy).

### Câu hỏi 3: Aspose.Page có bản dùng thử miễn phí không?

 Câu trả lời 3: Có, bạn có thể khám phá Aspose.Page với bản dùng thử miễn phí[đây](https://releases.aspose.com/).

### Câu hỏi 4: Làm cách nào tôi có thể nhận được hỗ trợ hoặc kết nối với cộng đồng Aspose?

 A4: Tham quan[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để nhận được sự hỗ trợ và kết nối với cộng đồng.

### Câu hỏi 5: Giấy phép tạm thời là gì và làm cách nào để có được giấy phép?

 Câu trả lời 5: Nếu bạn cần giấy phép tạm thời cho mục đích thử nghiệm hoặc đánh giá, bạn có thể xin giấy phép[đây](https://purchase.aspose.com/temporary-license/).