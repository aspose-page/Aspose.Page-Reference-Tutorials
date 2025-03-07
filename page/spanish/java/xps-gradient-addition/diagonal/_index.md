---
title: Agregar degradado diagonal en Java XPS
linktitle: Agregar degradado diagonal en Java XPS
second_title: API de Java de Aspose.Page
description: Aprenda cómo agregar un impresionante degradado diagonal a sus documentos XPS en Java usando Aspose.Page. Mejore su presentación visual sin esfuerzo.
weight: 10
url: /es/java/xps-gradient-addition/diagonal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar degradado diagonal en Java XPS

## Introducción
En el mundo en constante evolución del desarrollo de Java, mejorar el atractivo visual de sus documentos XPS es crucial. Una forma eficaz de lograrlo es incorporando gradientes diagonales. Este tutorial lo guiará a través del proceso de uso de Aspose.Page para Java, brindándole instrucciones paso a paso y fragmentos de código.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Conocimientos básicos de programación Java.
- Instaló el kit de desarrollo de Java (JDK) en su sistema.
-  Aspose.Page para la biblioteca Java. Puedes descargarlo[aquí](https://releases.aspose.com/page/java/).
- Un editor de código como IntelliJ IDEA o Eclipse.
## Importar paquetes
Comience importando los paquetes necesarios para su proyecto Java. En su código, puede agregar las siguientes importaciones:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```
## Paso 1: configura tu proyecto
Cree un nuevo proyecto Java en su entorno de desarrollo integrado (IDE) preferido e incluya la biblioteca Aspose.Page en las dependencias de su proyecto.
## Paso 2: definir el directorio de documentos
Establezca la ruta al directorio de documentos donde se guardará el archivo XPS:
```java
String dataDir = "Your Document Directory";
```
## Paso 3: crear un documento XPS
Inicialice un nuevo objeto XpsDocument:
```java
XpsDocument doc = new XpsDocument();
```
## Paso 4: agregue una ruta de degradado diagonal
Agregue una ruta al documento XPS con un degradado diagonal:
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```
## Paso 5: definir paradas de degradado lineal
Configure paradas de degradado lineal con colores y posiciones específicas:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repetir para otros colores y posiciones
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```
## Paso 6: aplicar degradado lineal al trazado
Aplique el degradado lineal al camino previamente definido:
```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Paso 7: guarde el documento
Guarde el documento XPS con el degradado diagonal agregado:
```java
doc.save(dataDir + "LinearGradient.xps");
```
## Conclusión
¡Felicidades! Ha agregado con éxito un degradado diagonal a su documento XPS usando Aspose.Page para Java. Esta característica visualmente atractiva puede mejorar la presentación general de sus documentos.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Page para Java con otros marcos de Java?
Aspose.Page está diseñado para integrarse perfectamente con varios marcos Java, lo que lo convierte en una opción versátil para sus proyectos.
### P: ¿Existen consideraciones de licencia para Aspose.Page?
 Sí, asegúrese de revisar los detalles de la licencia en el[Página de compra de Aspose.Page](https://purchase.aspose.com/buy).
### P: ¿Puedo probar Aspose.Page para Java antes de comprarlo?
 ¡Absolutamente! Puedes explorar un[versión de prueba gratuita aquí](https://releases.aspose.com/).
### P: ¿Cómo puedo obtener soporte o conectarme con la comunidad Aspose?
 Visita el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) involucrarse con la comunidad y buscar ayuda.
### P: ¿Existe alguna disposición para licencias temporales?
 Sí, puedes obtener un[licencia temporal aquí](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
