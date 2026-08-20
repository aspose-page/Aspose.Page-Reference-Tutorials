---
date: 2026-03-21
description: Узнайте, как добавить Unicode‑текст в документ XPS с помощью Aspose.Page
  для .NET. Это руководство покажет, как создать документ XPS на C# и добавить текст
  с Unicode‑строками с помощью Aspose.Page.
linktitle: Add Text with Unicode String to XPS Document
second_title: Aspose.Page .NET API
title: Как добавить Unicode‑текст в XPS‑документ с помощью Aspose.Page
url: /ru/net/text-manipulation/add-text-with-unicode-string-to-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как добавить Unicode‑текст в документ XPS с помощью Aspose.Page

## Введение

Если вам нужно **how to add unicode** символы в файл XPS, вы попали по адресу. В этом руководстве мы пройдем точные шаги, необходимые для **create XPS document C#**‑style с использованием Aspose.Page for .NET и продемонстрируем возможность **aspose page add text** с Unicode‑строкой. К концу у вас будет полностью функционирующий документ XPS, который правильно отображает Unicode‑текст справа налево (RTL).

## Быстрые ответы
- **Что покрывает руководство?** Adding Unicode text to an XPS document with Aspose.Page for .NET.  
- **Какой язык используется?** C# (compatible with .NET Framework and .NET Core).  
- **Нужна ли лицензия?** A free trial works for development; a commercial license is required for production.  
- **Можно ли изменить шрифт или размер?** Yes – the example uses Arial 20 pt, but any installed font works.  
- **Включена ли поддержка RTL?** Setting `BidiLevel = 1` enables right‑to‑left rendering for Unicode strings.

## Что такое “how to add unicode” в XPS?

Добавление Unicode‑текста означает вставку символов из любого языка — арабского, иврита, китайского и т.д. — в документ XPS. Класс `XpsGlyphs` из Aspose.Page обрабатывает низкоуровневое размещение глифов, а свойство `BidiLevel` управляет направлением текста для RTL‑скриптов.

## Почему использовать Aspose.Page для добавления текста?

- **Полная интеграция с .NET** – работает с .NET Framework, .NET Core, .NET 5/6+.  
- **Отсутствие внешних зависимостей** – чистый управляемый код, без COM‑interop.  
- **Поддержка расширенной типографии** – шрифты, стили, цвета и двунаправленный текст.  
- **Высокая производительность** – быстро создает и сохраняет файлы XPS, идеально подходит для генерации на сервере.

## Требования

- Базовые знания C# и разработки на .NET.  
- Visual Studio (любая современная версия).  
- Библиотека Aspose.Page for .NET – скачайте её по ссылке [here](https://releases.aspose.com/page/net/).

## Импорт пространств имён

Сначала импортируйте пространства имён, которые дают доступ к модели XPS и утилитам рисования.

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Шаг 1: Настройка документа – create XPS document C#

Создайте новый документ XPS, который будет содержать Unicode‑текст.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

## Шаг 2: Добавление Unicode‑текста – aspose page add text

Теперь добавим фактическую Unicode‑строку. В этом примере мы используем шрифт Arial, размер 20, и размещаем текст в позиции (400 f, 200 f). `BidiLevel` со значением 1 указывает рендереру обрабатывать строку как справа налево.

```csharp
// Add Text
XpsSolidColorBrush textFill = doc.CreateSolidColorBrush(Color.Black);
XpsGlyphs glyphs = doc.AddGlyphs("Arial", 20, FontStyle.Regular, 400f, 200f, "TEN. rof SPX.esopsA");
glyphs.BidiLevel = 1;
glyphs.Fill = textFill;
```

## Шаг 3: Сохранение документа

Наконец, сохраните файл XPS на диск.

```csharp
// Save resultant XPS document
doc.Save(dataDir + "AddTextRTL_out.xps");
```

Поздравляем! Вы успешно добавили **how to add unicode** текст в документ XPS с помощью Aspose.Page for .NET.

## Распространённые проблемы и решения

| Проблема | Причина | Решение |
|-------|--------|-----|
| Text appears garbled | Font does not support the Unicode range | Use a font that contains the required glyphs (e.g., Arial Unicode MS). |
| RTL text still left‑to‑right | `BidiLevel` not set or set to 0 | Ensure `glyphs.BidiLevel = 1;` for RTL scripts. |
| File not saved | Invalid `dataDir` path | Verify that the directory exists and the app has write permissions. |

## Часто задаваемые вопросы

**Q: Совместима ли Aspose.Page с последними версиями .NET?**  
A: Yes, Aspose.Page is regularly updated to support .NET Framework, .NET Core, and .NET 5/6+.

**Q: Можно ли настроить стиль и размер шрифта при добавлении текста?**  
A: Absolutely! The `AddGlyphs` method lets you specify any font family, size, and `FontStyle` you need.

**Q: Где можно найти дополнительную документацию по Aspose.Page?**  
A: You can refer to the documentation [here](https://reference.aspose.com/page/net/) for comprehensive API details.

**Q: Есть ли бесплатные ресурсы для начала работы с Aspose.Page?**  
A: Yes, explore the community forum at [Aspose.Page forum](https://forum.aspose.com/c/page/39) for tips, examples, and peer support.

**Q: Доступна ли пробная версия перед покупкой?**  
A: Certainly! Download the free trial from [here](https://releases.aspose.com/) to evaluate the library.

---

**Последнее обновление:** 2026-03-21  
**Тестировано с:** Aspose.Page 24.11 for .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}