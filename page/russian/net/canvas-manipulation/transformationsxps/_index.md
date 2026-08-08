---
date: 2026-06-25
description: Узнайте, как легко преобразовывать документы XPS — окончательное руководство
  по преобразованию XPS с использованием Aspose.Page for .NET, с пошаговыми инструкциями
  без кода и практическими советами.
keywords:
- how to transform xps
- convert images to xps
- Aspose.Page transformations
linktitle: Преобразования XPS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to transform XPS documents effortlessly – the definitive
    guide on how to transform xps using Aspose.Page for .NET, with code‑free steps
    and real‑world tips.
  headline: How to Transform XPS with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to transform XPS documents effortlessly – the definitive
    guide on how to transform xps using Aspose.Page for .NET, with code‑free steps
    and real‑world tips.
  name: How to Transform XPS with Aspose.Page for .NET
  steps:
  - name: Create a New XPS Document
    text: '`XpsDocument` is the Aspose.Page object that represents an XPS file in
      memory. *Explanation*: We start by defining the folder that holds our source
      and output files, then instantiate an empty `XpsDocument`. This object will
      be the canvas for all subsequent transformations.'
  - name: Create a Main Canvas
    text: '`Canvas` is the drawing surface that groups shapes, text, and other graphical
      elements. *Why this matters*: The main canvas acts as a container for all other
      canvases. By applying a small offset we ensure the content isn’t clipped at
      the page edge.'
  - name: Create a Rectangle Path Geometry
    text: '`PathGeometry` defines vector shapes using XPS path syntax (M = move, L
      = line, Z = close). *Tip*: The path string follows the standard XPS path syntax.
      Adjust the coordinates to change rectangle size.'
  - name: Add a Fill for Rectangles
    text: '`SolidColorBrush` creates a solid‑color fill that can be reused across
      multiple shapes. *Pro tip*: Use `CreateColor` with RGB values to match your
      brand palette.'
  - name: Add a New Canvas Without Transformations
    text: '`Canvas` without a transform serves as a baseline element for comparison.
      Here we simply place a rectangle on the page with no extra transformation—useful
      as a baseline element.'
  - name: Add a New Canvas with Translate Transformation
    text: '`TranslateTransform` moves objects along the X and Y axes. *What’s happening?*
      The first matrix moves the rectangle down by 200 units. The subsequent `Translate`
      call shifts it 500 units to the right, demonstrating how multiple translations
      can be chained.'
  - name: Add a New Canvas with Double Scale Transformation
    text: '`ScaleTransform` multiplies the width and height of the canvas by the supplied
      factors. *Why scale?* Scaling by 2 doubles the rectangle’s width and height,
      letting you create larger graphics without redefining the geometry.'
  - name: Add a New Canvas with Rotation Around a Point Transformation
    text: '`RotateAroundTransform` pivots the canvas around a custom point (here (100,
      50)). *Key insight*: `RotateAround` pivots the canvas around a custom point,
      giving you fine control over rotation anchors.'
  - name: Save Resultant XPS Document
    text: '`Save` persists the in‑memory document to disk in XPS format. After all
      transformations are applied, the document is persisted to `output1.xps`. Open
      the file in any XPS viewer to see the stacked rectangles with their respective
      translations, scaling, and rotation.'
  type: HowTo
