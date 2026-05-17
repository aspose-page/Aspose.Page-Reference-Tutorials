---
date: 2026-02-25
description: Tìm hiểu cách tạo gradient XPS với độ phủ ngang bằng Aspose.Page cho
  .NET. Nâng cao sức hấp dẫn hình ảnh một cách dễ dàng trong tài liệu của bạn.
linktitle: Add Horizontal Gradient to XPS
second_title: Aspose.Page .NET API
title: 'Tạo Gradient XPS: Đổ ngang với Aspose.Page cho .NET'
url: /vi/net/gradient-fills/add-horizontal-gradient-to-xps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Gradient XPS – Thêm Gradient Ngang vào XPS với Aspose.Page cho .NET

## Giới thiệu

Trong hướng dẫn này, bạn sẽ **tạo gradient XPS** với các màu chuyển dần theo chiều ngang trên các trang của mình. Thêm gradient ngang có thể ngay lập tức làm cho tài liệu XPS trông chuyên nghiệp và hấp dẫn hơn, đặc biệt đối với báo cáo, brochure hoặc bất kỳ đầu ra nào giàu hình ảnh. Chúng tôi sẽ hướng dẫn toàn bộ quy trình sử dụng Aspose.Page cho .NET, từ việc thiết lập môi trường đến lưu tệp XPS cuối cùng.

## Câu trả lời nhanh
- **Hướng dẫn này đề cập đến gì?** Thêm gradient ngang vào tài liệu XPS bằng Aspose.Page cho .NET.  
- **Thư viện nào cần thiết?** Aspose.Page cho .NET (bất kỳ phiên bản mới nào).  
- **Có cần giấy phép không?** Bản dùng thử hoạt động cho việc phát triển; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Thời gian triển khai khoảng bao lâu?** Khoảng 5–10 phút cho một gradient cơ bản.  
- **Có thể thay đổi hướng gradient không?** Có – chỉ cần chỉnh điểm bắt đầu/kết thúc của `LinearGradientBrush`.

## Cách tạo gradient XPS với Aspose.Page cho .NET

Dưới đây là hướng dẫn từng bước giải thích **tại sao** mỗi dòng mã tồn tại, không chỉ **cái gì** nó làm. Bạn có thể thực hiện theo trong Visual Studio hoặc trình soạn thảo .NET yêu thích.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã chuẩn bị các yêu cầu sau:

1. Thư viện Aspose.Page cho .NET: Đảm bảo bạn đã cài đặt thư viện Aspose.Page cho .NET trong môi trường phát triển. Bạn có thể tải xuống từ [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).

2. Môi trường phát triển: Thiết lập môi trường phát triển phù hợp, bao gồm một trình soạn thảo mã như Visual Studio.

## Nhập các namespace

