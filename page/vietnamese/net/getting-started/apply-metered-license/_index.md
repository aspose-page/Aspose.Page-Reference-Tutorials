---
title: Áp dụng Giấy phép Metered với Aspose.Page cho .NET
linktitle: Áp dụng giấy phép đo
second_title: API Aspose.Page .NET
description: Khám phá sự tích hợp liền mạch của Aspose.Page cho .NET với hướng dẫn từng bước này về cách áp dụng giấy phép có đồng hồ đo. Tối ưu hóa việc xử lý tài liệu một cách dễ dàng.
type: docs
weight: 10
url: /vi/net/getting-started/apply-metered-license/
---
## Giới thiệu

Mở khóa toàn bộ tiềm năng của Aspose.Page cho .NET bằng cách áp dụng giấy phép đồng hồ đo. Hướng dẫn này sẽ hướng dẫn bạn qua quá trình thiết lập và áp dụng giấy phép đồng hồ đo, đảm bảo việc sử dụng trơn tru và tối ưu hóa thư viện .NET mạnh mẽ này.

## Điều kiện tiên quyết

Trước khi đi sâu vào các bước, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

-  Giấy phép Aspose.Page hợp lệ cho .NET: Bạn có thể lấy nó từ[mua hàng.aspose.com](https://purchase.aspose.com/buy).
-  Đã cài đặt thư viện Aspose.Page: Tham khảo[tài liệu](https://reference.aspose.com/page/net/) để biết hướng dẫn cài đặt.
- Môi trường phát triển .NET: Đảm bảo rằng bạn đã thiết lập môi trường .NET đang hoạt động trên máy của mình.

## Nhập không gian tên

Trong dự án .NET của bạn, hãy nhập các không gian tên cần thiết để truy cập các chức năng của Aspose.Page:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Bước 1: Đặt khóa công khai và khóa riêng tư được đo lường

 Khởi tạo`Aspose.Page.Metered` lớp và đặt khóa công khai và khóa riêng. Thay thế`<type public key here>` Và`<type private key here>` với các phím thực tế của bạn.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Bước 2: Tải tệp EPS và tạo tài liệu

 Chỉ định đường dẫn đến tệp EPS của bạn và tạo luồng để đọc nội dung của nó. Sau đó, tạo một thể hiện của`PsDocument` lớp từ luồng.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Bước 3: Chuyển đổi hình ảnh EPS sang PNG

 Tạo ra một`ImageDevice` để chuyển đổi tệp EPS thành hình ảnh PNG. Lưu tệp EPS dưới dạng hình ảnh bằng cách sử dụng`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Bước 4: Truy xuất byte hình ảnh

Lấy byte hình ảnh, trong đó mỗi mảng byte đại diện cho một trang. Trong trường hợp này, chúng tôi có một trang.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Bước 5: Lưu byte hình ảnh vào tệp

Lưu byte hình ảnh vào một tệp, đảm bảo chuyển đổi thành công từ EPS sang PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## Bước 6: Xác minh giấy phép đo

Kiểm tra trực quan xem giấy phép đo có được áp dụng thành công hay không. Nếu hình ảnh thu được không chứa thông báo đánh giá màu đỏ thì điều đó cho biết rằng giấy phép đo được áp dụng mà không gặp bất kỳ sự cố nào.

Bây giờ bạn đã sẵn sàng tận dụng toàn bộ khả năng của Aspose.Page cho .NET với giấy phép đồng hồ đo!

## Phần kết luận

Hướng dẫn từng bước này đã trang bị cho bạn kiến thức để áp dụng liền mạch giấy phép đo lường bằng cách sử dụng Aspose.Page cho .NET. Nâng cao khả năng xử lý tài liệu của bạn và khám phá các tính năng phong phú được cung cấp bởi thư viện mạnh mẽ này.

## Câu hỏi thường gặp

### Câu hỏi 1: Làm cách nào để tôi có được giấy phép đo lường cho Aspose.Page cho .NET?

 A1: Tham quan[mua hàng.aspose.com](https://purchase.aspose.com/buy) để có được giấy phép hợp lệ.

### Câu hỏi 2: Tôi có thể tìm tài liệu về Aspose.Page cho .NET ở đâu?

 A2: Tham khảo[Aspose.Page .NET](https://reference.aspose.com/page/net/) để có tài liệu đầy đủ.

### Câu 3: Có diễn đàn nào để thảo luận và hỗ trợ Aspose.Page không?

 A3: Vâng, hãy ghé thăm[diễn đàn](https://forum.aspose.com/c/page/39) để hòa nhập với cộng đồng và tìm kiếm sự giúp đỡ.

### Câu hỏi 4: Tôi có thể dùng thử Aspose.Page cho .NET trước khi mua không?

 A4: Chắc chắn rồi! Truy cập bản dùng thử miễn phí tại[đây](https://releases.aspose.com/).

### Câu hỏi 5: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page cho .NET?

 A5: Thăm quan[giấy phép tạm thời/](https://purchase.aspose.com/temporary-license/) để có được giấy phép tạm thời.