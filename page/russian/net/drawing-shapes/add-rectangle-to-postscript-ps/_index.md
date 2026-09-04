---
date: 2026-06-30
description: Узнайте, как создать документ PostScript .NET и добавить прямоугольники
  с помощью Aspose.Page для .NET. Пошаговое руководство с примерами кода.
keywords:
- create postscript document .net
- how to generate postscript file
- Aspose.Page rectangle
linktitle: Добавить прямоугольник в PostScript (PS)
schemas:
- author: Aspose
  dateModified: '2026-06-30'
  description: Learn how to create postscript document .net and add rectangles using
    Aspose.Page for .NET. Step‑by‑step guide with code samples.
  headline: Create PostScript Document .NET – Add Rectangle Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page for .NET.
    question: What library do I need?
  - answer: Yes – the API lets you build PS files programmatically.
    question: Can I create a PostScript document from scratch?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Which .NET versions are supported?
  - answer: A free trial works for testing; a license is required for production.
    question: Do I need a license for development?
  - answer: Typically under 10 minutes for basic shapes.
    question: How long does the implementation take?
  type: FAQPage
second_title: Aspose.Page .NET API
title: Создать документ PostScript .NET – Добавить прямоугольник Aspose.Page
url: /ru/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить прямоугольник в PostScript (PS) с помощью Aspose.Page для .NET

## Введение

Aspose.Page for .NET — это библиотека, позволяющая программно создавать и изменять файлы PostScript, EPS и XPS. Если вы ищете **create postscript document .net**, это руководство проведёт вас через процесс добавления прямоугольников в документ PostScript с использованием Aspose.Page, предоставляя прочную основу для более сложной генерации графики.

## Быстрые ответы
- **Какую библиотеку мне нужно?** Aspose.Page for .NET.  
- **Могу ли я создать документ PostScript с нуля?** Да — API позволяет программно создавать PS‑файлы.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; для продакшна требуется лицензия.  
- **Сколько времени занимает реализация?** Обычно менее 10 минут для базовых фигур.

## Что такое создание postscript документа .net?
Создание документа PostScript в .NET означает программную генерацию файла `.ps`, описывающего содержимое страницы — текст, графику или фигуры — с помощью API Aspose.Page. Такой подход идеален для серверной генерации графики, автоматического создания отчётов или любых сценариев, где требуется точный контроль над форматом вывода.

## Почему использовать Aspose.Page для .NET?
Aspose.Page поддерживает **30+ графических примитивов** и может генерировать файлы размером до **500 МБ** без загрузки всего документа в память, обеспечивая высокопроизводительный рендеринг на Windows, Linux и macOS. Библиотека даёт полный контроль над фигурами, цветами и обводками, устраняя необходимость писать низкоуровневый код PostScript.

- **Полный контроль над графикой** — рисуйте фигуры, задавайте цвета и применяйте обводки без работы с низкоуровневым синтаксисом PS.  
- **Кроссплатформенность** — работает в средах Windows, Linux и macOS.  
- **Отсутствие внешних зависимостей** — библиотека полностью обрабатывает генерацию PS.  
- **Богатая документация и примеры** — быстро начните работу.

## Требования

