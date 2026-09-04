---
date: 2026-09-04
description: Aprenda cómo agregar gradient en Java PostScript con Aspose.Page Java,
  creando transiciones de color diagonales usando LinearGradientPaint para documentos
  vibrantes.
keywords:
- how to add gradient
- diagonal gradient java
- Aspose.Page Java
- LinearGradientPaint
- Java PostScript graphics
lastmod: 2026-09-04
linktitle: 'Cómo agregar gradient: gradient diagonal en Java PostScript usando Aspose.Page
  Java'
og_description: Aprenda cómo agregar gradient en Java PostScript usando Aspose.Page
  Java. Esta guía le muestra cómo crear un gradient diagonal con LinearGradientPaint
  en solo unos pocos pasos.
og_image_alt: Code example creating a diagonal gradient in a PostScript document using
  Aspose.Page for Java
og_title: Cómo agregar gradient en Java PostScript con Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to add gradient in Java PostScript with Aspose.Page Java,
    creating diagonal color transitions using LinearGradientPaint for vibrant documents.
  headline: 'How to add gradient: diagonal gradient in Java PostScript using Aspose.Page
    Java'
  type: TechArticle
- questions:
  - answer: Yes, Aspose.Page for Java provides a full set of drawing primitives, text
      rendering, and image handling capabilities.
    question: Can I use this library for other graphic operations in Java?
  - answer: Absolutely. You can download a fully functional trial from the [Aspose
      free trial page](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page Java?
  - answer: The official API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find documentation for Aspose.Page Java?
  - answer: Licenses can be bought directly from the [Aspose purchase portal](https://purchase.aspose.com/buy).
    question: How can I purchase a license for Aspose.Page Java?
  - answer: Visit the community‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for help from both Aspose engineers and fellow developers.
    question: Need assistance or have questions?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- LinearGradientPaint
- document graphics
title: 'Cómo agregar gradient: gradient diagonal en Java PostScript usando Aspose.Page
  Java'
url: /es/java/postscript-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar degradado diagonal en Java PostScript usando Aspose.Page Java

## Introducción
Si buscas enriquecer un archivo PostScript con una transición de color diagonal suave, **Aspose.Page Java** lo hace sorprendentemente fácil. En este tutorial aprenderás **cómo agregar efectos de degradado** paso a paso, usando la clase `LinearGradientPaint` de Java 2D. Al final tendrás un fragmento listo para ejecutar que crea un documento PostScript con un vibrante degradado diagonal, y comprenderás por qué este enfoque es más mantenible que codificar manualmente comandos PostScript crudos.

## Cómo agregar degradado en Java PostScript
Agregar un degradado podría sonar como una tarea solo de gráficos, pero con Aspose.Page obtienes control total sobre los comandos PostScript subyacentes mientras permaneces en Java puro. Esta sección explica por qué el enfoque funciona y qué ganas comparado con codificar manualmente PostScript crudo.

## Respuestas rápidas
- **¿Qué biblioteca se requiere?** Aspose.Page for Java.  
- **¿Qué clase crea el degradado?** `LinearGradientPaint`.  
- **¿Puedo cambiar los colores?** Sí – modifique la matriz `Color[]`.  
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial; hay una prueba gratuita disponible.  
- **¿Cuánto tiempo lleva la implementación?** Alrededor de 10 minutos para un degradado básico.

## ¿Qué es Aspose.Page Java?
Aspose.Page Java es una API completa que permite a los desarrolladores generar, editar y convertir archivos PostScript y PDF sin software externo. La biblioteca soporta **más de 50 formatos de entrada y salida** y puede procesar documentos con **más de 500 páginas** manteniendo el uso de memoria bajo 100 MB.

## ¿Por qué usar un degradado diagonal?
Un degradado diagonal añade profundidad e interés visual a gráficos, banners o cualquier elemento que necesite un aspecto moderno. Como el degradado va de una esquina a la opuesta, funciona bien para fondos, pieles de botones y formas decorativas, proporcionando un acabado profesional sin activos de imagen adicionales.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

- Java Development Kit (JDK) 8 o superior.  
- Un IDE como Eclipse, IntelliJ IDEA o VS Code.  
- **Aspose.Page for Java** library – descarga la última versión desde la [official download page](https://releases.aspose.com/page/java/).

## Importar paquetes
El paquete `java.awt` proporciona las clases gráficas centrales, mientras que el paquete `com.aspose.page` te da acceso a las API específicas de PostScript.

La clase `LinearGradientPaint` es el puente de Aspose.Page a la funcionalidad de degradado de Java 2D.  
`AffineTransform` permite rotar y escalar el degradado para que se alinee diagonalmente.

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

## Paso 1: crear flujo de salida para el documento PostScript
Primero, define la carpeta donde se guardará el archivo y abre un `FileOutputStream`. Este flujo recibe los datos PostScript generados.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "DiagonalGradient_outPS.ps");
```

## Paso 2: crear opciones de guardado con tamaño A4
`PsSaveOptions` te permite especificar el tamaño de página, resolución y otras configuraciones de salida. Aquí usamos el tamaño A4 predeterminado, que es 595 × 842 puntos a 72 dpi.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

## Paso 3: crear nuevo documento PS
La clase `PsDocument` representa un documento PostScript y proporciona métodos para crear páginas y dibujar gráficos.  
Instancia un `PsDocument` usando el flujo de salida y las opciones de guardado. La bandera `false` indica al constructor que no abra automáticamente una nueva página – lo haremos más tarde.

```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Paso 4: crear un rectángulo
Define el rectángulo que recibirá el relleno de degradado. La posición del rectángulo (200, 100) y su tamaño (200 × 100) se eligen para que el degradado sea claramente visible.

```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Paso 5: crear transformación del degradado
Un `AffineTransform` nos permite rotar, escalar y trasladar el degradado para que recorra diagonalmente el rectángulo. Las matemáticas a continuación calculan la hipotenusa y ajustan la proporción de escala en consecuencia.

```java
// Create the gradient transform. Scale components must be equal to the rectangle width and height.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate gradient, then scale and translate for visible color transition
transform.rotate(-45 * (Math.PI / 180));
float hypotenuse = (float) Math.sqrt(200 * 200 + 100 * 100);
float ratio = hypotenuse / 200;
transform.scale(-ratio, 1);
transform.translate(100 / transform.getScaleX(), 0);
```

## Paso 6: crear pintura de degradado lineal diagonal
`LinearGradientPaint` es la clase central que genera la transición de color. Se extiende desde la esquina superior izquierda del rectángulo hasta la esquina inferior derecha, usando la transformación definida previamente. `MultipleGradientPaint.CycleMethod.NO_CYCLE` asegura que el degradado no se repita.

```java
// Create diagonal linear gradient paint
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{Color.RED, Color.BLUE}, MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB, transform);
```

## Paso 7: establecer la pintura y rellenar el rectángulo
Aplica la pintura de degradado al documento y rellena la forma del rectángulo. Este paso renderiza la transición de color diagonal en la página PostScript.

```java
// Set paint and fill the rectangle
document.setPaint(paint);
document.fill(rectangle);
```

## Paso 8: cerrar la página actual y guardar el documento
Finalmente, cierra la página, vacía el flujo y guarda el archivo. El archivo resultante `DiagonalGradient_outPS.ps` puede abrirse con cualquier visor de PostScript.

```java
// Close current page and save the document
document.closePage();
document.save();
```

## Problemas comunes y consejos
- **El degradado aparece plano** – verifica el ángulo de rotación; una rotación de 45° crea una verdadera diagonal.  
- **Los colores se ven deslavados** – asegúrate de usar `MultipleGradientPaint.ColorSpaceType.SRGB` para una representación de color precisa.  
- **Error de archivo no encontrado** – verifica que `dataDir` apunte a una carpeta existente y que la aplicación tenga permisos de escritura.  
- **Los documentos grandes causan picos de memoria** – usa `PsSaveOptions.setCompress(true)` para reducir el consumo de memoria.

## Preguntas frecuentes

**P: ¿Puedo usar esta biblioteca para otras operaciones gráficas en Java?**  
R: Sí, Aspose.Page for Java provides a full set of drawing primitives, text rendering, and image handling capabilities.

**P: ¿Hay una prueba gratuita disponible para Aspose.Page Java?**  
R: Absolutamente. Puedes descargar una prueba totalmente funcional desde la [Aspose free trial page](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar la documentación de Aspose.Page Java?**  
R: La referencia oficial de la API está disponible [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**P: ¿Cómo puedo comprar una licencia para Aspose.Page Java?**  
R: Las licencias se pueden comprar directamente desde el [Aspose purchase portal](https://purchase.aspose.com/buy).

**P: ¿Necesita asistencia o tiene preguntas?**  
R: Visite el foro de la comunidad‑run [Aspose.Page forum](https://forum.aspose.com/c/page/39) para ayuda de ingenieros de Aspose y otros desarrolladores.

---

**Last Updated:** 2026-09-04  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose

## Tutoriales relacionados

- [Crear degradado radial en PostScript con Aspose.Page para Java](/page/java/postscript-gradient-addition/)
- [Cómo agregar degradado en Java PostScript con Linear Gradient Paint](/page/java/postscript-gradient-addition/horizontal/)
- [Crear degradado PostScript en Java – Agregar degradado vertical](/page/java/postscript-gradient-addition/vertical/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}