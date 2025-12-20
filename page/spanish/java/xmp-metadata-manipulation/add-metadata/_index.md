---
date: 2025-12-20
description: Aprende cómo agregar metadatos XMP a archivos EPS con el tutorial de
  Aspose Page para Java. Sigue esta guía paso a paso para mejorar la gestión de tus
  documentos.
linktitle: Add Metadata in XMP using Java
second_title: Aspose.Page Java API
title: Tutorial de Aspose Page Java – Añadir metadatos XMP a archivos EPS
url: /es/java/xmp-metadata-manipulation/add-metadata/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar metadatos en XMP usando Java

## Introducción
En este **aspose page java tutorial**, aprenderás cómo mejorar los metadatos de tu documento añadiendo información XMP usando Java. Esta guía paso a paso te lleva a través de la lectura de un archivo EPS existente, la extracción de sus metadatos XMP y el guardado de los cambios en disco con la biblioteca Aspose.Page for Java. Al final del tutorial tendrás un patrón sólido y reutilizable para trabajar con XMP en cualquier flujo de trabajo EPS.

## Respuestas rápidas
- **¿Qué biblioteca se requiere?** Aspose.Page for Java  
- **¿Puedo agregar XMP a cualquier archivo EPS?** Sí – la API crea un nuevo bloque XMP si aún no existe.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para evaluación; se requiere una licencia comercial para producción.  
- **¿Qué versión de Java es compatible?** Java 8 y posteriores.  
- **¿Cuánto tiempo lleva la implementación?** Normalmente menos de 10 minutos para una actualización básica de metadatos.

## Descripción general del tutorial de Aspose Page Java
Este tutorial muestra los pasos principales que necesitas para manipular los metadatos XMP en archivos EPS. Entender estos pasos te ayudará a integrar el manejo de metadatos en pipelines de procesamiento de documentos más grandes, mejorar la capacidad de búsqueda y cumplir con los estándares de la industria para la gestión de activos digitales.

## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrate de contar con los siguientes requisitos:
- Conocimientos básicos de programación en Java.  
- Biblioteca Aspose.Page for Java instalada. Puedes descargarla [aquí](https://releases.aspose.com/page/java/).  
- Un archivo EPS que deseas modificar.

## Importar paquetes
Primero, importa los paquetes necesarios en tu programa Java:

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

Reemplaza `"Your Document Directory"` con la ruta real donde se almacenan tus documentos.

## Paso 2: Recuperar el valor CreatorTool
```java
// Get "CreatorTool" value
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Paso 3: Recuperar el valor CreateDate
```java
// Get "CreateDate" value
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Paso 4: Recuperar el valor Title
```java
// Get "Title" value
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```

## Paso 5: Recuperar el valor Format
```java
// Get "format" value
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Paso 6: Recuperar el valor Creator
```java
// Get "creator" value
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```

## Paso 7: Recuperar el valor MetadataDate
```java
// Get "MetadataDate" value
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```

## Paso 8: Guardar el documento con nuevos metadatos XMP
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

Finalmente, no olvides cerrar el flujo de entrada EPS:

```java
// Close input EPS stream
psStream.close();
```

¡Ahora has agregado metadatos a tu archivo EPS usando Aspose.Page for Java!

## Conclusión
En este **aspose page java tutorial**, exploramos cómo añadir metadatos XMP a un archivo EPS usando la biblioteca Aspose.Page for Java. Esta potente API te permite manipular los metadatos del documento de forma programática, ayudándote a mantener los activos organizados y fácilmente buscables.

## Preguntas frecuentes

**Q: ¿Aspose.Page for Java es gratuito?**  
A: Aspose.Page for Java es un producto comercial. Puedes explorar sus funciones mediante una prueba gratuita [aquí](https://releases.aspose.com/).

**Q: ¿Dónde puedo encontrar la documentación de Aspose.Page for Java?**  
A: La documentación está disponible [aquí](https://reference.aspose.com/page/java/).

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?**  
A: Puedes obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**Q: ¿Qué formatos de archivo admite Aspose.Page for Java?**  
A: Aspose.Page for Java admite varios formatos, incluidos EPS, PDF y XPS.

**Q: ¿Puedo comprar Aspose.Page for Java?**  
A: Sí, puedes comprar Aspose.Page for Java [aquí](https://purchase.aspose.com/buy).

**Q: ¿Cómo manejo archivos EPS grandes al agregar metadatos?**  
A: Procesa el archivo de forma streaming (como se muestra) para mantener bajo el uso de memoria y cierra los flujos rápidamente.

**Q: ¿Puedo modificar campos XMP existentes en lugar de solo leerlos?**  
A: Por supuesto – puedes usar `xmp.put(key, value)` para actualizar o añadir nuevas entradas antes de guardar.

---

**Última actualización:** 2025-12-20  
**Probado con:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}