Bắt đầu bằng cách nhập các namespace cần thiết vào dự án của bạn. Các namespace này là cần thiết để làm việc với Aspose.Page cho .NET:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Collections.Generic;
using System.Drawing;
```

Bây giờ, hãy phân tách ví dụ được cung cấp thành nhiều bước.

## Bước 1: Đặt đường dẫn thư mục tài liệu

```csharp
// ExStart:3
// The path to the documents directory.
string dataDir = "Your Document Directory";
// ExEnd:3
```

## Bước 2: Tạo tài liệu XPS mới

```csharp
// ExStart:4
// Create new XPS Document
XpsDocument doc = new XpsDocument();
// ExEnd:4
```

## Bước 3: Khởi tạo các Gradient Stop

```csharp
// ExStart:5
// Initialize List of XpsGradientStop
List<XpsGradientStop> stops = new List<XpsGradientStop>();
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 244, 253, 225), 0.0673828f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 251, 240, 23), 0.314453f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 252, 209, 0), 0.482422f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 241, 254, 161), 0.634766f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 53, 253, 255), 0.915039f));
stops.Add(doc.CreateGradientStop(doc.CreateColor(255, 12, 91, 248), 1f));
// ExEnd:5
```

## Bước 4: Tạo một Path mới

```csharp
// ExStart:6
// Create new path by defining geometry in abbreviation form
XpsPath path = doc.AddPath(doc.CreatePathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.RenderTransform = doc.CreateMatrix(1f, 0f, 0f, 1f, 20f, 70f);
path.Fill = doc.CreateLinearGradientBrush(new PointF(10f, 0f), new PointF(228f, 0f));
((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);
// ExEnd:6
```

## Bước 5: Lưu tài liệu XPS đã tạo

```csharp
// ExStart:7
// Save resultant XPS document
doc.Save(dataDir + "AddHorizontalGradient_outXPS.xps");
// ExEnd:7
```

Bây giờ, bạn đã thêm thành công gradient ngang vào tài liệu XPS của mình bằng Aspose.Page cho .NET.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|------------|----------|
| Gradient hiển thị màu đồng nhất | Các gradient stop không được thêm đúng cách | Đảm bảo `((XpsGradientBrush)path.Fill).GradientStops.AddRange(stops);` được thực thi sau khi thiết lập brush. |
| Tệp lưu trống | `dataDir` trỏ tới thư mục không tồn tại | Kiểm tra thư mục tồn tại hoặc sử dụng đường dẫn tuyệt đối. |
| Lỗi biên dịch ở `PointF` | Thiếu tham chiếu `System.Drawing` | Thêm tham chiếu tới `System.Drawing.Common` (đối với .NET Core/5+). |

## Câu hỏi thường gặp

### Q1: Tôi có thể tìm tài liệu Aspose.Page cho .NET ở đâu?

A1: Bạn có thể tìm tài liệu [tại đây](https://reference.aspose.com/page/net/).

### Q2: Làm sao để tải Aspose.Page cho .NET?

A2: Bạn có thể tải thư viện từ [trang tải Aspose.Page cho .NET](https://releases.aspose.com/page/net/).

### Q3: Tôi có thể mua Aspose.Page cho .NET ở đâu?

A3: Bạn có thể mua Aspose.Page cho .NET từ [trang mua hàng](https://purchase.aspose.com/buy).

### Q4: Có bản dùng thử miễn phí không?

A4: Có, bạn có thể nhận bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### Q5: Làm sao để lấy giấy phép tạm thời cho Aspose.Page cho .NET?

A5: Bạn có thể nhận giấy phép tạm thời từ [liên kết này](https://purchase.aspose.com/temporary-license/).

## Các câu hỏi thường gặp khác

**Hỏi: Tôi có thể sử dụng kỹ thuật gradient này cho các tài liệu XPS đã có sẵn hình ảnh không?**  
Đáp: Chắc chắn rồi. Gradient được áp dụng lên lớp path, vì vậy các hình ảnh hiện có sẽ không bị ảnh hưởng.

**Hỏi: Có thể tạo gradient dọc thay vì ngang không?**  
Đáp: Có. Thay đổi các điểm bắt đầu và kết thúc của `LinearGradientBrush` để có tọa độ Y khác nhau trong khi giữ X không đổi.

**Hỏi: Aspose.Page có hỗ trợ .NET Core không?**  
Đáp: Thư viện hoàn toàn tương thích với .NET Core, .NET 5 và các phiên bản sau này.

**Hỏi: Làm sao để tái sử dụng cùng một gradient trên nhiều trang?**  
Đáp: Tạo một `XpsLinearGradientBrush` một lần, lưu vào biến và gán cho các path trên mỗi trang.

## Kết luận

Việc nâng cấp tài liệu XPS của bạn bằng gradient không chỉ cải thiện tính thẩm mỹ mà còn mang lại trải nghiệm người dùng sinh động hơn. Với Aspose.Page cho .NET, bạn có thể **tạo gradient XPS** nhanh chóng và đáng tin cậy, giúp các báo cáo, brochure hoặc e‑book của bạn trở nên chuyên nghiệp hơn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Cập nhật lần cuối:** 2026-02-25  
**Đã kiểm tra với:** Aspose.Page cho .NET 24.11  
**Tác giả:** Aspose  

---