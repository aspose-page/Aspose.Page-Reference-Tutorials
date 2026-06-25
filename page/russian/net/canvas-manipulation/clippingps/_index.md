---
date: 2026-06-25
description: Узнайте, как добавить обрезающий путь в PostScript, используя Aspose.Page
  для .NET — пошаговое руководство с техниками paint brush и dashed rectangle.
keywords:
- how to add clipping path
- Aspose.Page clipping
- PostScript graphics .NET
linktitle: Обрезка PS
schemas:
- author: Aspose
  dateModified: '2026-06-25'
  description: Learn how to add clipping path in PostScript using Aspose.Page for
    .NET – step‑by‑step guide with paint brush and dashed rectangle techniques.
  headline: How to Add Clipping Path to PostScript with Aspose.Page for .NET
  type: TechArticle
- description: Learn how to add clipping path in PostScript using Aspose.Page for
    .NET – step‑by‑step guide with paint brush and dashed rectangle techniques.
  name: How to Add Clipping Path to PostScript with Aspose.Page for .NET
  steps:
  - name: Set Document Directory
    text: Define the folder where your source and output files will live. This makes
      it easy to locate the generated PS file later.
  - name: Create Output Stream for PostScript Document
    text: Create a writable stream that will hold the generated PS file. Using a `FileStream`
      ensures the file is written directly to disk.
  - name: Create Save Options
    text: '`PsSaveOptions` is Aspose.Page’s configuration object for PS output. It
      lets you control compression, version, and other rendering details.'
  - name: Create a New 1‑Paged PS Document
    text: '`PsDocument` represents a PostScript document object. You instantiate it
      with the output stream and the save options you just configured.'
  - name: Create Graphics Path from the Rectangle
    text: '`GraphicsPath` is a vector container for geometric shapes. Here we start
      with a simple rectangle that will later be clipped.'
  - name: Clipping by Shape
    text: We add a clipping path using a circle, set the paint brush to blue, and
      fill the rectangle within the clipped region. This demonstrates how clipping
      limits drawing to the circle’s interior.
  - name: Displace Upper Level Graphics State & Draw Dashed Rectangle
    text: After restoring the previous graphics state, we translate the cursor, create
      a `Pen` with `DashStyle.Dash`, and draw a dashed rectangle around the clipped
      content. The blue stroke highlights the clipping boundary. `Pen` defines stroke
      attributes such as color and dash style. `DashStyle.Dash` specifi
  - name: Close and Save Document
    text: Finish the page, flush the stream, and dispose of resources. The PS file
      is now written to disk and ready for viewing in any PostScript viewer. You have
      now successfully **added clipping path**, set a custom paint brush, and drawn
      a dashed rectangle around your graphics using Aspose.Page for .NET.
  type: HowTo
- questions:
  - answer: It restricts drawing operations to a defined shape, hiding everything
      outside that shape.
    question: What does “add clipping path” do?
  - answer: Aspose.Page for .NET provides a rich API for PS/EPS manipulation.
    question: Which library handles clipping in .NET?
  - answer: A free trial works for development; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes, use `SetPaint` with any `SolidBrush` or gradient you prefer.
    question: Can I change the brush color?
  - answer: Absolutely – create a `Pen` with `DashStyle.Dash` and use `Draw`.
    question: Is drawing a dashed rectangle possible?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Как добавить обрезающий путь в PostScript с помощью Aspose.Page для .NET
url: /ru/net/canvas-manipulation/clippingps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как добавить путь обрезки в PostScript с помощью Aspose.Page для .NET

## Введение

В этом всестороннем руководстве вы научитесь **добавлять путь обрезки** в документ PostScript (PS) с помощью Aspose.Page для .NET. Мы пройдем каждый шаг, покажем, как **установить кисть**, и продемонстрируем, как **нарисовать пунктирный прямоугольник** вокруг обрезанного содержимого. К концу у вас будет полностью функционирующий файл PS, демонстрирующий обрезку по форме, придавая вашим графикам более динамичный и профессиональный вид.

