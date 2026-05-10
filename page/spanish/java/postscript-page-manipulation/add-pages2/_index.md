---
date: 2026-02-18
description: Aprende cómo establecer un tamaño de página personalizado y agregar páginas
  a documentos PostScript de Java usando Aspose.Page. Sigue nuestra guía paso a paso
  para una manipulación de documentos sin problemas.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
title: Tutorial de Aspose.Page para Java – establecer tamaño de página personalizado
  al agregar páginas en PostScript
url: /es/java/postscript-page-manipulation/add-pages2/
weight: 11
---

 tables.

Let's translate.

We'll translate headings: "Aspose.Page Java Tutorial – set custom page size while Adding Pages in PostScript" -> "Tutorial de Aspose.Page para Java – establecer tamaño de página personalizado al agregar páginas en PostScript"

Similarly others.

Bullet points: translate.

Make sure to keep URLs unchanged.

Also keep **bold** formatting.

Let's produce final output.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial de Aspose.Page para Java – establecer tamaño de página personalizado al agregar páginas en PostScript

## Introducción
En las aplicaciones Java modernas, **establecer un tamaño de página personalizado** para la salida PostScript suele ser necesario—ya sea que estés generando facturas, tickets o gráficos personalizados. En este tutorial aprenderás a **establecer un tamaño de página personalizado** para cada página, agregar varias páginas y, finalmente, **generar un archivo PostScript** que coincida con tus necesidades de diseño exactas. Revisaremos el código paso a paso para que puedas aplicar rápidamente la técnica en tus propios proyectos.

## Respuestas rápidas
- **¿Puedo establecer diferentes tamaños de página para cada página?** Sí, puedes abrir páginas con dimensiones personalizadas usando `document.openPage(width, height)`.  
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia válida de Aspose.Page para implementaciones que no sean de evaluación.  
- **¿Qué versiones de Java son compatibles?** La biblioteca funciona con Java 8 y versiones posteriores.  
- **¿Es el API thread‑safe?** Las instancias de Document no son seguras para subprocesos; crea un `PsDocument` separado por hilo.  
- **¿Qué tan grande puede ser un archivo PostScript?** Aspose.Page maneja archivos de varios megabytes de forma eficiente; el uso de memoria escala con el contenido, no con la cantidad de páginas.  
- **¿Puedo usar la sobrecarga de ancho/alto al abrir la página?** Absolutamente—`openPage(double width, double height)` te permite especificar cualquier dimensión en puntos.  

## Requisitos previos
Antes de comenzar, asegúrate de tener:

- Un conocimiento básico de programación en Java.  
- Aspose.Page para Java añadido a tu proyecto (Maven/Gradle o JAR manual).  
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

## Paso 2: Añadir contenido a la primera página
Con el documento listo, puedes añadir cualquier contenido que necesites a la primera página. Cuando termines, cierra la página para bloquear su contenido.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Cómo establecer un tamaño de página personalizado
Si el tamaño de página predeterminado no es lo que necesitas, puedes **establecer un tamaño de página personalizado** al abrir una nueva página. Esto es útil para recibos, etiquetas o cualquier diseño no estándar.

## Paso 3: Añadir una segunda página con tamaño diferente
A continuación, abrimos una segunda página y proporcionamos explícitamente un ancho y alto personalizados (en puntos). Esto demuestra cómo establecer un tamaño de página personalizado para páginas individuales, dándote la capacidad de trabajar con **diferentes tamaños de página** dentro del mismo documento.

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

Al seguir estos pasos, puedes agregar páginas y **establecer un tamaño de página personalizado** en un documento PostScript Java usando Aspose.Page, dándote control total sobre el diseño de cada página.

## ¿Por qué usar Aspose.Page para establecer un tamaño de página personalizado?
- **Precisión:** Las dimensiones se definen en puntos, por lo que obtienes un control exacto sobre el ancho y alto de la página.  
- **Flexibilidad:** Mezcla y combina **diferentes tamaños de página** en un solo archivo PostScript.  
- **Rendimiento:** La biblioteca transmite el contenido directamente al archivo de salida, lo que la hace adecuada para escenarios de **generación de archivos PostScript** a gran escala.  
- **API rica:** Soporta dibujar gráficos, incrustar imágenes y añadir texto—todo mientras respeta las dimensiones personalizadas que establezcas.

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **Las dimensiones de la página aparecen intercambiadas** | Recuerda que `openPage(width, height)` espera primero el ancho y luego la altura (ambos en puntos). |
| **El contenido se desborda de la página** | Usa el sistema de coordenadas `PsGraphics` para posicionar los elementos dentro de los límites personalizados, o escala tu dibujo. |
| **Errores de falta de memoria en documentos enormes** | Habilita la transmisión escribiendo directamente a un `FileOutputStream` como se muestra, y evita cargar imágenes grandes en memoria de una sola vez. |

## Preguntas frecuentes
### ¿Puedo agregar páginas de diferentes tamaños en un solo documento PostScript?
Sí, como se muestra en este tutorial, puedes agregar páginas con tamaños variables en un documento PostScript multipágina.  

### ¿Hay alguna limitación en la cantidad de páginas que puedo agregar?
Aspose.Page admite agregar una cantidad prácticamente ilimitada de páginas a un documento.  

### ¿Puedo añadir contenido personalizado, como imágenes o gráficos, a las páginas?
¡Absolutamente! Aspose.Page permite agregar una amplia gama de contenido, incluyendo texto, imágenes y otros elementos gráficos.  

### ¿Es Aspose.Page adecuado para manejar documentos grandes?
Sí, Aspose.Page está diseñado para manejar de manera eficiente tanto documentos pequeños como grandes.  

### ¿Dónde puedo encontrar recursos adicionales y soporte para Aspose.Page?
Explora la [documentación de Aspose.Page](https://reference.aspose.com/page/java/), o visita el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para obtener soporte de la comunidad.  

**Preguntas y respuestas adicionales**

**P:** *¿Qué formatos de imagen son compatibles al dibujar en una página PostScript?*  
**R:** Puedes incrustar imágenes PNG, JPEG, BMP y GIF directamente usando la API de dibujo.  

**P:** *¿Cómo cambio el DPI predeterminado del documento?*  
**R:** Establece `PsSaveOptions.setResolution(int dpi)` antes de crear el `PsDocument`.  

**P:** *¿Puedo cifrar un archivo PostScript con una contraseña?*  
**R:** PostScript en sí no admite cifrado, pero puedes envolver la salida en un PDF y aplicar configuraciones de seguridad si lo necesitas.

---

**Última actualización:** 2026-02-18  
**Probado con:** Aspose.Page para Java 24.10  
**Autor:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}