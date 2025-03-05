---
title: Agregar propiedades simples en XMP usando Java
linktitle: Agregar propiedades simples en XMP usando Java
second_title: API de Java de Aspose.Page
description: Desbloquee Aspose.Page para aprovechar el potencial de Java con nuestra guía sobre cómo agregar propiedades a los metadatos XMP en archivos EPS. ¡Mejore el procesamiento de documentos sin esfuerzo!
type: docs
weight: 14
url: /es/java/xmp-metadata-manipulation/add-simple-properties/
---
## Introducción
En el panorama en constante evolución del procesamiento de documentos, la gestión eficiente de los metadatos es crucial. Aspose.Page para Java permite a los desarrolladores manipular datos de la plataforma de metadatos extensible (XMP) sin problemas. En este tutorial, exploraremos el proceso de agregar propiedades simples a XMP usando Java, brindándole una guía completa paso a paso.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Conocimientos básicos de programación Java.
-  Aspose.Page para la biblioteca Java instalada. Puedes descargarlo[aquí](https://releases.aspose.com/page/java/).
- Un archivo EPS de muestra que contiene metadatos. Si no tiene uno, no dude en utilizar el archivo "xmp3.eps" proporcionado.
## Importar paquetes
Asegúrese de importar los paquetes necesarios para iniciar su proyecto:
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
## Paso 2: agregar propiedad de fecha
```java
// Agregar el valor "xmp:Date1" de la propiedad de fecha
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```
## Paso 3: agregar propiedad entera
```java
// Agregar el valor entero de la propiedad "xmp:Intg1"
xmp.put("xmp:Intg1", new XmpValue(111));
```
## Paso 4: agregar propiedad doble
```java
// Agregue el valor de propiedad doble "xmp:Double1"
xmp.put("xmp:Double1", new XmpValue(111.11D));
```
## Paso 5: agregar propiedad de cadena
```java
// Agregar el valor de la propiedad de cadena "xmp:String1"
xmp.put("xmp:String1", new XmpValue("ABC"));
```
## Paso 6: guardar el documento
```java
// Inicializar flujo de archivos EPS de salida
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
//Guardar documento con metadatos XMP modificados
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Paso 7: Cerrar transmisiones
```java
// Cerrar flujo EPS de entrada
psStream.close();
```
## Conclusión
Aspose.Page para Java simplifica el proceso de manipulación de metadatos XMP en archivos EPS. Si sigue esta guía paso a paso, podrá agregar fácilmente propiedades simples para mejorar los metadatos de su documento.
## Preguntas frecuentes
### ¿Puedo utilizar Aspose.Page para Java con otros lenguajes de programación?
Aspose.Page admite principalmente Java, pero hay versiones disponibles para otros lenguajes como .NET.
### ¿Hay una prueba gratuita disponible para Aspose.Page para Java?
 Sí, puede explorar las funciones de Aspose.Page obteniendo una prueba gratuita[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar documentación detallada para Aspose.Page para Java?
 La documentación está disponible.[aquí](https://reference.aspose.com/page/java/).
### ¿Cómo puedo obtener una licencia temporal de Aspose.Page para Java?
 Se puede adquirir una licencia temporal.[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo comprar Aspose.Page para Java?
 Puedes adquirir el producto.[aquí](https://purchase.aspose.com/buy).