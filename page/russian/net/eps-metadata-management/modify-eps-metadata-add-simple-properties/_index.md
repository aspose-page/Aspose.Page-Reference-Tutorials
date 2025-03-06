---
title: Добавьте простые свойства с помощью Aspose.Page для .NET
linktitle: Добавить простые свойства
second_title: Aspose.Page .NET API
description: Улучшите файлы EPS с помощью Aspose.Page для .NET. Легко добавляйте простые свойства для персонализированных метаданных документа.
weight: 14
url: /ru/net/eps-metadata-management/modify-eps-metadata-add-simple-properties/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавьте простые свойства с помощью Aspose.Page для .NET

## Введение

В области манипулирования и улучшения документов Aspose.Page для .NET выступает в качестве мощного инструмента, предоставляющего разработчикам возможность беспрепятственно добавлять и изменять метаданные XMP в файлах EPS. Это руководство проведет вас через процесс добавления простых свойств в файл EPS с помощью Aspose.Page для .NET.

## Предварительные условия

Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:

1.  Aspose.Page для .NET: убедитесь, что в вашей среде разработки установлен Aspose.Page для .NET. Если нет, то вы можете скачать его[здесь](https://releases.aspose.com/page/net/).

2.  Каталог документов: настройте каталог для хранения файлов EPS. Обновите`dataDir` переменная в предоставленном фрагменте кода с путем к каталогу вашего документа.

## Импортировать пространства имен

Для начала импортируйте необходимые пространства имен, чтобы обеспечить связь с Aspose.Page для .NET. Добавьте следующие строки в начало файла кода:

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

```csharp
// ExStart:1
// Путь к каталогу документов.
string dataDir = "Your Document Directory";
// Инициализировать входной поток файла EPS
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_simple_props_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
//Создать экземпляр PsDocument из потока
PsDocument document = new PsDocument(psStream);
```

## Шаг 2. Получите метаданные XMP

```csharp
// Получите метаданные XMP. Если файл EPS не содержит метаданных XMP, мы получаем новый, заполненный значениями из комментариев метаданных PS (%%Creator, %%CreateDate, %%Title и т. д.).
XmpMetadata xmp = document.GetXmpMetadata();
```

## Шаг 3. Измените значения метаданных XMP

```csharp
// Изменение значений метаданных XMP
DateTime now = DateTime.UtcNow;

// Добавить целочисленное свойство
xmp.Add("xmp:Intg1", new XmpValue(111));

// Добавить свойство DateTime
xmp.Add("xmp:Date1", new XmpValue(now));

// Добавить свойство Double
xmp.Add("xmp:Double1", new XmpValue(111.11D));

//Добавить строковое свойство
xmp.Add("xmp:String1", new XmpValue("ABC"));
```

## Шаг 4. Сохраните файл EPS с измененными метаданными XMP

```csharp
// Сохраните файл EPS с измененными метаданными XMP.

// Создать выходной поток
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_simple_props_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    // Сохранить файл EPS
    document.Save(outPsStream);
}
```

## Шаг 5. Закройте FileStream.

```csharp
finally
{
    psStream.Close();
}
```

Следуя этим шагам, вы сможете легко включать простые свойства в свои файлы EPS, используя Aspose.Page для .NET.

## Заключение

В заключение, Aspose.Page для .NET оказывается бесценным активом для разработчиков, стремящихся улучшить файлы EPS с помощью пользовательских метаданных XMP. Добавляя простые свойства, вы можете настраивать и обогащать свои документы в соответствии с конкретными требованиями, открывая мир возможностей для манипулирования документами.

## Часто задаваемые вопросы

### Вопрос 1. Совместим ли Aspose.Page для .NET со всеми файлами EPS?

A1: Aspose.Page для .NET поддерживает широкий спектр файлов EPS. Однако совместимость может различаться в зависимости от сложности и структуры отдельных файлов.

### Вопрос 2. Могу ли я изменить существующие метаданные XMP с помощью Aspose.Page для .NET?

А2: Абсолютно! Как показано в этом руководстве, вы можете легко изменить существующие значения метаданных XMP или добавить новые в соответствии с вашими потребностями.

### Вопрос 3. Существуют ли какие-либо ограничения на типы свойств, которые я могу добавить?

A3: Aspose.Page для .NET поддерживает различные типы данных для свойств, включая целые числа, даты, двойные значения и строки. У вас есть гибкость в выборе подходящего типа для ваших метаданных.

### Вопрос 4: Как я могу получить техническую поддержку для Aspose.Page для .NET?

 A4: Для получения технической помощи посетите[Форум Aspose.Page](https://forum.aspose.com/c/page/39) или изучить[документация](https://reference.aspose.com/page/net/) для всестороннего руководства.

### Вопрос 5: Существует ли бесплатная пробная версия Aspose.Page для .NET?

 О5: Да, вы можете получить доступ к бесплатной пробной версии.[здесь](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
