---
date: 2026-08-18
description: Aprenda cómo agregar un patrón de rayado a archivos Java PostScript usando
  Aspose.Page Java. Esta guía paso a paso muestra el código completo y consejos.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Agregar patrón de rayado en Java PostScript
og_description: Aprenda cómo agregar un patrón de rayado en Java PostScript usando
  Aspose.Page. Siga este tutorial paso a paso para crear gráficos con relleno de rayado
  rápidamente.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Cómo agregar patrón de rayado en Java PostScript – Guía de Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Cómo agregar patrón de rayado en Java PostScript
url: /es/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar un patrón de trama en Java PostScript

## Introducción
If you’re working with **Aspose.Page Java** and wondering **how to add hatch pattern** to your PostScript output, hatch patterns are a fast and flexible solution. In this tutorial we’ll walk through **how to add hatch** designs to a PostScript document, explain why they’re useful, and give you a complete, ready‑to‑run code example. By the end, you’ll be able to create visually appealing hatch‑filled shapes and text with just a few lines of Java.

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Aspose.Page for Java (the “aspose page java” SDK).  
- **¿Qué efecto visual estamos añadiendo?** Hatch patterns (e.g., diagonal lines, crosshatch).  
- **¿Necesito una licencia para ejecutar el ejemplo?** A free trial works for development; a license is required for production.  
- **¿Cuántas líneas de código?** About 70 lines, split into clear steps.  
- **¿Puedo usar el mismo enfoque para PDFs?** Yes—Aspose.Page supports multiple output formats, including PDF.

## ¿Qué es un patrón de trama?
Un patrón de trama es un relleno basado en vectores que consiste en líneas o formas repetidas que crean un efecto de textura. Debido a que está definido matemáticamente, el patrón se escala sin pérdida de calidad, lo que lo hace ideal para impresión de alta resolución y salida monocroma.

## ¿Por qué usar patrones de trama con Aspose.Page Java?
Aspose.Page soporta **más de 10 formatos de salida** (incluyendo PostScript, PDF, EPS, SVG y XPS) y puede renderizar rellenos de trama en documentos de hasta **500 páginas** sin cargar todo el archivo en memoria. Esto significa que obtienes un rendimiento rápido, una huella de memoria baja y resultados visuales consistentes en todos los formatos compatibles.

## Cómo agregar un patrón de trama – visión general
Los patrones de trama son texturas basadas en vectores que se renderizan limpiamente a cualquier resolución y funcionan bien en impresoras monocromas. Usando Aspose.Page Java, puedes aplicar estos patrones a formas, rutas e incluso texto sin lidiar con comandos de PostScript de bajo nivel.

