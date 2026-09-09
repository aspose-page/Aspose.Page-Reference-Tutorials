---
date: 2026-09-09
description: Aprenda cómo crear un degradado radial en Java PostScript usando Aspose.Page.
  Esta guía paso a paso le muestra cómo añadir un degradado de puntos de color, establecer
  los radios y generar un archivo PS rápidamente.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Dominar los degradados radiales en Java
og_description: Aprenda cómo crear un degradado radial en Java PostScript usando Aspose.Page.
  Esta guía explica cómo añadir un degradado de puntos de color, establecer los radios
  y generar un archivo PS en minutos.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Cómo crear un degradado radial en Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Cómo crear un degradado radial en Java PostScript
url: /es/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un degradado radial en Java PostScript con Aspose.Page

## Introducción
Si necesitas **crear un degradado radial** dentro de un archivo PostScript, has llegado al lugar correcto. En este tutorial recorreremos cada paso necesario para generar un documento PostScript que contenga un degradado radial suave, usando **Aspose.Page for Java**. Al final comprenderás la API, verás un ejemplo completo ejecutable y sabrás cómo ajustar colores, posiciones y radios para cualquier escenario de diseño.

## Respuestas rápidas
- **¿Qué biblioteca crea degradados radiales en PostScript?** Aspose.Page for Java.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un ejemplo básico.  
- **¿Necesito una licencia para ejecutar el código?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Qué versión de Java es compatible?** Java 8 o superior.  
- **¿Puedo cambiar la forma del degradado?** Sí – ajusta el radio y el punto central en el constructor `RadialGradientPaint`.

## Cómo crear un degradado radial en Java

Carga tu proyecto Java, importa las clases requeridas y sigue la guía paso a paso a continuación. La respuesta principal es que instancias un `RadialGradientPaint` con tus paradas de color y luego lo aplicas a un rectángulo dibujado en un `PsDocument`. Este enfoque de dos objetos maneja todos los comandos de PostScript de bajo nivel por ti.

## ¿Qué es un degradado radial?
`RadialGradientPaint` es una clase de Java AWT que define una transición de color circular desde un punto central hacia afuera. Crea una mezcla suave de múltiples paradas de color, lo que la hace ideal para focos, fondos suaves o cualquier efecto donde los colores irradian desde un punto focal.

## ¿Por qué usar Aspose.Page para degradados radiales?
Aspose.Page te brinda control programático total sobre la salida PostScript mientras se encarga del trabajo pesado de la sintaxis de PS de bajo nivel. Soporta **más de 50 formatos de entrada y salida**, puede renderizar documentos de cientos de páginas sin cargar todo el archivo en memoria, y se ejecuta en cualquier sistema operativo que soporte Java 8+. Esta capacidad cuantificada lo convierte en una opción fiable para la generación de gráficos de nivel empresarial.

