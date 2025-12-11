---
date: 2025-12-07
description: Aprenda cómo agregar un degradado horizontal en Java PostScript usando
  Linear Gradient Paint Java con Aspose.Page para Java.
linktitle: Add Gradient in Java PostScript using Linear Gradient Paint Java
second_title: Aspose.Page Java API
title: Agregar degradado en Java PostScript usando Linear Gradient Paint Java
url: /es/java/postscript-gradient-addition/horizontal/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Añadir degradado en Java PostScript usando Linear Gradient Paint Java

## Introducción
En este tutorial exhaustivo descubrirás cómo crear un hermoso degradado horizontal en un documento PostScript aprovechando **Linear Gradient Paint Java**. Aspose.Page for Java facilita el trabajo con PostScript, PDF y otros formatos vectoriales, y la clase `LinearGradientPaint` te brinda un control detallado sobre las transiciones de color. Al final de esta guía, podrás renderizar degradados en formas **y** texto, dando a tus documentos un aspecto profesional y llamativo.

## Respuestas rápidas
- **¿Qué biblioteca se requiere?** Aspose.Page for Java (compatible con Linear Gradient Paint Java).  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un degradado básico.  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para uso en producción.  
- **¿Qué versión de JDK funciona?** Java 8 o superior.  
- **¿Puedo usar el degradado tanto en formas como en texto?** Sí – puedes rellenar formas y trazar o rellenar texto con el mismo degradado.

## Requisitos previos
Antes de sumergirte en el código, asegúrate de contar con lo siguiente:

- Java Development Kit (JDK) instalado en tu máquina.  
- Biblioteca Aspose.Page for Java. Puedes descargarla desde la [documentación de Aspose.Page Java](https://reference.aspose.com/page/java/).

## Importar paquetes
Comienza importando los paquetes necesarios en tu proyecto Java. Estas importaciones te dan acceso a primitivas gráficas, manejo de degradados y la API de Aspose.Page.

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

## Paso 1: Crear un rectángulo
Primero, configura el flujo de salida, el documento y un rectángulo que alojará el degradado.

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

## Paso 2: Crear Linear Gradient Paint horizontal
Aquí construimos el objeto **Linear Gradient Paint Java** que define una transición de color horizontal. El `AffineTransform` escala el degradado para que coincida con el ancho y alto del rectángulo.

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

## Paso 3: Rellenar el rectángulo
Ahora rellena el rectángulo con el degradado que acabamos de definir.

```java
// Fill the rectangle
document.fill(rectangle);
```

## Paso 4: Rellenar texto con el degradado
También puedes aplicar el mismo degradado al texto, creando un efecto visual impactante.

```java
// Fill a text with the gradient
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```

## Paso 5: Trazar texto con el degradado
Finalmente, contornea el texto usando el degradado como color de trazo.

```java
// Stroke a text with the gradient
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| El degradado aparece estirado | Escalado incorrecto en `AffineTransform` | Asegúrate de que el ancho y alto del transform coincidan con las dimensiones del rectángulo (200 × 100 en el ejemplo). |
| Los colores se ven desvanecidos | Valores alfa demasiado bajos | Incrementa el componente alfa (el cuarto valor en `new Color(r,g,b,alpha)`). |
| El texto no es visible | No se estableció la pintura antes de dibujar el texto | Llama a `document.setPaint(paint)` **antes** de cualquier llamada a `fillAndStrokeText` o `outlineText`. |

## Preguntas frecuentes
### ¿Puedo usar Aspose.Page for Java en proyectos comerciales?
Sí, Aspose.Page for Java puede usarse en proyectos comerciales. Para detalles de licenciamiento, visita [Aspose.Purchase](https://purchase.aspose.com/buy).

### ¿Hay una versión de prueba gratuita disponible?
Sí, puedes acceder a una prueba gratuita de Aspose.Page for Java [aquí](https://releases.aspose.com/).

### ¿Dónde puedo encontrar documentación adicional y soporte?
Visita la [documentación de Aspose.Page Java](https://reference.aspose.com/page/java/) para recursos completos. Para soporte comunitario, consulta el [foro de Aspose.Page](https://forum.aspose.com/c/page/39).

### ¿Cómo puedo obtener una licencia temporal?
Puedes obtener una licencia temporal en [Aspose.Purchase](https://purchase.aspose.com/temporary-license/).

### ¿Cuáles son los requisitos del sistema para Aspose.Page for Java?
Consulta la [documentación](https://reference.aspose.com/page/java/) para obtener los requisitos del sistema detallados.

---

**Última actualización:** 2025-12-07  
**Probado con:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}