---
date: 2026-05-15
description: Узнайте, как редактировать метаданные XMP и как изменять значения XMP
  в файлах EPS с помощью Aspose.Page for Java – понятное пошаговое руководство.
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Изменить именованное значение в XMP с помощью Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: как редактировать XMP – изменить именованное значение в XMP с помощью Java
url: /ru/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Как редактировать XMP – изменить именованное значение в XMP с помощью Java

В современных документооборотах **Aspose.Page for Java** упрощает чтение, редактирование и запись XMP‑метаданных внутри EPS‑файлов. **Этот учебник показывает, как редактировать XMP**‑метаданные в EPS‑документах с помощью API Aspose.Page, чтобы вы могли поддерживать точность, поиск и соответствие информации в документе отраслевым стандартам. Независимо от того, обновляете ли вы размеры страниц, информацию об авторе или пользовательские теги, ниже приведённые шаги проведут вас через процесс на Java.

## Быстрые ответы
- **Что покрывает этот учебник?** Изменение именованного значения XMP в EPS‑файле с помощью Aspose.Page for Java.  
- **Какая версия библиотеки требуется?** Любой недавний релиз Aspose.Page for Java (API стабилен уже несколько лет).  
- **Нужна ли лицензия?** Для продакшна требуется временная или полная лицензия; бесплатная пробная версия подходит для тестирования.  
- **Сколько времени занимает реализация?** Около 10‑15 минут для разработчика, знакомого с Java I/O.  
- **Можно ли использовать это с другими форматами файлов?** API XMP также доступен для PDF, SVG и других форматов, поддерживаемых Aspose.Page.

## Что такое XMP‑метаданные?
XMP (Extensible Metadata Platform) — это стандартизированный формат на основе XML для внедрения богатых метаданных — таких как создатель, название и пользовательские свойства — непосредственно в файлы. В EPS‑документах XMP находится рядом с традиционными комментариями PostScript, позволяя приложениям читать и изменять метаданные без изменения визуального содержимого.

## Почему использовать Aspose.Page for Java для редактирования XMP?
Aspose.Page предоставляет **полный контроль более чем над 150 свойствами схемы XMP** и работает последовательно с форматами EPS, PDF и SVG. Он обрабатывает файлы размером до **500 МБ** без загрузки всего документа в память и включает встроенную проверку, гарантируя, что полученный EPS остаётся соответствующим стандартам. Внешние XML‑парсеры или нативные библиотеки не требуются.

## Введение
Aspose.Page for Java — это надёжная библиотека, упрощающая манипуляцию и обработку EPS‑файлов. При работе с XMP‑метаданными внутри этих файлов Aspose.Page предоставляет разработчикам обширный набор возможностей. В этом учебнике мы сосредоточимся на изменении именованного значения в XMP, предлагая чёткое и лаконичное руководство для разработчиков, желающих расширить возможности обработки документов.

## Предварительные требования
Прежде чем приступать к учебнику, убедитесь, что у вас есть следующие предварительные требования:
1. **Среда разработки Java** — JDK (8 или выше) и IDE или система сборки (Maven/Gradle).  
2. **Библиотека Aspose.Page for Java** — Скачайте и интегрируйте библиотеку Aspose.Page for Java в ваш проект. Вы можете найти библиотеку и подробную документацию [здесь](https://reference.aspose.com/page/java/).  
3. **Пример EPS‑файла** — Подготовьте пример EPS‑файла для экспериментов. Если у вас его нет, используйте предоставленный примерный файл с именем **"xmp4.eps"**.

## Импорт пакетов
Операторы `import` импортируют необходимые классы Aspose.Page.

Класс `PsDocument` — основной объект Aspose.Page, представляющий EPS‑документ в памяти.  
Класс `XmpMetadata` предоставляет доступ к XMP‑пакету, встроенному в EPS‑файл.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Как редактировать XMP‑метаданные?
Загрузите EPS‑файл, получите его XMP‑пакет, измените нужное свойство и сохраните документ — всё это в нескольких простых строках. Такой подход работает для любого именованного значения XMP, будь то стандартное поле Dublin Core или пользовательское пространство имён, которое вы определили.

## Шаг 1: Инициализировать поток входного EPS‑файла
`FileInputStream` открывает поток только для чтения к исходному EPS‑файлу, позволяя Aspose.Page загрузить документ без блокировки файловой системы.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Шаг 2: Инициализировать PsDocument
`PsDocument` — основной объект, инкапсулирующий содержимое EPS и предоставляющий доступ к его метаданным, страницам и ресурсам.

```java
PsDocument document = new PsDocument(psStream);
```

## Шаг 3: Получить XMP‑метаданные
`XmpMetadata` представляет XMP‑пакет внутри EPS‑файла и предоставляет методы для чтения, изменения или удаления отдельных свойств.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Шаг 4: Установить новое значение в XMP
`setProperty` задаёт значение указанного свойства XMP в пакете метаданных.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Шаг 5: Инициализировать поток вывода EPS‑файла
`FileOutputStream` создаёт поток записи для сохранения изменённого EPS‑файла.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Шаг 6: Сохранить документ с изменёнными XMP‑метаданными
`save` записывает PsDocument из памяти, включая обновлённый XMP, в поток вывода.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Шаг 7: Закрыть поток входного EPS
`close` освобождает дескриптор файла и ресурсы, связанные с входным потоком.

```java
// Close input EPS stream
psStream.close();
```

## Распространённые проблемы и решения
- **FileNotFoundException** — Убедитесь, что `dataDir` указывает на правильную папку и файл `xmp4.eps` существует.  
- **LicenseException** — Если появляются ошибки лицензирования, убедитесь, что действительный файл лицензии Aspose.Page загружен до создания `PsDocument`.  
- **Metadata Not Updated** — После сохранения откройте полученный EPS в просмотрщике метаданных (например, Adobe Bridge), чтобы убедиться, что новое значение отображается.

## Часто задаваемые вопросы
**Q: Могу ли я использовать Aspose.Page for Java с другими языками программирования?**  
A: Aspose.Page в основном поддерживает Java, но Aspose предлагает эквивалентные библиотеки для .NET, C++ и Python, которые предоставляют аналогичные возможности работы с XMP.

**Q: Доступна ли бесплатная пробная версия Aspose.Page for Java?**  
A: Да, вы можете ознакомиться с бесплатной пробной версией Aspose.Page for Java [здесь](https://releases.aspose.com/).

**Q: Где я могу найти дополнительную поддержку и обсуждения по Aspose.Page for Java?**  
A: Посетите [форум Aspose.Page](https://forum.aspose.com/c/page/39) для поддержки сообщества и обсуждений.

**Q: Как получить временную лицензию для Aspose.Page for Java?**  
A: Вы можете получить временную лицензию [здесь](https://purchase.aspose.com/temporary-license/).

**Q: Где можно приобрести Aspose.Page for Java?**  
A: Чтобы купить Aspose.Page for Java, посетите [страницу покупки](https://purchase.aspose.com/buy).

---

**Последнее обновление:** 2026-05-15  
**Тестировано с:** Aspose.Page for Java (последний релиз)  
**Автор:** Aspose

## Связанные учебники

- [How to Read XMP Metadata using Java – Aspose.Page Guide](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Aspose Page Java Tutorial – Add XMP Metadata to EPS Files](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – Change Values in XMP using Java](/page/java/xmp-metadata-manipulation/change-values/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}