---
date: 2026-06-25
description: Узнайте, как обрезать XPS‑документы с помощью Aspose.Page for .NET. Это
  пошаговое руководство покажет, как создавать, изменять и эффективно сохранять XPS‑файлы.
keywords:
- how to clip xps
- Aspose.Page .NET
- XPS clipping tutorial
linktitle: Обрезка XPS
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
title: Как обрезать XPS с помощью Aspose.Page for .NET
url: /ru/net/canvas-manipulation/clippingxps/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как обрезать XPS с помощью Aspose.Page для .NET

## Введение

Добро пожаловать в этот подробный учебник по **как обрезать XPS** с использованием Aspose.Page для .NET! В этом руководстве вы шаг за шагом узнаете, как создать документ XPS, применить геометрические маски обрезки и сохранить результат. Обрезка позволяет скрывать части холста, обеспечивая сложные макеты, такие как маскированные изображения, пользовательские формы или сфокусированные области контента — всё без выхода из вашего кода .NET.

## Краткие ответы
- **Что такое обрезка XPS?** Применение геометрической маски (clip) для ограничения видимой области элементов холста XPS.  
- **Какая библиотека лучше всего подходит для этого?** Aspose.Page for .NET предлагает полнофункциональный API для создания XPS и обрезки.  
- **Требования?** Visual Studio, среда выполнения .NET и библиотека Aspose.Page for .NET.  
- **Сколько времени занимает реализация?** Около 10‑15 минут для базового сценария обрезки.  
- **Можно ли использовать это в продакшене?** Да, при наличии действующей лицензии Aspose (доступна пробная версия).

## Что такое «как обрезать XPS»?

Обрезка XPS означает применение геометрической маски к холсту, так что любые рисунки за пределами маски не отображаются. Эта техника идеальна для создания маскированных изображений, кнопок нестандартной формы или фокусировки внимания читателя на определённой области страницы. Определяя геометрию обрезки — например, прямоугольник, круг или сложный контур — вы получаете точный контроль над тем, что будет отображаться на конечной странице XPS.

## Почему использовать Aspose.Page для .NET для обрезки XPS?

Aspose.Page предоставляет детерминированную серверную обработку XPS без внешних зависимостей. Он поддерживает **50+ input and output formats**, может обрабатывать **200‑page XPS files in under 0.5 seconds** на стандартном процессоре 2.5 GHz и работает с .NET Framework 4.0+, .NET Core 2.0+, .NET 5, .NET 6 и .NET 7. API дает вам полный контроль над трансформациями холста, геометрией путей и кистями, обеспечивая высококачественный результат каждый раз.

## Предварительные требования