- **Aspose.Page for .NET Library** — загрузите и установите её с [here](https://releases.aspose.com/page/net/).  
- **Среда разработки** — Visual Studio, VS Code или любой совместимый с .NET IDE.

## Импорт пространств имён

Пространство имён `Aspose.Page` предоставляет основные классы, которые вам понадобятся, такие как `Document`, `Page`, `SolidBrush` и `Pen`. Импортируйте его перед тем, как начать писать код.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Шаг 1: Настройте каталог документа

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Замените `"Your Document Directory"` на папку, в которой вы хотите сохранить полученный PS‑файл.

## Шаг 2: Создайте поток вывода для документа PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Этот поток указывает на **AddRectangle_outPS.ps**. При желании переименуйте файл или измените расположение.

## Шаг 3: Установите параметры сохранения и создайте документ PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Здесь мы указываем Aspose.Page использовать размер страницы A4 и создавать одностраничный документ.

## Шаг 4: Добавьте заполненный прямоугольник

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Мы определяем прямоугольник в точке (250, 100) шириной 150 и высотой 100, задаём оранжевую кисть и заполняем форму.

## Шаг 5: Добавьте прямоугольник с обводкой

```csharp
//Create graphics path from the second rectangle
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Stroke (outline) the rectangle
document.Draw(path);
```

Второй прямоугольник создаётся ниже на странице, на этот раз с красной обводкой толщиной 3 пункта.

## Шаг 6: Закройте страницу и сохраните документ

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Закрытие страницы завершает рисование, а `Save()` записывает PS‑файл на диск.

## Как создать postscript документ .net?
`Document` — основной класс, представляющий файл PostScript в Aspose.Page. `SaveOptions` задаёт параметры, такие как размер страницы и формат вывода. Загрузите объект `Document`, настройте `SaveOptions` для страницы A4, нарисуйте фигуры с помощью `SolidBrush` или `Pen`, затем вызовите `document.Save()` — весь процесс занимает всего несколько строк кода и работает на любой поддерживаемой платформе .NET. Этот подход позволяет генерировать полностью совместимые файлы PostScript без необходимости писать сырой код PS.

## Как сгенерировать файл postscript
Используйте класс `SaveOptions` Aspose.Page, чтобы указать формат вывода как PostScript (`SaveFormat.PS`). Библиотека напрямую передаёт содержимое в файл или поток памяти, позволяя эффективно создавать большие документы без избыточного потребления памяти.

## Распространённые проблемы и советы

- **Неправильный путь к файлу** — Убедитесь, что `dataDir` заканчивается разделителем пути (`\\` или `/`) или используйте `Path.Combine`.  
- **Отсутствие лицензии** — В продакшн‑среде примените вашу лицензию Aspose перед созданием документа, чтобы избежать водяных знаков оценки.  
- **Видимость цвета** — Если прямоугольник выглядит пустым, проверьте, контрастируют ли цвета кисти или пера с фоном страницы.

## Часто задаваемые вопросы

**Q:** Могу ли я настроить цвета прямоугольников?  
**A:** Конечно. Измените значения `Color.Orange` или `Color.Red` в конструкторах `SolidBrush` и `Pen` на любой `System.Drawing.Color`, который вам нужен.

**Q:** Совместима ли Aspose.Page с другими форматами документов?  
**A:** Да. Помимо PostScript, Aspose.Page также поддерживает генерацию XPS и EPS.

**Q:** Как добавить текст в тот же документ?  
**A:** Используйте класс `TextFragment`, чтобы разместить текст в нужных координатах, затем вызовите `document.Draw(textFragment)`.

**Q:** Где найти дополнительные примеры и полную справку по API?  
**A:** Изучите документацию [here](https://reference.aspose.com/page/net/) и присоединяйтесь к сообществу на форуме [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**Q:** Можно ли попробовать Aspose.Page перед покупкой?  
**A:** Да, загрузите бесплатную пробную версию [here](https://releases.aspose.com/). Для длительной оценки рассмотрите [temporary license](https://purchase.aspose.com/temporary-license/).

---

**Последнее обновление:** 2026-06-30  
**Тестировано с:** Aspose.Page 24.12 for .NET  
**Автор:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Связанные руководства

- [Как создать документ PostScript с Aspose.Page для .NET](/page/net/document-creation/create-postscript-document/)
- [Добавить изображение в документ PostScript (PS) с Aspose.Page](/page/net/image-management/add-image-to-postscript-ps-document/)
- [Добавить текст в документ PostScript (PS) с Aspose.Page](/page/net/text-manipulation/add-text-to-postscript-ps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}