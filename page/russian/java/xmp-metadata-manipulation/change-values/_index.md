---
title: Измените значения в XMP с помощью Java
linktitle: Измените значения в XMP с помощью Java
second_title: API Aspose.Page Java
description: Улучшите документы EPS с помощью Aspose.Page для Java. Легко изменяйте метаданные XMP для создания индивидуального и профессионального контента. #JavaDevelopment
type: docs
weight: 17
url: /ru/java/xmp-metadata-manipulation/change-values/
---
## Введение
В области обработки и манипулирования документами Aspose.Page для Java выделяется как мощный инструмент. В этом руководстве рассматривается процесс изменения значений XMP (расширяемая платформа метаданных) в документах EPS (инкапсулированный PostScript) с использованием Java с библиотекой Aspose.Page. Следуя предоставленному пошаговому руководству, вы узнаете, как легко изменять метаданные, гарантируя, что ваши документы будут адаптированы к вашим конкретным требованиям.
## Предварительные условия
Прежде чем мы приступим к этому руководству, убедитесь, что у вас есть следующие предварительные условия:
1. Среда разработки Java. Убедитесь, что на вашем компьютере установлена работающая среда разработки Java.
2.  Библиотека Aspose.Page для Java: Загрузите и установите библиотеку Aspose.Page для Java. Вы можете найти необходимый пакет[здесь](https://releases.aspose.com/page/java/).
## Импортировать пакеты
Начните с импорта необходимых пакетов в ваш проект Java. Эти пакеты жизненно важны для взаимодействия и управления документами EPS.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.util.Date;
import java.util.TimeZone;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```
## Шаг 1. Получите метаданные XMP
Получите метаданные XMP из документа EPS. Если файл EPS не содержит метаданных XMP, будет создан новый файл со значениями из комментариев к метаданным PS, такими как %%Creator, %%CreateDate и %%Title.
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Инициализировать входной поток файлов EPS
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Получите метаданные XMP. Если файл EPS не содержит метаданных XMP, создается новый файл со значениями из комментариев метаданных PS.
XmpMetadata xmp = document.getXmpMetadata();
```
## Шаг 2. Измените значение «ModifyDate»
Измените значение «ModifyDate» в метаданных XMP, чтобы оно отражало желаемую дату.
```java
// Измените значение «ModifyDate»
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## Шаг 3. Измените значение «Создатель»
Обновите значение «Создатель» в метаданных XMP, чтобы указать создателя документа.
```java
// Изменить значение «создатель»
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Шаг 4. Измените значение «Название»
Измените значение «Заголовок» в метаданных XMP, чтобы задать соответствующий заголовок для документа.
```java
//Изменить значение «заголовка»
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Шаг 5. Сохраните документ с измененными метаданными XMP
Сохраните документ с обновленными метаданными XMP в новый файл EPS.
```java
// Инициализировать выходной поток файлов EPS
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Сохранить документ с измененными метаданными XMP
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Заключение
Поздравляем! Вы успешно прошли процесс изменения значений XMP в документах EPS с помощью Aspose.Page для Java. Это руководство дало вам знания по изменению метаданных, гарантируя беспрепятственное соответствие ваших документов вашим конкретным требованиям.
## Часто задаваемые вопросы
### Вопрос: Как учитывать часовой пояс при изменении значений XMP?
 использовать`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` для обеспечения согласованности настроек часового пояса.
### Вопрос: Могу ли я изменить несколько значений XMP за одну операцию?
 Да, с помощью`put` для каждого желаемого значения, вы можете одновременно изменять несколько значений XMP.
### Вопрос: Где я могу найти дополнительную документацию по Aspose.Page для Java?
 Изучите полную документацию[здесь](https://reference.aspose.com/page/java/).
### Вопрос: Существует ли бесплатная пробная версия Aspose.Page для Java?
 Да, вы можете получить доступ к бесплатной пробной версии[здесь](https://releases.aspose.com/).
### Вопрос: Как я могу получить временную лицензию на Aspose.Page для Java?
 Получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).