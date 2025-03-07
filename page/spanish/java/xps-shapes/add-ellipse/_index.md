---
title: Agregar elipse de degradado radial con Aspose.Page
linktitle: Agregar elipse en Java XPS
second_title: API de Java de Aspose.Page
description: Explore la guía paso a paso sobre cómo agregar una elipse con trazo de degradado radial en Java XPS usando Aspose.Page para Java. Mejore la creación de sus documentos sin esfuerzo.
weight: 10
url: /es/java/xps-shapes/add-ellipse/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar elipse de degradado radial con Aspose.Page

## Introducción
Bienvenido a nuestra guía paso a paso sobre cómo agregar una elipse en Java XPS usando Aspose.Page para Java. Aspose.Page es una potente biblioteca Java que permite a los desarrolladores trabajar con documentos XPS sin esfuerzo. En este tutorial, lo guiaremos a través del proceso de crear una elipse con trazo de degradado radial y guardarla como un documento XPS.
## Requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:
- Kit de desarrollo de Java (JDK) instalado en su máquina.
-  Descarga la biblioteca Aspose.Page para Java. Puedes conseguirlo[aquí](https://releases.aspose.com/page/java/).
- Un editor de código de su elección (Eclipse, IntelliJ, etc.) para escribir y ejecutar código Java.
## Importar paquetes
Asegúrese de tener los paquetes necesarios importados en su proyecto Java para usar Aspose.Page. Agregue las siguientes declaraciones de importación en la parte superior de su archivo Java:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## Paso 1: configurar el directorio de documentos
Defina la ruta a su directorio de documentos donde se guardará el documento XPS:
```java
String dataDir = "Your Document Directory";
```
## Paso 2: crear un documento XPS
Inicialice un nuevo documento XPS usando el siguiente código:
```java
XpsDocument doc = new XpsDocument();
```
## Paso 3: definir paradas de gradiente radial
Cree una lista de paradas de degradado para la elipse con trazo de degradado radial:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## Paso 4: crear geometría de ruta
Defina una elipse con trazo de degradado radial utilizando la geometría de ruta:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## Paso 5: agregue lienzo y ruta
Agregue un nuevo lienzo al documento y agregue la ruta con la geometría definida:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## Paso 6: establecer trazo y degradado
Configura el trazo del trazado con un pincel degradado radial:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## Paso 7: establecer el grosor del trazo
Especifique el grosor del trazo del trazado:
```java
path.setStrokeThickness(12f);
```
## Paso 8: guarde el documento
Guarde el documento XPS resultante:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
¡Felicidades! Ha agregado con éxito una elipse con trazo de degradado radial en Java XPS usando Aspose.Page para Java.
## Conclusión
En este tutorial, exploramos los pasos para crear un documento XPS con una elipse con trazos de degradado radial visualmente atractiva. Aspose.Page para Java simplifica la manipulación de documentos XPS y proporciona a los desarrolladores un potente conjunto de herramientas.
## Preguntas frecuentes
### ¿Puedo usar Aspose.Page para Java con otras bibliotecas de Java?
Sí, Aspose.Page para Java se puede integrar perfectamente con otras bibliotecas de Java.
### ¿Aspose.Page es adecuado para el procesamiento de documentos a gran escala?
¡Absolutamente! Aspose.Page está diseñado para manejar el procesamiento de documentos a gran escala de manera eficiente.
### ¿Dónde puedo encontrar más tutoriales y ejemplos de Aspose.Page para Java?
 Visita el[Aspose.Page para la documentación de Java](https://reference.aspose.com/page/java/)para tutoriales y ejemplos completos.
### ¿Cómo puedo obtener una licencia temporal de Aspose.Page para Java?
 Puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Existen foros comunitarios para discusiones sobre Aspose.Page?
 Sí, únete al[Foro de la comunidad Aspose.Page](https://forum.aspose.com/c/page/39) para interactuar con otros desarrolladores y obtener ayuda.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