## Быстрые ответы
- **Что делает «добавление пути обрезки»?** Ограничивает операции рисования определенной формой, скрывая всё, что находится за её пределами.  
- **Какая библиотека обрабатывает обрезку в .NET?** Aspose.Page для .NET предоставляет богатый API для работы с PS/EPS.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; для продакшн‑использования требуется коммерческая лицензия.  
- **Можно ли изменить цвет кисти?** Да, используйте `SetPaint` с любой `SolidBrush` или градиентом по вашему выбору.  
- **Можно ли нарисовать пунктирный прямоугольник?** Конечно — создайте `Pen` с `DashStyle.Dash` и используйте `Draw`.  

## Что такое путь обрезки в PostScript?

Путь обрезки определяет видимую область последующих команд рисования, отбрасывая всё, что отрисовано за её пределами. На практике это позволяет маскировать графику так, чтобы отображалась только часть внутри пути, что необходимо для создания сложных композиций без постоянного изменения исходных объектов.

## Как добавить путь обрезки в документ PostScript с помощью Aspose.Page?

Загрузите `PsDocument`, определите графический путь (например, круг), примените `Clip()`, чтобы ограничить область рисования, затем используйте `SetPaint` и `Fill` для отрисовки содержимого внутри обрезанной области. После восстановления состояния графики вы можете рисовать дополнительные фигуры — например, пунктирный прямоугольник — без влияния на обрезанную область. Эта последовательность осуществляет обрезку всего за несколько лаконичных вызовов API.

`PsDocument` представляет объект документа PostScript.  
`GraphicsPath` — векторный контейнер для геометрических фигур.  
`Clip()` задаёт область обрезки для последующего рисования.  
`SetPaint` назначает кисть, используемую для заполнения фигур.  
`Fill` отрисовывает текущий путь, используя текущую кисть.

## Почему стоит использовать Aspose.Page для обрезки?

Aspose.Page поддерживает **более 50 форматов ввода и вывода**, включая PS, EPS, PDF, SVG и типы изображений, и может обрабатывать документы из нескольких сотен страниц без загрузки всего файла в память. Библиотека не имеет **внешних зависимостей**, работает на **.NET Framework 4.5+**, **.NET Core 3.1+** и **.NET 6+**, и предоставляет полный контроль над состоянием графики (save/restore, translate, rotate). Эти измеримые преимущества делают её надёжным выбором для серверной генерации графики.

## Требования