- questions:
  - answer: Yes, it works seamlessly with Visual Studio, Visual Studio Code, Rider,
      and any IDE that supports .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.
    question: Is Aspose.Page for .NET compatible with all .NET development environments?
  - answer: Visit the official documentation at [Aspose.Page for .NET Documentation](https://reference.aspose.com/page/net/).
    question: Where can I find additional examples and detailed API docs?
  - answer: 'Absolutely. A free trial is available here: [Aspose.Page Free Trial](https://releases.aspose.com/).'
    question: Can I try Aspose.Page before buying a license?
  - answer: 'Request one via the temporary‑license page: [Temporary License](https://purchase.aspose.com/temporary-license/).'
    question: How do I obtain a temporary license for testing?
  - answer: 'Purchase directly from the Aspose store: [Aspose.Page Buy](https://purchase.aspose.com/buy).'
    question: Where do I purchase a full license?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Как преобразовать XPS с помощью Aspose.Page for .NET
url: /ru/net/canvas-manipulation/transformationsxps/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как преобразовать XPS с помощью Aspose.Page для .NET

## Введение

В этом полном руководстве вы узнаете **как преобразовать XPS**‑документы с помощью Aspose.Page для .NET. Независимо от того, нужно ли вам перемещать, масштабировать, вращать или комбинировать несколько графических элементов на одной странице, библиотека предоставляет управление на основе матриц без необходимости работать с сырым XML. Мы пройдём каждый шаг, объясним, почему каждое преобразование важно, и поделимся практическими советами, которые можно сразу внедрить в производственный код.

## Быстрые ответы
- **Что вы можете достичь?** Создавать, перемещать, масштабировать и вращать элементы холста XPS программно.  
- **Какая библиотека требуется?** Aspose.Page for .NET (последняя версия).  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшна.  
- **Поддерживаемые платформы?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Время реализации?** Около 10‑15 минут для базовых преобразований, показанных ниже.

## Что такое «how to transform xps»?
Фраза *how to transform xps* описывает программное изменение макета, размера и ориентации элементов внутри документа XPS (XML Paper Specification). С помощью Aspose.Page вы применяете трансформации на основе матриц к холстам, получая пиксель‑точный контроль над позиционированием, масштабированием и вращением без ручного редактирования разметки XPS.

## Почему использовать Aspose.Page для преобразований XPS?
Загрузите ваш XPS‑файл, примените серию трансформаций и сохраните — всё это занимает две строки кода. Aspose.Page поддерживает **более 50 форматов ввода и вывода**, может обработать **200‑страничные XPS‑файлы менее чем за 2 секунды** и не требует **внешних зависимостей**. Это делает её идеальной для генерации счетов, отчётов или любой печатной графики «на лету».

## Предварительные требования

Перед началом убедитесь, что у вас есть:

- **Aspose.Page for .NET Library** – скачайте её из официальной документации: [Документация Aspose.Page для .NET](https://reference.aspose.com/page/net/).  
- **Development Environment** – Visual Studio, Visual Studio Code, Rider или любой IDE, поддерживающий .NET.  
- **Document Directory** – папка на вашем компьютере, где будут читаться/записываться XPS‑файлы. Замените заполнители в коде реальным путём.

Теперь, когда всё готово, приступим к коду.

## Импорт пространств имён

Следующие пространства имён предоставляют основные типы Aspose.Page, с которыми вы будете работать:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Как преобразовать XPS с помощью Aspose.Page?

Загрузите исходный XPS (или начните с нового документа), затем примените последовательность матричных трансформаций — перемещение, масштабирование и вращение — непосредственно к объектам canvas. Каждая трансформация применяется в порядке вызова, позволяя создавать сложные макеты с помощью нескольких методов.

## Как преобразовать XPS – Пошаговое руководство

В этом разделе мы пройдем полный пример, который создаёт XPS‑файл, добавляет несколько холстов и применяет серию трансформаций, таких как перемещение, масштабирование и вращение. Каждый шаг включает лаконичный фрагмент кода (представлен заполнителями) и объясняет, зачем выполняется операция, чтобы вы могли легко воспроизвести её.

### Шаг 1: Создать новый документ XPS

`XpsDocument` — это объект Aspose.Page, представляющий XPS‑файл в памяти.  
```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

*Explanation*: Мы начинаем с определения папки, в которой находятся исходные и выходные файлы, затем создаём пустой `XpsDocument`. Этот объект будет холстом для всех последующих трансформаций.

### Шаг 2: Создать основной холст

`Canvas` — это поверхность рисования, объединяющая фигуры, текст и другие графические элементы.  
```csharp
// Create main canvas, common for all page elements
XpsCanvas canvas1 = doc.AddCanvas();

// Make left and top offsets in the main canvas
canvas1.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 20, 10);
```

*Why this matters*: Основной холст служит контейнером для всех остальных холстов. Применяя небольшое смещение, мы гарантируем, что содержимое не будет обрезано у края страницы.

### Шаг 3: Создать геометрию пути прямоугольника

`PathGeometry` определяет векторные формы с использованием синтаксиса пути XPS (M = move, L = line, Z = close).  
```csharp
// Create rectangle path geometry
XpsPathGeometry rectGeom = doc.CreatePathGeometry("M 0,0 L 200,0 200,100 0,100 Z");
```

*Tip*: Строка пути следует стандартному синтаксису XPS. Изменяйте координаты, чтобы изменить размер прямоугольника.

### Шаг 4: Добавить заливку для прямоугольников

`SolidColorBrush` создаёт сплошную заливку, которую можно переиспользовать в нескольких фигурах.  
```csharp
// Create a fill for rectangles
XpsBrush fill = doc.CreateSolidColorBrush(doc.CreateColor(12, 15, 159));
```

*Pro tip*: Используйте `CreateColor` с RGB‑значениями, чтобы соответствовать палитре вашего бренда.

### Шаг 5: Добавить новый холст без трансформаций

`Canvas` без трансформации служит базовым элементом для сравнения.  
```csharp
// Add new canvas without any transformations to the main canvas
XpsCanvas canvas2 = canvas1.AddCanvas();

// Create rectangle in this canvas and fill it
XpsPath rect = canvas2.AddPath(rectGeom);
rect.Fill = fill;
```

Здесь мы просто размещаем прямоугольник на странице без дополнительных трансформаций — полезно как базовый элемент.

### Шаг 6: Добавить новый холст с трансформацией перемещения

`TranslateTransform` перемещает объекты вдоль осей X и Y.  
```csharp
// Add new canvas with translate transformation to the main canvas
XpsCanvas canvas3 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas3.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 200);

