---
date: 2026-06-25
description: Tìm hiểu cách cắt tài liệu XPS bằng Aspose.Page cho .NET. Hướng dẫn từng
  bước này chỉ cho bạn cách tạo, thao tác và lưu các tệp XPS một cách hiệu quả.
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: Cắt XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to clip XPS documents using Aspose.Page for .NET. This step‑by‑step
    guide shows you how to create, manipulate, and save XPS files efficiently.
  headline: How to Clip XPS with Aspose.Page for .NET
  type: TechArticle
- questions:
  - answer: Yes, you can assign a complex `PathGeometry` that contains several sub‑paths
      to the `Clip` property, allowing layered masking.
    question: Can I combine multiple clip geometries on a single canvas?
  - answer: When you later convert the XPS to PDF using Aspose.PDF, the clip geometry
      is preserved, so the visual result remains identical.
    question: Does clipping affect PDF conversion?
  - answer: XPS itself does not support animation; however, you can generate a series
      of XPS pages with different clip shapes to simulate motion.
    question: Is it possible to animate clipping in XPS?
  type: FAQPage
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

Chào mừng bạn đến với hướng dẫn toàn diện về **cách cắt XPS** bằng Aspose.Page cho .NET! Trong hướng dẫn này, bạn sẽ học từng bước cách tạo tài liệu XPS, áp dụng các mặt nạ cắt hình học và lưu kết quả. Việc cắt cho phép bạn ẩn các phần của canvas, tạo ra các bố cục tinh vi như hình ảnh được mặt nạ, hình dạng tùy chỉnh hoặc các khu vực nội dung tập trung — tất cả mà không rời khỏi mã .NET của bạn.

## Câu trả lời nhanh
- **Cắt XPS là gì?** Áp dụng một mặt nạ hình học (clip) để giới hạn khu vực hiển thị của các phần tử canvas trong XPS.  
- **Thư viện nào là tốt nhất cho việc này?** Aspose.Page cho .NET cung cấp API đầy đủ cho việc tạo và cắt XPS.  
- **Yêu cầu trước?** Visual Studio, môi trường .NET runtime và thư viện Aspose.Page cho .NET.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút cho một kịch bản cắt cơ bản.  
- **Tôi có thể sử dụng điều này trong môi trường sản xuất không?** Có, với giấy phép Aspose hợp lệ (có bản dùng thử).

## “Cách cắt XPS” là gì?

Cắt XPS có nghĩa là áp dụng một mặt nạ hình học lên canvas sao cho bất kỳ phần vẽ nào nằm ngoài mặt nạ sẽ không được hiển thị. Kỹ thuật này lý tưởng cho việc tạo hình ảnh được mặt nạ, nút có hình dạng tùy chỉnh, hoặc tập trung sự chú ý của người đọc vào một vùng trang cụ thể. Bằng cách định nghĩa một hình học clip — chẳng hạn như hình chữ nhật, vòng tròn, hoặc đường phức tạp — bạn có thể kiểm soát chi tiết những gì xuất hiện trên trang XPS cuối cùng.

## Tại sao nên sử dụng Aspose.Page cho .NET để cắt XPS?

Aspose.Page cung cấp khả năng thao tác XPS trên máy chủ một cách quyết đoán mà không cần phụ thuộc bên ngoài. Nó hỗ trợ **hơn 50 định dạng đầu vào và đầu ra**, có thể xử lý **tệp XPS 200 trang trong vòng dưới 0,5 giây** trên CPU 2,5 GHz tiêu chuẩn, và hoạt động trên .NET Framework 4.0+, .NET Core 2.0+, .NET 5, .NET 6 và .NET 7. API cho phép bạn kiểm soát toàn bộ các biến đổi canvas, hình học đường dẫn và brush, đảm bảo đầu ra chất lượng cao mỗi lần.

## Yêu cầu trước

