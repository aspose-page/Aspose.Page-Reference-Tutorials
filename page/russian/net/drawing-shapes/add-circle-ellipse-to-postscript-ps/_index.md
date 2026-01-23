---
date: 2026-01-23
description: Узнайте, как генерировать файл PostScript и добавлять эллипсы с помощью
  Aspose.Page для .NET. Следуйте этому пошаговому руководству, чтобы быстро нарисовать
  эллипс с помощью кода C#.
linktitle: Add Circle Ellipse to PostScript (PS)
second_title: Aspose.Page .NET API
title: Создать файл PostScript и добавить круг и эллипс – Aspose.Page
url: /ru/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание файла PostScript и добавление эллипса‑круга – Aspose.Page

## Введение

В этом учебнике вы узнаете **как создать файл PostScript** и внедрить идеальный эллипс‑круг с помощью Aspose.Page .NET API. Независимо от того, создаёте ли вы движок отчётности, векторную графику или вам нужно программно нарисовать эллипс в C#, это руководство проведёт вас через каждый шаг — от настройки окружения до сохранения готового PS‑документа.

## Быстрые ответы
- **Что покрывает этот учебник?** Добавление двух эллипсов (заполненного и обведённого) в файл PostScript с помощью Aspose.Page для .NET.  
- **Какой основной ключевой запрос?** *generate postscript file*.  
- **Нужна ли лицензия?** Бесплатная пробная версия подходит для разработки; коммерческая лицензия требуется для продакшна.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Сколько времени занимает реализация?** Около 10‑15 минут для базового примера эллипса.

## Что означает “generate postscript file”?

Создание файла PostScript означает программное формирование .ps‑документа, описывающего содержимое страницы с использованием языка PostScript. Этот формат широко используется для печати, графического дизайна и конвертации в PDF.

## Почему добавить эллипс‑круг с помощью Aspose.Page?

- **Точность** – Векторная отрисовка обеспечивает масштабирование без потерь.  
- **Кросс‑платформенность** – Один и тот же PS‑файл может быть отрисован на любом принтере, совместимом с PostScript.  
- **Удобно для C#** – API абстрагирует низкоуровневые PS‑команды, позволяя вам *draw ellipse* с привычными типами .NET.

## Требования

Перед тем как приступить, убедитесь, что у вас есть:

1. **Aspose.Page for .NET** – Скачайте и установите библиотеку с [here](https://releases.aspose.com/page/net/).  
2. **Среда разработки .NET** – Visual Studio, Rider или установленный .NET CLI на вашем компьютере.

Теперь, когда всё готово, давайте начнём кодировать.

## Импорт пространств имён

Сначала подключите необходимые пространства имён, чтобы классы Aspose.Page были доступны.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Пошаговое руководство

### Шаг 1: Установить каталог документа

```csharp
// ExStart:1
// The path to the documents directory.
string dataDir = "Your Document Directory";
```

> **Совет:** Замените `"Your Document Directory"` на абсолютный или относительный путь, в который ваше приложение может записывать.

### Шаг 2: Создать поток вывода для документа PostScript

```csharp
//Create output stream for PostScript document
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

`FileStream` открывает (или создаёт) *AddEllipse_outPS.ps*, куда будет сохранено сгенерированное содержимое PS.

### Шаг 3: Создать параметры сохранения и документ PS

```csharp
//Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();

// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

Здесь мы указываем размер страницы A4 и создаём одностраничный `PsDocument`.

### Шаг 4: Создать графический путь для первого эллипса

```csharp
//Create graphics path from the first ellipse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

`GraphicsPath` хранит геометрическое определение эллипса, расположенного в точке (250, 100) с шириной 150 pt и высотой 100 pt.

### Шаг 5: Установить заливку и заполнить эллипс

```csharp
//Set paint
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Fill the ellipse
document.Fill(path);
```

Мы заполняем первый эллипс ярким оранжевым цветом.

### Шаг 6: Создать графический путь для второго эллипса

```csharp
//Create graphics path from the second ellipse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

Второй эллипс определён ниже на странице (координата y = 300).

### Шаг 7: Установить обводку и нарисовать эллипс

```csharp
//Set stroke
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Stroke (outline) the ellipse
document.Draw(path);
```

На этот раз мы *draw ellipse* с помощью красной ручки толщиной 3 pt, получая обведённый контур.

### Шаг 8: Закрыть текущую страницу и сохранить документ

```csharp
//Close current page
document.ClosePage();

//Save the document
document.Save();
```

Закрытие страницы завершает содержимое, а `Save()` записывает вывод PostScript в ранее созданный поток.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|---------|
| **Файл не создан** | ``dataDir`` указывает на несуществующую папку. | Убедитесь, что каталог существует, или используйте `Directory.CreateDirectory(dataDir);` перед открытием потока. |
| **Эллипс выглядит искажённым** | Неправильные размеры прямоугольника (ширина ≠ высота). | Используйте одинаковую ширину и высоту для идеального круга; скорректируйте значения `RectangleF` соответственно. |
| **Исключение лицензии** | Запуск без действующей лицензии Aspose.Page в продакшн‑среде. | Примените временную или постоянную лицензию, как описано в документации Aspose. |

## Часто задаваемые вопросы

**Q: Можно ли использовать Aspose.Page для .NET с другими форматами документов?**  
A: Aspose.Page в основном ориентирован на PostScript, но Aspose предлагает дополнительные библиотеки для PDF, DOCX и других форматов. См. [Aspose documentation](https://reference.aspose.com/page/net/) для полного списка.

**Q: Где можно найти дополнительную поддержку и обсуждения сообщества?**  
A: Посетите [Aspose.Page forum](https://forum.aspose.com/c/page/39), чтобы задавать вопросы, делиться примерами и получать помощь от других разработчиков.

**Q: Есть ли бесплатная пробная версия Aspose.Page?**  
A: Да, вы можете скачать бесплатную пробную версию со страницы [free trial](https://releases.aspose.com/) для оценки библиотеки перед покупкой.

**Q: Как получить временную лицензию для тестирования?**  
A: Временную лицензию можно запросить [здесь](https://purchase.aspose.com/temporary-license/); она действительна 30 дней.

**Q: Где можно приобрести полную лицензию Aspose.Page?**  
A: Варианты покупки указаны на официальной [buy page](https://purchase.aspose.com/buy).

## Заключение

Теперь вы знаете, как **создать файл PostScript** и **рисовать формы эллипса** с помощью Aspose.Page для .NET. Следуя описанным шагам, вы легко интегрируете векторную графику в любой процесс печати или рендеринга. Экспериментируйте с разными цветами, толщинами линий и позициями, чтобы создавать более сложные иллюстрации.

---

**Последнее обновление:** 2026-01-23  
**Тестировано с:** Aspose.Page 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}