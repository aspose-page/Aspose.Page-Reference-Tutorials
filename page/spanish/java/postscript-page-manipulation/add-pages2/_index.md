---
date: 2025-12-11
description: Aprenda a establecer tamaños de página personalizados y agregar páginas
  a documentos PostScript de Java usando Aspose.Page. Siga nuestra guía paso a paso
  para una manipulación de documentos sin problemas.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Tutorial de Aspose.Page para Java – establecer tamaño de página personalizado
  al agregar páginas en PostScript
url: /es/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial de Aspose.Page Java – establecer tamaño de página personalizado al agregar páginas en PostScript

## Introducción
En las aplicaciones Java modernas, **establecer un tamaño de página personalizado** para la salida PostScript es a menudo necesario—ya sea que estés generando facturas, tickets o gráficos personalizados. Aspose.Page para Java hace que esta tarea sea sencilla. En este tutorial aprenderás a agregar páginas y establecer tamaños de página personalizados en un documento PostScript, paso a paso, para que puedas producir el diseño exacto que necesitas cada vez.

## Respuestas rápidas
- **¿Puedo establecer diferentes tamaños de página para cada página?** Sí, puedes abrir páginas con dimensiones personalizadas usando `document.openPage(width, height)`.  
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia válida de Aspose.Page para implementaciones que no sean de evaluación.  
- **¿Qué versiones de Java son compatibles?** La biblioteca funciona con Java 8 y versiones posteriores.  
- **¿Es segura la API para hilos?** Las instancias de documento no son seguras para hilos; crea un `PsDocument` separado por cada hilo.  
- **¿Qué tan grande puede ser un archivo PostScript?** Aspose.Page maneja archivos de varios megabytes de forma eficiente; el uso de memoria escala con el contenido, no con la cantidad de páginas.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

- Un conocimiento básico de programación en Java.  
- Aspose.Page para Java agregado a tu proyecto (Maven/Gradle o JAR manual).  
- Un entorno de desarrollo Java (IDE, JDK 8+).  

## Importar paquetes
Para comenzar, importa las clases necesarias de la biblioteca Aspose.Page.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Paso 1: Crear un documento PostScript multipágina
Primero, crea un nuevo `PsDocument` configurado para múltiples páginas. Esto configura el flujo de salida y le indica a la biblioteca que trabajaremos con un archivo multipágina.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Paso 2: Agregar contenido a la primera página
Con el documento listo, puedes añadir cualquier contenido que necesites a la primera página. Cuando termines, cierra la página para bloquear su contenido.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Cómo establecer un tamaño de página personalizado
Si el tamaño de página predeterminado no es lo que necesitas, puedes **establecer un tamaño de página personalizado** al abrir una nueva página. Esto es útil para recibos, etiquetas o cualquier diseño no estándar.

## Paso 3: Agregar una segunda página con tamaño diferente
A continuación, abrimos una segunda página y proporcionamos explícitamente un ancho y alto personalizados (en puntos). Esto demuestra cómo establecer un tamaño de página personalizado para páginas individuales.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Paso 4: Guardar el documento
Finalmente, persiste los cambios guardando el documento. Todas las páginas—incluidas aquellas con tamaños personalizados—se escriben en el archivo de salida.

```java
// Save the document
document.save();
```

Al seguir estos pasos, puedes agregar páginas y **establecer tamaños de página personalizados** en un documento PostScript Java usando Aspose.Page, dándote control total sobre el diseño de cada página.

## Conclusión
Aspose.Page para Java ofrece una API robusta y amigable para desarrolladores al manejar documentos PostScript. Ahora sabes cómo agregar múltiples páginas, aplicar dimensiones personalizadas y guardar el resultado—permitiéndote generar una salida perfectamente formateada para cualquier solución basada en Java.

## Preguntas frecuentes
### ¿Puedo agregar páginas de diferentes tamaños en un solo documento PostScript?
Sí, como se muestra en este tutorial, puedes agregar páginas con tamaños variables en un documento PostScript multipágina.  
### ¿Existen limitaciones en la cantidad de páginas que puedo agregar?
Aspose.Page admite la adición de un número prácticamente ilimitado de páginas a un documento.  
### ¿Puedo agregar contenido personalizado, como imágenes o gráficos, a las páginas?
¡Absolutamente! Aspose.Page permite agregar una amplia gama de contenido, incluidos texto, imágenes y otros elementos gráficos.  
### ¿Es Aspose.Page adecuado para manejar documentos grandes?
Sí, Aspose.Page está diseñado para manejar de manera eficiente tanto documentos pequeños como grandes.  
### ¿Dónde puedo encontrar recursos adicionales y soporte para Aspose.Page?
Explora la [documentación de Aspose.Page](https://reference.aspose.com/page/java/), o visita el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para obtener soporte de la comunidad.  

**Preguntas y respuestas adicionales**

**P:** *¿Qué formatos de imagen son compatibles al dibujar en una página PostScript?*  
**R:** Puedes incrustar imágenes PNG, JPEG, BMP y GIF directamente usando la API de dibujo.  

**P:** *¿Cómo cambio la DPI predeterminada del documento?*  
**R:** Establece `PsSaveOptions.setResolution(int dpi)` antes de crear el `PsDocument`.  

**P:** *¿Puedo encriptar un archivo PostScript con una contraseña?*  
**R:** PostScript en sí no admite encriptación, pero puedes envolver la salida en un PDF y aplicar configuraciones de seguridad si lo necesitas.

---

**Última actualización:** 2025-12-11  
**Probado con:** Aspose.Page para Java 24.10  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
