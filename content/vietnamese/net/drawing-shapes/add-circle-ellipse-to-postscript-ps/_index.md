---
title: Thêm hình elip hình tròn vào PostScript (PS) bằng Aspose.Page
linktitle: Thêm hình elip hình tròn vào PostScript (PS)
second_title: API Aspose.Page .NET
description: Tìm hiểu cách dễ dàng thêm hình elip hình tròn vào tài liệu PostScript (PS) bằng Aspose.Page cho .NET. Hãy làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch.
type: docs
weight: 10
url: /vi/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---
## Giới thiệu

Chào mừng bạn đến với hướng dẫn toàn diện này về cách thêm hình elip hình tròn vào tài liệu PostScript (PS) bằng Aspose.Page cho .NET. Aspose.Page là một thư viện mạnh mẽ cho phép các nhà phát triển làm việc liền mạch với PostScript và các định dạng tài liệu khác. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn bạn quy trình kết hợp các hình elip hình tròn vào tài liệu PS của bạn một cách dễ dàng.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

1.  Aspose.Page for .NET Library: Tải xuống và cài đặt thư viện Aspose.Page cho .NET từ[đây](https://releases.aspose.com/page/net/).

2. Môi trường phát triển: Đảm bảo bạn đã thiết lập môi trường phát triển .NET đang hoạt động trên máy của mình.

Bây giờ, hãy bắt đầu với hướng dẫn từng bước.

## Nhập không gian tên

Ở bước đầu tiên, bạn cần nhập các không gian tên cần thiết để cung cấp chức năng Aspose.Page trong mã của bạn.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Bây giờ, hãy chia nhỏ ví dụ được cung cấp thành nhiều bước để hướng dẫn bạn qua quá trình thêm hình elip hình tròn vào tài liệu PostScript.

## Bước 1: Đặt thư mục tài liệu

```csharp
// Bắt đầu:1
// Đường dẫn đến thư mục tài liệu.
string dataDir = "Your Document Directory";
```

Đảm bảo thay thế "Thư mục tài liệu của bạn" bằng đường dẫn thực tế đến thư mục tài liệu của bạn.

## Bước 2: Tạo luồng đầu ra cho tài liệu PostScript

```csharp
//Tạo luồng đầu ra cho tài liệu PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Ở đây, FileStream được tạo để ghi tài liệu PostScript và chế độ tệp được đặt để tạo tệp mới.

## Bước 3: Tạo tùy chọn lưu và tài liệu PS

```csharp
//Tạo tùy chọn lưu với khổ A4
PsSaveOptions options = new PsSaveOptions();

// Tạo tài liệu PS 1 trang mới
PsDocument document = new PsDocument(outPsStream, options, false);
```

Bước này bao gồm việc tạo các tùy chọn lưu với kích thước A4 và khởi tạo Tài liệu PS 1 trang mới.

## Bước 4: Tạo đường dẫn đồ họa cho hình elip đầu tiên

```csharp
//Tạo đường dẫn đồ họa từ hình elip đầu tiên
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

Đường dẫn đồ họa được tạo cho hình elip đầu tiên, xác định vị trí và kích thước của nó.

## Bước 5: Đặt màu và tô màu cho hình elip

```csharp
//Đặt sơn
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Điền vào hình elip
document.Fill(path);
```

Ở đây, lớp sơn đã được thiết lập và hình elip đầu tiên được tô bằng màu được chỉ định.

## Bước 6: Tạo đường dẫn đồ họa cho hình elip thứ hai

```csharp
//Tạo đường dẫn đồ họa từ hình elip thứ hai
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Tương tự, một đường dẫn đồ họa được tạo cho hình elip thứ hai, xác định vị trí và kích thước của nó.

## Bước 7: Đặt nét và vẽ hình elip

```csharp
//Đặt nét
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Stroke (phác thảo) hình elip
document.Draw(path);
```

Trong bước này, nét vẽ được thiết lập và hình elip thứ hai được phác thảo với màu sắc và độ dày đường kẻ được chỉ định.

## Bước 8: Đóng trang hiện tại và lưu tài liệu

```csharp
//Đóng trang hiện tại
document.ClosePage();

//Lưu tài liệu
document.Save();
```

Cuối cùng, trang hiện tại được đóng lại và toàn bộ tài liệu được lưu, hoàn tất quá trình.

## Phần kết luận

Chúc mừng! Bạn đã học thành công cách thêm hình elip hình tròn vào tài liệu PostScript bằng Aspose.Page cho .NET. Hướng dẫn này cung cấp hướng dẫn chi tiết từng bước để giúp bạn tích hợp chức năng này vào các dự án của mình một cách liền mạch.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng Aspose.Page cho .NET với các định dạng tài liệu khác không?

 Câu trả lời 1: Aspose.Page chủ yếu tập trung vào PostScript, nhưng Aspose cung cấp các thư viện khác cho các định dạng tài liệu khác nhau. Kiểm tra[Cung cấp tài liệu](https://reference.aspose.com/page/net/) để biết thêm chi tiết.

### Câu hỏi 2: Tôi có thể tìm thêm hỗ trợ và thảo luận cộng đồng ở đâu?

 A2: Tham quan[Diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để thảo luận và hỗ trợ cộng đồng.

### Câu hỏi 3: Có bản dùng thử miễn phí dành cho Aspose.Page dành cho .NET không?

 A3: Có, bạn có thể truy cập[dùng thử miễn phí](https://releases.aspose.com/)để khám phá các tính năng của Aspose.Page cho .NET.

### Câu hỏi 4: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.Page?

 A4: Xin giấy phép tạm thời[đây](https://purchase.aspose.com/temporary-license/) nhằm mục đích kiểm tra và đánh giá.

### Câu hỏi 5: Tôi có thể mua Aspose.Page cho .NET ở đâu?

 Câu trả lời 5: Mua Aspose.Page cho .NET từ[trang mua](https://purchase.aspose.com/buy).