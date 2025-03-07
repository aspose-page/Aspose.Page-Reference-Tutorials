---
title: Agregar elementos de matriz en metadatos XMP usando Java
linktitle: Agregar elementos de matriz en metadatos XMP usando Java
second_title: API de Java de Aspose.Page
description: Mejore archivos EPS con Aspose.Page para Java. Aprenda a agregar elementos de matriz a metadatos XMP sin esfuerzo. ¡Sigue nuestra guía paso a paso ahora!
weight: 10
url: /es/java/xmp-metadata-manipulation/add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar elementos de matriz en metadatos XMP usando Java

## Introducción
Bienvenido a nuestra guía paso a paso sobre el uso de Aspose.Page para Java para agregar elementos de matriz en metadatos XMP. Aspose.Page es una potente biblioteca Java que le permite manipular y trabajar con varios formatos de documentos, incluidos archivos EPS. En este tutorial, nos centraremos en la tarea específica de agregar elementos de matriz en metadatos XMP usando Java.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de tener los siguientes requisitos previos:
- Aspose.Page para la biblioteca Java instalada.
- Conocimientos básicos de programación Java.
- Un archivo EPS válido con metadatos XMP existentes o comentarios de metadatos PS.
## Importar paquetes
Para comenzar, necesita importar los paquetes necesarios para trabajar con Aspose.Page. Incluya las siguientes líneas al comienzo de su archivo Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Paso 1: obtenga metadatos XMP
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Inicializar flujo de archivos EPS de entrada
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Obtenga metadatos XMP. Si el archivo EPS no contiene metadatos XMP, obtenemos uno nuevo lleno de valores de los comentarios de metadatos de PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
En este paso, recuperamos los metadatos XMP existentes del archivo EPS. Si el archivo EPS aún no contiene metadatos XMP, Aspose.Page genera uno nuevo y lo llena con valores de comentarios de metadatos PS.
## Paso 2: agregar el elemento de matriz "dc:title"
```java
// Agregue un elemento de matriz "dc:title" más
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Ahora, agregamos un nuevo elemento de matriz a la propiedad "dc:title" en los metadatos XMP. Reemplace "NewTitle" con el título deseado.
## Paso 3: Agregar elemento de matriz "dc:creator"
```java
// Agregue un elemento de matriz "dc:creator" más
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
De manera similar, agregamos un nuevo elemento de matriz a la propiedad "dc:creator" en los metadatos XMP. Reemplace "NuevoCreador" con la información del creador deseado.
## Paso 4: Inicializar la secuencia de archivos EPS de salida
```java
// Inicializar flujo de archivos EPS de salida
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Prepare la secuencia del archivo EPS de salida donde se guardará el documento modificado con metadatos XMP actualizados.
## Paso 5: guardar el documento con metadatos XMP modificados
```java
//Guardar documento con metadatos XMP modificados
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Guarde el documento con los metadatos XMP actualizados en el archivo EPS de salida.
## Conclusión
¡Felicidades! Ha aprendido con éxito cómo agregar elementos de matriz en metadatos XMP usando Aspose.Page para Java. Esta poderosa biblioteca simplifica el proceso de manipulación de archivos EPS y proporciona una amplia funcionalidad para el procesamiento de documentos.
## Preguntas frecuentes

### ¿Puedo utilizar Aspose.Page para Java con otros formatos de documentos?
Sí, Aspose.Page admite varios formatos de documentos, incluidos EPS, PDF y XPS.
### ¿Hay una prueba gratuita disponible para Aspose.Page para Java?
 Sí, puedes acceder a la prueba gratuita.[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar la documentación de Aspose.Page para Java?
 La documentación está disponible.[aquí](https://reference.aspose.com/page/java/).
### ¿Cómo puedo comprar Aspose.Page para Java?
 Puedes comprar el producto.[aquí](https://purchase.aspose.com/buy).
### ¿Hay licencias temporales disponibles para Aspose.Page para Java?
 Sí, puedes obtener una licencia temporal.[aquí](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
