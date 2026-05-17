---
date: 2026-02-25
description: Học cách tạo tài liệu XPS và áp dụng gradient tuyến tính với Aspose.Page
  cho .NET. Thực hiện theo hướng dẫn từng bước của chúng tôi để lưu tệp XPS.
linktitle: Add Vertical Gradient to XPS
second_title: Aspose.Page .NET API
title: Tạo tài liệu XPS với gradient dọc bằng Aspose.Page
url: /vi/net/gradient-fills/add-vertical-gradient-to-xps/
weight: 15
---

 sure to keep all markdown formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Thêm Gradient Dọc vào XPS với Aspose.Page cho .NET

## Giới thiệu

Trong hướng dẫn này, bạn sẽ **tạo tài liệu XPS** có gradient dọc mượt mà. Thêm gradient là cách phổ biến để làm cho các tệp XPS trông chuyên nghiệp hơn—hoàn hảo cho báo cáo, brochure, hoặc bất kỳ đồ họa có thể in nào. Chúng tôi sẽ hướng dẫn từng bước, từ thiết lập dự án đến lưu tệp XPS cuối cùng, để bạn có thể nhanh chóng áp dụng gradient tuyến tính cho bất kỳ đường nào.

## Câu trả lời nhanh
- **Hướng dẫn này đề cập đến gì?** Thêm gradient tuyến tính dọc vào một đường trong tài liệu XPS.  
- **Thư viện nào được yêu cầu?** Aspose.Page cho .NET.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút cho ví dụ cơ bản.  
- **Tôi có thể lưu kết quả dưới dạng tệp XPS không?** Có, phương thức `Save` ghi tệp vào ổ đĩa.

## Gradient dọc trong XPS là gì?

Gradient dọc là sự chuyển đổi màu sắc chạy từ phía trên của một hình dạng xuống phía dưới. Trong XPS, điều này được thực hiện bằng **brush gradient tuyến tính** xác định các điểm bắt đầu và kết thúc, cùng với một tập hợp các điểm dừng gradient kiểm soát màu tại các vị trí cụ thể.

## Tại sao nên sử dụng Aspose.Page để tạo tài liệu XPS với gradient?

- **Tích hợp .NET đầy đủ** – hoạt động với .NET Framework, .NET Core và .NET 5/6+.  
- **Không phụ thuộc bên ngoài** – mọi việc render được thư viện xử lý.  
- **Độ trung thực cao** – gradient được render chính xác như đã định nghĩa, phù hợp với chuẩn XPS.  
- **Dễ bảo trì** – mô hình đối tượng rõ ràng cho các đường, brush và màu.

## Yêu cầu trước

- Thư viện Aspose.Page cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Page cho .NET trong môi trường phát triển. Bạn có thể tải xuống [tại đây](https://releases.aspose.com/page/net/).
- Môi trường phát triển: Thiết lập môi trường phát triển .NET với IDE ưa thích, chẳng hạn Visual Studio.

Bây giờ mọi thứ đã sẵn sàng, hãy bắt đầu vào mã.

## Nhập không gian tên

Trong ứng dụng .NET của bạn, bao gồm các không gian tên cần thiết để truy cập các lớp và phương thức của Aspose.Page.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

## Bước 1: Thiết lập Thư mục Tài liệu của Bạn

Xác định thư mục nơi tệp XPS được tạo sẽ được lưu.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Bước 2: Tạo Tài liệu XPS Mới

Khởi tạo một tài liệu XPS mới mà sau này chúng ta sẽ điền vào một đường có gradient.

```csharp
// ExStart:4
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Bước 3: Định nghĩa các điểm dừng Gradient

Các điểm dừng gradient xác định màu sắc và vị trí của chúng dọc theo đường gradient. Ở đây chúng ta tạo năm điểm dừng để tạo ra chuyển đổi dọc mượt mà.

```csharp
// ExStart:5
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 12, 0), 0f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 154, 0), 0.359375f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 56, 0), 0.424805f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(253, 255, 229, 0), 0.879883f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(252, 255, 255, 234), 1f));
// ExEnd:5
```

## Bước 4: Tạo Đường với Gradient

Chúng ta vẽ một đường dạng hình chữ nhật và áp dụng **brush gradient tuyến tính** chạy dọc từ điểm (10, 110) đến điểm (10, 200). Brush nhận các điểm dừng gradient đã định nghĩa trước.

```csharp
// ExStart:6
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,110 L 228,110 228,200 10,200"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 110f), new PointF(10f, 200f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Bước 5: Lưu Tài liệu XPS Kết quả

Cuối cùng, ghi tài liệu XPS ra đĩa. Bước **lưu tệp XPS** này tạo ra `AddVerticalGradient_outXPS.xps` trong thư mục bạn đã chỉ định.

```csharp
// ExStart:7
doc.Save(dataDir + "AddVerticalGradient_outXPS.xps");
// ExEnd:7
```

**Mẹo chuyên nghiệp:** Kiểm tra kết quả bằng cách mở tệp XPS trong Windows XPS Viewer hoặc bất kỳ trình xem bên thứ ba nào để đảm bảo gradient hiển thị đúng như mong đợi.

## Các vấn đề thường gặp & Khắc phục

| Triệu chứng | Nguyên nhân có thể | Cách khắc phục |
|------------|-------------------|----------------|
| Gradient hiển thị thành màu đồng nhất | Các điểm dừng gradient chưa được thêm vào brush | Đảm bảo `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` được thực thi. |
| Không tìm thấy tệp khi lưu | `dataDir` trỏ tới thư mục không tồn tại | Tạo thư mục trước hoặc sử dụng đường dẫn tuyệt đối. |
| Màu sắc hiển thị khác | Giá trị màu sử dụng thứ tự ARGB; kiểm tra lại thứ tự kênh | Sử dụng `CreateColor(alpha, red, green, blue)` một cách đúng. |

## Câu hỏi thường gặp

**Q: Aspose.Page có tương thích với Visual Studio 2019 không?**  
A: Có, Aspose.Page tương thích với Visual Studio 2019. Đảm bảo bạn đã cài đặt phiên bản thư viện đúng.

**Q: Tôi có thể sử dụng Aspose.Page cho dự án thương mại không?**  
A: Có, Aspose.Page có thể được sử dụng cho dự án thương mại. Truy cập [tại đây](https://purchase.aspose.com/buy) để khám phá các tùy chọn giấy phép.

**Q: Có bản dùng thử miễn phí không?**  
A: Có, bạn có thể nhận bản dùng thử miễn phí của Aspose.Page [tại đây](https://releases.aspose.com/).

**Q: Tôi có thể tìm tài liệu Aspose.Page ở đâu?**  
A: Tài liệu có sẵn [tại đây](https://reference.aspose.com/page/net/).

**Q: Làm sao tôi có thể nhận hỗ trợ hoặc đặt câu hỏi?**  
A: Truy cập [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để được cộng đồng hỗ trợ.

## Kết luận

Bây giờ bạn đã biết cách **tạo tài liệu XPS**, **áp dụng gradient tuyến tính**, và **lưu tệp XPS** bằng Aspose.Page cho .NET. Cách tiếp cận này cho phép bạn kiểm soát hoàn toàn phong cách hình ảnh trong đầu ra XPS, giúp tài liệu có thể in của bạn nổi bật.

---  

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.Page for .NET 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}