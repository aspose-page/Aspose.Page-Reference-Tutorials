---
date: 2026-01-05
description: Tìm hiểu cách cắt tài liệu XPS bằng Aspose.Page cho .NET. Hướng dẫn từng
  bước này cho bạn biết cách tạo, thao tác và lưu các tệp XPS một cách hiệu quả.
linktitle: Clipping XPS
second_title: Aspose.Page .NET API
title: Cách cắt XPS bằng Aspose.Page cho .NET
url: /vi/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Cắt XPS bằng Aspose.Page cho .NET

## Giới thiệu

Chào mừng bạn đến với hướng dẫn toàn diện **cách cắt XPS** bằng Aspose.Page cho .NET! Trong tài liệu này, chúng tôi sẽ hướng dẫn bạn quy trình tạo, thao tác và lưu tài liệu XPS bằng thư viện. XPS, hay XML Paper Specification, là một định dạng tài liệu tiêu chuẩn và mở, và Aspose.Page cho .NET cung cấp các công cụ mạnh mẽ để làm việc với tài liệu XPS trong các ứng dụng .NET của bạn.

## Trả lời nhanh
- **Cắt XPS là gì?** Áp dụng một mặt nạ hình học (clip) để giới hạn vùng hiển thị của các phần tử canvas trong XPS.  
- **Thư viện nào tốt nhất cho việc này?** Aspose.Page cho .NET cung cấp API đầy đủ tính năng cho việc tạo và cắt XPS.  
- **Yêu cầu trước?** Visual Studio, .NET runtime và thư viện Aspose.Page cho .NET.  
- **Thời gian triển khai khoảng bao lâu?** Khoảng 10‑15 phút cho một kịch bản cắt cơ bản.  
- **Có thể dùng trong môi trường production không?** Có, với giấy phép Aspose hợp lệ (có bản dùng thử).

## “Cách cắt XPS” là gì?
Việc cắt trong XPS hoạt động bằng cách định nghĩa một **địa hình clip** (ví dụ: vòng tròn hoặc hình chữ nhật) và gán nó cho một canvas. Bất kỳ gì được vẽ ra ngoài địa hình đó sẽ không được hiển thị, cho phép bạn tạo các bố cục trang tinh vi như hình ảnh được mặt nạ, hình dạng tùy chỉnh, hoặc các khu vực nội dung tập trung.

## Tại sao nên dùng Aspose.Page cho .NET để cắt XPS?
- **Kiểm soát đầy đủ** các biến đổi canvas, địa hình đường dẫn và brush.  
- **Không phụ thuộc bên ngoài** – mọi thứ chạy trong ứng dụng .NET của bạn.  
- **Hỗ trợ đa nền tảng** cho .NET Framework, .NET Core và .NET 5/6+.  
- **Hiệu năng cao** với API nhẹ nhàng tạo ra các tệp XPS hợp lệ.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn bạn đã có:

