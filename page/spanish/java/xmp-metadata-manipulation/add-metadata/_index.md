---
title: Agregar metadatos en XMP usando Java
linktitle: Agregar metadatos en XMP usando Java
second_title: API de Java de Aspose.Page
description: Explore la perfecta integración de Aspose.Page para Java y aprenda cómo agregar metadatos XMP a sus archivos EPS sin esfuerzo. ¡Mejora tu juego de gestión de documentos hoy!
weight: 11
url: /es/java/xmp-metadata-manipulation/add-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar metadatos en XMP usando Java

## Introducción
¿Está buscando mejorar los metadatos de su documento agregando información XMP usando Java? ¡No busque más! Esta guía paso a paso lo guiará a través del proceso de agregar metadatos a un archivo EPS utilizando la biblioteca Aspose.Page para Java. Aspose.Page es una poderosa herramienta que simplifica las tareas de manipulación de documentos en aplicaciones Java.
## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de tener los siguientes requisitos previos:
- Conocimientos básicos de programación Java.
-  Aspose.Page para la biblioteca Java instalada. Puedes descargarlo[aquí](https://releases.aspose.com/page/java/).
- Un archivo EPS que desea modificar.
## Importar paquetes
En primer lugar, importe los paquetes necesarios a su programa Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## Paso 1: obtenga metadatos XMP
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Inicializar flujo de archivos EPS de entrada
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Obtenga metadatos XMP. Si el archivo EPS no contiene metadatos XMP, se crea uno nuevo utilizando valores de los comentarios de metadatos de PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Asegúrese de reemplazar "Su directorio de documentos" con la ruta real donde se almacenan sus documentos.

## Paso 2: recuperar el valor de CreatorTool
```java
// Obtener el valor de "CreatorTool"
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Paso 3: recuperar el valor CreateDate
```java
// Obtener el valor "Crear fecha"
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Paso 4: recuperar el valor del título
```java
// Obtener el valor de "Título"
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Paso 5: recuperar el valor del formato
```java
//Obtener el valor de "formato"
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Paso 6: recuperar el valor del creador
```java
// Obtener valor de "creador"
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Paso 7: recuperar el valor de fecha de metadatos
```java
// Obtener el valor "MetadataDate"
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## Paso 8: guarde el documento con nuevos metadatos XMP
```java
// Inicializar flujo de archivos EPS de salida
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Guardar documento con nuevos metadatos XMP
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Finalmente, no olvide cerrar la secuencia EPS de entrada:
```java
// Cerrar flujo EPS de entrada
psStream.close();
```
¡Ahora ha agregado metadatos exitosamente a su archivo EPS usando Aspose.Page para Java!
## Conclusión
En este tutorial, exploramos el proceso de agregar metadatos XMP a un archivo EPS usando la biblioteca Aspose.Page para Java. Esta poderosa herramienta le permite manipular documentos sin problemas, mejorando su experiencia general de gestión de documentos.
## Preguntas frecuentes
### P: ¿Aspose.Page para Java es de uso gratuito?
 R: Aspose.Page para Java es un producto comercial. Puede explorar sus funciones a través de una prueba gratuita.[aquí](https://releases.aspose.com/).
### P: ¿Dónde puedo encontrar la documentación de Aspose.Page para Java?
 R: La documentación está disponible.[aquí](https://reference.aspose.com/page/java/).
### P: ¿Cómo puedo obtener una licencia temporal de Aspose.Page para Java?
 R: Puede obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### P: ¿Qué formatos de archivo admite Aspose.Page para Java?
R: Aspose.Page para Java admite varios formatos, incluidos EPS, PDF y XPS.
### P: ¿Puedo comprar Aspose.Page para Java?
 R: Sí, puedes comprar Aspose.Page para Java[aquí](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
