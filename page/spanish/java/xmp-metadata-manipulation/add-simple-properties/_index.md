---
date: 2025-12-20
description: Aprende a crear metadatos XMP en archivos EPS usando Aspose.Page para
  Java. Guía paso a paso para agregar propiedades XMP simples de forma programática.
linktitle: Add Simple Properties in XMP using Java
second_title: Aspose.Page Java API
title: Cómo crear EPS con metadatos XMP con Java
url: /es/java/xmp-metadata-manipulation/add-simple-properties/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Añadir propiedades simples en XMP usando Java

## Introducción
En los flujos de trabajo de documentos modernos, poder **create xmp metadata eps** archivos de forma programática le brinda control total sobre cómo se describen, buscan y archivan sus gráficos. Con Aspose.Page for Java puede leer, modificar y escribir paquetes XMP dentro de documentos EPS sin salir del ecosistema Java. En este tutorial le guiaremos paso a paso para añadir propiedades XMP simples a un archivo EPS, de modo que pueda enriquecer sus gráficos con metadatos personalizados de forma rápida y fiable.

## Respuestas rápidas
- **¿Qué significa “create xmp metadata eps”?** Añadir un paquete XMP (metadatos basados en XML) a un archivo EPS.  
- **¿Qué biblioteca se requiere?** Aspose.Page for Java (descargable desde el sitio de Aspose).  
- **¿Necesito una licencia para pruebas?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Cuántas líneas de código?** Menos de 30 líneas de Java más algunas declaraciones de importación.  
- **¿Puedo añadir otros tipos de datos?** Sí, se admiten fechas, enteros, dobles, cadenas e incluso matrices.

## ¿Qué es create xmp metadata eps?
XMP (Extensible Metadata Platform) es un estándar para incrustar metadatos ricos dentro de archivos. Cuando **create XMP metadata EPS**, inserta un paquete XML dentro de un documento EPS (Encapsulated PostScript), lo que permite a las aplicaciones posteriores leer el autor, la fecha de creación, etiquetas personalizadas y más.

## ¿Por qué añadir metadatos XMP a archivos EPS?
- **Facilidad de búsqueda:** Permite la indexación automática por sistemas DAM.  
- **Cumplimiento:** Almacena información legal o de licencias directamente en el archivo.  
- **Automatización:** Permite que las canalizaciones posteriores tomen decisiones basadas en los datos incrustados.  
- **Portabilidad:** Los metadatos viajan con el EPS, garantizando consistencia entre plataformas.

## Requisitos previos
Antes de comenzar, asegúrese de tener:

- Conocimientos básicos de programación en Java.  
- La biblioteca Aspose.Page for Java instalada. Puede descargarla **[here](https://releases.aspose.com/page/java/)**.  
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
Abrimos el archivo EPS, creamos una instancia de `PsDocument` y recuperamos (o creamos) el paquete XMP.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Paso 2: Añadir una propiedad de fecha
Añadir una fecha es tan simple como crear un objeto `Date` y colocarlo en el mapa XMP.

```java
// Add date property "xmp:Date1" value
TimeZone.setDefault(TimeZone.getTimeZone("UTC"));
Date now = new Date();
xmp.put("xmp:Date1", new XmpValue(now));
```

## Paso 3: Añadir una propiedad entera
Puede almacenar identificadores numéricos o números de versión usando un valor entero.

```java
// Add integer property "xmp:Intg1" value
xmp.put("xmp:Intg1", new XmpValue(111));
```

## Paso 4: Añadir una propiedad doble
Los números de punto flotante son útiles para mediciones o calificaciones.

```java
// Add double property "xmp:Double1" value
xmp.put("xmp:Double1", new XmpValue(111.11D));
```

## Paso 5: Añadir una propiedad de cadena
Las etiquetas textuales personalizadas (p. ej., códigos de proyecto) se almacenan como cadenas.

```java
// Add string property "xmp:String1" value
xmp.put("xmp:String1", new XmpValue("ABC"));
```

## Paso 6: Guardar el archivo EPS actualizado
Después de añadir todas las propiedades, escriba el documento de nuevo en el disco.

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

## Paso 7: Liberar recursos
Siempre cierre el flujo de entrada para evitar fugas de manejadores de archivo.

```java
// Close input EPS stream
psStream.close();
```

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| **Metadatos XMP nulos** | El archivo EPS no tenía paquete XMP y la biblioteca no pudo inferir los comentarios PS. | Asegúrese de que el EPS de origen contenga al menos un comentario PS (p. ej., `%%Creator`). La biblioteca generará automáticamente un paquete XMP mínimo. |
| **Desajuste de zona horaria** | Las fechas aparecen desplazadas al abrirse en otra aplicación. | Establezca `TimeZone.setDefault(TimeZone.getTimeZone("UTC"))` antes de crear el objeto `Date`, como se muestra en el Paso 2. |
| **Excepción de licencia** | En tiempo de ejecución se lanza `LicenseException`. | Aplique una licencia válida de Aspose.Page antes de usar la API, o ejecute en modo de prueba para evaluación. |

## Conclusión
Al seguir estos pasos ahora sabe cómo **create XMP metadata EPS** archivos usando Aspose.Page for Java. Añadir propiedades simples como fechas, enteros, dobles y cadenas es sencillo, y los archivos EPS resultantes llevan metadatos ricos y buscables que benefician cualquier flujo de trabajo posterior.

## Preguntas frecuentes
### ¿Puedo usar Aspose.Page for Java con otros lenguajes de programación?
Aspose.Page principalmente soporta Java, pero existen versiones disponibles para otros lenguajes como .NET.

### ¿Está disponible una prueba gratuita para Aspose.Page for Java?
Sí, puede explorar las funciones de Aspose.Page obteniendo una prueba gratuita [here](https://releases.aspose.com/).

### ¿Dónde puedo encontrar documentación detallada para Aspose.Page for Java?
La documentación está disponible [here](https://reference.aspose.com/page/java/).

### ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?
Una licencia temporal se puede adquirir [here](https://purchase.aspose.com/temporary-license/).

### ¿Dónde puedo comprar Aspose.Page for Java?
Puede comprar el producto [here](https://purchase.aspose.com/buy).

---

**Última actualización:** 2025-12-20  
**Probado con:** Aspose.Page for Java 24.11 (última disponible al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}