- Visual Studio được cài đặt trên máy tính.  
- Thư viện Aspose.Page cho .NET đã được thêm vào dự án. Bạn có thể tải xuống [tại đây](https://releases.aspose.com/page/net/).  
- Kiến thức cơ bản về ngôn ngữ lập trình C#.

## Nhập không gian tên

Để sử dụng các chức năng của Aspose.Page cho .NET, bạn cần nhập các không gian tên cần thiết vào dự án. Thực hiện các bước sau:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

Bây giờ, chúng ta sẽ phân tích đoạn mã mẫu mà bạn đã cung cấp thành nhiều bước.

## Bước 1: Đặt đường dẫn thư mục tài liệu.

```csharp
string dataDir = "Your Document Directory";
```

Hãy thay thế “Your Document Directory” bằng đường dẫn thực tế tới thư mục tài liệu của bạn.

## Bước 2: Tạo một tài liệu XPS mới.

```csharp
XpsDocument doc = new XpsDocument();
```

Điều này tạo ra một tài liệu XPS mới mà bạn sẽ làm việc.

## Bước 3: Tạo canvas chính.

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

Bước này tạo canvas chính, dùng chung cho tất cả các phần tử trang.

## Bước 4: Đặt offset trái và trên trong canvas chính.

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

Điều chỉnh offset trái và trên theo yêu cầu của bạn.

## Bước 5: Tạo địa hình đường dẫn hình chữ nhật.

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

Điều này tạo một địa hình đường dẫn cho hình chữ nhật.

## Bước 6: Tạo màu nền cho các hình chữ nhật.

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

Xác định màu nền cho các hình chữ nhật.

## Bước 7: Thêm một canvas khác có clip vào canvas chính.

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

Bước này thêm một canvas khác vào canvas chính.

## Bước 8: Tạo địa hình vòng tròn cho clip.

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

Điều này tạo một địa hình clip dạng vòng tròn và áp dụng nó cho canvas thứ hai.

## Bước 9: Tạo một hình chữ nhật trong canvas thứ hai và tô màu.

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Bước này tạo một hình chữ nhật trong canvas thứ hai và tô màu cho nó.

## Bước 10: Thêm canvas thứ hai với hình chữ nhật có viền vào canvas chính.

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

Điều này thêm một canvas khác vào canvas chính.

## Bước 11: Tạo một hình chữ nhật trong canvas thứ ba và vẽ viền cho nó.

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

Điều này tạo một hình chữ nhật trong canvas thứ ba và áp dụng viền cho nó.

## Bước 12: Lưu tài liệu XPS đã tạo.

```csharp
doc.Save(dataDir + "output2.xps");
```

Lưu tài liệu XPS vào thư mục đã chỉ định.

## Các vấn đề thường gặp và giải pháp
- **Đường dẫn không hợp lệ** – Đảm bảo `dataDir` kết thúc bằng dấu gạch chéo ngược (`\\`) hoặc sử dụng `Path.Combine`.  
- **Clip không được áp dụng** – Kiểm tra chuỗi địa hình clip có đúng định dạng không; một khoảng trắng thiếu có thể khiến clip bị bỏ qua.  
- **Lỗi giấy phép** – Trong bản không phải dùng thử, thêm giấy phép Aspose hợp lệ trước khi tạo tài liệu để tránh ngoại lệ thời gian chạy.

## Câu hỏi thường gặp

### Q1: Tôi có thể dùng Aspose.Page cho .NET với các định dạng tài liệu khác không?

A1: Aspose.Page cho .NET chủ yếu tập trung vào tài liệu XPS, nhưng Aspose cung cấp các thư viện khác cho nhiều định dạng tài liệu.

### Q2: Aspose.Page cho .NET có phù hợp cho người mới bắt đầu không?

A2: Có, Aspose.Page cho .NET được thiết kế thân thiện với người dùng, và người mới có thể nhanh chóng nắm bắt các chức năng của nó với tài liệu hướng dẫn đầy đủ.

### Q3: Tôi có thể tìm thêm ví dụ và tài nguyên ở đâu?

A3: Tham khảo [tài liệu](https://reference.aspose.com/page/net/) và [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để có nhiều tài nguyên và ví dụ phong phú.

### Q4: Làm sao tôi có thể lấy giấy phép tạm thời cho Aspose.Page cho .NET?

A4: Bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

### Q5: Có bản dùng thử miễn phí cho Aspose.Page cho .NET không?

A5: Có, bạn có thể khám phá bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

## Các câu hỏi thường gặp bổ sung

**Hỏi: Tôi có thể kết hợp nhiều địa hình clip trên một canvas duy nhất không?**  
Đáp: Có, bạn có thể gán một `PathGeometry` phức tạp chứa nhiều sub‑path vào thuộc tính `Clip`, cho phép tạo lớp mặt nạ đa tầng.

**Hỏi: Việc clip có ảnh hưởng đến việc chuyển đổi sang PDF không?**  
Đáp: Khi bạn chuyển đổi XPS sang PDF bằng Aspose.PDF, địa hình clip sẽ được giữ nguyên, vì vậy kết quả hiển thị vẫn giống nhau.

**Hỏi: Có thể tạo hoạt ảnh clip trong XPS không?**  
Đáp: XPS không hỗ trợ hoạt ảnh; tuy nhiên, bạn có thể tạo một loạt các trang XPS với các hình dạng clip khác nhau để mô phỏng chuyển động.

---

**Cập nhật lần cuối:** 2026-01-05  
**Kiểm tra với:** Aspose.Page 24.11 cho .NET  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}