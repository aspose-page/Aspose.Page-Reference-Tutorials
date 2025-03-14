---
title: Добавить мозаичное изображение в Java XPS
linktitle: Добавить мозаичное изображение в Java XPS
second_title: API Aspose.Page Java
description: Исследуйте беспрепятственное манипулирование документами Java XPS с помощью Aspose.Page. Научитесь легко добавлять мозаичные изображения, используя это пошаговое руководство.
weight: 11
url: /ru/java/xps-image-manipulation/add-tiled-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Добавить мозаичное изображение в Java XPS

## Введение
В динамичном мире разработки Java потребность в эффективном манипулировании и создании документов постоянно растет. Aspose.Page для Java представляет собой мощный инструмент, предоставляющий разработчикам возможность беспрепятственно работать с документами XPS. В этом руководстве основное внимание уделяется конкретной задаче — добавлению мозаичного изображения в документ Java XPS.
## Предварительные условия
Прежде чем приступить к изучению руководства, убедитесь, что у вас есть следующие предварительные условия:
1. Java Development Kit (JDK): убедитесь, что в вашей системе установлен JDK.
2.  Aspose.Page для Java: Загрузите и установите Aspose.Page для Java с[Веб-сайт](https://releases.aspose.com/page/java/).
3. Каталог ваших документов: выберите или создайте каталог, в котором вы хотите сохранить документ XPS.
## Импортировать пакеты
В свой проект Java импортируйте необходимые пакеты для использования функций Aspose.Page:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Теперь давайте разобьем процесс добавления мозаичного изображения в документ Java XPS на понятные и выполнимые шаги.
## Шаг 1. Настройте свой проект
Начните с настройки вашего проекта Java и убедитесь, что Aspose.Page для Java правильно интегрирован.
## Шаг 2. Создайте документ XPS
Инициализируйте новый документ XPS, используя следующий код:
```java
// Путь к каталогу документов.
String dataDir = "Your Document Directory";
// Создать новый документ XPS
XpsDocument doc = new XpsDocument();
```
## Шаг 3. Определите путь к мозаичному изображению
Укажите путь к мозаичному изображению, которое вы хотите добавить в документ XPS.
## Шаг 4. Добавьте мозаичное изображение
Используйте приведенный ниже фрагмент кода, чтобы добавить мозаичное изображение в документ XPS:
```java
// Изображение плитки
// Прямоугольник, заполненный ImageBrush, справа вверху внизу
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## Шаг 5: Сохраните документ
Наконец, сохраните полученный документ XPS, используя приведенный ниже код:
```java
// Сохраните полученный документ XPS.
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Повторите эти шаги, чтобы легко включить мозаичное изображение в документ Java XPS с помощью Aspose.Page.
## Заключение
Aspose.Page для Java оптимизирует процесс работы с документами XPS, предлагая разработчикам эффективное решение для манипулирования документами. Следуя этому пошаговому руководству, вы сможете легко добавить мозаичное изображение в документ Java XPS.

## Часто задаваемые вопросы
### Совместим ли Aspose.Page со всеми версиями Java?
 Aspose.Page предназначен для работы с различными версиями Java. Убедитесь в совместимости, проверив документацию.[здесь](https://reference.aspose.com/page/java/).
### Могу ли я использовать Aspose.Page для коммерческих проектов?
Да, Aspose.Page предлагает коммерческие лицензии. Купите их[здесь](https://purchase.aspose.com/buy).
### Доступна ли бесплатная пробная версия?
 Да, изучите возможности Aspose.Page с помощью бесплатной пробной версии.[здесь](https://releases.aspose.com/).
### Где я могу найти поддержку сообщества и обсуждения?
 Взаимодействуйте с сообществом Aspose.Page на[Форум](https://forum.aspose.com/c/page/39).
### Как я могу получить временную лицензию для Aspose.Page?
 Приобретите временную лицензию[здесь](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
