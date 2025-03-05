---
title: Agregar degradado horizontal en Java XPS
linktitle: Agregar degradado horizontal en Java XPS
second_title: API de Java de Aspose.Page
description: Aprenda cómo agregar un impresionante degradado horizontal a documentos XPS en Java usando Aspose.Page. Siga nuestra guía paso a paso para una integración perfecta.
type: docs
weight: 11
url: /es/java/xps-gradient-addition/horizontal/
---
## Introducción
Bienvenido a esta guía paso a paso sobre cómo agregar un degradado horizontal en Java XPS usando Aspose.Page para Java. Aspose.Page para Java es una potente biblioteca que permite a los desarrolladores trabajar con documentos XPS (XML Paper Especificación) sin problemas.
En este tutorial, lo guiaremos a través del proceso de creación de una aplicación Java para agregar un degradado horizontal a un documento XPS. Siga los pasos a continuación para lograrlo con facilidad.
## Requisitos previos
Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:
1. Entorno de desarrollo de Java: asegúrese de tener Java instalado en su sistema. De lo contrario, descargue e instale la última versión de Java desde[java.com](https://www.java.com).
2.  Biblioteca Aspose.Page para Java: debe tener la biblioteca Aspose.Page para Java. Puedes descargarlo desde el[Aspose.Page para la documentación de Java](https://reference.aspose.com/page/java/).
## Importar paquetes
Comience importando los paquetes necesarios para su aplicación Java. Incluya la biblioteca Aspose.Page para Java en su proyecto. Puede hacer esto agregando las siguientes líneas de código:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```
## Paso 1: inicializar el documento
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
//Inicializar documento
XpsDocument doc = new XpsDocument();
```
## Paso 2: crea un degradado horizontal
```java
// gradiente horizontal
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```
## Paso 3: agregar ruta con degradado
```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```
## Paso 4: guarde el documento
```java
doc.save(dataDir + "HorizontalGradient.xps");
```
Repita estos pasos según sea necesario, ajustando los parámetros según sus requisitos específicos.
## Conclusión
¡Felicidades! Ha agregado con éxito un degradado horizontal a un documento XPS utilizando Aspose.Page para Java. Este tutorial proporcionó una guía completa para los desarrolladores que buscan mejorar sus aplicaciones Java con efectos de degradado.
## Preguntas frecuentes
### P: ¿Puedo aplicar varios degradados en un solo documento XPS?
Sí, puedes agregar múltiples trazados con diferentes degradados para crear diseños complejos.
### P: ¿Aspose.Page es compatible con las últimas versiones de Java?
Aspose.Page para Java se actualiza periódicamente para garantizar la compatibilidad con las últimas versiones de Java.
### P: ¿Hay otros tipos de degradado disponibles en Aspose.Page?
Sí, además de los degradados lineales, Aspose.Page admite degradados radiales para efectos más diversos.
### P: ¿Puedo personalizar los colores y las posiciones de las paradas de degradado?
¡Absolutamente! Tienes control total sobre los colores y las posiciones de cada parada de degradado.
### P: ¿Existe un foro comunitario para Aspose.Page donde pueda buscar ayuda?
 Sí, puedes visitar el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para conectarse con la comunidad y obtener ayuda.