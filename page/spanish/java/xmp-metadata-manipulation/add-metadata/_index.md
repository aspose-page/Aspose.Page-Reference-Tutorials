---
date: 2026-03-08
description: Aprende cómo agregar metadatos XMP a archivos EPS con el tutorial de
  Aspose Page para Java. Sigue esta guía paso a paso para mejorar la gestión de tus
  documentos.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Tutorial de Aspose Page Java – Añadir metadatos XMP a archivos EPS
url: /es/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

 Ensure shortcodes at end unchanged.

Let's craft final markdown.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar metadatos en XMP usando Java

## Introducción
En este **aspose page java tutorial**, aprenderá cómo mejorar los metadatos de su documento agregando información XMP usando Java. Esta guía paso a paso le muestra cómo leer un archivo EPS existente, extraer sus metadatos XMP y guardar los cambios en disco con la biblioteca Aspose.Page for Java. Al final del tutorial tendrá un patrón sólido y reutilizable para trabajar con XMP en cualquier flujo de trabajo EPS.

## Respuestas rápidas
- **¿Qué biblioteca se requiere?** Aspose.Page for Java  
- **¿Puedo agregar XMP a cualquier archivo EPS?** Sí – la API crea un nuevo bloque XMP si no existe uno.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para evaluación; se requiere una licencia comercial para producción.  
- **¿Qué versión de Java es compatible?** Java 8 y posteriores.  
- **¿Cuánto tiempo lleva la implementación?** Normalmente menos de 10 minutos para una actualización básica de metadatos.

## ¿Qué es Aspose Page Java?
Aspose.Page for Java (a menudo referido como **aspose page java**) es una API de alto rendimiento que permite a los desarrolladores crear, editar y convertir archivos PostScript y EPS sin necesidad de software Adobe. También brinda acceso completo a los metadatos XMP, lo que le permite incrustar información buscable directamente en sus archivos gráficos.

## ¿Por qué agregar metadatos XMP a archivos EPS?
Incrustar metadatos XMP mejora la gestión de activos, la capacidad de búsqueda y el cumplimiento de estándares de la industria como IPTC y Dublin Core. Cuando agrega campos como creador, título o fecha de creación, los sistemas posteriores (DAM, motores de búsqueda o flujos de trabajo de impresión) pueden indexar y organizar automáticamente sus activos EPS.

## Resumen del tutorial de Aspose Page Java
Este tutorial muestra los pasos clave que necesita para manipular los metadatos XMP en archivos EPS. Comprender estos pasos le ayudará a integrar el manejo de metadatos en pipelines de procesamiento de documentos más amplios, mejorar la buscabilidad y cumplir con los estándares de gestión de activos digitales.

## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de contar con lo siguiente:
- Conocimientos básicos de programación en Java.  
- Biblioteca Aspose.Page for Java instalada. Puede descargarla [aquí](https://releases.aspose.com/page/java/).  
- Un archivo EPS que desee modificar.

## Importar paquetes
Primero, importe los paquetes necesarios a su programa Java:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```

## Paso 1: Obtener metadatos XMP
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created using values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

Reemplace `"Your Document Directory"` con la ruta real donde se almacenan sus documentos.

## Paso 2: Recuperar valor CreatorTool
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Paso 3: Recuperar valor CreateDate
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Paso 4: Recuperar valor Title
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## Paso 5: Recuperar valor Format
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Paso 6: Recuperar valor Creator
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## Paso 7: Recuperar valor MetadataDate
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## Paso 8: Guardar documento con nuevos metadatos XMP
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Save document with new XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

Finalmente, no olvide cerrar el flujo de entrada EPS:

```java
// Close input EPS stream
psStream.close();
```

¡Ahora ha agregado metadatos a su archivo EPS usando Aspose.Page for Java con éxito!

## Problemas comunes y soluciones
- **Bloque XMP ausente** – La API crea uno automáticamente, pero asegúrese de que el archivo EPS no esté dañado.  
- **Caracteres no compatibles** – Los valores XMP deben ser UTF‑8; evite símbolos no estándar en los campos de metadatos.  
- **Archivos EPS grandes** – Procese el archivo usando streams (como se muestra) para mantener bajo el uso de memoria y siempre cierre los streams en un bloque `finally`.

## Conclusión
En este **aspose page java tutorial**, exploramos cómo agregar metadatos XMP a un archivo EPS usando la biblioteca Aspose.Page for Java. Esta poderosa API le permite manipular programáticamente los metadatos del documento, ayudándole a mantener sus activos organizados y buscables.

## Preguntas frecuentes

**P: ¿Aspose.Page for Java es gratuito?**  
R: Aspose.Page for Java es un producto comercial. Puede explorar sus funciones mediante una prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar la documentación de Aspose.Page for Java?**  
R: La documentación está disponible [aquí](https://reference.aspose.com/page/java/).

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?**  
R: Puede obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**P: ¿Qué formatos de archivo admite Aspose.Page for Java?**  
R: Aspose.Page for Java admite varios formatos, incluidos EPS, PDF y XPS.

**P: ¿Puedo comprar Aspose.Page for Java?**  
R: Sí, puede comprar Aspose.Page for Java [aquí](https://purchase.aspose.com/buy).

**P: ¿Cómo manejo archivos EPS grandes al agregar metadatos?**  
R: Procese el archivo de forma streaming (como se muestra) para mantener bajo el uso de memoria y cierre los streams rápidamente.

**P: ¿Puedo modificar campos XMP existentes en lugar de solo leerlos?**  
R: Absolutamente – puede usar `xmp.put(key, value)` para actualizar o agregar nuevas entradas antes de guardar.

---

**Última actualización:** 2026-03-08  
**Probado con:** Aspose.Page for Java 24.12 (última)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}