---
title: Agregar degradado vertical en Java XPS
linktitle: Agregar degradado vertical en Java XPS
second_title: API de Java de Aspose.Page
description: Aprenda cómo agregar un degradado vertical a documentos Java XPS con Aspose.Page. Mejore el atractivo visual sin esfuerzo. Guía paso a paso en el interior.
type: docs
weight: 12
url: /es/java/xps-gradient-addition/vertical/
---
## Introducción
En este tutorial, exploraremos cómo agregar un degradado vertical en Java XPS usando Aspose.Page para Java. Agregar degradados a sus documentos XPS puede mejorar el atractivo visual de su contenido, haciéndolo más atractivo y estéticamente agradable.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Un entorno de desarrollo Java funcional.
-  Aspose.Page para la biblioteca Java. Puedes descargarlo desde[aquí](https://releases.aspose.com/page/java/).
- Un conocimiento básico de la programación Java.
## Importar paquetes
Comience importando los paquetes necesarios para su proyecto Java. Asegúrese de haber incluido la biblioteca Aspose.Page para Java en las dependencias de su proyecto.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
        
// Importar Aspose.Page para Java
```
## Paso 1: Inicializar el documento
Comience inicializando el documento XPS. Esto sienta las bases para agregar elementos como trazados y degradados a su documento.
```java
// Inicializar documento
XpsDocument doc = new XpsDocument();
```
## Paso 2: crea un camino con degradado vertical
Ahora, creemos un camino con un degradado vertical. Esto implica definir la geometría del camino y especificar las paradas del gradiente.
```java
// Crea un camino con geometría.
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Definir paradas de gradiente vertical
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//Aplicar el degradado vertical al camino.
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Paso 3: guarde el documento
Finalmente, guarde el documento XPS con el degradado vertical agregado en el directorio que desee.
```java
// guardar el documento
doc.save(dataDir + "VerticalGradient.xps");
```
¡Felicidades! Ha agregado con éxito un degradado vertical a su documento Java XPS usando Aspose.Page.
## Conclusión
Mejorar sus documentos XPS con degradados puede mejorar significativamente su atractivo visual. Aspose.Page para Java simplifica este proceso y le permite crear documentos impresionantes con facilidad.

### Preguntas frecuentes
### ¿Puedo utilizar Aspose.Page para Java en proyectos comerciales?
 Sí, Aspose.Page para Java está disponible para uso comercial. puedes comprarlo[aquí](https://purchase.aspose.com/buy).
### ¿Hay una prueba gratuita disponible para Aspose.Page para Java?
 Sí, puedes acceder a una prueba gratuita[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar la documentación de Aspose.Page para Java?
 La documentación está disponible.[aquí](https://reference.aspose.com/page/java/).
### ¿Cómo puedo obtener una licencia temporal de Aspose.Page para Java?
 Obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Necesita ayuda o tiene preguntas?
 Visita la comunidad Aspose.Page[foro](https://forum.aspose.com/c/page/39).