// Translate this canvas to the right side of the page
canvas3.RenderTransform.Translate(500, 0);

// Create rectangle in this canvas and fill it
rect = canvas3.AddPath(rectGeom);
rect.Fill = fill;
```

*What’s happening?* Первая матрица перемещает прямоугольник вниз на 200 единиц. Последующий вызов `Translate` сдвигает его на 500 единиц вправо, демонстрируя, как можно цепочкой применять несколько перемещений.

### Шаг 7: Добавить новый холст с двойным масштабированием

`ScaleTransform` умножает ширину и высоту холста на указанные коэффициенты.  
```csharp
// Add new canvas with double scale transformation to the main canvas
XpsCanvas canvas4 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas4.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 400);

// Scale this canvas
canvas4.RenderTransform.Scale(2, 2);

// Create rectangle in this canvas and fill it
rect = canvas4.AddPath(rectGeom);
rect.Fill = fill;
```

*Why scale?* Масштабирование на 2 удваивает ширину и высоту прямоугольника, позволяя создавать более крупную графику без переопределения геометрии.

### Шаг 8: Добавить новый холст с вращением вокруг точки

`RotateAroundTransform` вращает холст вокруг пользовательской точки (здесь (100, 50)).  
```csharp
// Add new canvas with rotation around a point transformation to the main canvas
XpsCanvas canvas5 = canvas1.AddCanvas();

// Translate this canvas to position a new rectangle below the previous rectangle
canvas5.RenderTransform = doc.CreateMatrix(1, 0, 0, 1, 0, 800);

// Rotate this canvas around a point on 45 degrees
canvas5.RenderTransform.RotateAround(45, new PointF(100, 50));

// Create rectangle in this canvas and fill it
rect = canvas5.AddPath(rectGeom);
rect.Fill = fill;
```

*Key insight*: `RotateAround` вращает холст вокруг заданной точки, предоставляя точный контроль над точкой привязки вращения.

### Шаг 9: Сохранить полученный документ XPS

`Save` сохраняет документ из памяти на диск в формате XPS.  
```csharp
// Save resultant XPS document
doc.Save(dataDir + "output1.xps");
// ExEnd:1
```

После применения всех трансформаций документ сохраняется в `output1.xps`. Откройте файл в любом XPS‑просмотрщике, чтобы увидеть наложенные прямоугольники с их соответствующими перемещениями, масштабированием и вращением.

## Распространённые проблемы и их устранение

| Симптом | Возможная причина | Решение |
|---------|-------------------|---------|
| Пустой файл вывода | `dataDir` указывает на несуществующую папку | Убедитесь, что директория существует, или используйте абсолютный путь |
| Прямоугольники расположены не так, как ожидалось | Неправильные значения матрицы | Проверьте порядок вызовов `Translate`, `Scale` и `RotateAround` |
| Цвета отображаются неверно | Значения RGB вне диапазона 0‑255 | Используйте корректные байтовые значения для каждого канала |

## Часто задаваемые вопросы

**Q: Совместима ли Aspose.Page for .NET со всеми средами разработки .NET?**  
A: Да, она без проблем работает с Visual Studio, Visual Studio Code, Rider и любой IDE, поддерживающей .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.

**Q: Где я могу найти дополнительные примеры и подробную документацию API?**  
A: Посетите официальную документацию по адресу [Документация Aspose.Page для .NET](https://reference.aspose.com/page/net/).

**Q: Можно ли попробовать Aspose.Page перед покупкой лицензии?**  
A: Конечно. Бесплатная пробная версия доступна здесь: [Aspose.Page Free Trial](https://releases.aspose.com/).

**Q: Как получить временную лицензию для тестирования?**  
A: Запросите её на странице временной лицензии: [Temporary License](https://purchase.aspose.com/temporary-license/).

**Q: Где купить полную лицензию?**  
A: Приобретайте напрямую в магазине Aspose: [Aspose.Page Buy](https://purchase.aspose.com/buy).

**Last Updated:** 2026-06-25  
**Tested With:** Aspose.Page 24.11 for .NET  
**Author:** Aspose

## Связанные руководства

- [Создать документ XPS с помощью Aspose.Page для .NET](/page/net/document-creation/create-xps-document/)
- [Как обрезать XPS с помощью Aspose.Page для .NET](/page/net/canvas-manipulation/clippingxps/)
- [Конвертировать XPS в PDF с помощью Aspose.Page для .NET](/page/net/document-conversion/convert-xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}