---
date: 2026-08-08
description: Узнайте, как создавать EPS с метаданными XMP и добавлять именованные
  значения с помощью Aspose.Page для .NET. Пошаговое руководство с шаблонами кода.
keywords:
- create eps with xmp
- add named value eps
- aspose.page metadata
lastmod: 2026-08-08
linktitle: Добавить именованное значение
og_description: Создавайте EPS с метаданными XMP в .NET с помощью Aspose.Page. Это
  руководство показывает, как быстро и надёжно добавлять именованные значения в файлы
  EPS.
og_image_alt: Guide showing how to add XMP named value to an EPS file with Aspose.Page
og_title: Создание EPS с XMP – добавление именованного значения с помощью Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-08'
  description: Learn how to create EPS with XMP metadata and add named values using
    Aspose.Page for .NET. Step‑by‑step guide with code placeholders.
  headline: Create EPS with XMP – add named value using Aspose.Page
  type: TechArticle
- questions:
  - answer: Aspose.Page supports EPS versions 3.0 through 3.3, ensuring broad compatibility
      with legacy and modern files.
    question: Is Aspose.Page compatible with different EPS file versions?
  - answer: Yes, a commercial license is required for production use. You can purchase
      a license **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.
    question: Can I use Aspose.Page for commercial projects?
  - answer: Yes, a fully functional trial can be downloaded **[Aspose.Page free trial
      download page](https://releases.aspose.com/)**.
    question: Is there a free trial available?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      to ask questions and share experiences.
    question: How can I get support or join the community?
  - answer: A temporary license lets you evaluate the product for a short period.
      You can request one **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: What is a temporary license and how do I obtain one?
  type: FAQPage
second_title: Aspose.Page .NET API
tags:
- eps metadata
- aspose.page
- .net document processing
title: Создание EPS с XMP – добавление именованного значения с помощью Aspose.Page
url: /ru/net/eps-metadata-management/modify-eps-metadata-add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Создание EPS с XMP – добавление именованного значения с помощью Aspose.Page

## Введение

В этом руководстве вы узнаете, как **создать EPS с XMP**‑метаданными и добавить именованное значение с помощью библиотеки Aspose.Page для .NET. Независимо от того, создаёте ли вы конвейер пакетной обработки или хотите обогатить EPS‑файлы пользовательскими XMP‑тегами, ниже приведённые шаги проведут вас от настройки проекта до сохранения изменённого файла. Aspose.Page может обрабатывать EPS‑документы до **500 страниц** без загрузки всего файла в память, что делает её подходящей для сценариев с высоким объёмом.

## Быстрые ответы
- **Какова основная цель?** Добавить именованное XMP‑значение в существующий EPS‑файл.  
- **Какая библиотека требуется?** Aspose.Page для .NET.  
- **Нужна ли лицензия?** Для продакшн‑использования требуется коммерческая лицензия; доступна бесплатная пробная версия.  
- **Какие версии .NET поддерживаются?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Сколько времени занимает реализация?** Около 10–15 минут для базового сценария.

## Как создать EPS с XMP‑метаданными в .NET?

Загрузите целевой EPS‑файл, получите (или создайте) объект его XMP‑метаданных, добавьте требуемое именованное значение и, наконец, сохраните документ обратно на диск. Этот рабочий процесс требует всего несколько вызовов методов и стабильно работает со всеми поддерживаемыми версиями EPS. Подход также сохраняет существующее содержимое страниц и другие структуры XMP, поэтому вы можете безопасно выполнять несколько обновлений метаданных подряд.

## Требования

- Базовые знания C# и структуры .NET‑проекта.  
- Visual Studio 2022 (или любой совместимый IDE).  
- Библиотека Aspose.Page для .NET. Если у вас её ещё нет, загрузите её со **страницы загрузки Aspose.Page для .NET**([Aspose.Page for .NET download page](https://releases.aspose.com/page/net/)).  

## Импорт пространств имён

Следующие пространства имён предоставляют доступ к классам Aspose.Page для работы с EPS, вывода устройств и XMP‑метаданных.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

## Шаг 1: инициализация входного потока EPS‑файла

Создайте `FileStream` для исходного EPS‑файла и создайте объект `PsDocument` для работы с документом.

```csharp
// ExStart:1
string dataDir = "Your Document Directory";
System.IO.FileStream psStream = new System.IO.FileStream(dataDir + "add_named_value_input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Шаг 2: получение XMP‑метаданных

Получите объект `XmpMetadata` из документа; этот объект представляет встроенный XMP‑пакет.

```csharp
XmpMetadata xmp = document.GetXmpMetadata();
```

## Шаг 3: изменение значений XMP‑метаданных

Используйте метод `AddNamedValue` класса `XmpMetadata` для вставки нового именованного значения в указанную структуру XMP.

```csharp
xmp.AddNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

## Шаг 4: сохранение EPS‑файла с изменёнными XMP‑метаданными

Сохраните изменённый документ, записав его в новый `FileStream`.

```csharp
using (System.IO.FileStream outPsStream = new System.IO.FileStream(dataDir + "add_named_value_output.eps", System.IO.FileMode.Create, System.IO.FileAccess.Write))
{
    document.Save(outPsStream);
}
```

## Почему использовать Aspose.Page для EPS‑метаданных?

Aspose.Page поддерживает **более 50 XMP‑схем** и может обрабатывать EPS‑файлы до **500 страниц**, удерживая использование памяти ниже **30 МБ** для типичных документов. Библиотека не зависит от внешних инструментов или нативного кода, гарантируя одинаковое поведение в средах Windows, Linux и macOS.

## Распространённые проблемы и их устранение

- **Отсутствует XMP‑пакет:** Если `GetXmpMetadata()` возвращает `null`, EPS‑файл не содержит XMP‑блок. Библиотека автоматически создаст его, но убедитесь, что файл не повреждён.  
- **Конфликты пространств имён:** При добавлении пользовательских именованных значений используйте уникальный URI пространства имён, чтобы избежать конфликтов с существующими схемами.  
- **Большие файлы:** Для EPS‑файлов размером более 200 МБ рекомендуется использовать потоковую запись вывода, чтобы избежать чрезмерного потребления памяти.

## Часто задаваемые вопросы

**Q: Совместима ли Aspose.Page с различными версиями EPS‑файлов?**  
A: Aspose.Page поддерживает версии EPS 3.0‑3.3, обеспечивая широкую совместимость с устаревшими и современными файлами.

**Q: Могу ли я использовать Aspose.Page в коммерческих проектах?**  
A: Да, для продакшн‑использования требуется коммерческая лицензия. Вы можете приобрести лицензию **[Aspose.Page license purchase page](https://purchase.aspose.com/buy)**.

**Q: Доступна ли бесплатная пробная версия?**  
A: Да, полностью функциональная пробная версия доступна для загрузки **[Aspose.Page free trial download page](https://releases.aspose.com/)**.

**Q: Как получить поддержку или присоединиться к сообществу?**  
A: Посетите **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**, чтобы задать вопросы и поделиться опытом.

**Q: Что такое временная лицензия и как её получить?**  
A: Временная лицензия позволяет оценить продукт на короткий срок. Вы можете запросить её на **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.

---

**Последнее обновление:** 2026-08-08  
**Тестировано с:** Aspose.Page 24.11 for .NET  
**Автор:** Aspose

## Связанные руководства

- [Добавить метаданные в EPS‑документ с помощью Aspose.Page для .NET](/page/net/eps-metadata-management/add-metadata-to-eps-document/)
- [Изменить именованное значение с помощью Aspose.Page для .NET](/page/net/eps-metadata-management/modify-eps-metadata-change-named-value/)
- [Извлечь метаданные из EPS‑документа с помощью Aspose.Page для .NET](/page/net/eps-metadata-management/extract-metadata-from-eps-document/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}