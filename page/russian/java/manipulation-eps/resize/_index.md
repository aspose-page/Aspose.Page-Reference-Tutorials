---
title: Изменение размера файлов EPS в Java с помощью Aspose.Page
linktitle: Изменение размера файла EPS в Java
second_title: API Aspose.Page Java
description: Узнайте, как легко изменить размер файлов EPS на Java с помощью Aspose.Page для Java. Следуйте нашему подробному руководству для получения пошаговых инструкций.
weight: 11
url: /ru/java/manipulation-eps/resize/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Изменение размера файлов EPS в Java с помощью Aspose.Page

## Введение
Добро пожаловать в наше пошаговое руководство по изменению размера файлов EPS в Java с использованием мощной библиотеки Aspose.Page. Если вам когда-либо приходилось программно настраивать размеры изображений EPS, вы попали по адресу. В этом уроке мы рассмотрим различные варианты изменения размера, включая точки, дюймы, миллиметры и проценты, что предоставит вам гибкость, необходимую для ваших конкретных требований.
## Предварительные условия
Прежде чем мы углубимся в руководство, убедитесь, что у вас есть следующее:
- На вашем компьютере установлен Java Development Kit (JDK).
-  Aspose.Page для библиотеки Java. Вы можете скачать его[здесь](https://releases.aspose.com/page/java/).
- Базовое понимание программирования на Java.
## Импортировать пакеты
В вашем проекте Java убедитесь, что у вас есть необходимый импорт для использования функций Aspose.Page. Вот пример:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Теперь давайте разобьем руководство на несколько шагов для каждого варианта изменения размера:
## Изменение размера EPS с помощью точек
### Шаг 1. Настройте входной поток
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### Шаг 2. Инициализируйте объект PsDocument.
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### Шаг 3. Извлеките текущий размер изображения EPS.
```java
Dimension oldSize = doc.extractEpsSize();
```
### Шаг 4. Создайте выходной поток
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### Шаг 5. Измените размер и сохраните в точках.
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## Изменение размера EPS в дюймах
Выполните действия, аналогичные примеру 1, заменив «Точки» на «Дюймы» и соответствующим образом настроив новый размер.
## Изменение размера EPS в миллиметрах
Выполните действия, аналогичные примеру 1, заменив «Точки» на «Миллиметры» и соответствующим образом настроив новый размер.
## Измените размер EPS, используя проценты
Выполните действия, аналогичные примеру 1, заменив «Точки» на «Проценты» и соответствующим образом настроив новый размер.
## Заключение
Поздравляем! Вы успешно научились изменять размер файлов EPS в Java с помощью Aspose.Page. Это руководство предоставляет вам универсальные возможности, позволяющие адаптировать процесс изменения размера в соответствии с вашими конкретными потребностями.

## Часто задаваемые вопросы
### Могу ли я использовать эту библиотеку для других форматов изображений?
Нет, Aspose.Page специально разработан для работы с файлами PostScript и EPS.
### Доступна ли бесплатная пробная версия Aspose.Page для Java?
Да, вы можете изучить бесплатную пробную версию[здесь](https://releases.aspose.com/).
### Где я могу найти дополнительную помощь и обсуждения?
 Посетить[Форум Aspose.Page](https://forum.aspose.com/c/page/39) для поддержки сообщества.
### Как получить временную лицензию?
 Вы можете получить временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
### Есть ли примеры проектов?
 Да, проверьте документацию[здесь](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