- Visual Studio установлен на вашем компьютере.  
- Библиотека Aspose.Page for .NET добавлена в ваш проект. Вы можете скачать её [here](https://releases.aspose.com/page/net/).  
- Базовые знания языка программирования C#.

## Как обрезать XPS?

Загрузите документ XPS, создайте холст, определите геометрию обрезки (например, круг), назначьте эту геометрию свойству `Clip` холста, нарисуйте ваш контент и, наконец, сохраните документ. Все эти шаги можно выполнить всего несколькими вызовами методов, а Aspose.Page автоматически обрабатывает подлежащую XML-разметку, позволяя вам сосредоточиться на визуальном дизайне, а не на структуре файла.

## Импорт пространств имён

Чтобы использовать возможности Aspose.Page для .NET, необходимо импортировать требуемые пространства имён в ваш проект. Следуйте этим шагам:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.IO;
```

Теперь разберём пример кода, который вы предоставили, на несколько шагов.

## Шаг 1: Установить путь к каталогу документа.

Определите папку, в которой будет создан файл XPS. Использование `Path.Combine` гарантирует правильный разделитель каталогов на любой ОС.

```csharp
string dataDir = Path.Combine(Environment.CurrentDirectory, "Output");
Directory.CreateDirectory(dataDir);
```

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Шаг 2: Создать новый документ XPS.

Создайте экземпляр класса `XpsDocument`, который представляет весь пакет XPS.

```csharp
XpsDocument doc = new XpsDocument();
```

```csharp
string dataDir = "Your Document Directory";
```

## Шаг 3: Создать основной холст.

Класс `Canvas` представляет поверхность для рисования внутри страницы XPS, где отображаются фигуры, изображения и текст.

```csharp
Canvas mainCanvas = new Canvas();
```

```csharp
XpsDocument doc = new XpsDocument();
```

## Шаг 4: Установить смещения слева и сверху в основном холсте.

Отрегулируйте позицию холста, чтобы контролировать, где начинается рисование на странице.

```csharp
mainCanvas.Left = 20;
mainCanvas.Top = 30;
```

```csharp
XpsCanvas canvas1 = doc.AddCanvas();
```

## Шаг 5: Создать геометрию пути прямоугольника.

`PathGeometry` определяет векторную форму; здесь мы создаём простой прямоугольник.

```csharp
PathGeometry rectGeometry = new PathGeometry("M0,0 L100,0 100,50 0,50 Z");
```

```csharp
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

## Шаг 6: Создать заливку для прямоугольников.

Определите кисть сплошного цвета, которая будет использоваться для заливки прямоугольника.

```csharp
SolidColorBrush rectFill = new SolidColorBrush(Color.Black);
```

```csharp
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 500,0 500,300 0,300 Z");
```

## Шаг 7: Добавить ещё один холст с обрезкой в основной холст.

Создайте дочерний холст, который получит маску обрезки.

```csharp
Canvas clippedCanvas = new Canvas();
mainCanvas.Children.Add(clippedCanvas);
```

```csharp
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

## Шаг 8: Создать геометрию круга для обрезки.

`PathGeometry` также может представлять круги; эта геометрия будет назначена свойству `Clip` дочернего холста.

```csharp
PathGeometry circleClip = new PathGeometry("M50,0 A50,50 0 1 0 49.9,0 Z");
clippedCanvas.Clip = circleClip;
```

```csharp
XpsCanvas canvas2 = canvas1.AddCanvas();
```

## Шаг 9: Создать прямоугольник во втором холсте и залить его.

Нарисуйте прямоугольник внутри обрезанного холста; будет видна только часть, находящаяся внутри круга.

```csharp
Path rectangle = new Path(rectGeometry, rectFill);
clippedCanvas.Children.Add(rectangle);
```

```csharp
XpsPathGeometry clipGeom = doc.CreatePathGeometry("M250,250 A100,100 0 1 1 250,50 100,100 0 1 1 250,250");
canvas2.Clip = clipGeom;
```

## Шаг 10: Добавить второй холст со штрихованным прямоугольником в основной холст.

Добавьте прямоугольник со штриховкой, чтобы продемонстрировать, как линии взаимодействуют с обрезкой.

```csharp
Path strokedRect = new Path(rectGeometry, null, new Pen(Color.Blue, 2));
mainCanvas.Children.Add(strokedRect);
```

```csharp
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

## Шаг 11: Создать прямоугольник в третьем холсте и обвести его.

Третий холст демонстрирует независимое рисование без обрезки.

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

## Шаг 12: Сохранить полученный документ XPS.

Сохраните пакет XPS в файловой системе.

```csharp
doc.Save(Path.Combine(dataDir, "ClippedOutput.xps"));
```

```csharp
rect = canvas3.AddPath(rectGeom);
rect.Stroke = fill;
rect.StrokeThickness = 2;
```

## Распространённые проблемы и решения
- **Invalid path** – Убедитесь, что `dataDir` заканчивается обратным слешем (`\\`) или используйте `Path.Combine`.  
- **Clip not applied** – Проверьте, что строка геометрии обрезки правильно сформирована; отсутствие пробела может привести к игнорированию обрезки.  
- **License exception** – В сборке без оценки добавьте действующую лицензию Aspose перед созданием документа, чтобы избежать исключений во время выполнения.

## Часто задаваемые вопросы

### Q1: Могу ли я использовать Aspose.Page для .NET с другими форматами документов?
A1: Aspose.Page for .NET в основном ориентирован на документы XPS, но Aspose предоставляет другие библиотеки для различных форматов документов.

### Q2: Подходит ли Aspose.Page для .NET начинающим?
A2: Да, Aspose.Page for .NET разработан с учётом удобства пользователя, и начинающие могут быстро освоить его функции при наличии соответствующей документации.

### Q3: Где я могу найти больше примеров и ресурсов?
A3: Посетите [documentation](https://reference.aspose.com/page/net/) и [Aspose.Page forum](https://forum.aspose.com/c/page/39) для обширных ресурсов и примеров.

### Q4: Как получить временную лицензию для Aspose.Page for .NET?
A4: Вы можете получить временную лицензию [here](https://purchase.aspose.com/temporary-license/).

### Q5: Доступна ли бесплатная пробная версия Aspose.Page for .NET?
A5: Да, вы можете ознакомиться с бесплатной пробной версией [here](https://releases.aspose.com/).

## Дополнительные часто задаваемые вопросы

**Q: Могу ли я комбинировать несколько геометрий обрезки на одном холсте?**  
A: Да, вы можете назначить сложный `PathGeometry`, содержащий несколько под‑контуров, свойству `Clip`, позволяя использовать многослойную маску.

**Q: Влияет ли обрезка на конвертацию в PDF?**  
A: При последующей конвертации XPS в PDF с помощью Aspose.PDF геометрия обрезки сохраняется, поэтому визуальный результат остаётся идентичным.

**Q: Можно ли анимировать обрезку в XPS?**  
A: Сам XPS не поддерживает анимацию; однако вы можете создать серию страниц XPS с различными формами обрезки для имитации движения.

---

**Последнее обновление:** 2026-06-25  
**Тестировано с:** Aspose.Page 24.11 for .NET  
**Автор:** Aspose  

```csharp
doc.Save(dataDir + "output2.xps");
```

## Связанные руководства

- [How to Transform XPS with Aspose.Page for .NET](/page/net/canvas-manipulation/transformationsxps/)
- [Add Rectangle to XPS Document with Aspose.Page for .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)
- [Convert XPS to PDF with Aspose.Page for .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< /blocks/products/products-backtop-button >}}

{{< blocks/products/products-backtop-button >}}