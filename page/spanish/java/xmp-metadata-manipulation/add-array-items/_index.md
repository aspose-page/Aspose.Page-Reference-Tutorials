---
date: 2025-12-18
description: Aprenda cómo agregar metadatos insertando elementos de matriz en los
  metadatos XMP de archivos EPS usando Aspose.Page para Java. Siga nuestra guía paso
  a paso.
linktitle: Add Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Cómo añadir metadatos – Añadir elementos de matriz en XMP (Java)
url: /es/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar elementos de matriz en los metadatos XMP usando Java

## Cómo agregar metadatos
Bienvenido a nuestra guía paso a paso sobre **cómo agregar metadatos** a archivos EPS con Aspose.Page para Java. En este tutorial le mostraremos cómo añadir elementos de matriz a los metadatos XMP, un requisito frecuente cuando necesita enriquecer la información del documento, como títulos o creadores. Al final, comprenderá por qué XMP es valioso, cómo manipularlo programáticamente y cómo guardar el archivo EPS actualizado.

## Respuestas rápidas
- **¿Qué biblioteca se utiliza?** Aspose.Page para Java  
- **¿Qué formato de archivo se dirige?** EPS (Encapsulated PostScript)  
- **¿Puedo agregar varios títulos?** Sí, use `xmp.addArrayItem("dc:title", ...)` repetidamente  
- **¿Necesito una licencia para producción?** Sí, se requiere una licencia válida de Aspose.Page  
- **¿El código es compatible con Java 8+?** Absolutamente, funciona con todas las versiones modernas de Java  

## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrese de contar con los siguientes requisitos:
- Biblioteca Aspose.Page para Java instalada.  
- Conocimientos básicos de programación en Java.  
- Un archivo EPS válido con metadatos XMP existentes o comentarios de metadatos PS.

## Importar paquetes
Para comenzar, necesita importar los paquetes necesarios para trabajar con Aspose.Page. Incluya las siguientes líneas al inicio de su archivo Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Paso 1: Obtener metadatos XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
En este paso, recuperamos los metadatos XMP existentes del archivo EPS. Si el archivo EPS no contiene metadatos XMP, Aspose.Page genera uno nuevo y lo rellena con valores de los comentarios de metadatos PS.

## Paso 2: Agregar elemento de matriz "dc:title"
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Ahora, añadimos un nuevo elemento de matriz a la propiedad **dc:title** en los metadatos XMP. Reemplace `"NewTitle"` por el título deseado.

## Paso 3: Agregar elemento de matriz "dc:creator"
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
De manera similar, añadimos un nuevo elemento de matriz a la propiedad **dc:creator** en los metadatos XMP. Reemplace `"NewCreator"` por la información del creador deseada.

## Paso 4: Inicializar el flujo del archivo EPS de salida
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Prepare el flujo del archivo EPS de salida donde se guardará el documento modificado con los metadatos XMP actualizados.

## Paso 5: Guardar el documento con los metadatos XMP modificados
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Guarde el documento con los metadatos XMP actualizados en el archivo EPS de salida.

## Conclusión
¡Felicidades! Ha aprendido con éxito **cómo agregar metadatos** insertando elementos de matriz en los metadatos XMP usando Aspose.Page para Java. Esta poderosa biblioteca simplifica el proceso de manipular archivos EPS y ofrece una funcionalidad extensa para el procesamiento de documentos.

## Preguntas frecuentes

### ¿Puedo usar Aspose.Page para Java con otros formatos de documento?
Sí, Aspose.Page admite varios formatos de documento, incluidos EPS, PDF y XPS.

### ¿Hay una versión de prueba gratuita disponible para Aspose.Page para Java?
Sí, puede acceder a la prueba gratuita [aquí](https://releases.aspose.com/).

### ¿Dónde puedo encontrar la documentación de Aspose.Page para Java?
La documentación está disponible [aquí](https://reference.aspose.com/page/java/).

### ¿Cómo puedo comprar Aspose.Page para Java?
Puede adquirir el producto [aquí](https://purchase.aspose.com/buy).

### ¿Existen licencias temporales disponibles para Aspose.Page para Java?
Sí, puede obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

## Preguntas frecuentes adicionales

**P: ¿Puedo agregar más de un elemento de matriz a la misma propiedad?**  
R: Absolutamente. Llame a `xmp.addArrayItem` varias veces para la misma propiedad y construya una lista de valores.

**P: ¿Este enfoque funciona con esquemas XMP existentes diferentes a Dublin Core?**  
R: Sí, puede agregar elementos de matriz a cualquier propiedad XMP siempre que el espacio de nombres esté referenciado correctamente.

**P: ¿Cómo puedo verificar que los metadatos se hayan agregado correctamente?**  
R: Abra el archivo EPS resultante en un visor que admita XMP (por ejemplo, Adobe Bridge) o extraiga los metadatos programáticamente usando los métodos de `XmpMetadata`.

---

**Última actualización:** 2025-12-18  
**Probado con:** Aspose.Page para Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}