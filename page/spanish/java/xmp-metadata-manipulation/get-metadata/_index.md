---
date: 2026-05-25
description: Aprenda cómo leer XMP usando Aspose.Page con Java. Esta guía paso a paso
  muestra la extracción de XMP metadata, creator info, timestamps, thumbnails y más.
keywords:
- read xmp using aspose.page
- xmp metadata java
- aspose.page java
linktitle: Cómo leer XMP Metadata usando Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to read xmp using aspose.page with Java. This step‑by‑step
    guide shows extracting XMP metadata, creator info, timestamps, thumbnails, and
    more.
  headline: Read XMP using Aspose.Page – Java Guide
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page can read XMP from PDF, EPS, and several image formats.
    question: Does this approach work with PDF files that contain XMP?
  - answer: Absolutely. The `XmpMetadata` object is mutable; you can add, update,
      or remove keys and then save the document.
    question: Can I modify XMP metadata after reading it?
  - answer: You can retrieve the binary data from the `xmpGImg:data` property of each
      thumbnail entry and write it to a file.
    question: Is there a way to extract all thumbnail images, not just dimensions?
  type: FAQPage
second_title: Aspose.Page Java API
title: Leer XMP usando Aspose.Page – Guía de Java
url: /es/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obtener metadatos de XMP usando Java

## ¿Cómo leer XMP usando Aspose.Page (Java)?

Cargue el archivo EPS con `new Document("file.eps")` — la clase `Document` representa un archivo cargado. Llame a `getXmpMetadata()`, que extrae el paquete XMP, y luego consulte el objeto `XmpMetadata` devuelto — una interfaz similar a un mapa para las propiedades XMP — para obtener las claves que necesita. Todo esto es necesario para leer XMP usando Aspose.Page. La API abstrae el análisis de bajo nivel, por lo que obtiene un mapa de propiedades listo para usar en solo dos líneas de código.

Bienvenido a nuestro tutorial paso a paso que muestra **cómo leer XMP** metadatos con Java y la biblioteca Aspose.Page. XMP (Extensible Metadata Platform) es un estándar ampliamente adoptado para incrustar metadatos ricos dentro de documentos. Al final de esta guía podrá leer XMP del formato de documento, extraer información del creador, marcas de tiempo, miniaturas y más, lo que le permitirá crear soluciones de análisis de documentos más inteligentes.

