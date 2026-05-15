---
date: 2026-05-15
description: Aprende cómo editar los metadatos XMP y cómo cambiar los valores XMP
  en archivos EPS con Aspose.Page for Java – una guía clara paso a paso.
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Cambiar valor con nombre en XMP usando Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: Cómo editar XMP – Cambiar valor con nombre en XMP usando Java
url: /es/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# cómo editar xmp – Cambiar valor nombrado en XMP usando Java

En los flujos de trabajo modernos de documentos, **Aspose.Page for Java** facilita la lectura, edición y escritura de metadatos XMP dentro de archivos EPS. **Este tutorial muestra cómo editar metadatos xmp** en documentos EPS usando la API de Aspose.Page, para que puedas mantener la información de tu documento precisa, buscable y conforme a los estándares de la industria. Ya sea que estés actualizando dimensiones de página, información del autor o etiquetas personalizadas, los pasos a continuación te guiarán a través del proceso en Java.

## Respuestas rápidas
- **¿Qué cubre este tutorial?** Cambiar un valor XMP nombrado en un archivo EPS con Aspose.Page for Java.  
- **¿Qué versión de la biblioteca se requiere?** Cualquier versión reciente de Aspose.Page for Java (la API ha sido estable durante varios años).  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para producción; una prueba gratuita funciona para pruebas.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un desarrollador familiarizado con Java I/O.  
- **¿Puedo usar esto con otros formatos de archivo?** La API XMP también está disponible para PDF, SVG y otros formatos compatibles con Aspose.Page.

## ¿Qué son los metadatos XMP?
XMP (Extensible Metadata Platform) es un formato estandarizado basado en XML para incrustar metadatos ricos —como creador, título y propiedades personalizadas— directamente dentro de los archivos. En los documentos EPS, XMP vive junto a los comentarios tradicionales de PostScript, lo que permite a las aplicaciones leer y modificar los metadatos sin alterar el contenido visual.

## ¿Por qué usar Aspose.Page para Java para editar XMP?
Aspose.Page te brinda **control total sobre más de 150 propiedades de esquema XMP** y funciona de manera consistente en formatos EPS, PDF y SVG. Procesa archivos de hasta **500 MB** sin cargar todo el documento en memoria, e incluye validación incorporada que garantiza que el EPS resultante cumpla con los estándares. No se requieren analizadores XML externos ni bibliotecas nativas.

## Introducción
Aspose.Page for Java es una biblioteca robusta que facilita la manipulación y el procesamiento de archivos EPS. Cuando se trata de manejar metadatos XMP dentro de estos archivos, Aspose.Page capacita a los desarrolladores con un conjunto completo de funciones. En este tutorial nos enfocaremos en cambiar un valor nombrado en XMP, ofreciendo una guía clara y concisa para los desarrolladores que desean mejorar sus capacidades de procesamiento de documentos.

## Requisitos previos
Antes de sumergirte en el tutorial, asegúrate de contar con los siguientes requisitos:
1. **Entorno de desarrollo Java** – Un JDK (8 o superior) y un IDE o herramienta de compilación (Maven/Gradle).  
2. **Biblioteca Aspose.Page for Java** – Descarga e integra la biblioteca Aspose.Page for Java en tu proyecto. Puedes encontrar la biblioteca y la documentación detallada [aquí](https://reference.aspose.com/page/java/).  
3. **Archivo EPS de muestra** – Ten listo un archivo EPS de muestra para experimentar. Si no tienes uno, usa el archivo de ejemplo proporcionado llamado **"xmp4.eps."**

## Importar paquetes
Las sentencias `import` traen las clases esenciales de Aspose.Page al alcance.

La clase `PsDocument` es el objeto central de Aspose.Page que representa un documento EPS en memoria.  
La clase `XmpMetadata` proporciona acceso al paquete XMP incrustado en el archivo EPS.  

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## ¿Cómo editar metadatos XMP?
Carga el archivo EPS, recupera su paquete XMP, modifica la propiedad deseada y guarda el documento, todo en unas pocas líneas sencillas. Este enfoque funciona para cualquier valor XMP nombrado, ya sea un campo estándar Dublin Core o un espacio de nombres personalizado que hayas definido.

## Paso 1: Inicializar flujo de archivo EPS de entrada
`FileInputStream` abre un flujo de solo lectura al archivo EPS de origen, permitiendo que Aspose.Page ingiera el documento sin bloquear el sistema de archivos.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Paso 2: Inicializar PsDocument
`PsDocument` es el objeto principal que encapsula el contenido EPS y brinda acceso a sus metadatos, páginas y recursos.

```java
PsDocument document = new PsDocument(psStream);
```

## Paso 3: Obtener metadatos XMP
`XmpMetadata` representa el paquete XMP dentro del archivo EPS y ofrece métodos para leer, modificar o eliminar propiedades individuales.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Paso 4: Establecer nuevo valor en XMP
`setProperty` establece el valor de una propiedad XMP especificada en el paquete de metadatos.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Paso 5: Inicializar flujo de archivo EPS de salida
`FileOutputStream` crea un flujo de escritura para guardar el archivo EPS modificado.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Paso 6: Guardar documento con metadatos XMP modificados
`save` escribe el `PsDocument` en memoria, incluidos los XMP actualizados, al flujo de salida.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Paso 7: Cerrar flujo de archivo EPS de entrada
`close` libera el manejador del archivo y libera los recursos asociados al flujo de entrada.

```java
// Close input EPS stream
psStream.close();
```

## Problemas comunes y soluciones
- **FileNotFoundException** – Verifica que `dataDir` apunte a la carpeta correcta y que `xmp4.eps` exista.  
- **LicenseException** – Si ves errores de licencia, asegúrate de cargar un archivo de licencia válido de Aspose.Page antes de crear `PsDocument`.  
- **Metadata Not Updated** – Después de guardar, abre el EPS resultante en un visor de metadatos (p. ej., Adobe Bridge) para confirmar que el nuevo valor aparece.

## Preguntas frecuentes
**P: ¿Puedo usar Aspose.Page for Java con otros lenguajes de programación?**  
R: Aspose.Page se centra principalmente en Java, pero Aspose ofrece bibliotecas equivalentes para .NET, C++ y Python que exponen capacidades similares de manipulación XMP.

**P: ¿Hay una prueba gratuita disponible para Aspose.Page for Java?**  
R: Sí, puedes explorar una prueba gratuita de Aspose.Page for Java [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar soporte adicional y discusiones sobre Aspose.Page for Java?**  
R: Visita el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para soporte comunitario y discusiones.

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?**  
R: Puedes adquirir una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**P: ¿Dónde puedo comprar Aspose.Page for Java?**  
R: Para comprar Aspose.Page for Java, visita la [página de compra](https://purchase.aspose.com/buy).

---

**Última actualización:** 2026-05-15  
**Probado con:** Aspose.Page for Java (última versión)  
**Autor:** Aspose

## Tutoriales relacionados

- [How to Read XMP Metadata using Java – Aspose.Page Guide](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Aspose Page Java Tutorial – Add XMP Metadata to EPS Files](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modify xmp – Change Values in XMP using Java](/page/java/xmp-metadata-manipulation/change-values/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}