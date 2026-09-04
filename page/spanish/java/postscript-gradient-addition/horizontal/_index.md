---
date: 2026-09-04
description: Aprenda cómo crear un gradiente horizontal java en un archivo PostScript
  usando Linear Gradient Paint Java con Aspose.Page para Java. Código paso a paso,
  errores comunes y preguntas frecuentes.
keywords:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page Java
- PostScript gradient Java
lastmod: 2026-09-04
linktitle: Crear gradiente horizontal java en PostScript usando Aspose
og_description: Crear gradiente horizontal java en PostScript con Linear Gradient
  Paint Java. Este tutorial de Aspose.Page le muestra los pasos exactos, requisitos
  previos y consejos de solución de problemas en menos de 15 minutos.
og_image_alt: Screenshot of a Java PostScript file rendered with a horizontal gradient
  using Aspose.Page
og_title: Crear gradiente horizontal java en PostScript usando Aspose
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to create horizontal gradient java in a PostScript file using
    Linear Gradient Paint Java with Aspose.Page for Java. Step‑by‑step code, common
    pitfalls, and FAQs.
  headline: Create horizontal gradient java in PostScript using Aspose
  type: TechArticle
- questions:
  - answer: Aspose.Page for Java (includes Linear Gradient Paint Java).
    question: What library is required?
  - answer: About 10‑15 minutes for a basic horizontal gradient.
    question: How long does implementation take?
  - answer: A temporary or full license is required for production use.
    question: Do I need a license?
  - answer: Java 8 or newer.
    question: Which JDK version works?
  - answer: Yes – the same `LinearGradientPaint` instance can fill shapes and be applied
      to text strokes or fills.
    question: Can I use the gradient on both shapes and text?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create horizontal gradient java
- linear gradient paint java
- Aspose.Page
- Java PostScript
title: Crear gradiente horizontal java en PostScript usando Aspose
url: /es/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar un degradado horizontal en Java PostScript usando Linear Gradient Paint

## Introducción
En este tutorial integral aprenderás **cómo crear un degradado horizontal en Java** en un documento PostScript usando la clase **Linear Gradient Paint Java** que se incluye con Aspose.Page for Java. Recorreremos cada paso—desde configurar el proyecto hasta renderizar el degradado en formas y texto—para que puedas producir gráficos pulidos y listos para imprimir en minutos. Ya sea que estés construyendo un motor de informes, una herramienta de automatización de diseño o un controlador de impresora personalizado, esta guía te brinda el código exacto que necesitas.

## Respuestas rápidas
- **¿Qué biblioteca se requiere?** Aspose.Page for Java (incluye Linear Gradient Paint Java).  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un degradado horizontal básico.  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para uso en producción.  
- **¿Qué versión de JDK funciona?** Java 8 o superior.  
- **¿Puedo usar el degradado tanto en formas como en texto?** Sí – la misma instancia `LinearGradientPaint` puede rellenar formas y aplicarse a trazos o rellenos de texto.

## Qué es un degradado horizontal y por qué usarlo
Un degradado horizontal mezcla colores desde el borde izquierdo de un objeto hasta su borde derecho, creando una transición suave que añade profundidad e interés visual. Es ideal para componentes de UI modernos, encabezados resaltados o sombreados sutiles de fondo en informes PDF o PostScript. Usar **Linear Gradient Paint Java** te permite controlar con precisión los colores de inicio y fin, la opacidad y el escalado, garantizando que el resultado se vea nítido en cualquier dispositivo o impresora.

## Requisitos previos
Antes de sumergirte en el código, asegúrate de contar con lo siguiente:

- Java Development Kit (JDK) instalado en su máquina.  
- Biblioteca Aspose.Page for Java. Puede descargarla desde la [documentación de Aspose.Page Java](https://reference.aspose.com/page/java/).

## Importar paquetes
Comienza importando los paquetes necesarios en tu proyecto Java. Estas importaciones te dan acceso a primitivas gráficas, manejo de degradados y la API de Aspose.Page.

La clase `PsDocument` representa un documento PostScript en el que puede dibujar gráficos.  

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Paso 1: crear un rectángulo
Primero, configure el flujo de salida, el documento y un rectángulo que alojará el degradado.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

## Paso 2: crear un degradado lineal horizontal
`LinearGradientPaint` es la clase central que define una transición de color lineal.  
La clase `LinearGradientPaint` representa un objeto de pintura que renderiza un degradado a lo largo de una línea recta; usted especifica los puntos de inicio/fin, los puntos de color y un `AffineTransform` opcional para escalarlo a su forma.

```java
// Create horizontal linear gradient paint. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Set paint
document.setPaint(paint);
```

## Paso 3: rellenar el rectángulo
Ahora rellene el rectángulo con el degradado que acabamos de definir.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Paso 4: rellenar un texto con el degradado
También puede aplicar el mismo degradado al texto, creando un efecto visual impactante.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Paso 5: trazar un texto con el degradado
Finalmente, contorne el texto usando el degradado como color de trazo.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| El degradado aparece estirado | Escalado incorrecto de `AffineTransform` | Asegúrese de que el ancho y la altura de la transformación coincidan con las dimensiones del rectángulo (200 × 100 en el ejemplo). |
| Los colores se ven desvanecidos | Los valores alfa están configurados demasiado bajos | Aumente el componente alfa (el cuarto valor en `new Color(r,g,b,alpha)`). |
| El texto no es visible | La pintura no se estableció antes de dibujar el texto | Llame a `document.setPaint(paint)` **antes** de cualquier llamada a `fillAndStrokeText` o `outlineText`. |

## Preguntas frecuentes
**P:** ¿Puedo usar Aspose.Page for Java en proyectos comerciales?  
**R:** Sí, Aspose.Page for Java puede usarse en proyectos comerciales. Para detalles de licenciamiento, visite la página [Aspose.Purchase](https://purchase.aspose.com/buy).

**P:** ¿Hay una prueba gratuita disponible?  
**R:** Sí, puede acceder a una prueba gratuita de Aspose.Page for Java en la página [Aspose.Page for Java free trial](https://releases.aspose.com/).

**P:** ¿Dónde puedo encontrar documentación adicional y soporte?  
**R:** Visite la [documentación de Aspose.Page Java](https://reference.aspose.com/page/java/) para recursos completos. Para ayuda de la comunidad, consulte el [foro de Aspose.Page](https://forum.aspose.com/c/page/39).

**P:** ¿Cómo puedo obtener una licencia temporal?  
**R:** Puede obtener una licencia temporal en la [página de licencia temporal de Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

**P:** ¿Cuáles son los requisitos del sistema para Aspose.Page for Java?  
**R:** Consulte la [documentación de Aspose.Page Java](https://reference.aspose.com/page/java/) para obtener requisitos detallados del sistema.

---

**Última actualización:** 2026-09-04  
**Probado con:** Aspose.Page for Java 24.11  
**Autor:** Aspose

## Tutoriales relacionados

- [Crear degradado PostScript en Java – Agregar degradado vertical](/page/java/postscript-gradient-addition/vertical/)
- [Cómo agregar degradado: Degradado diagonal en Java PostScript usando Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Crear degradado PostScript – Degradado radial en Java](/page/java/postscript-gradient-addition/radial1/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}