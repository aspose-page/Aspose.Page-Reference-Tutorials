---
date: 2025-12-21
description: Узнайте, как читать XMP‑метаданные с помощью Java и Aspose.Page. Это
  пошаговое руководство покажет, как читать XMP в формате документа и извлекать ключевые
  свойства.
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: Как читать XMP‑метаданные с помощью Java – руководство Aspose.Page
url: /ru/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Получить метаданные из XMP с помощью Java

## Как читать метаданные XMP с помощью Java

Добро пожаловать в наш пошаговый учебник, который показывает **как читать XMP** метаданные с помощью Java и библиотеки Aspose.Page. XMP (Extensible Metadata Platform) — широко принятый стандарт для встраивания богатых метаданных в документы. К концу этого руководства вы сможете читать XMP формата документа, извлекать информацию о создателе, временные метки, миниатюры и многое другое, что позволит вам создавать более интеллектуальные решения для анализа документов.

## Быстрые ответы
- **Что означает «how to read xmp»?** Это относится к программному извлечению XMP‑метаданных из файлов.  
- **Какая библиотека требуется?** Aspose.Page for Java (доступна на странице загрузки Aspose).  
- **Нужна ли лицензия?** Для использования в продакшене требуется временная или полная лицензия; доступна бесплатная пробная версия.  
- **Какая версия Java поддерживается?** Java 8 или выше.  
- **Можно ли читать XMP из других форматов?** Да, Aspose.Page может работать с EPS, PDF и несколькими типами изображений, содержащих XMP.

## Требования
Перед тем как приступить к коду, убедитесь, что у вас есть:

- **Java Development Kit (JDK)** – установленный и настроенный Java 8+ на вашем компьютере.  
- **Aspose.Page for Java** – загрузите библиотеку с официального сайта [здесь](https://releases.aspose.com/page/java/).  
- EPS‑файл, содержащий XMP‑метаданные (например, `xmp1.eps`).  

## Импорт пакетов
В вашем Java‑проекте импортируйте необходимые пакеты:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Шаг 1: Инициализация входного потока EPS‑файла
Начните с указания пути к каталогу документов и инициализации входного потока EPS‑файла.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Шаг 2: Получить XMP‑метаданные
Извлеките XMP‑метаданные из EPS‑файла. Если файл не содержит XMP‑метаданных, будет создан новый набор на основе комментариев PS‑метаданных.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Шаг 3: Извлечь информацию CreatorTool
Проверьте и выведите значение «CreatorTool» из XMP‑метаданных.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Шаг 4: Извлечь информацию CreateDate
Проверьте и выведите значение «CreateDate» из XMP‑метаданных.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Шаг 5: Получить ширину миниатюры
Если миниатюры существуют, извлеките и выведите ширину первой миниатюры.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Шаг 6: Извлечь информацию о формате
Проверьте и выведите значение «format» из XMP‑метаданных.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Шаг 7: Получить DocumentID
Проверьте и выведите значение «DocumentID» из XMP‑метаданных.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Почему это важно
Чтение XMP‑метаданных позволяет программно определить источник, дату создания и другие важные атрибуты документа без его открытия в просмотрщике. Это особенно полезно для пакетной обработки, систем управления контентом и цифровых конвейеров, где метаданные управляют индексацией и поиском.

## Распространённые ошибки и советы
- **Missing XMP:** Некоторые EPS‑файлы могут не содержать XMP. Вызов `getXmpMetadata()` синтезирует минимальный набор на основе существующих PS‑комментариев, но вы не получите полные метаданные, если они не встроены.  
- **Thumbnail Arrays:** Ключ `xmp:Thumbnails` может содержать несколько записей. Пример извлекает только первую; при необходимости всех миниатюр пройдите массив.  
- **Namespace Awareness:** Ключи XMP используют пространства имён (например, `xmp:`, `dc:`). Убедитесь, что вы указываете точное имя ключа, иначе `containsKey` вернёт false.

## Часто задаваемые вопросы
### Можно ли использовать Aspose.Page for Java с другими языками программирования?
Да, Aspose.Page поддерживает несколько языков, включая Java, .NET и другие. См. [документацию](https://reference.aspose.com/page/java/) для подробностей.

### Доступна ли бесплатная пробная версия Aspose.Page for Java?
Да, бесплатную пробную версию можно получить [здесь](https://releases.aspose.com/).

### Где можно найти поддержку Aspose.Page for Java?
Посетите [форум Aspose.Page](https://forum.aspose.com/c/page/39) для получения помощи от сообщества.

### Как получить временную лицензию для Aspose.Page for Java?
Временную лицензию можно получить [здесь](https://purchase.aspose.com/temporary-license/).

### Есть ли дополнительные ресурсы для Aspose.Page for Java?
Изучите полную [документацию](https://reference.aspose.com/page/java/) и скачайте библиотеку [здесь](https://releases.aspose.com/page/java/).

## Дополнительные вопросы
**В: Работает ли этот подход с PDF‑файлами, содержащими XMP?**  
О: Да, Aspose.Page может читать XMP из PDF, EPS и нескольких форматов изображений.

**В: Можно ли изменить XMP‑метаданные после их чтения?**  
О: Абсолютно. Объект `XmpMetadata` изменяем; вы можете добавлять, обновлять или удалять ключи, а затем сохранять документ.

**В: Есть ли способ извлечь все изображения миниатюр, а не только их размеры?**  
О: Вы можете получить бинарные данные из свойства `xmpGImg:data` каждой записи миниатюры и записать их в файл.

## Заключение
Теперь вы освоили **как читать XMP** метаданные с помощью Java и Aspose.Page. Следуя этим шагам, вы сможете извлекать инструменты создания, временные метки, миниатюры, информацию о формате и идентификаторы документов, получая полное представление о встроенных метаданных ваших EPS‑файлов. Не стесняйтесь экспериментировать с дополнительными пространствами имён XMP, чтобы получать ещё более богатые данные для ваших приложений.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Последнее обновление:** 2025-12-21  
**Тестировано с:** Aspose.Page for Java 24.12 (latest)  
**Автор:** Aspose