## Respuestas rápidas
- **¿Qué significa “read XMP”?** Significa extraer programáticamente el paquete XMP que almacena metadatos dentro de un archivo.  
- **¿Qué biblioteca se requiere?** Aspose.Page for Java (descargue desde la página oficial [here](https://releases.aspose.com/page/java/)).  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para producción; una prueba gratuita funciona para evaluación.  
- **¿Qué versión de Java es compatible?** Java 8 o superior.  
- **¿Puedo leer XMP de otros formatos?** Sí – Aspose.Page extrae XMP de EPS, PDF, JPEG, PNG y más de 20 formatos adicionales.

## Requisitos previos
Antes de sumergirse en el código, asegúrese de tener:

- **Java Development Kit (JDK)** – Java 8+ instalado y configurado en su máquina.  
- **Aspose.Page for Java** – Descargue la biblioteca desde el sitio oficial [here](https://releases.aspose.com/page/java/).  
- Un archivo EPS que contenga metadatos XMP (p. ej., `xmp1.eps`).  

## Importar paquetes
La clase `XmpMetadata` se encuentra en el espacio de nombres `com.aspose.page.xmp`, mientras que la clase `Document` está en `com.aspose.page`. Importe ambas para poder trabajar con el archivo EPS y sus metadatos.  
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Paso 1: Inicializar el flujo de archivo EPS de entrada
Comience estableciendo la ruta a su directorio de documentos e inicializando el flujo de archivo EPS de entrada.  
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Paso 2: Obtener metadatos XMP
`XmpMetadata` es el objeto de Aspose.Page que contiene el paquete XMP extraído de un documento. Obténgalo con `document.getXmpMetadata()`. Si el archivo no tiene XMP, la API sintetiza un paquete mínimo a partir de los comentarios PostScript existentes.  
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Paso 3: Extraer información de CreatorTool
La clave `CreatorTool` se encuentra bajo el espacio de nombres `xmp` y registra la aplicación que generó el archivo. Verifique su presencia e imprima el valor.  
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Paso 4: Extraer información de CreateDate
`CreateDate` almacena la marca de tiempo cuando el documento fue creado originalmente. Use el mismo patrón `containsKey`/`get` para leerlo.  
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Paso 5: Recuperar el ancho de la miniatura
Si existen miniaturas, la matriz `xmp:Thumbnails` contiene una o más entradas. Cada entrada incluye `width`, `height` y datos binarios. El ejemplo extrae el ancho de la primera miniatura.  
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Paso 6: Extraer información de formato
La clave `format` indica el formato original del archivo (p. ej., “application/postscript”). Esto es útil cuando necesita registrar o validar tipos de origen.  
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Paso 7: Obtener DocumentID
`DocumentID` es un identificador único asignado por la aplicación creadora. Puede usarse para deduplicación en grandes bibliotecas de recursos.  
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Por qué es importante
Aspose.Page puede leer XMP de **más de 20** formatos de archivo y procesa documentos de hasta **500 MB** sin cargar el archivo completo en memoria, brindándole un acceso rápido y de bajo consumo a los metadatos esenciales. Esta capacidad es crítica para tuberías de procesamiento por lotes, sistemas de gestión de activos digitales y cualquier solución que dependa de atributos de documentos buscables y legibles por máquina.

## Errores comunes y consejos
- **XMP faltante:** Algunos archivos EPS pueden no contener XMP. La llamada `getXmpMetadata()` sintetizará un conjunto mínimo basado en los comentarios PS existentes, pero no obtendrá metadatos completos a menos que estén incrustados.  
- **Arreglos de miniaturas:** La clave `xmp:Thumbnails` puede contener múltiples entradas. El ejemplo extrae solo la primera; itere el arreglo si necesita todas las miniaturas.  
- **Conciencia de espacios de nombres:** Las claves XMP usan espacios de nombres (p. ej., `xmp:`, `dc:`). Asegúrese de referenciar el nombre exacto de la clave; de lo contrario `containsKey` devolverá false.  

## Preguntas frecuentes
### ¿Puedo usar Aspose.Page para Java con otros lenguajes de programación?
Sí, Aspose.Page soporta Java, .NET y varios otros lenguajes. Consulte la lista completa en la [documentation](https://reference.aspose.com/page/java/).

### ¿Está disponible una prueba gratuita para Aspose.Page para Java?
Sí, puede acceder a la prueba gratuita [here](https://releases.aspose.com/).

### ¿Dónde puedo encontrar soporte para Aspose.Page para Java?
Visite el [Aspose.Page forum](https://forum.aspose.com/c/page/39) para obtener ayuda de la comunidad y soporte oficial.

### ¿Cómo obtengo una licencia temporal para Aspose.Page para Java?
Puede obtener una licencia temporal [here](https://purchase.aspose.com/temporary-license/).

### ¿Hay recursos adicionales para Aspose.Page para Java?
Explore la [documentation](https://reference.aspose.com/page/java/) completa y descargue la biblioteca [here](https://releases.aspose.com/page/java/).

## Preguntas frecuentes adicionales
**Q: ¿Este enfoque funciona con archivos PDF que contienen XMP?**  
A: Sí, Aspose.Page puede leer XMP de PDF, EPS y varios formatos de imagen.

**Q: ¿Puedo modificar los metadatos XMP después de leerlos?**  
A: Absolutamente. El objeto `XmpMetadata` es mutable; puede agregar, actualizar o eliminar claves y luego guardar el documento.

**Q: ¿Hay una forma de extraer todas las imágenes en miniatura, no solo sus dimensiones?**  
A: Puede obtener los datos binarios de la propiedad `xmpGImg:data` de cada entrada de miniatura y escribirlos a un archivo.

## Conclusión
Ahora ha dominado **cómo leer XMP** metadatos usando Java y Aspose.Page. Siguiendo estos pasos puede extraer herramientas de creación, marcas de tiempo, miniaturas, información de formato y IDs de documento, brindándole una visión completa de los metadatos incrustados en sus archivos EPS. Siéntase libre de experimentar con espacios de nombres XMP adicionales para obtener datos aún más ricos para sus aplicaciones.

---

**Última actualización:** 2026-05-25  
**Probado con:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose

## Tutoriales relacionados

- [Tutorial Aspose Page Java – Añadir metadatos XMP a archivos EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [tutorial xmp de aspose.page – Añadir espacio de nombres en XMP usando Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [tutorial xmp de aspose page – Cambiar valor nombrado en XMP usando Java](/page/java/xmp-metadata-manipulation/change-named-value/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}