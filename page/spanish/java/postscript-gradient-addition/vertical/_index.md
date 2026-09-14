---
date: 2026-09-14
description: Aprenda cómo crear gradiente PostScript Java con Aspose.Page. Esta guía
  paso a paso le muestra cómo añadir un gradiente vertical a un archivo PostScript
  con solo unas pocas líneas de código Java.
keywords:
- create postscript gradient java
- vertical gradient java
- aspose.page gradient
- postscript graphics java
- java postscript tutorial
lastmod: 2026-09-14
linktitle: Añadir gradiente vertical en Java PostScript
og_description: Aprenda cómo crear gradiente PostScript Java con Aspose.Page. Esta
  guía paso a paso le muestra cómo añadir un gradiente vertical a un archivo PostScript
  con solo unas pocas líneas de código Java.
og_image_alt: Tutorial showing how to create a vertical PostScript gradient in Java
  using Aspose.Page
og_title: Crear gradiente PostScript Java – gradiente vertical
schemas:
- author: Aspose
  dateModified: '2026-09-14'
  description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  headline: Create postscript gradient java – vertical gradient
  type: TechArticle
- description: Learn how to create postscript gradient java with Aspose.Page. This
    step‑by‑step guide shows you how to add a vertical gradient to a PostScript file
    in just a few lines of Java code.
  name: Create postscript gradient java – vertical gradient
  steps:
  - name: set up your document directory
    text: '`File` objects represent the folder where the output will be written. The
      directory must exist before the stream is opened, otherwise an `IOException`
      is thrown.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` writes the binary PostScript data to disk. Using a `try‑with‑resources`
      block guarantees that the stream is closed even if an exception occurs.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` lets you specify page size, DPI, and whether to embed fonts.
      Setting the size to A4 (595 × 842 points) matches most printable documents.'
  - name: create a new PS document
    text: '`Document` is the top‑level object that represents a single PostScript
      file in memory. All drawing commands are issued against this object.'
  - name: create a rectangle
    text: '`Rectangle2D.Double` defines the area that will be filled with the gradient.
      The rectangle’s coordinates are expressed in points (1 point = 1/72 inch).'
  - name: set up colors and fractions for the gradient
    text: A `float[]` array defines the position of each color stop (from 0.0 to 1.0).
      `Color` objects hold the actual RGB values. You can use any `java.awt.Color`
      you like.
  - name: create the gradient transform
    text: '`AffineTransform` scales and rotates the gradient. For a pure vertical
      gradient you only need to scale the Y‑axis; rotation can be added later if desired.'
  - name: create vertical linear gradient paint
    text: '`LinearGradientPaint` ties together the rectangle, the color stops, and
      the transform. This object is later passed to the graphics context.'
  - name: set paint and fill the rectangle
    text: '`Graphics2D.setPaint` applies the gradient, and `fill` renders it inside
      the rectangle you defined earlier.'
  - name: close current page and save the document
    text: Calling `document.save` writes the entire PostScript stream to the output
      file and releases all native resources. Congratulations! You’ve successfully
      added a vertical gradient to your Java PostScript document using Aspose.Page
      for Java.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly alongside other
      Java libraries such as Apache Commons or Spring.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can get a free trial [free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Detailed documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find additional documentation?
  - answer: You can purchase Aspose.Page for Java [Aspose.Page purchase page](https://purchase.aspose.com/buy).
    question: How can I purchase Aspose.Page for Java?
  - answer: Yes, you can join the community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Is there a forum for Aspose.Page discussions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- postscript gradient
- aspose.page
- java graphics
- vertical gradient
- document processing
title: Crear gradiente PostScript Java – gradiente vertical
url: /es/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear gradiente postscript java – gradiente vertical

## Introducción
Aspose.Page for Java es una biblioteca que permite la creación y manipulación de archivos PostScript y PDF de forma programática. En este tutorial exhaustivo aprenderá a **crear gradiente postscript java** usando esa biblioteca. Añadir un gradiente vertical puede hacer que sus documentos se vean más vibrantes y profesionales, y con solo unas pocas líneas de código podrá lograr efectos visuales impresionantes. Le guiaremos paso a paso, explicaremos por qué cada elemento es importante y le daremos consejos prácticos para evitar errores comunes. Al final de esta guía podrá generar archivos PostScript con transiciones de color verticales suaves y llamativas.

## Respuestas rápidas
- **¿Qué biblioteca se necesita?** Aspose.Page for Java  
- **¿Puedo personalizar los colores?** Sí, se puede usar cualquier `java.awt.Color`  
- **¿Se admite la rotación?** Sí, puede rotar el gradiente con un `AffineTransform`  
- **¿Qué formato de salida se produce?** Un archivo PostScript estándar (.ps)  
- **¿Necesito una licencia para producción?** Sí, se requiere una licencia comercial  

## ¿Por qué añadir un gradiente vertical a un documento PostScript?
Añadir un gradiente vertical brinda profundidad a sus páginas, mejora la jerarquía visual y mantiene el tamaño del archivo bajo porque el gradiente se define en forma vectorial en lugar de imágenes rasterizadas. Esta técnica es perfecta para encabezados de informes, manuales técnicos o cualquier folleto que necesite un aspecto moderno sin sacrificar la escalabilidad.

## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de contar con los siguientes requisitos:
- Java Development Kit (JDK) instalado en su máquina.  
- Biblioteca Aspose.Page for Java. Puede descargarla desde la [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).

## Importar paquetes
En su proyecto Java, importe los paquetes necesarios para comenzar:
```java
import java.awt.Color;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Ahora, recorramos el proceso de añadir un gradiente vertical paso a paso.

## Cómo crear gradiente postscript java
Cargue su entorno Java, cree una instancia de `PsSaveOptions` y llame a `Document.save`; esa es la secuencia central que crea un archivo PostScript con un gradiente vertical. La API maneja la interpolación de colores, las transformaciones de coordenadas y el vaciado de la página por usted, por lo que solo necesita centrarse en definir el rectángulo y los parámetros del gradiente.

### Paso 1: configurar el directorio de su documento
Los objetos `File` representan la carpeta donde se escribirá la salida. El directorio debe existir antes de abrir el flujo, de lo contrario se lanza una `IOException`.
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Paso 2: crear el flujo de salida para el documento PostScript
`FileOutputStream` escribe los datos binarios de PostScript en disco. Usar un bloque `try‑with‑resources` garantiza que el flujo se cierre incluso si ocurre una excepción.
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Paso 3: crear opciones de guardado con tamaño A4
`PsSaveOptions` le permite especificar el tamaño de página, DPI y si se incrustan fuentes. Establecer el tamaño a A4 (595 × 842 puntos) coincide con la mayoría de los documentos imprimibles.
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Paso 4: crear un nuevo documento PS
`Document` es el objeto de nivel superior que representa un único archivo PostScript en memoria. Todos los comandos de dibujo se emiten contra este objeto.
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Paso 5: crear un rectángulo
`Rectangle2D.Double` define el área que se rellenará con el gradiente. Las coordenadas del rectángulo se expresan en puntos (1 punto = 1/72 pulgada).
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Paso 6: configurar colores y fracciones para el gradiente
Una matriz `float[]` define la posición de cada parada de color (de 0.0 a 1.0). Los objetos `Color` contienen los valores RGB reales. Puede usar cualquier `java.awt.Color` que desee.
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Paso 7: crear la transformación del gradiente
`AffineTransform` escala y rota el gradiente. Para un gradiente vertical puro solo necesita escalar el eje Y; la rotación puede añadirse más tarde si se desea.
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Paso 8: crear la pintura de gradiente lineal vertical
`LinearGradientPaint` une el rectángulo, las paradas de color y la transformación. Este objeto se pasa posteriormente al contexto gráfico.
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Paso 9: establecer la pintura y rellenar el rectángulo
`Graphics2D.setPaint` aplica el gradiente, y `fill` lo renderiza dentro del rectángulo que definió anteriormente.
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Paso 10: cerrar la página actual y guardar el documento
Llamar a `document.save` escribe todo el flujo PostScript en el archivo de salida y libera todos los recursos nativos.
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

¡Felicidades! Ha añadido con éxito un gradiente vertical a su documento PostScript Java usando Aspose.Page for Java.

## Problemas comunes y soluciones
- **El gradiente aparece plano:** Asegúrese de que el escalado del `AffineTransform` coincida con las dimensiones del rectángulo.  
- **Los colores se ven deslavados:** Verifique que esté usando el `ColorSpaceType` correcto (SRGB) y que la matriz de fracciones esté ordenada de 0.0 a 1.0.  
- **El archivo no se genera:** Compruebe que el directorio de salida (`dataDir`) exista y que la aplicación tenga permisos de escritura.  

## Preguntas frecuentes
**P: ¿Puedo usar Aspose.Page for Java con otras bibliotecas Java?**  
R: Sí, Aspose.Page for Java está diseñado para funcionar sin problemas junto a otras bibliotecas Java como Apache Commons o Spring.

**P: ¿Hay una versión de prueba gratuita disponible para Aspose.Page for Java?**  
R: Sí, puede obtener una prueba gratuita en la [página de descarga de prueba gratuita](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar documentación adicional?**  
R: La documentación detallada está disponible en la [referencia de API Aspose.Page Java](https://reference.aspose.com/page/java/).

**P: ¿Cómo puedo comprar Aspose.Page for Java?**  
R: Puede comprar Aspose.Page for Java en la [página de compra de Aspose.Page](https://purchase.aspose.com/buy).

**P: ¿Existe un foro para discusiones sobre Aspose.Page?**  
R: Sí, puede unirse al foro de la comunidad en el [foro de la comunidad Aspose.Page](https://forum.aspose.com/c/page/39).

## Preguntas frecuentes adicionales

**P: ¿Puedo crear otras direcciones de gradiente (horizontal, diagonal)?**  
R: Absolutamente. Ajuste los puntos de inicio y fin en `LinearGradientPaint` y modifique el ángulo de rotación en el `AffineTransform`.

**P: ¿Esto funciona también con salida PDF?**  
R: La misma lógica de gradiente puede aplicarse al guardar en PDF usando `PdfSaveOptions` en lugar de `PsSaveOptions`.

**P: ¿Cómo cambio el tamaño del gradiente de forma dinámica?**  
R: Calcule las dimensiones del rectángulo en tiempo de ejecución y pase esos valores tanto al constructor de `Rectangle2D` como al de `AffineTransform`.

---

**Última actualización:** 2026-09-14  
**Probado con:** Aspose.Page for Java 24.11 (última versión)  
**Autor:** Aspose

## Tutoriales relacionados

- [Crear gradiente radial en PostScript con Aspose.Page for Java](/page/java/postscript-gradient-addition/)
- [Cómo convertir PostScript a PDF usando Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Tutorial de transparencia Aspose.Page – Añadir transparencia en Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}