---
title: Obtenga metadatos de XMP usando Java
linktitle: Obtenga metadatos de XMP usando Java
second_title: API de Java de Aspose.Page
description: Desbloquee el poder de Aspose.Page para Java para extraer metadatos XMP sin esfuerzo. ¡Mejore el análisis de documentos con nuestra guía paso a paso!
weight: 18
url: /es/java/xmp-metadata-manipulation/get-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obtenga metadatos de XMP usando Java

## Introducción
Bienvenido a nuestra guía paso a paso sobre cómo utilizar Aspose.Page para Java para extraer metadatos de archivos XMP. XMP (Plataforma de metadatos extensible) proporciona una forma estandarizada de almacenar metadatos en archivos. Este tutorial se centra en recuperar información esencial de XMP utilizando Java y ofrece información sobre los detalles del documento.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
- Kit de desarrollo de Java (JDK): asegúrese de tener Java instalado en su máquina.
-  Aspose.Page para Java: descargue e instale la biblioteca Aspose.Page, que puede encontrar[aquí](https://releases.aspose.com/page/java/).
## Importar paquetes
En su proyecto Java, importe los paquetes necesarios:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Paso 1: Inicializar la secuencia de archivos EPS de entrada
Comience estableciendo la ruta a su directorio de documentos e inicializando el flujo de archivos EPS de entrada.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```
## Paso 2: obtenga metadatos XMP
Recupere metadatos XMP del archivo EPS. Si el archivo carece de metadatos XMP, se generará uno nuevo con valores de los comentarios de metadatos de PS.
```java
XmpMetadata xmp = document.getXmpMetadata();
```
## Paso 3: extraiga la información de CreatorTool
Verifique e imprima el valor de "CreatorTool" de los metadatos XMP.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Paso 4: extraiga la información de CreateDate
Verifique e imprima el valor "CreateDate" de los metadatos XMP.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Paso 5: recuperar el ancho de la miniatura
Si existen miniaturas, extraiga e imprima el ancho de la primera miniatura.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```
## Paso 6: extraer información de formato
Verifique e imprima el valor de "formato" de los metadatos XMP.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Paso 7: Obtenga el ID del documento
Verifique e imprima el valor "DocumentID" de los metadatos XMP.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```
## Conclusión
¡Felicidades! Ha aprendido con éxito cómo extraer metadatos XMP usando Aspose.Page para Java. Esta guía proporciona una descripción general completa del proceso, lo que garantiza que pueda recuperar eficazmente información esencial de sus documentos.
## Preguntas frecuentes
### ¿Puedo utilizar Aspose.Page para Java con otros lenguajes de programación?
 Sí, Aspose.Page admite varios lenguajes, incluidos Java, .NET y más. Comprobar el[documentación](https://reference.aspose.com/page/java/) para detalles.
### ¿Hay una prueba gratuita disponible para Aspose.Page para Java?
 Sí, puedes acceder a la prueba gratuita.[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar soporte para Aspose.Page para Java?
 Visita el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para el apoyo de la comunidad.
### ¿Cómo obtengo una licencia temporal de Aspose.Page para Java?
 Puedes obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Existen recursos adicionales para Aspose.Page para Java?
 Explora el completo[documentación](https://reference.aspose.com/page/java/) y descargar la biblioteca[aquí](https://releases.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
