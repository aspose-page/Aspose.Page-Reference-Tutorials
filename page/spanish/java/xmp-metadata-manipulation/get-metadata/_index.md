---
date: 2025-12-21
description: Aprenda a leer metadatos XMP usando Java con Aspose.Page. Esta guía paso
  a paso le muestra cómo leer XMP del formato de documento y extraer propiedades clave.
linktitle: How to Read XMP Metadata using Java
second_title: Aspose.Page Java API
title: Cómo leer metadatos XMP usando Java – Guía de Aspose.Page
url: /es/java/xmp-metadata-manipulation/get-metadata/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Obtener metadatos de XMP usando Java

## Cómo leer metadatos XMP usando Java

Bienvenido a nuestro tutorial paso a paso que muestra **cómo leer XMP** con Java y la biblioteca Aspose.Page. XMP (Extensible Metadata Platform) es un estándar ampliamente adoptado para incrustar metadatos ricos dentro de documentos. Al final de esta guía podrás leer XMP de documentos, extraer información del creador, marcas de tiempo, miniaturas y más, lo que te permitirá crear soluciones de análisis de documentos más inteligentes.

## Respuestas rápidas
- **¿Qué significa “cómo leer xmp”?** Se refiere a extraer metadatos XMP de archivos de forma programática.  
- **¿Qué biblioteca se requiere?** Aspose.Page para Java (disponible en la página de descarga de Aspose).  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para uso en producción; hay una prueba gratuita disponible.  
- **¿Qué versión de Java es compatible?** Java 8 o superior.  
- **¿Puedo leer XMP de otros formatos?** Sí, Aspose.Page puede manejar EPS, PDF y varios tipos de imagen que incrustan XMP.

## Requisitos previos
Antes de sumergirte en el código, asegúrate de tener:

- **Java Development Kit (JDK)** – Java 8+ instalado y configurado en tu máquina.  
- **Aspose.Page para Java** – Descarga la biblioteca del sitio oficial [here](https://releases.aspose.com/page/java/).  
- Un archivo EPS que contenga metadatos XMP (por ejemplo, `xmp1.eps`).  

## Importar paquetes
En tu proyecto Java, importa los paquetes necesarios:
```java
import java.io.FileInputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Paso 1: Inicializar flujo de archivo EPS de entrada
Comienza estableciendo la ruta a tu directorio de documentos e inicializando el flujo del archivo EPS de entrada.
```java
String dataDir = "Your Document Directory";
FileInputStream psStream = new FileInputStream(dataDir + "xmp1.eps");
PsDocument document = new PsDocument(psStream);
```

## Paso 2: Obtener metadatos XMP
Recupera los metadatos XMP del archivo EPS. Si el archivo no contiene metadatos XMP, se generará uno nuevo con valores de los comentarios de metadatos PS.
```java
XmpMetadata xmp = document.getXmpMetadata();
```

## Paso 3: Extraer información de CreatorTool
Verifica e imprime el valor de "CreatorTool" de los metadatos XMP.
```java
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```

## Paso 4: Extraer información de CreateDate
Verifica e imprime el valor de "CreateDate" de los metadatos XMP.
```java
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```

## Paso 5: Recuperar ancho de la miniatura
Si existen miniaturas, extrae e imprime el ancho de la primera miniatura.
```java
if (xmp.containsKey("xmp:Thumbnails") && xmp.get("xmp:Thumbnails").isArray()) {
    XmpValue val = xmp.get("xmp:Thumbnails").toArray()[0];
    if (val.isNamedValues() && val.toNamedValues().containsKey("xmpGImg:width"))
        System.out.println("Thumbnail Width: " + val.toNamedValues().get("xmpGImg:width").toInteger());
}
```

## Paso 6: Extraer información de formato
Verifica e imprime el valor de "format" de los metadatos XMP.
```java
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```

## Paso 7: Obtener DocumentID
Verifica e imprime el valor de "DocumentID" de los metadatos XMP.
```java
if (xmp.containsKey("xmpMM:DocumentID"))
    System.out.println("DocumentID: " + xmp.get("xmpMM:DocumentID").toStringValue());
```

## Por qué es importante
Leer metadatos XMP te permite descubrir programáticamente el origen, la fecha de creación y otros atributos esenciales de un documento sin abrirlo en un visor. Esto es especialmente útil para procesamiento por lotes, sistemas de gestión de contenido y flujos de trabajo de activos digitales donde los metadatos impulsan la indexación y la búsqueda.

## Errores comunes y consejos
- **XMP ausente:** Algunos archivos EPS pueden no contener XMP. La llamada `getXmpMetadata()` sintetizará un conjunto mínimo basado en los comentarios PS existentes, pero no obtendrás metadatos completos a menos que estén incrustados.  
- **Arreglos de miniaturas:** La clave `xmp:Thumbnails` puede contener varias entradas. El ejemplo extrae solo la primera; itera el arreglo si necesitas todas las miniaturas.  
- **Conciencia de espacios de nombres:** Las claves XMP usan espacios de nombres (p. ej., `xmp:`, `dc:`). Asegúrate de referenciar el nombre exacto de la clave; de lo contrario `containsKey` devolverá false.

## Preguntas frecuentes
### ¿Puedo usar Aspose.Page para Java con otros lenguajes de programación?
Sí, Aspose.Page soporta varios lenguajes, incluidos Java, .NET y más. Consulta la [documentación](https://reference.aspose.com/page/java/) para más detalles.

### ¿Hay una prueba gratuita disponible para Aspose.Page para Java?
Sí, puedes acceder a la prueba gratuita [here](https://releases.aspose.com/).

### ¿Dónde puedo encontrar soporte para Aspose.Page para Java?
Visita el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para soporte comunitario.

### ¿Cómo obtengo una licencia temporal para Aspose.Page para Java?
Puedes obtener una licencia temporal [here](https://purchase.aspose.com/temporary-license/).

### ¿Hay recursos adicionales para Aspose.Page para Java?
Explora la documentación completa [here](https://reference.aspose.com/page/java/) y descarga la biblioteca [here](https://releases.aspose.com/page/java/).

## Preguntas frecuentes adicionales
**P: ¿Este enfoque funciona con archivos PDF que contienen XMP?**  
R: Sí, Aspose.Page puede leer XMP de PDF, EPS y varios formatos de imagen.

**P: ¿Puedo modificar los metadatos XMP después de leerlos?**  
R: Absolutamente. El objeto `XmpMetadata` es mutable; puedes agregar, actualizar o eliminar claves y luego guardar el documento.

**P: ¿Existe una forma de extraer todas las imágenes de miniatura, no solo sus dimensiones?**  
R: Puedes obtener los datos binarios de la propiedad `xmpGImg:data` de cada entrada de miniatura y escribirlos a un archivo.

## Conclusión
Ahora dominas **cómo leer XMP** usando Java y Aspose.Page. Siguiendo estos pasos puedes extraer herramientas del creador, marcas de tiempo, miniaturas, información de formato e IDs de documento, obteniendo una visión completa de los metadatos incrustados en tus archivos EPS. Siéntete libre de experimentar con espacios de nombres XMP adicionales para obtener datos aún más ricos para tus aplicaciones.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2025-12-21  
**Probado con:** Aspose.Page para Java 24.12 (última)  
**Autor:** Aspose