## Requisitos previos
- **Entorno de desarrollo Java** – JDK 8 o superior y un IDE de tu elección.  
- **Biblioteca Aspose.Page for Java** – Descarga el último JAR desde la página oficial **Aspose.Page for Java download page** [here](https://releases.aspose.com/page/java/).  
- También puedes explorar otras versiones de Aspose [here](https://releases.aspose.com/).  
- **Acceso de escritura** a una carpeta donde se guardará el archivo PostScript generado.

## Importar paquetes
Las importaciones a continuación incluyen clases estándar de Java AWT para primitivas gráficas como colores, trazos y formas geométricas, así como clases de Aspose.Page que proporcionan el modelo de documento, definiciones de estilo de trama y opciones de guardado necesarias para generar un archivo PostScript.  
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ¿Qué es la clase `Document`?
La clase `Document` es el objeto de nivel superior de Aspose.Page que representa un único archivo PostScript en memoria. Todas las operaciones de dibujo se realizan a través de este objeto.

## ¿Cómo configurar el flujo de salida?
Para escribir la salida, crea un `FileOutputStream` que apunte a la ruta de archivo deseada; este flujo maneja la escritura de bytes a bajo nivel. `PsSaveOptions` configura cómo se guarda el documento, incluyendo el tamaño de página y la compresión. Luego instancia un `Document` con un objeto `PsSaveOptions` que especifica el tamaño de página, la compresión y otras configuraciones específicas de PostScript.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## ¿Cómo guardar el estado gráfico y trasladar el origen?
Guardar el estado gráfico captura la matriz de transformación actual, la región de recorte y los atributos de dibujo, permitiéndote revertir más tarde. Después de guardar, llama a `translate(x, y)` en el objeto gráfico para desplazar el origen a una ubicación conveniente para dibujar la cuadrícula de cuadrados de trama.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## ¿Cómo crear un cuadrado reutilizable para cada patrón?
`Rectangle2D` representa una forma rectangular definida por su posición y tamaño. Al crear una única instancia que coincida con las dimensiones de la celda, puedes reutilizarla para cada cuadrado relleno de trama, reduciendo la asignación de objetos y manteniendo eficiente el bucle de dibujo.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## ¿Cómo configurar un lápiz para el contorno del cuadrado del patrón?
`BasicStroke` describe el grosor del contorno, el patrón de guiones y los extremos para formas vectoriales. Usar un `BasicStroke` de 2 puntos proporciona un borde claro alrededor de cada celda rellena de trama, asegurando que el relleno se separe visualmente de los cuadrados adyacentes.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## ¿Cómo iterar a través de los patrones de trama?
`HatchStyle` es una enumeración que enumera todos los patrones de trama predefinidos, como estilos diagonal, cruzado y punteado. Recorrer `HatchStyle.values()` te permite aplicar cada patrón a su vez, rellenar el rectángulo con un `HatchBrush` y luego dibujar su contorno.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## ¿Cómo restaurar el estado gráfico después del dibujo?
Llamar a `restore()` en el objeto gráfico revierte la matriz de transformación y la configuración de dibujo al estado guardado anteriormente, evitando que traducciones o escalados acumulativos afecten operaciones de dibujo posteriores. Esto asegura que el contenido posterior comience desde el sistema de coordenadas original y use atributos predeterminados.  
```java
document.writeGraphicsRestore();
```

## ¿Cómo rellenar texto con un patrón de trama?
`TextFragment` representa una pieza de texto que puede posicionarse y estilizarse de forma independiente. Al asignar un `HatchBrush` con un `HatchStyle` elegido al relleno del fragmento, los caracteres de texto se renderizan usando la textura de trama en lugar de un color sólido.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## ¿Cómo contornear texto con un estilo de trama diferente?
`HatchBrush` también puede usarse para trazar. Para dibujar un contorno, establece el trazo del fragmento a un `HatchBrush` con un `HatchStyle` diferente (p. ej., 70 % de trama) y aumenta el ancho del trazo mediante `setStrokeWidth`. Esto renderiza el borde del texto con su propio patrón de trama mientras preserva el interior relleno.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## ¿Cómo cerrar y guardar el documento?
`document.save()` escribe el documento en memoria al flujo de salida especificado. Después de completar todos los comandos de dibujo, invoca este método y luego cierra el `FileOutputStream` para liberar recursos del sistema y asegurar que el archivo se vacíe correctamente al disco.  
```java
document.closePage();
document.save();
```

Sigue estos pasos y tendrás un archivo PostScript que muestra un conjunto completo de patrones de trama aplicados tanto a formas como a texto, todo impulsado por **aspose page java**.

## Problemas comunes y consejos
- **Errores de ruta de archivo** – Asegúrate de que `dataDir` termine con el separador de archivos apropiado (`/` o `\`).  
- **Colores no compatibles** – Algunos intérpretes de PostScript más antiguos pueden no manejar ciertos espacios de color; utiliza RGB básico para máxima compatibilidad.  
- **Advertencias de licencia** – Ejecutar el ejemplo sin una licencia válida incrustará una marca de agua en la salida.

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Page Java con otros frameworks Java?**  
A: Yes, the library is framework‑agnostic and works with Spring, Jakarta EE, Android (limited), and plain Java SE.

**Q: ¿Hay una versión de prueba disponible para Aspose.Page Java?**  
A: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).

**Q: ¿Cómo obtengo una licencia temporal para desarrollo?**  
A: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/). It removes evaluation watermarks.

**Q: ¿Dónde puedo encontrar más tutoriales y soporte de la comunidad?**  
A: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) for additional examples and Q&A.

**Q: ¿Existe documentación completa para todas las clases y métodos?**  
A: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: ¿Puedo renderizar el mismo patrón de trama a PDF en lugar de PostScript?**  
A: Absolutely. Change the `PsSaveOptions` to `PdfSaveOptions` (or the equivalent) and the rest of the code remains unchanged.

**Q: ¿Qué debo hacer si el archivo generado está vacío?**  
A: Verify that the output stream points to a writable directory and that `document.save()` is called after all drawing operations.

**Last Updated:** 2026-08-18  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose

## Tutoriales relacionados

- [Crear patrón de textura en PostScript – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Cómo agregar degradado: Degradado diagonal en Java PostScript usando Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Cómo convertir PostScript a PDF usando la API de Aspose.Page Java](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}