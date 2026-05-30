---
date: 2026-01-18
description: Узнайте, как создавать PostScript‑документы в .NET и добавлять прямоугольники
  с помощью Aspose.Page для .NET. Пошаговое руководство с примерами кода.
linktitle: Add Rectangle to PostScript (PS)
second_title: Aspose.Page .NET API
title: Создание PostScript‑документа в .NET – Добавление прямоугольника с помощью
  Aspose.Page
url: /ru/net/drawing-shapes/add-rectangle-to-postscript-ps/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить прямоугольник в PostScript (PS) с помощью Aspose.Page для .NET

## Введение

Если вы хотите **создать документ PostScript в .NET**, Aspose.Page предоставляет мощное решение для работы с файлами PostScript. В этом руководстве мы покажем, как добавить прямоугольники в документ PostScript с помощью Aspose.Page для .NET, предоставив вам прочную основу для создания более сложной графики.

## Быстрые ответы
- **Какую библиотеку мне нужно?** Aspose.Page for .NET.
- **Могу ли я создать документ PostScript с нуля?** Да — API позволяет программно создавать PS‑файлы.
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; для продакшн‑использования требуется лицензия.
- **Сколько времени занимает реализация?** Обычно менее 10 минут для базовых фигур.

## Что значит создание документа PostScript в .NET?
Создание документа PostScript в .NET означает программную генерацию файла .ps, описывающего содержимое страницы — текст, графику или фигуры — с использованием API Aspose.Page. Такой подход идеален для серверной генерации графики, автоматического создания отчетов или любых сценариев, где требуется точный контроль над форматом вывода.

## Почему использовать Aspose.Page для .NET?
- **Полный контроль над графикой** — рисуйте фигуры, задавайте цвета и применяйте обводки без работы с низкоуровневым синтаксисом PS.  
- **Кроссплатформенный** — работает в средах Windows, Linux и macOS.  
- **Без внешних зависимостей** — библиотека самостоятельно генерирует весь PS.  
- **Богатая документация и примеры** — быстро начните работу.

## Требования

- **Aspose.Page for .NET Library** — скачайте и установите с [here](https://releases.aspose.com/page/net/).
- **Среда разработки** — Visual Studio, VS Code или любой совместимый с .NET IDE.

## Импорт пространств имён

Before you start coding, import the namespaces that expose the required classes:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Теперь разобьем пример на чёткие, пронумерованные шаги.

## Шаг 1: Настройте каталог документа

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

Замените `"Your Document Directory"` на папку, в которой вы хотите сохранить полученный PS‑файл.

## Шаг 2: Создайте поток вывода для документа PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Этот поток указывает на **AddRectangle_outPS.ps**. При необходимости можете переименовать файл или изменить расположение.

## Шаг 3: Установите параметры сохранения и создайте документ PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1‑paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Здесь мы указываем Aspose.Page использовать размер страницы A4 и создать документ из одной страницы.

## Шаг 4: Добавьте заполненный прямоугольник

```csharp
//Create graphics path from the first rectangle
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Fill the rectangle
document.Fill(path);
```

Мы определяем прямоугольник в точке (250, 100) шириной 150 и высотой 100, задаём оранжевую кисть и заполняем фигуру.

## Шаг 5: Добавьте контурный прямоугольник

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

## Шаг 6: Закройте страницу и сохраните документ

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Закрытие страницы завершает рисование, а `Save()` записывает PS‑файл на диск.

## Распространённые проблемы и советы

- **Неправильный путь к файлу** — убедитесь, что `dataDir` заканчивается разделителем пути (`\\` или `/`) или используйте `Path.Combine`.  
- **Отсутствует лицензия** — в продакшн‑среде примените вашу лицензию Aspose перед созданием документа, чтобы избежать водяных знаков оценки.  
- **Невидимость цвета** — если прямоугольник выглядит пустым, проверьте, что цвета кисти или пера контрастируют с фоном страницы.

## Часто задаваемые вопросы

**В:** Могу ли я настроить цвета прямоугольников?  
**О:** Конечно. Измените значения `Color.Orange` или `Color.Red` в конструкторах `SolidBrush` и `Pen` на любой `System.Drawing.Color`, который вам нужен.

**В:** Совместим ли Aspose.Page с другими форматами документов?  
**О:** Да. Помимо PostScript, Aspose.Page также поддерживает генерацию XPS и EPS.

**В:** Как добавить текст в тот же документ?  
**О:** Используйте класс `TextFragment` для размещения текста в нужных координатах, затем вызовите `document.Draw(textFragment)`.

**В:** Где найти дополнительные примеры и полную справку по API?  
**О:** Изучите документацию [here](https://reference.aspose.com/page/net/) и присоединяйтесь к сообществу на форуме [Aspose.Page forum](https://forum.aspose.com/c/page/39).

**В:** Можно ли попробовать Aspose.Page перед покупкой?  
**О:** Да, скачайте бесплатную пробную версию [here](https://releases.aspose.com/). Для расширенной оценки рассмотрите [temporary license](https://purchase.aspose.com/temporary-license/).

---

**Последнее обновление:** 2026-01-18  
**Тестировано с:** Aspose.Page 24.12 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}