## Requisitos previos
- **Java Development Kit (JDK) 8+** – verifica con `java -version`.  
- **Aspose.Page for Java** – descarga el último JAR desde la página oficial de [descarga de Aspose.Page](https://releases.aspose.com/page/java/).  
- **IDE de tu elección** – Eclipse, IntelliJ IDEA o VS Code con extensiones Java.  
- **Una carpeta con permisos de escritura** – donde se guardará el archivo `.ps` generado.

## Importar paquetes
Primero, importa las clases que necesitaremos. El paquete `java.awt` proporciona los objetos de pintura de degradado, mientras que `com.aspose.eps` contiene las clases de manejo de documentos PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Guía paso a paso

### Paso 1: crear un rectángulo y abrir un documento PS
`PsDocument` es la clase de Aspose.Page que representa un documento PostScript y proporciona métodos para dibujar formas, texto e imágenes. Comenzamos creando un flujo de salida, configurando el tamaño de página (A4 por defecto) y definiendo un rectángulo que alojará el degradado.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Consejo profesional:** Ajusta las coordenadas del rectángulo (`200, 100, 200, 200`) para posicionar el degradado en cualquier parte de la página.

### Paso 2: definir colores y fracciones
Un degradado radial se construye a partir de *paradas de color* (los colores) y *fracciones* (las posiciones relativas de esas paradas). Aquí creamos una matriz de seis colores y sus fracciones correspondientes.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Por qué es importante:** Al ajustar `fractions` controlas la rapidez con la que los colores hacen la transición, lo que permite efectos sutiles o dramáticos.

### Paso 3: crear pintura de degradado radial
`RadialGradientPaint` es la clase central que describe un degradado de color radial, incluyendo el punto central, radio, punto focal, fracciones, colores, método de ciclo y espacio de color. Ahora construimos el objeto `RadialGradientPaint` usando las matrices definidas arriba.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Nota:** `transform` puede ser `null` si no necesitas escalado o rotación adicional. Siéntete libre de experimentar con `AffineTransform` para degradados sesgados.

### Paso 4: establecer la pintura y rellenar el rectángulo
Con la pintura lista, indicamos al `PsDocument` que la use y luego rellenamos el rectángulo que definimos anteriormente.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

En este punto la página PostScript contiene un rectángulo relleno suavemente con el degradado radial que configuramos.

### Paso 5: cerrar y guardar el documento
Finalmente, cierra la página actual y escribe el archivo en disco.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Abre `RadialGradient1_outPS.ps` en cualquier visor de PostScript (p.ej., Ghostscript) y verás el degradado renderizado exactamente como se definió.

## Problemas comunes y soluciones
| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| El degradado aparece como un color sólido | La matriz `fractions` no comienza en `0.0f` o no termina en `1.0f` | Asegúrate de que la primera fracción sea `0.0f` y la última sea `1.0f`. |
| Los colores se ven deslavados | Uso del `ColorSpaceType` incorrecto | Cambia a `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` para una salida más vibrante. |
| No se genera el archivo de salida | La ruta de `FileOutputStream` es inválida o no tiene permisos de escritura | Verifica que `dataDir` exista y que la aplicación tenga permisos de escritura. |

## Preguntas frecuentes

**Q:** ¿Puedo usar Aspose.Page for Java en proyectos comerciales?  
**A:** Sí. Se requiere una licencia comercial para uso en producción. Puedes comprar una en la [página de licencias de Aspose](https://purchase.aspose.com/buy).

**Q:** ¿Dónde puedo encontrar la referencia oficial de la API?  
**A:** La documentación completa está disponible en la [referencia de API de Aspose.Page Java](https://reference.aspose.com/page/java/).

**Q:** ¿Hay una prueba gratuita disponible para pruebas?  
**A:** Por supuesto. Descarga una versión de prueba desde la [página de lanzamientos de Aspose.Page](https://releases.aspose.com/).

**Q:** ¿Cómo obtengo una licencia temporal para evaluación?  
**A:** Puedes solicitar una licencia temporal en la [página de solicitud de licencia temporal](https://purchase.aspose.com/temporary-license/).

**Q:** ¿Dónde puedo obtener soporte de la comunidad?  
**A:** Únete al foro de la comunidad de Aspose.Page en [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusión
Ahora sabes **cómo crear un degradado radial** en un documento Java PostScript usando Aspose.Page. Ajustando el tamaño del rectángulo, las paradas de color y el radio del degradado puedes crear innumerables efectos visuales — desde rellenos de fondo sutiles hasta gráficos de foco audaces. Siéntete libre de experimentar con diferentes valores de `AffineTransform` para rotar o sesgar el degradado, y combina esta técnica con texto e imágenes para obtener salidas PDF o EPS más ricas.

---

**Última actualización:** 2026-09-09  
**Probado con:** Aspose.Page for Java latest (al momento de escribir)  
**Autor:** Aspose

## Tutoriales relacionados

- [Rellenar forma con degradado: ejemplo radial Java PostScript](/page/java/postscript-gradient-addition/radial2/)
- [Crear degradado PostScript en Java – Añadir degradado vertical](/page/java/postscript-gradient-addition/vertical/)
- [Tutorial de transparencia Aspose.Page – Añadir transparencia en Java PostScript](/page/java/postscript-transparency/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}