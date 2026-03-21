---
date: 2026-03-21
description: Узнайте, как создавать XPS‑документы в .NET и добавлять текст с помощью
  Aspose.Page для .NET. Пошаговое руководство для разработчиков .NET.
linktitle: Add Text to XPS Document
second_title: Aspose.Page .NET API
title: Создание XPS‑документа в .NET и добавление текста с помощью Aspose.Page
url: /ru/net/text-manipulation/add-text-to-xps-document/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание XPS-документа .NET и добавление текста с помощью Aspose.Page

В современном .NET-разработке возможность **create XPS document .NET** файлов программно является ценным навыком, особенно когда необходимо генерировать печатные отчёты, счета или пользовательскую графику. Этот учебник покажет, как использовать Aspose.Page для **aspose.page add text** в XPS-документ, предоставляя полный контроль над макетом и стилем — всё из вашего .NET‑приложения.

## Быстрые ответы
- **What does this tutorial cover?** Добавление текста в только что созданный XPS-документ с использованием Aspose.Page для .NET.  
- **How long does it take?** Около 5‑10 минут для базовой реализации.  
- **What are the prerequisites?** Среда разработки .NET и библиотека Aspose.Page.  
- **Is a license required?** Да, для использования в продакшене требуется действительная лицензия Aspose.Page.  
- **Can it run on .NET Core / .NET 6+?** Абсолютно — Aspose.Page поддерживает все современные версии .NET.

## Что такое create xps document .net?

Создание XPS‑документа в .NET означает генерацию файла фиксированного макета, который сохраняет точный вид вашего содержимого на разных устройствах и принтерах. XPS (XML Paper Specification) — открытый стандарт Microsoft для описания страниц, похожий на PDF, но полностью основанный на XML.

## Почему использовать Aspose.Page для добавления текста?

Aspose.Page предоставляет высокоуровневый объектно‑ориентированный API, который абстрагирует низкоуровневую разметку XPS. Вы можете добавлять текст, графику и фигуры без работы с сырым XML, что делает процесс разработки быстрее и менее подверженным ошибкам.

## Предварительные требования

- Aspose.Page for .NET: Убедитесь, что библиотека Aspose.Page установлена. Вы можете скачать её из [Aspose.Page for .NET documentation](https://reference.aspose.com/page/net/).
- Development Environment: Настройте свою среду разработки .NET. Если вы ещё этого не сделали, следуйте инструкциям по установке, приведённым в [documentation](https://reference.aspose.com/page/net/).
- Document Directory: Создайте каталог, в котором будете хранить документы. Замените "Your Document Directory" в приведённом фрагменте кода на фактический путь.

Теперь, когда мы рассмотрели основы, давайте перейдём к коду.

## Импорт пространств имён

Сначала импортируйте необходимые пространства имён, чтобы запустить проект:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Шаг 1: Создание XPS-документа .NET

Создайте новый XPS‑документ, который будет служить холстом для нашего текста.

```csharp
// ExStart:3
string dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
// ExEnd:3
```

## Шаг 2: Создание кисти для текста

Определите сплошную кисть, задающую цвет текста. Здесь мы используем чёрный.

```csharp
// ExStart:4
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
// ExEnd:4
```

## Шаг 3: Добавление глифов (aspose.page add text)

Глифы — это низкоуровневое представление символов в XPS‑документе. Этот вызов добавляет текст «Hello World!» в указанные координаты.

```csharp
// ExStart:5
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
glyphs.Fill = textFill;
// ExEnd:5
```

## Шаг 4: Сохранение полученного XPS‑документа

Сохраните документ на диск, чтобы позже просмотреть или распечатать его.

```csharp
// ExStart:6
doc.Save(dataDir + "AddText_out.xps");
// ExEnd:6
```

Следуя этим шагам, вы успешно **create XPS document .NET** и добавили пользовательский текст с помощью Aspose.Page.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|----------|---------|---------|
| **File not found** при сохранении | `dataDir` указывает на несуществующую папку | Убедитесь, что каталог существует, или используйте `Directory.CreateDirectory(dataDir)` перед сохранением. |
| **Text not visible** | Цвет кисти совпадает с фоном | Измените `Color.Black` на другой контрастный цвет. |
| **Unsupported font** | Шрифт не установлен на машине | Используйте шрифт, который гарантированно присутствует, либо внедрите шрифт с помощью функций встраивания шрифтов Aspose.Page. |

## Часто задаваемые вопросы

### Q1: Можно ли настроить шрифт и размер добавленного текста?

A1: Да, вы полностью контролируете шрифт и размер. Соответственно настройте параметры в методе `AddGlyphs`.

### Q2: Совместима ли Aspose.Page с .NET Core?

A2: Абсолютно! Aspose.Page поддерживает .NET Core, обеспечивая совместимость с новейшими технологиями .NET.

### Q3: Есть ли лицензионные требования для использования Aspose.Page?

A3: Да, требуется действительная лицензия. Ознакомьтесь с вариантами лицензирования [здесь](https://purchase.aspose.com/buy).

### Q4: Как получить поддержку или помощь?

A4: Посетите [Aspose.Page forum](https://forum.aspose.com/c/page/39), чтобы связаться с сообществом и получить помощь.

### Q5: Доступна ли бесплатная пробная версия?

A5: Конечно! Вы можете получить бесплатную пробную версию [здесь](https://releases.aspose.com/).

**Дополнительные вопросы и ответы**

**Q: Можно ли добавить несколько текстовых блоков на одной странице?**  
A: Да, просто вызывайте `doc.AddGlyphs` несколько раз с разными координатами.

**Q: Позволяет ли Aspose.Page вращать текст?**  
A: Вы можете применить матрицу преобразования к объекту `XpsGlyphs`, чтобы вращать или наклонять текст.

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

**Последнее обновление:** 2026-03-21  
**Тестировано с:** Aspose.Page 24.11 for .NET  
**Автор:** Aspose  

---