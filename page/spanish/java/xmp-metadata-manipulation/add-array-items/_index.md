---
date: 2026-03-05
description: Aprende cómo agregar elementos de la matriz dc:title en los metadatos
  XMP de archivos EPS usando Aspose.Page para Java. Sigue esta guía paso a paso para
  obtener resultados rápidos.
linktitle: How to Add dc:title Array Items in XMP Metadata using Java
second_title: Aspose.Page Java API
title: Cómo añadir elementos de la matriz dc:title en los metadatos XMP usando Java
url: /es/java/xmp-metadata-manipulation/add-array-items/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar elementos de matriz en los metadatos XMP usando Java

## Introducción
En este tutorial descubrirás **cómo agregar dc:title** (y otros elementos de matriz) a los metadatos XMP dentro de un archivo EPS con Aspose.Page for Java. Actualizar los metadatos XMP es útil cuando necesitas incrustar información buscable—como títulos, creadores o palabras clave—directamente en tus archivos gráficos. Recorreremos cada paso, explicaremos por qué cada línea es importante y te mostraremos cómo verificar los cambios.

## Respuestas rápidas
- **¿Qué representa “dc:title”?** Es la propiedad de título del Dublin Core almacenada como una matriz XMP.  
- **¿Por qué modificar los metadatos XMP?** Permite una mejor gestión de activos, capacidad de búsqueda y cumplimiento de estándares.  
- **¿Necesito un bloque XMP existente?** No—Aspose.Page generará uno a partir de los comentarios PS si falta.  
- **¿Qué versión de la biblioteca se requiere?** Cualquier versión reciente de Aspose.Page for Java (probada con la última compilación 2026).  
- **¿Puedo agregar otras propiedades de matriz?** Sí—utilice el mismo método `addArrayItem` para propiedades como `dc:creator`.

## Requisitos previos
Antes de profundizar, asegúrate de tener:

- Biblioteca Aspose.Page for Java instalada (agregue el JAR al classpath de su proyecto).  
- Experiencia básica en desarrollo Java (se recomienda JDK 8+).  
- Un archivo EPS que ya contenga metadatos XMP o al menos comentarios de metadatos PS (p. ej., `%%Title`, `%%Creator`).  

## Importar paquetes
Para comenzar, importe las clases necesarias para leer, manipular y guardar archivos EPS:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Paso 1: Cargar el documento EPS y recuperar los metadatos XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Aquí abrimos el archivo EPS y solicitamos a Aspose.Page su bloque XMP. Si el archivo carece de XMP, la biblioteca lo crea automáticamente usando los comentarios PS existentes, garantizando que siempre tengas un contenedor de metadatos con el que trabajar.

## Paso 2: Agregar un nuevo elemento de matriz **dc:title**  
```java
// Add one more "dc:title" array item 
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```

Esta línea demuestra **cómo agregar dc:title**. Reemplaza `"NewTitle"` con el título real que deseas incrustar. El método añade el valor a la matriz de títulos existente, preservando cualquier título previo.

## Paso 3: Agregar un nuevo elemento de matriz **dc:creator**  
```java
// Add one more "dc:creator" array item
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```

De manera similar, puedes enriquecer la propiedad `dc:creator`. Se pueden almacenar varios creadores; cada llamada agrega otra entrada.

## Paso 4: Preparar el flujo de salida  
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```

Creamos un flujo para el archivo EPS modificado. Usar un nombre de archivo diferente (`xmp3_changed.eps`) mantiene intacto el archivo original.

## Paso 5: Guardar el documento con los metadatos XMP actualizados  
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

La llamada `save` escribe los datos EPS junto con el bloque XMP actualizado. El bloque `finally` garantiza que el manejador de archivo se libere incluso si ocurre una excepción.

## Por qué es importante
Incrustar valores precisos de `dc:title` y `dc:creator` mejora:

- **Capacidad de búsqueda** en sistemas de gestión de activos digitales (DAM).  
- **Cumplimiento** con los estándares de publicación que requieren metadatos.  
- **Colaboración**, ya que los compañeros pueden identificar rápidamente el contenido del archivo sin abrir el EPS.

## Problemas comunes y consejos
- **Problema:** Sobrescribir elementos de matriz existentes sin querer.  
  **Consejo:** Usa `xmp.getArrayItems("dc:title")` para inspeccionar los valores actuales antes de agregar nuevos.  
- **Problema:** Olvidar cerrar los flujos, lo que provoca bloqueos de archivos.  
  **Consejo:** Siempre envuelve I/O en try‑with‑resources o en un bloque `finally` como se muestra.  
- **Consejo:** Puedes encadenar varias llamadas a `addArrayItem` para agregar varios títulos o creadores en una sola pasada.

## Preguntas frecuentes

### ¿Puedo usar Aspose.Page for Java con otros formatos de documento?
Sí, Aspose.Page admite varios formatos de documento, incluidos EPS, PDF y XPS.

### ¿Hay una prueba gratuita disponible para Aspose.Page for Java?
Sí, puedes acceder a la prueba gratuita [here](https://releases.aspose.com/).

### ¿Dónde puedo encontrar la documentación de Aspose.Page for Java?
La documentación está disponible [here](https://reference.aspose.com/page/java/).

### ¿Cómo puedo comprar Aspose.Page for Java?
Puedes comprar el producto [here](https://purchase.aspose.com/buy).

### ¿Están disponibles licencias temporales para Aspose.Page for Java?
Sí, puedes obtener una licencia temporal [here](https://purchase.aspose.com/temporary-license/).

---

**Última actualización:** 2026-03-05  
**Probado con:** Aspose.Page for Java (última versión 2026)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}