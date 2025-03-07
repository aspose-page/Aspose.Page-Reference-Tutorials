---
title: Добавьте именованное значение с помощью Aspose.Page
linktitle: Добавить именованное значение
second_title: Aspose.Page .NET API
description: Узнайте, как добавлять именованные значения в файлы EPS в .NET с помощью Aspose.Page. Это подробное руководство шаг за шагом проведет вас через весь процесс.
weight: 12
url: /ru/net/eps-metadata-management/modify-eps-metadata-add-named-value/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавьте именованное значение с помощью Aspose.Page

## Введение

В области обработки документов с помощью .NET Aspose.Page выделяется как мощный инструмент для работы с файлами EPS. Aspose.Page позволяет разработчикам манипулировать метаданными XMP, облегчая такие задачи, как добавление именованных значений. Это руководство шаг за шагом проведет вас через процесс добавления именованных значений в файл EPS с помощью Aspose.Page.

## Предварительные условия

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

- Базовые знания языка программирования C#.
- Установлена интегрированная среда разработки (IDE), например Visual Studio.
-  Aspose.Page для библиотеки .NET. Если он не установлен, вы можете скачать его с[здесь](https://releases.aspose.com/page/net/).

## Импортировать пространства имен

Во-первых, давайте импортируем необходимые пространства имен в ваш код C#. Эти пространства имен жизненно важны для доступа к функциям, предоставляемым Aspose.Page:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Шаг 1. Инициализация входного потока файла EPS

 Первый шаг включает инициализацию входного потока для файла EPS. Заменять`"Your Document Directory"` с путем к каталогу вашего документа:

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Шаг 2. Получите метаданные XMP

Получите метаданные XMP из файла EPS. Если в файле EPS отсутствуют метаданные XMP, будет создан новый, заполненный значениями из комментариев к метаданным PS:

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Шаг 3. Измените значения метаданных XMP

Теперь давайте внесем изменения в метаданные XMP. В этом примере мы добавим именованное значение в структуру «xmpTPg:MaxPageSize»:

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Шаг 4. Сохраните файл EPS с измененными метаданными XMP

Сохраните файл EPS с обновленными метаданными XMP. Создайте выходной поток и сохраните измененный файл EPS:

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Заключение

Поздравляем! Вы успешно добавили именованное значение в файл EPS с помощью Aspose.Page в .NET. Это руководство провело вас через основные шаги, продемонстрировав простоту и эффективность Aspose.Page при манипулировании документами.

## Часто задаваемые вопросы

### Вопрос 1: Совместим ли Aspose.Page с различными версиями файлов EPS?

A1: Aspose.Page поддерживает различные версии файлов EPS, обеспечивая совместимость с широким спектром документов.

### Вопрос 2: Могу ли я использовать Aspose.Page для коммерческих проектов?

 О2: Да, Aspose.Page поставляется с коммерческой лицензией, и вы можете приобрести ее.[здесь](https://purchase.aspose.com/buy).

### Вопрос 3: Существует ли бесплатная пробная версия Aspose.Page?

 О3: Да, вы можете изучить Aspose.Page с доступной бесплатной пробной версией.[здесь](https://releases.aspose.com/).

### Вопрос 4: Как я могу получить поддержку или связаться с сообществом Aspose?

 А4: Посетите[Форум Aspose.Page](https://forum.aspose.com/c/page/39) чтобы получить поддержку и связаться с сообществом.

### Вопрос 5. Что такое временная лицензия и как ее получить?

 О5: Если вам нужна временная лицензия для целей тестирования или оценки, вы можете приобрести ее.[здесь](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
