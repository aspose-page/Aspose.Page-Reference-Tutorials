---
date: 2026-07-10
description: Узнайте, как aspose.page create xps документы с использованием Aspose.Page
  for .NET – пошаговое руководство по созданию высококачественных XPS‑файлов.
keywords:
- aspose.page create xps
- XPS document generation
- Aspose.Page .NET
lastmod: 2026-07-10
linktitle: Создать XPS‑документ
og_description: aspose.page create xps быстро с Aspose.Page for .NET. Следуйте этому
  руководству, чтобы создавать высококачественные XPS‑файлы менее чем за 20 строк
  кода.
og_image_alt: 'Guide: Create XPS document using Aspose.Page for .NET'
og_title: aspose.page create xps – Создание XPS‑документов с .NET
schemas:
- author: Aspose
  dateModified: '2026-07-10'
  description: Learn how to aspose.page create xps documents using Aspose.Page for
    .NET – a step‑by‑step guide to generate high‑quality XPS files.
  headline: aspose.page create xps – Generate XPS Documents with .NET
  type: TechArticle
- questions:
  - answer: Yes. Provide the exact font family name when calling `AddGlyphs`; the
      font must be installed on the runtime machine.
    question: Can I use custom fonts in my XPS document?
  - answer: Absolutely. The library works on .NET Core 3.1, .NET 5, .NET 6 and later,
      enabling cross‑platform XPS generation.
    question: Is Aspose.Page compatible with .NET Core?
  - answer: Use the `AddImage` method of the `XpsPage` class. The API accepts PNG,
      JPEG, BMP, and GIF formats.
    question: How do I add images to an XPS document?
  - answer: Yes. Instantiate multiple `XpsPage` objects, populate each with glyphs
      or images, and then save the document once.
    question: Can I create multi‑page XPS documents?
  - answer: Yes, you can explore the full feature set by downloading the [free trial](https://releases.aspose.com/).
    question: Is there a trial version available?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- aspose.page
- create xps
- XPS document
- .NET document generation
title: aspose.page create xps – Создание XPS‑документов с .NET
url: /ru/net/document-creation/create-xps-document/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose.page create xps – Создание XPS документа с Aspose.Page для .NET

## Введение

В этом руководстве вы научитесь создавать документы **aspose.page create xps** шаг за шагом, используя библиотеку Aspose.Page для .NET. Независимо от того, создаёте ли вы движок отчетности, генератор счетов или любую систему, требующую высококачественных электронных документов, XPS — надёжный формат на основе XML, сохраняющий макет на разных платформах. Мы пройдём всё от предварительных требований до сохранения конечного файла, предоставив практические советы, которые вы сможете сразу применить.

## Быстрые ответы

- **Какая библиотека нужна?** Aspose.Page for .NET  
- **Можно ли запускать это на .NET Core?** Да — полностью поддерживается на .NET Core 3.1, .NET 5, .NET 6 и более новых версиях  
- **Сколько строк кода?** Менее 20 строк для базового XPS‑файла «Hello World»  
- **Нужна ли лицензия для тестирования?** Бесплатная пробная версия подходит для разработки; лицензия требуется для продакшн‑развёртываний  
- **В каком формате вывод?** XPS (XML Paper Specification)  

## Как создать XPS документ с помощью Aspose.Page для .NET?

Загрузите библиотеку Aspose.Page, создайте экземпляр `XpsDocument`, добавьте одну страницу с глифами, задайте цвет заливки и вызовите `Save`. Этот полный рабочий процесс требует всего несколько вызовов методов и генерирует XPS‑файл, соответствующий стандартам, который можно открыть в Windows Reader, Adobe Acrobat или любом просмотрщике, поддерживающем XPS. Подход работает на Windows, Linux и macOS без дополнительных зависимостей.

## Что такое aspose.page create xps?

`aspose.page create xps` относится к процессу программного создания файла XPS (XML Paper Specification) с использованием API Aspose.Page для .NET. API абстрагирует низкоуровневые структуры PDF/XPS, позволяя сосредоточиться на содержимом, а не на тонкостях формата файла. Он поддерживает установку размера страницы, шрифтов, цветов и встраивание изображений, позволяя разработчикам создавать богатые печатные документы напрямую из кода.

## Зачем использовать Aspose.Page для генерации XPS?

Aspose.Page поддерживает **более 30 форматов вывода** и может рендерить XPS‑файлы размером до **500 МБ** без загрузки всего документа в память, обеспечивая высокую производительность в серверных нагрузках. Библиотека гарантирует пиксель‑точную точность макета, автоматическое встраивание шрифтов и полную поддержку Unicode, устраняя необходимость в сторонних конвертерах.

## Требования

Перед тем как перейти к коду, убедитесь, что у вас есть следующее:

1. **Aspose.Page for .NET Library** – загрузите её по [download link](https://releases.aspose.com/page/net/).  
2. **Target Directory** – определите, куда будет сохраняться сгенерированный XPS‑файл на вашем компьютере.  

Теперь, когда среда готова, импортируем необходимые пространства имён.

## Импорт пространств имён

Чтобы использовать Aspose.Page для .NET, необходимо импортировать необходимые пространства имён в ваш проект. Выполните следующие шаги:

### Шаг 1: Добавить ссылку на Aspose.Page

В вашем проекте добавьте ссылку на библиотеку Aspose.Page for .NET. Требуемый DLL находится в загруженном пакете.

### Шаг 2: Импортировать пространства имён

Включите следующие пространства имён в ваш файл кода:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
```

## Шаг 1: Установить каталог документа

Переменная `directoryPath` указывает API, куда записать полученный XPS‑файл.

```csharp
string dir = "Your Document Directory";
```

Замените `"Your Document Directory"` на фактический путь к папке в вашей системе, например, `C:\\Docs\\Output`.

## Шаг 2: Создать XPS документ

Класс `XpsDocument` представляет корневой объект XPS‑файла.

```csharp
XpsDocument xDocs = new XpsDocument();
```

Инициализируйте его именем целевого файла, и новая страница будет создана автоматически.

## Шаг 3: Добавить глифы в документ

Метод `AddGlyphs` вставляет текст (глифы) на текущую страницу.

```csharp
var glyphs = xDocs.AddGlyphs("Arial", 12, FontStyle.Regular, 300f, 450f, "Hello World!");
```

Вы можете управлять семейством шрифта, размером, стилем и точными координатами, чтобы точно разместить текст.

## Шаг 4: Установить цвет заливки глифов

Метод `SetFillColor` определяет кисть, используемую для рисования глифов.

```csharp
glyphs.Fill = xDocs.CreateSolidColorBrush(Color.Black);
```

В этом примере мы используем чёрный (`Color.Black`), но поддерживается любой цвет ARGB.

## Шаг 5: Сохранить результат

Вызов `Save` записывает XPS‑документ на диск.

```csharp
xDocs.Save(dir + "output.xps");
```

Файл будет содержать текст «Hello World!», который вы добавили на предыдущих шагах.

## Общие советы и подводные камни

- **Путь к каталогу** – используйте `Path.Combine(dir, "output.xps")`, чтобы избежать отсутствия разделителей пути в Windows, Linux или macOS.  
- **Наличие шрифта** – указанный шрифт должен быть установлен на хост‑машине; иначе Aspose заменит его резервным шрифтом, что может повлиять на макет.  
- **Несколько страниц** – для вывода многостраничного документа создавайте дополнительные объекты `XpsPage`, добавляйте контент в каждый и затем вызывайте `Save` один раз.  

## Часто задаваемые вопросы

**Q: Можно ли использовать пользовательские шрифты в моём XPS документе?**  
A: Да. Укажите точное название семейства шрифта при вызове `AddGlyphs`; шрифт должен быть установлен на машине выполнения.

**Q: Совместима ли Aspose.Page с .NET Core?**  
A: Абсолютно. Библиотека работает на .NET Core 3.1, .NET 5, .NET 6 и более новых версиях, позволяя генерировать XPS кросс‑платформенно.

**Q: Как добавить изображения в XPS документ?**  
A: Используйте метод `AddImage` класса `XpsPage`. API принимает форматы PNG, JPEG, BMP и GIF.

**Q: Можно ли создавать многостраничные XPS документы?**  
A: Да. Создайте несколько объектов `XpsPage`, заполните каждый глифами или изображениями, а затем сохраните документ один раз.

**Q: Доступна ли пробная версия?**  
A: Да, вы можете ознакомиться с полным набором функций, загрузив [бесплатную пробную версию](https://releases.aspose.com/).

## Заключение

Теперь у вас есть полный готовый к продакшн рабочий процесс для создания документов **aspose.page create xps** с использованием Aspose.Page для .NET. Экспериментируйте с разными шрифтами, цветами и макетами страниц, чтобы адаптировать вывод под потребности вашего приложения. Для более сложных сценариев — например, встраивания векторной графики или обработки больших пакетных заданий — обратитесь к официальной справке API.

---

**Последнее обновление:** 2026-07-10  
**Тестировано с:** Aspose.Page 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Добавить текст в XPS документ с Aspose.Page для .NET](/page/net/text-manipulation/add-text-to-xps-document/)
- [Добавить изображение в XPS документ с Aspose.Page для .NET](/page/net/image-management/add-image-to-xps-document/)
- [Добавить прямоугольник в XPS документ с Aspose.Page для .NET](/page/net/drawing-shapes/add-rectangle-to-xps-document/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}