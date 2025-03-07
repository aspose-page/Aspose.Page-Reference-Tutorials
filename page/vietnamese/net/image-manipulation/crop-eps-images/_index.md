---
title: Cắt hình ảnh EPS bằng Aspose.Page cho .NET
linktitle: Cắt hình ảnh EPS
second_title: API Aspose.Page .NET
description: Khám phá thế giới liền mạch của thao tác hình ảnh EPS trong .NET với Aspose.Page. Cắt và thay đổi kích thước hình ảnh một cách dễ dàng để có kết quả tuyệt đẹp.
weight: 10
url: /vi/net/image-manipulation/crop-eps-images/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cắt hình ảnh EPS bằng Aspose.Page cho .NET

## Giới thiệu

Bạn đang gặp khó khăn với việc thao tác hình ảnh EPS trong các ứng dụng .NET của mình? Đừng tìm đâu xa! Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình cắt xén hình ảnh EPS bằng thư viện Aspose.Page cho .NET mạnh mẽ. Cho dù bạn là nhà phát triển dày dạn kinh nghiệm hay mới bắt đầu, hướng dẫn từng bước này sẽ giúp bạn cắt xén hình ảnh chính xác một cách dễ dàng.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Kiến thức làm việc về phát triển .NET.
-  Đã cài đặt thư viện Aspose.Page cho .NET. Nếu không, bạn có thể tải xuống[đây](https://releases.aspose.com/page/net/).
- Một hình ảnh EPS mẫu (thay thế "input.eps" trong mã bằng tệp thực tế của bạn).

## Nhập không gian tên

Hãy bắt đầu bằng cách nhập các không gian tên cần thiết để mã của chúng ta chạy trơn tru. 

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

Bây giờ, hãy chia hướng dẫn thành nhiều bước.

## Bước 1: Khởi tạo PsDocument

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

 Khởi tạo một`PsDocument` đối tượng với luồng EPS đầu vào.

## Bước 2: Trích xuất hộp giới hạn

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

Truy xuất hộp giới hạn ban đầu của hình ảnh EPS.

## Bước 3: Tạo luồng đầu ra

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Tạo luồng đầu ra cho hình ảnh EPS đã cắt.

## Bước 4: Xác định hộp giới hạn mới

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Xác định một hộp giới hạn mới để cắt xén. Đảm bảo các giá trị mới nằm trong hộp giới hạn ban đầu.

## Bước 5: Cắt và lưu

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Cắt hình ảnh EPS bằng hộp giới hạn mới và lưu nó vào luồng đầu ra.

Lặp lại các bước này cho các trường hợp thay đổi kích thước khác nhau.

## Thay đổi kích thước hình ảnh EPS

### Thay đổi kích thước theo inch

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

Thay đổi kích thước hình ảnh EPS và lưu nó với kích thước được chỉ định tính bằng inch.

### Thay đổi kích thước tính bằng milimét

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

Thay đổi kích thước hình ảnh EPS và lưu nó với kích thước được chỉ định tính bằng milimét.

### Thay đổi kích thước theo phần trăm

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Thay đổi kích thước hình ảnh EPS và lưu nó với kích thước được chỉ định theo tỷ lệ phần trăm.

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách cắt và thay đổi kích thước hình ảnh EPS bằng Aspose.Page cho .NET. Bây giờ, hãy nâng cao khả năng xử lý hình ảnh của bạn và đưa ứng dụng .NET của bạn lên một tầm cao mới.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng Aspose.Page cho .NET với các định dạng hình ảnh khác không?

Câu trả lời 1: Aspose.Page chủ yếu tập trung vào hình ảnh EPS, nhưng Aspose cung cấp nhiều thư viện khác nhau cho các định dạng khác nhau. Kiểm tra tài liệu của họ để biết các định dạng cụ thể.

### Câu hỏi 2: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page cho .NET?

 A2: Tham quan[liên kết này](https://purchase.aspose.com/temporary-license/) để có được giấy phép tạm thời để thử nghiệm.

### Câu hỏi 3: Có bất kỳ hạn chế nào đối với kích thước hình ảnh mà tôi có thể xử lý bằng Aspose.Page cho .NET không?

Câu trả lời 3: Aspose.Page được thiết kế để xử lý các hình ảnh có kích thước khác nhau. Tuy nhiên, hiệu suất có thể thay đổi tùy theo độ phức tạp của hình ảnh.

### Câu hỏi 4: Có diễn đàn cộng đồng nào để thảo luận về Aspose.Page không?

 Câu trả lời 4: Có, bạn có thể tham gia cộng đồng Aspose.Page[đây](https://forum.aspose.com/c/page/39).

### Câu hỏi 5: Tôi có thể tìm tài liệu chi tiết về Aspose.Page cho .NET ở đâu?

 A5: Tham khảo tài liệu[đây](https://reference.aspose.com/page/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
