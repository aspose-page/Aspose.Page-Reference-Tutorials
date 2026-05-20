---
date: 2026-05-20
description: Aprenda cómo agregar metadatos XMP a archivos EPS con Aspose.Page para
  Java. Guía paso a paso para incrustar propiedades XMP simples mediante programación.
keywords:
- add xmp metadata
- how to add xmp
- Aspose.Page Java XMP
linktitle: Agregar propiedades simples en XMP usando Java
schemas:
- author: Aspose
  dateModified: '2026-05-20'
  description: Learn how to add XMP metadata to EPS files with Aspose.Page for Java.
    Step‑by‑step guide to embed simple XMP properties programmatically.
  headline: Add XMP Metadata to EPS Files Using Java
  type: TechArticle
- questions:
  - answer: Aspose.Page primarily supports Java, but equivalent libraries are available
      for .NET, C++, and Python.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore the features of Aspose.Page by obtaining a free trial
      **[here](https://releases.aspose.com/)**.
    question: Is a free trial available for Aspose.Page for Java?
  - answer: The documentation is available **[here](https://reference.aspose.com/page/java/)**.
    question: Where can I find detailed documentation for Aspose.Page for Java?
  - answer: A temporary license can be acquired **[here](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: You can purchase the product **[here](https://purchase.aspose.com/buy)**.
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Agregar metadatos XMP a archivos EPS usando Java
url: /es/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar metadatos XMP a archivos EPS usando Java

## Introducción
En las tuberías gráficas modernas, poder **add XMP metadata** a archivos EPS de forma programática le brinda control total sobre cómo se describen, buscan y archivan sus ilustraciones. Con Aspose.Page for Java puede leer, modificar y escribir paquetes XMP dentro de documentos EPS sin salir del ecosistema Java. En este tutorial le guiaremos paso a paso para agregar propiedades XMP simples a un archivo EPS, de modo que pueda enriquecer sus gráficos con metadatos personalizados de forma rápida y fiable.

## Respuestas rápidas
- **¿Qué significa “add XMP metadata to EPS”?** Incrustar un paquete XMP (metadatos basados en XML) dentro de un archivo EPS.  
- **¿Qué biblioteca se requiere?** Aspose.Page for Java (descargable desde el sitio de Aspose).  
- **¿Necesito una licencia para pruebas?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Cuántas líneas de código?** Menos de 30 líneas de Java más algunas declaraciones de importación.  
- **¿Puedo agregar otros tipos de datos?** Sí: fechas, enteros, dobles, cadenas e incluso matrices son compatibles.

## Cómo agregar metadatos XMP a archivos EPS usando Java?
Cargue el archivo EPS con `new PsDocument("input.eps")`, recupere o cree su paquete XMP, inserte las propiedades deseadas y luego guarde el documento de nuevo en disco, todo en menos de diez líneas de código Java. Este enfoque le permite incrustar metadatos buscables y compatibles con estándares sin editar manualmente la fuente EPS.

## ¿Qué son los metadatos XMP en EPS?
Los metadatos XMP en EPS son un paquete XML que reside dentro del archivo EPS y almacena información como autor, fecha de creación y etiquetas personalizadas. Incrustar este paquete permite que las herramientas posteriores lean y actúen sobre los datos sin necesidad de archivos auxiliares separados.

## ¿Por qué agregar metadatos XMP a archivos EPS?
Incrustar metadatos XMP hace que los recursos EPS sean instantáneamente buscables, garantiza el cumplimiento al almacenar la información de licencia dentro del archivo, permite que las canalizaciones automatizadas tomen decisiones basadas en etiquetas incrustadas y asegura que los metadatos viajen con el gráfico en todas las plataformas. Aspose.Page puede procesar archivos de hasta 500 MB sin cargar todo el documento en memoria, ofreciendo un rendimiento rápido para cargas de trabajo a gran escala.

## Requisitos previos
Antes de comenzar, asegúrese de tener:

- Conocimientos básicos de programación Java.  
- Biblioteca Aspose.Page for Java instalada. Puede descargarla **[here](https://releases.aspose.com/page/java/)**.  
- Un archivo EPS de muestra que contenga metadatos. Si no tiene uno, siéntase libre de usar el archivo **`xmp3.eps`** proporcionado.

## Importar paquetes
Primero, importe las clases que necesitará. Las importaciones permanecen exactamente iguales que en el ejemplo original:

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

## Paso 1: Cargar el documento EPS y obtener los metadatos XMP
La clase `PsDocument` representa un archivo EPS y proporciona métodos para acceder a su contenido y metadatos.  
El objeto `XmpMetadata` contiene el paquete XMP asociado al documento.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Paso 2: Agregar una propiedad Date
La clase `Date` representa un instante específico en el tiempo, con precisión de milisegundos.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Paso 3: Agregar una propiedad Integer
La clase `Integer` envuelve un valor primitivo `int` como un objeto.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Paso 4: Agregar una propiedad Double
La clase `Double` envuelve un valor primitivo `double` como un objeto.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Paso 5: Agregar una propiedad String
La clase `String` representa una secuencia de caracteres.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Paso 6: Guardar el archivo EPS actualizado
El método `save` escribe el documento modificado de nuevo en disco, preservando la estructura EPS.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Paso 7: Limpiar recursos
Siempre cierre los flujos para evitar fugas de manejadores de archivo y asegurar que todos los buffers se vacíen.

```java
// Close input EPS stream
psStream.close();
```

## Problemas comunes y soluciones
| Issue | Reason | Fix |
|-------|--------|-----|
| **Null XMP metadata** | El archivo EPS no tenía paquete XMP y la biblioteca no pudo inferir los comentarios PS. | Asegúrese de que el EPS de origen contenga al menos un comentario PS (p.ej., `%%Creator`). La biblioteca generará automáticamente un paquete XMP mínimo. |
| **Time zone mismatch** | Las fechas aparecen desplazadas al abrirse en otra aplicación. | Establezca `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` antes de crear el objeto `Date`, como se muestra en el Paso 2. |
| **License exception** | En tiempo de ejecución se lanza `LicenseException`. | Aplique una licencia válida de Aspose.Page antes de usar la API, o ejecute en modo de prueba para evaluación. |

## Preguntas frecuentes
**Q: ¿Puedo usar Aspose.Page for Java con otros lenguajes de programación?**  
A: Aspose.Page admite principalmente Java, pero existen bibliotecas equivalentes para .NET, C++ y Python.

**Q: ¿Está disponible una prueba gratuita para Aspose.Page for Java?**  
A: Sí, puede explorar las funciones de Aspose.Page obteniendo una prueba gratuita **[here](https://releases.aspose.com/)**.

**Q: ¿Dónde puedo encontrar documentación detallada de Aspose.Page for Java?**  
A: La documentación está disponible **[here](https://reference.aspose.com/page/java/)**.

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?**  
A: Una licencia temporal se puede adquirir **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: ¿Dónde puedo comprar Aspose.Page for Java?**  
A: Puede comprar el producto **[here](https://purchase.aspose.com/buy)**.

---

**Last Updated:** 2026-05-20  
**Tested With:** Aspose.Page for Java 24.12 (última versión al momento de escribir)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo leer metadatos XMP usando Java – Guía Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [tutorial XMP de aspose.page – Agregar espacio de nombres en XMP usando Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Agregar elementos de matriz en metadatos XMP usando Java](/page/java/xmp-metadata-manipulation/add-array-items/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}