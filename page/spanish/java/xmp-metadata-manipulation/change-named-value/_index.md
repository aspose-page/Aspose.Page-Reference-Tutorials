---
date: 2025-12-21
description: tutorial de aspose page xmp – Aprende cómo modificar los metadatos XMP
  en archivos EPS con Aspose.Page para Java en una guía clara, paso a paso.
linktitle: Change Named Value in XMP using Java
second_title: Aspose.Page Java API
title: Tutorial de página XMP de Aspose – Cambiar valor nombrado en XMP usando Java
url: /es/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# aspose page xmp tutorial – Cambiar valor nombrado en XMP usando Java

En los flujos de trabajo modernos de documentos, **Aspose.Page for Java** facilita la lectura, edición y escritura de metadatos XMP dentro de archivos EPS. Este **aspose page xmp tutorial** le guiará a través del cambio de un valor nombrado en el paquete XMP, para que pueda mantener los metadatos de su documento precisos y buscables. Ya sea que esté actualizando dimensiones de página, información del autor o etiquetas personalizadas, los pasos a continuación muestran exactamente cómo hacerlo en Java.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Cambiar un valor nombrado de XMP en un archivo EPS usando Aspose.Page for Java.  
- **¿Qué versión de la biblioteca se requiere?** Cualquier versión reciente de Aspose.Page for Java (la API ha sido estable durante varios años).  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para producción; una prueba gratuita funciona para pruebas.  
- **¿Cuánto tiempo lleva la implementación?** Alrededor de 10‑15 minutos para un desarrollador familiarizado con Java I/O.  
- **¿Puedo usar esto con otros formatos de archivo?** La API XMP también está disponible para PDF, SVG y otros formatos compatibles con Aspose.Page.

## ¿Qué es la metadata XMP?
XMP (Extensible Metadata Platform) es un formato estandarizado para incrustar metadatos enriquecidos —como creador, título y propiedades personalizadas— directamente dentro de los archivos. En documentos EPS, XMP convive con los comentarios tradicionales de PostScript, lo que permite a las aplicaciones leer y modificar metadatos sin alterar el contenido visual.

## ¿Por qué usar Aspose.Page for Java para editar XMP?
- **Full control** – Control total – Acceda a cualquier propiedad XMP, incluidas estructuras personalizadas, sin analizar XML sin procesar.  
- **Cross‑format consistency** – Consistencia entre formatos – La misma API funciona para EPS, PDF y SVG, simplificando el mantenimiento del código.  
- **No external dependencies** – Sin dependencias externas – Biblioteca puramente Java, sin código nativo ni analizadores adicionales necesarios.  
- **Robust error handling** – Manejo robusto de errores – La validación incorporada garantiza que el EPS resultante cumpla con los estándares.

## Introducción
Aspose.Page for Java es una biblioteca Java robusta que facilita la manipulación y el procesamiento de archivos EPS. Cuando se trata de manejar metadatos XMP dentro de estos archivos, Aspose.Page brinda a los desarrolladores un conjunto completo de funciones. En este tutorial, nos enfocaremos en cambiar un valor nombrado en XMP, ofreciendo una guía clara y concisa para los desarrolladores que buscan mejorar sus capacidades de procesamiento de documentos.

## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de contar con los siguientes requisitos:
1. **Java Development Environment** – Entorno de desarrollo Java – Asegúrese de tener un entorno de desarrollo Java configurado en su máquina.  
2. **Aspose.Page for Java Library** – Biblioteca Aspose.Page for Java – Descargue e integre la biblioteca Aspose.Page for Java en su proyecto. Puede encontrar la biblioteca y la documentación detallada [aquí](https://reference.aspose.com/page/java/).  
3. **Sample EPS File** – Archivo EPS de muestra – Tenga un archivo EPS de muestra listo para experimentar. Si no tiene uno, puede usar el archivo de ejemplo proporcionado llamado **"xmp4.eps."**

## Importar paquetes
Para iniciar el proceso, importe los paquetes necesarios en su código Java. Estos paquetes son esenciales para interactuar con Aspose.Page for Java. Incluya las siguientes líneas al comienzo de su archivo Java:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

Ahora, desglosaremos el proceso de cambiar un valor nombrado en XMP usando Aspose.Page for Java en varios pasos:

## Paso 1: Inicializar flujo de archivo EPS de entrada
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Paso 2: Inicializar PsDocument
```java
PsDocument document = new PsDocument(psStream);
```

## Paso 3: Obtener metadatos XMP
```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Paso 4: Establecer nuevo valor en XMP
```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Paso 5: Inicializar flujo de archivo EPS de salida
```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Paso 6: Guardar documento con metadatos XMP modificados
```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Paso 7: Cerrar flujo de archivo EPS de entrada
```java
// Close input EPS stream
psStream.close();
```

Esta guía paso a paso garantiza un enfoque sistemático para cambiar un valor nombrado en XMP usando Aspose.Page for Java. Al seguir estos pasos, puede integrar sin problemas esta funcionalidad en sus aplicaciones Java.

## Problemas comunes y soluciones
- **FileNotFoundException** – Verifique que `dataDir` apunte a la carpeta correcta y que `xmp4.eps` exista.  
- **LicenseException** – Si ve errores de licencia, asegúrese de que se haya cargado un archivo de licencia válido de Aspose.Page antes de crear `PsDocument`.  
- **Metadata Not Updated** – Después de guardar, abra el EPS resultante en un visor de metadatos (p. ej., Adobe Bridge) para confirmar que el nuevo valor aparece.

## Conclusión
En conclusión, Aspose.Page for Java simplifica el proceso de trabajar con metadatos XMP en archivos EPS. Este tutorial le ha proporcionado el conocimiento para cambiar eficientemente un valor nombrado en XMP, mejorando sus capacidades de procesamiento de documentos.

## Preguntas frecuentes
### ¿Puedo usar Aspose.Page for Java con otros lenguajes de programación?
Aspose.Page admite principalmente Java, pero Aspose ofrece bibliotecas similares para varios lenguajes de programación.

### ¿Hay una prueba gratuita disponible para Aspose.Page for Java?
Sí, puede explorar una prueba gratuita de Aspose.Page for Java [aquí](https://releases.aspose.com/).

### ¿Dónde puedo encontrar soporte adicional y discusiones sobre Aspose.Page for Java?
Visite el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para obtener soporte de la comunidad y discusiones.

### ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?
Puede adquirir una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### ¿Dónde puedo comprar Aspose.Page for Java?
Para comprar Aspose.Page for Java, visite la [página de compra](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2025-12-21  
**Probado con:** Aspose.Page for Java (última versión)  
**Autor:** Aspose