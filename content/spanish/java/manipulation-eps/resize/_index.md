---
title: Cambiar el tamaño de archivos EPS en Java con Aspose.Page
linktitle: Cambiar el tamaño del archivo EPS en Java
second_title: API de Java de Aspose.Page
description: Aprenda a cambiar el tamaño de archivos EPS en Java sin esfuerzo con Aspose.Page para Java. Siga nuestra guía completa para obtener instrucciones paso a paso.
type: docs
weight: 11
url: /es/java/manipulation-eps/resize/
---
## Introducción
Bienvenido a nuestra guía paso a paso sobre cómo cambiar el tamaño de archivos EPS en Java utilizando la potente biblioteca Aspose.Page. Si alguna vez necesitó ajustar las dimensiones de sus imágenes EPS mediante programación, está en el lugar correcto. En este tutorial, exploraremos varias opciones de cambio de tamaño, incluidos puntos, pulgadas, milímetros y porcentajes, brindándole la flexibilidad que necesita para sus requisitos específicos.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de tener lo siguiente:
- Kit de desarrollo de Java (JDK) instalado en su máquina.
-  Aspose.Page para la biblioteca Java. Puedes descargarlo[aquí](https://releases.aspose.com/page/java/).
- Un conocimiento básico de la programación Java.
## Importar paquetes
En su proyecto Java, asegúrese de tener las importaciones necesarias para utilizar las funcionalidades de Aspose.Page. He aquí un ejemplo:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Ahora, dividamos el tutorial en varios pasos para cada opción de cambio de tamaño:
## Cambiar el tamaño de EPS usando puntos
### Paso 1: configurar el flujo de entrada
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### Paso 2: inicializar el objeto PsDocument
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### Paso 3: extraiga el tamaño actual de la imagen EPS
```java
Dimension oldSize = doc.extractEpsSize();
```
### Paso 4: crear un flujo de salida
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### Paso 5: cambia el tamaño y guarda en puntos
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## Cambiar el tamaño de EPS usando pulgadas
Siga pasos similares al ejemplo 1, reemplazando "Puntos" por "Pulgadas" y ajustando el nuevo tamaño en consecuencia.
## Cambiar el tamaño de EPS usando milímetros
Siga pasos similares al ejemplo 1, reemplazando "Puntos" por "Milímetros" y ajustando el nuevo tamaño en consecuencia.
## Cambiar el tamaño de EPS usando porcentajes
Siga pasos similares al ejemplo 1, reemplazando "Puntos" por "Porcentajes" y ajustando el nuevo tamaño en consecuencia.
## Conclusión
¡Felicidades! Ha aprendido con éxito cómo cambiar el tamaño de archivos EPS en Java usando Aspose.Page. Esta guía le brinda opciones versátiles, lo que garantiza que pueda adaptar el proceso de cambio de tamaño para satisfacer sus necesidades específicas.

## Preguntas frecuentes
### ¿Puedo usar esta biblioteca para otros formatos de imagen?
No, Aspose.Page está diseñado específicamente para manejar archivos PostScript y EPS.
### ¿Hay una prueba gratuita disponible para Aspose.Page para Java?
Sí, puedes explorar la prueba gratuita.[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar ayuda y debates adicionales?
 Visita el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para el apoyo de la comunidad.
### ¿Cómo puedo obtener una licencia temporal?
 Puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Hay algún proyecto de ejemplo disponible?
 Sí, consulta la documentación.[aquí](https://reference.aspose.com/page/java/).