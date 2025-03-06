---
title: Cambiar valores en XMP usando Java
linktitle: Cambiar valores en XMP usando Java
second_title: API de Java de Aspose.Page
description: Mejore los documentos EPS con Aspose.Page para Java. Modifique los metadatos XMP sin esfuerzo para obtener contenido personalizado y profesional. #DesarrolloJava
weight: 17
url: /es/java/xmp-metadata-manipulation/change-values/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cambiar valores en XMP usando Java

## Introducción
En el ámbito del procesamiento y manipulación de documentos, Aspose.Page para Java se destaca como una herramienta poderosa. Este tutorial profundiza en el proceso de cambio de valores XMP (Extensible Metadata Platform) en documentos EPS (Encapsulated PostScript) usando Java con la biblioteca Aspose.Page. Siguiendo la guía paso a paso proporcionada, aprenderá cómo modificar metadatos sin esfuerzo, asegurando que sus documentos se adapten a sus requisitos específicos.
## Requisitos previos
Antes de embarcarnos en este tutorial, asegúrese de tener implementados los siguientes requisitos previos:
1. Entorno de desarrollo de Java: asegúrese de tener un entorno de desarrollo de Java que funcione en su máquina.
2.  Biblioteca Aspose.Page para Java: descargue e instale la biblioteca Aspose.Page para Java. Puedes encontrar el paquete necesario.[aquí](https://releases.aspose.com/page/java/).
## Importar paquetes
Comience importando los paquetes necesarios a su proyecto Java. Estos paquetes son vitales para interactuar y manipular documentos EPS.
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
Recupere metadatos XMP del documento EPS. Si el archivo EPS no contiene metadatos XMP, se creará uno nuevo con valores de comentarios de metadatos PS como %%Creator, %%CreateDate y %%Title.
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Inicializar flujo de archivos EPS de entrada
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Obtenga metadatos XMP. Si el archivo EPS no contiene metadatos XMP, se crea uno nuevo con valores de los comentarios de metadatos PS
XmpMetadata xmp = document.getXmpMetadata();
```
## Paso 2: cambiar el valor de "ModifyDate"
Modifique el valor "ModifyDate" en los metadatos XMP para reflejar la fecha deseada.
```java
// Cambiar el valor de "Modificar fecha"
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```
## Paso 3: cambiar el valor de "Creador"
Actualice el valor "Creador" en los metadatos XMP para especificar el creador del documento.
```java
// Cambiar el valor del "creador"
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```
## Paso 4: cambiar el valor del "Título"
Modifique el valor "Título" en los metadatos XMP para establecer un título apropiado para el documento.
```java
//Cambiar el valor del "título"
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```
## Paso 5: guardar el documento con metadatos XMP modificados
Guarde el documento con los metadatos XMP actualizados en un nuevo archivo EPS.
```java
// Inicializar flujo de archivos EPS de salida
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
//Guardar documento con metadatos XMP modificados
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Conclusión
¡Felicidades! Ha navegado con éxito en el proceso de cambiar los valores XMP en documentos EPS utilizando Aspose.Page para Java. Este tutorial le ha proporcionado el conocimiento para modificar metadatos, garantizando que sus documentos se alineen perfectamente con sus requisitos específicos.
## Preguntas frecuentes
### P: ¿Cómo puedo manejar las consideraciones de zona horaria al modificar los valores XMP?
 Utilizar`TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` para garantizar la coherencia en la configuración de la zona horaria.
### P: ¿Puedo cambiar varios valores XMP en una sola operación?
 Sí, usando el`put` Para cada valor deseado, puede modificar varios valores XMP simultáneamente.
### P: ¿Dónde puedo encontrar documentación adicional para Aspose.Page para Java?
 Explora la documentación completa[aquí](https://reference.aspose.com/page/java/).
### P: ¿Hay una prueba gratuita disponible para Aspose.Page para Java?
 Sí, puedes acceder a la prueba gratuita.[aquí](https://releases.aspose.com/).
### P: ¿Cómo puedo obtener una licencia temporal de Aspose.Page para Java?
 Obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
