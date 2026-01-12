---
date: 2026-01-12
description: Узнайте, как создавать документы PostScript в .NET с помощью Aspose.Page.
  Это пошаговое руководство показывает, как создавать файлы PostScript, задавать размер
  страницы PostScript и настраивать поля для бесшовной интеграции.
linktitle: Create PostScript Document
second_title: Aspose.Page .NET API
title: Как создать документ PostScript с помощью Aspose.Page для .NET
url: /ru/net/document-creation/create-postscript-document/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как создать документ PostScript с помощью Aspose.Page для .NET

## Введение

Добро пожаловать! В этом всестороннем руководстве вы узнаете **как создавать документы PostScript** программно с помощью Aspose.Page для .NET. Независимо от того, генерируете ли вы счета‑фактуры, транспортные этикетки или любой векторный печатный вывод, это руководство проведёт вас через каждый шаг — от настройки окружения до сохранения окончательного файла *.ps*. Давайте погрузимся и посмотрим, как легко создать качественный файл PostScript всего в несколько строк C#.

## Краткие ответы
- **Какая библиотека нужна?** Aspose.Page для .NET  
- **Можно ли задать размер страницы?** Да — используйте `options.PageSize` (см. «установить размер страницы PostScript»).  
- **Нужна ли лицензия для разработки?** Бесплатная пробная версия подходит для тестирования; для продакшна требуется лицензия.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Сколько времени занимает реализация?** Обычно менее 10 минут для базового документа.

## Что такое «как создать PostScript» в .NET?
Aspose.Page предоставляет богатый API, который абстрагирует низкоуровневый синтаксис EPS/PostScript, позволяя сосредоточиться на макете страницы, графике и тексте. Используя библиотеку, вы избегаете ручного написания кода PS и получаете поддержку шрифтов, изображений и точных измерений.

## Почему использовать Aspose.Page для создания PostScript?
- **Полный контроль** над размерами страницы, полями и графическими примитивами.  
- **Без внешних зависимостей** — всё работает внутри вашего процесса .NET.  
- **Кроссплатформенная** поддержка для Windows, Linux и macOS.  
- **Надёжная работа со шрифтами**, включая пользовательские папки шрифтов.

## Требования

- Aspose.Page для .NET Library: Убедитесь, что библиотека Aspose.Page для .NET установлена. Вы можете скачать её [здесь](https://releases.aspose.com/page/net/).
- .NET Environment: Убедитесь, что у вас настроена рабочая среда .NET.
- Text Editor or IDE: Используйте предпочитаемый текстовый редактор или интегрированную среду разработки (IDE) для написания кода.

Теперь, когда всё готово, давайте начнём создавать документ.

## Импорт пространств имён

Сначала импортируйте пространства имён, которые дают доступ к основным классам Aspose.Page.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.IO;
```

Эти пространства имён предоставляют `PsDocument`, `PsSaveOptions` и вспомогательные классы, используемые в течение всего руководства.

## Шаг 1: Установить каталог документа

```csharp
string dir = "Your Document Directory";
```

Замените `"Your Document Directory"` на абсолютный или относительный путь, где вы хотите сохранить окончательный **PostScript**‑файл.

## Шаг 2: Создать поток вывода

```csharp
using (Stream outPsStream = new FileStream(dir + "document.ps", FileMode.Create))
```

`FileStream` открывает поток записи с именем **document.ps**. Все последующие команды рисования будут записаны в этот поток.

## Шаг 3: Создать параметры сохранения

```csharp
PsSaveOptions options = new PsSaveOptions();
```

`PsSaveOptions` позволяет настроить, как документ будет отрисован и сохранён.

## Шаг 4: Установить размер страницы PostScript и поля

```csharp
options.PageSize = PageConstants.GetSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT);
options.Margins = PageConstants.GetMargins(PageConstants.MARGINS_ZERO);
```

Здесь мы **устанавливаем размер страницы PostScript** на A4 в портретной ориентации и убираем все поля. Вы можете заменить `SIZE_A4` другими константами (например, `SIZE_LETTER`), чтобы соответствовать требованиям вашего макета.

## Шаг 5: Установить дополнительные папки шрифтов

```csharp
options.AdditionalFontsFolders = new string[] { dir };
```

Если ваш документ использует пользовательские шрифты, которые не установлены в системе, укажите Aspose.Page папку, содержащую эти файлы шрифтов.

## Шаг 6: Создать многостраничный документ

```csharp
bool multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

Экземпляр `PsDocument` представляет документ PostScript. Установка `multiPaged` в `false` создаёт одностраничный документ (можно переключить на `true` для многостраничного вывода).

## Шаг 7: Закрыть и сохранить

```csharp
document.ClosePage();
document.Save();
```

Вызов `ClosePage()` завершает содержимое страницы, а `Save()` записывает полностью сформированный поток PostScript на диск.

Поздравляем! Вы только что узнали **как создавать документы PostScript** с помощью Aspose.Page для .NET.

## Распространённые проблемы и решения

- **Ошибки пути к файлу** — Убедитесь, что переменная `dir` заканчивается разделителем пути (`\` или `/`) или используйте `Path.Combine`.
- **Отсутствуют шрифты** — Если текст отображается стандартными шрифтами, проверьте, что `options.AdditionalFontsFolders` указывает на правильный каталог.
- **Неправильный размер страницы** — Дважды проверьте константы, передаваемые в `PageConstants.GetSize`; также можно задать пользовательские размеры через `new SizeF(width, height)`.

## Часто задаваемые вопросы

### Q1: Где можно найти документацию по Aspose.Page для .NET?
A1: Документация доступна [здесь](https://reference.aspose.com/page/net/).

### Q2: Как скачать Aspose.Page для .NET?
A2: Вы можете скачать её по [этой ссылке](https://releases.aspose.com/page/net/).

### Q3: Где можно приобрести лицензию на Aspose.Page для .NET?
A3: Приобрести лицензию можно [здесь](https://purchase.aspose.com/buy).

### Q4: Есть ли бесплатная пробная версия Aspose.Page для .NET?
A4: Да, бесплатную пробную версию можно найти [здесь](https://releases.aspose.com/).

### Q5: Как получить временную лицензию для Aspose.Page для .NET?
A5: Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

### Q6: Могу ли я генерировать многостраничные файлы PostScript?
A6: Конечно. Установите `bool multiPaged = true` при создании `PsDocument` и вызывайте `document.NewPage()` для каждой дополнительной страницы.

### Q7: Поддерживает ли Aspose.Page управление цветом?
A7: Да, при необходимости можно внедрять ICC‑профили через `PsSaveOptions.ColorProfile`.

---

**Последнее обновление:** 2026-01-12  
**Тестировано с:** Aspose.Page 24.11 для .NET  
**Автор:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}