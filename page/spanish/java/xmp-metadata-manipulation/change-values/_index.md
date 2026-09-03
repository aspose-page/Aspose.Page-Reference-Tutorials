---
date: 2026-05-25
description: Aprenda cómo modificar xmp en documentos EPS usando Java con Aspose.Page.
  Actualice metadata de forma rápida y fiable.
keywords:
- how to modify xmp
- Aspose.Page Java
- XMP metadata EPS
linktitle: Cambiar valores en XMP usando Java
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to modify xmp in EPS documents using Java with Aspose.Page.
    Update metadata quickly and reliably.
  headline: how to modify xmp with Aspose.Page – Change Values in XMP using Java
  type: TechArticle
- questions:
  - answer: Utilize `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` to ensure consistency
      in time zone settings.
    question: How can I handle time zone considerations when modifying XMP values?
  - answer: Yes, by using the `put` method for each desired value, you can modify
      multiple XMP values concurrently.
    question: Can I change multiple XMP values in a single operation?
  - answer: Explore the comprehensive documentation [here](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation for Aspose.Page for Java?
  - answer: Yes, you can access the free trial [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Obtain a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Cómo modificar xmp con Aspose.Page – Cambiar valores en XMP usando Java
url: /es/java/xmp-metadata-manipulation/change-values/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cambiar valores en XMP usando Java

## Introducción
Si buscas **cómo modificar xmp** dentro de un archivo EPS con Java, has llegado al lugar correcto. Este tutorial te guía paso a paso: leyendo el bloque XMP existente, actualizando campos como creador, título y fecha de modificación, y finalmente guardando los cambios de vuelta en el documento EPS. Al final tendrás un fragmento reutilizable que encaja en cualquier flujo de trabajo automatizado, asegurando que tus archivos contengan los metadatos correctos para la marca, el cumplimiento o la indexación en motores de búsqueda.

## Respuestas rápidas
- **¿Qué hace “aspose.page modify xmp”?** Permite leer y escribir metadatos XMP en archivos EPS a través de la API Java de Aspose.Page.  
- **¿Qué versión de la biblioteca se requiere?** Cualquier versión reciente de Aspose.Page para Java (la API es estable entre versiones).  
- **¿Necesito una licencia para ejecutar el ejemplo?** Una prueba gratuita funciona para evaluación; se requiere una licencia comercial para producción.  
- **¿Puedo cambiar varios campos XMP a la vez?** Sí—llama a `put` para cada campo antes de guardar el documento.  
- **¿Se necesita manejo de zona horaria?** Configurar la zona horaria predeterminada (p.ej., UTC) garantiza valores de fecha consistentes.

## Qué es XMP y por qué modificarlo?
XMP (Extensible Metadata Platform) es un formato estandarizado basado en XML para incrustar metadatos enriquecidos directamente dentro de archivos como EPS, PDF e imágenes. Actualizar XMP te permite controlar cómo se indexan, muestran y buscan los documentos—crucial para la consistencia de la marca, el cumplimiento regulatorio y los flujos de contenido automatizados.

## ¿Por qué usar Aspose.Page para Java?
Aspose.Page ofrece una **API completa, puramente Java** que elimina la necesidad de herramientas externas o bibliotecas nativas. Soporta **más de 50 formatos de entrada y salida** y puede procesar archivos EPS de hasta **500 MB** sin cargar todo el documento en memoria, proporcionando una manipulación de metadatos rápida y de bajo consumo de memoria en cualquier sistema operativo que ejecute Java.

## Requisitos previos
Antes de comenzar este tutorial, asegúrate de tener los siguientes requisitos:
1. **Entorno de desarrollo Java** – Un JDK (8 o superior) y un IDE o herramienta de compilación de tu elección.  
2. **Biblioteca Aspose.Page para Java** – Descarga e instala la biblioteca Aspose.Page para Java. Puedes encontrar el paquete necesario [aquí](https://releases.aspose.com/page/java/).

## Importar paquetes
Comienza importando los paquetes necesarios en tu proyecto Java. Estos paquetes son esenciales para interactuar y manipular documentos EPS.

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

## ¿Cómo modificar XMP en EPS usando Java?
`Document` es la clase Aspose.Page que representa un archivo EPS y proporciona acceso a su contenido y metadatos. `XmpMetadata` representa el bloque XMP adjunto al documento y permite leer y escribir campos de metadatos. `put` agrega o actualiza una entrada de metadato en el objeto XmpMetadata. `save` escribe el documento modificado, incluyendo cualquier metadato XMP actualizado, a un archivo.

Carga el archivo EPS con `new Document("input.eps")`, recupera su objeto `XmpMetadata`, actualiza las claves deseadas usando `put` y finalmente llama a `save` para escribir los cambios en un nuevo archivo. Este flujo conciso maneja automáticamente los bloques XMP faltantes, crea uno a partir de los comentarios PostScript cuando es necesario y garantiza fechas consistentes con la zona horaria.

## Paso 1: Obtener metadatos XMP
La clase `XmpMetadata` representa el bloque XMP adjunto a un documento EPS. Cuando llamas a `document.getXmpMetadata()`, la API devuelve el bloque existente o crea uno nuevo a partir de los comentarios PS como `%%Creator`, `%%CreateDate` y `%%Title`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, a new one is created with values from PS metadata comments
XmpMetadata xmp = document.getXmpMetadata();
```

## Paso 2: Cambiar el valor de "ModifyDate"
Actualiza la entrada `"ModifyDate"` para reflejar la nueva marca de tiempo de modificación. Usa `java.util.Date` combinado con `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` para garantizar que el valor almacenado sea independiente de la zona horaria.

```java
// Change "ModifyDate" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:ModifyDate", new XmpValue(now));
```

## Paso 3: Cambiar el valor de "Creator"
La clave `"Creator"` almacena el nombre de la aplicación o persona que generó el archivo EPS. Llama a `xmp.put("dc:creator", "Your Company Name")` para reemplazar el valor existente con un identificador personalizado.

```java
// Change "creator" value
XmpValue value = new XmpValue("Aspose.Page");
xmp.put("dc:creator", value);
```

## Paso 4: Cambiar el valor de "Title"
El campo `"Title"` es mostrado por muchos sistemas de gestión de activos. Configurarlo mediante `xmp.put("dc:title", "New Document Title")` asegura que el documento aparezca correctamente en catálogos y resultados de búsqueda.

```java
// Change "title" value
value = new XmpValue("(PAGEJAVA-29.eps)");
xmp.put("dc:title", value);
```

## Paso 5: Guardar el documento con los metadatos XMP modificados
Después de todas las modificaciones, invoca `document.save("output.eps")`. La biblioteca escribe el bloque XMP actualizado de vuelta en el flujo EPS mientras preserva el contenido gráfico original sin cambios.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp1_changed.eps");
// Save document with changed XMP metadata
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Problemas comunes y soluciones
- **Bloque XMP faltante** – La API crea automáticamente uno a partir de los comentarios PS, pero también puedes instanciar manualmente `XmpMetadata` si es necesario.  
- **Desajustes de zona horaria** – Siempre establece `TimeZone.setDefault` antes de crear el objeto `Date` para evitar desplazamientos inesperados.  
- **Errores de acceso a archivos** – Asegúrate de que las rutas de entrada y salida sean correctas y de que tu aplicación tenga permisos de lectura/escritura.

## Preguntas frecuentes

**P: ¿Cómo puedo manejar consideraciones de zona horaria al modificar valores XMP?**  
Utiliza `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` para asegurar la consistencia en la configuración de la zona horaria.

**P: ¿Puedo cambiar varios valores XMP en una sola operación?**  
Sí, usando el método `put` para cada valor deseado, puedes modificar varios valores XMP simultáneamente.

**P: ¿Dónde puedo encontrar documentación adicional para Aspose.Page para Java?**  
Explora la documentación completa [aquí](https://reference.aspose.com/page/java/).

**P: ¿Hay una prueba gratuita disponible para Aspose.Page para Java?**  
Sí, puedes acceder a la prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.Page para Java?**  
Obtén una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**P: ¿Modificar XMP afecta el contenido visual del EPS?**  
No. Los cambios en XMP son solo de metadatos y no alteran los elementos gráficos del archivo EPS.

**P: ¿Puedo leer programáticamente los valores actualizados para verificar el cambio?**  
Absolutamente—simplemente llama a `xmp.get("dc:creator")` (o la clave correspondiente) después de guardar y antes de cerrar el documento.

## Conclusión
¡Felicidades! Has dominado **cómo modificar valores xmp** en documentos EPS usando Aspose.Page para Java. Al incrustar metadatos precisos de creador, título y fecha de modificación, aseguras que tus activos sean buscables, cumplan con las normativas y estén alineados con los estándares de tu marca. Siéntete libre de integrar este patrón en pipelines de procesamiento por lotes, pasos de CI/CD o cualquier flujo de trabajo automatizado de generación de documentos.

---

**Last Updated:** 2026-05-25  
**Tested With:** Aspose.Page for Java (latest release)  
**Author:** Aspose

## Tutoriales relacionados

- [Tutorial Aspose Page Java – Añadir metadatos XMP a archivos EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [Cómo leer metadatos XMP usando Java – Guía Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [aspose.page xmp java - Cambiar elementos de matriz en XMP usando Java](/page/java/xmp-metadata-manipulation/change-array-items/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}