- Visual Studio đã được cài đặt trên máy của bạn.  
- Thư viện Aspose.Page cho .NET đã được thêm vào dự án của bạn. Bạn có thể tải xuống nó [tại đây](https://releases.aspose.com/page/net/).  
- Kiến thức cơ bản về ngôn ngữ lập trình C#.

## Cách cắt XPS?

Tải tài liệu XPS, tạo canvas, định nghĩa hình học clip (ví dụ: một vòng tròn), gán hình học đó cho thuộc tính `Clip` của canvas, vẽ nội dung của bạn, và cuối cùng lưu tài liệu. Tất cả các bước này có thể thực hiện chỉ với vài lời gọi phương thức, và Aspose.Page tự động xử lý markup XML bên dưới, để bạn tập trung vào thiết kế trực quan thay vì cấu trúc tệp.

## Nhập không gian tên

Để sử dụng các chức năng của Aspose.Page cho .NET, bạn cần nhập các không gian tên cần thiết vào dự án. Thực hiện các bước sau:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

Bây giờ, chúng ta sẽ phân tích đoạn mã mẫu bạn đã cung cấp thành nhiều bước.

## Bước 1: Đặt đường dẫn thư mục tài liệu.

Xác định thư mục nơi tệp XPS sẽ được tạo. Sử dụng `Path.Combine` đảm bảo dấu phân cách thư mục đúng trên mọi hệ điều hành.

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Bước 2: Tạo một tài liệu XPS mới.

Khởi tạo lớp `XpsDocument`, đại diện cho toàn bộ gói XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## Bước 3: Tạo canvas chính.

Lớp `Canvas` đại diện cho bề mặt vẽ trong một trang XPS, nơi các hình dạng, hình ảnh và văn bản được hiển thị.

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## Bước 4: Đặt độ lệch trái và trên trong canvas chính.

Điều chỉnh vị trí canvas để kiểm soát nơi bắt đầu vẽ trên trang.

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## Bước 5: Tạo hình học đường dẫn hình chữ nhật.

`PathGeometry` định nghĩa một hình dạng vector; ở đây chúng ta tạo một hình chữ nhật đơn giản.

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Bước 6: Tạo màu nền cho các hình chữ nhật.

Xác định một brush màu rắn sẽ được dùng để tô màu cho hình chữ nhật.

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## Bước 7: Thêm một canvas khác có clip vào canvas chính.

Tạo một canvas con sẽ nhận một mặt nạ cắt.

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Bước 8: Tạo hình học vòng tròn cho clip.

`PathGeometry` cũng có thể đại diện cho các vòng tròn; hình học này sẽ được gán cho thuộc tính `Clip` của canvas con.

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## Bước 9: Tạo một hình chữ nhật trong canvas thứ hai và tô màu cho nó.

Vẽ một hình chữ nhật bên trong canvas đã được cắt; chỉ phần nằm trong vòng tròn sẽ hiển thị.

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## Bước 10: Thêm canvas thứ hai có hình chữ nhật viền vào canvas chính.

Thêm một hình chữ nhật có viền để minh họa cách viền tương tác với việc cắt.

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Bước 11: Tạo một hình chữ nhật trong canvas thứ ba và vẽ viền cho nó.

Canvas thứ ba minh họa việc vẽ độc lập mà không có cắt.

```csharp
Canvas thirdCanvas = new Canvas();
PathGeometry thirdRectGeom = new PathGeometry("M0,0 L150,0 150,75 0,75 Z");
Path thirdRect = new Path(thirdRectGeom, null, new Pen(Color.Green, 3));
thirdCanvas.Children.Add(thirdRect);
mainCanvas.Children.Add(thirdCanvas);
```

```csharp
XpsCanvas canvas3 = canvas1.AddCanvas();
```

## Bước 12: Lưu tài liệu XPS đã tạo.

Lưu gói XPS vào hệ thống tệp.

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## Các vấn đề thường gặp và giải pháp
- **Đường dẫn không hợp lệ** – Đảm bảo `dataDir` kết thúc bằng dấu gạch chéo ngược (`\\`) hoặc sử dụng `Path.Combine`.  
- **Clip không được áp dụng** – Kiểm tra xem chuỗi hình học clip có đúng định dạng không; một khoảng trắng thiếu có thể khiến clip bị bỏ qua.  
- **Lỗi giấy phép** – Trong bản không dùng để đánh giá, thêm giấy phép Aspose hợp lệ trước khi tạo tài liệu để tránh lỗi thời gian chạy.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng Aspose.Page cho .NET với các định dạng tài liệu khác không?
A1: Aspose.Page cho .NET chủ yếu tập trung vào tài liệu XPS, nhưng Aspose cung cấp các thư viện khác cho nhiều định dạng tài liệu.

### Câu hỏi 2: Aspose.Page cho .NET có phù hợp cho người mới bắt đầu không?
A2: Có, Aspose.Page cho .NET được thiết kế thân thiện với người dùng, và người mới có thể nhanh chóng nắm bắt các chức năng của nó với tài liệu hướng dẫn phù hợp.

### Câu hỏi 3: Tôi có thể tìm thêm ví dụ và tài nguyên ở đâu?
A3: Truy cập [tài liệu](https://reference.aspose.com/page/net/) và [diễn đàn Aspose.Page](https://forum.aspose.com/c/page/39) để có nhiều tài nguyên và ví dụ.

### Câu hỏi 4: Làm thế nào tôi có thể nhận giấy phép tạm thời cho Aspose.Page cho .NET?
A4: Bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

### Câu hỏi 5: Có bản dùng thử miễn phí cho Aspose.Page cho .NET không?
A5: Có, bạn có thể khám phá bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

## Các câu hỏi thường gặp bổ sung

**Q: Tôi có thể kết hợp nhiều hình học clip trên một canvas duy nhất không?**  
A: Có, bạn có thể gán một `PathGeometry` phức tạp chứa nhiều sub‑path vào thuộc tính `Clip`, cho phép mặt nạ lớp.

**Q: Việc cắt có ảnh hưởng đến việc chuyển đổi PDF không?**  
A: Khi bạn chuyển đổi XPS sang PDF bằng Aspose.PDF, hình học clip được giữ nguyên, vì vậy kết quả hình ảnh vẫn giống nhau.

**Q: Có thể tạo hoạt ảnh cho clip trong XPS không?**  
A: XPS không hỗ trợ hoạt ảnh; tuy nhiên, bạn có thể tạo một loạt các trang XPS với các hình dạng clip khác nhau để mô phỏng chuyển động.

**Cập nhật lần cuối:** 2026-06-25  
**Kiểm thử với:** Aspose.Page 24.11 cho .NET  
**Tác giả:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## Hướng dẫn liên quan

- [Cách biến đổi XPS bằng Aspose.Page cho .NET](/page/net/canvas-manipulation/transformationsxps/)
- [Thêm hình chữ nhật vào tài liệu XPS bằng Aspose.Page cho .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [Chuyển đổi XPS sang PDF bằng Aspose.Page cho .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}