- Базовые знания программирования на C#.  
- Библиотека Aspose.Page для .NET установлена — её можно скачать [здесь](https://releases.aspose.com/page/net/).  
- Visual Studio или любой другой предпочтительный .NET IDE.  

## Импорт пространств имён

Следующие пространства имён предоставляют доступ к основным графическим объектам и параметрам сохранения, специфичным для PS.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Теперь разберём пример на чёткие, пронумерованные шаги.

### Шаг 1: Установить каталог документа

Определите папку, где будут находиться ваши исходные и выходные файлы. Это упрощает поиск сгенерированного файла PS позже.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

### Шаг 2: Создать поток вывода для документа PostScript

Создайте поток записи, который будет содержать сгенерированный файл PS. Использование `FileStream` гарантирует, что файл будет записан напрямую на диск.

```csharp
// Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "Clipping_outPS.ps", FileMode.Create))
```

### Шаг 3: Создать параметры сохранения

`PsSaveOptions` — объект конфигурации Aspose.Page для вывода PS. Он позволяет управлять сжатием, версией и другими деталями рендеринга.

```csharp
// Create save options with default values
PsSaveOptions options = new PsSaveOptions();
```

### Шаг 4: Создать новый одностраничный документ PS

`PsDocument` представляет объект документа PostScript. Вы создаёте его, передавая поток вывода и только что настроенные параметры сохранения.

```csharp
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Шаг 5: Создать графический путь из прямоугольника

`GraphicsPath` — векторный контейнер для геометрических фигур. Здесь мы начинаем с простого прямоугольника, который позже будет обрезан.

```csharp
// Create graphics path from the rectangle
GraphicsPath rectanglePath = new GraphicsPath();
rectanglePath.AddRectangle(new RectangleF(0, 0, 300, 200));
```

### Шаг 6: Обрезка по форме

Мы добавляем путь обрезки с помощью круга, устанавливаем кисть заливки в синий цвет и заполняем прямоугольник внутри обрезанной области. Это демонстрирует, как обрезка ограничивает рисование внутренней частью круга.

```csharp
// Save graphics state in order to return back to this state after transformation
document.WriteGraphicsSave();

// Displace current graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

// Create graphics path from the circle
GraphicsPath circlePath = new GraphicsPath();
circlePath.AddEllipse(new RectangleF(50, 0, 200, 200));

// Add clipping by circle to the current graphics state
document.Clip(circlePath);

// Set paint in the current graphics state
document.SetPaint(new SolidBrush(Color.Blue));

// Fill the rectangle in the current graphics state (with clipping)
document.Fill(rectanglePath);

// Restore graphics state to the previous (upper) level
document.WriteGraphicsRestore();
```

### Шаг 7: Сместить состояние графики верхнего уровня и нарисовать пунктирный прямоугольник

После восстановления предыдущего состояния графики мы перемещаем курсор, создаём `Pen` с `DashStyle.Dash` и рисуем пунктирный прямоугольник вокруг обрезанного содержимого. Синяя обводка подчёркивает границу обрезки.

`Pen` определяет атрибуты обводки, такие как цвет и стиль штриха.  
`DashStyle.Dash` задаёт пунктирный шаблон линии.

```csharp
// Displace upper-level graphics state on 100 points to the right and 100 points to the bottom.
document.Translate(100, 100);

Pen pen = new Pen(new SolidBrush(Color.Blue), 2);
pen.DashStyle = DashStyle.Dash;

document.SetStroke(pen);

// Draw the rectangle in the current graphics state (has no clipping) above the clipped rectangle
document.Draw(rectanglePath);
```

### Шаг 8: Закрыть и сохранить документ

Завершите страницу, сбросьте поток и освободите ресурсы. Файл PS теперь записан на диск и готов к просмотру в любом просмотрщике PostScript.

```csharp
// Close current page
document.ClosePage();

// Save the document
document.Save();
```

Вы успешно **добавили путь обрезки**, установили пользовательскую кисть и нарисовали пунктирный прямоугольник вокруг вашей графики с помощью Aspose.Page для .NET.

## Распространённые проблемы и решения

- **Обрезка не видна:** Убедитесь, что вы вызываете `WriteGraphicsSave()` перед перемещением и `WriteGraphicsRestore()` после заполнения.  
- **Неправильные цвета:** Проверьте, что `SetPaint` вызывается после `Clip` и перед `Fill`.  
- **Пунктирные линии отображаются сплошными:** Убедитесь, что у `Pen` параметр `DashStyle` установлен в `DashStyle.Dash` перед `SetStroke`.  

## Часто задаваемые вопросы

### Q1: Могу ли я использовать Aspose.Page для .NET с другими языками программирования?
A: Aspose.Page в первую очередь предназначен для приложений .NET, однако Aspose предлагает аналогичные библиотеки для Java, C++ и других платформ.

### Q2: Где я могу найти дополнительные примеры и документацию по Aspose.Page для .NET?
A: Вы можете изучить больше примеров и подробную документацию на странице [документация Aspose.Page](https://reference.aspose.com/page/net/).

### Q3: Доступна ли бесплатная пробная версия Aspose.Page для .NET?
A: Да, вы можете получить бесплатную пробную версию Aspose.Page для .NET [здесь](https://releases.aspose.com/).

### Q4: Как я могу получить временную лицензию для Aspose.Page для .NET?
A: Вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

### Q5: Где я могу получить поддержку или обсудить вопросы, связанные с Aspose.Page?
A: Посетите [форумы Aspose.Page](https://forum.aspose.com/c/page/39) для поддержки сообщества и обсуждений.

---

**Последнее обновление:** 2026-06-25  
**Тестировано с:** Aspose.Page 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Как создать документ PostScript с помощью Aspose.Page для .NET](/page/net/document-creation/create-postscript-document/)
- [Сохранить файл PostScript с помощью трансформаций Aspose.Page (.NET)](/page/net/canvas-manipulation/transformationsps/)
- [Создать документ PostScript .NET – добавить прямоугольник с Aspose.Page](/page/net/drawing-shapes/add-rectangle-to-postscript-ps/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}