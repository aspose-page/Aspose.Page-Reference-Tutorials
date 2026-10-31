---
date: 2026-10-31
description: Aprenda cómo establecer el color de pintura y rellenar una elipse en
  Java PostScript usando Aspose.Page. Esta guía muestra cómo rellenar la elipse, dibujar
  el contorno de la elipse y establecer el grosor del trazo con pasos de código claros.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Agregar elipse en Java PostScript
og_description: Aprenda cómo rellenar una elipse y establecer el color de pintura
  en Java PostScript usando Aspose.Page. Siga el código paso a paso para dibujar elipses
  rellenas y con contorno en segundos.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Cómo rellenar una elipse y establecer el color de pintura en Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Cómo rellenar una elipse y establecer el color de pintura en Java PostScript
url: /es/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo rellenar una elipse y establecer el color de pintura en Java PostScript

## Introducción
Si necesita **establecer el color de pintura** mientras dibuja gráficos vectoriales, la biblioteca Aspose.Page for Java le brinda control total sobre cada trazo y relleno. En este tutorial descubrirá cómo **establecer el color de pintura**, **rellenar una elipse** y **dibujar el contorno de una elipse** usando un enfoque simple, paso a paso. Al final, podrá agregar elipses PostScript de alta calidad a facturas, informes o cualquier documento imprimible.

## Respuestas rápidas
- **¿Qué biblioteca es la mejor para dibujar gráficos PostScript en Java?** Aspose.Page for Java.  
- **¿Puedo rellenar una elipse con un color sólido?** Sí – use `document.setPaint(Color.YOUR_COLOR)` antes de `fill`.  
- **¿Cómo dibujo solo el contorno de una elipse?** Establezca la pintura y el trazo, luego llame a `document.draw(...)`.  
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia comercial; una licencia temporal está disponible para pruebas.  
- **¿Qué versión de Java es compatible?** Cualquier tiempo de ejecución Java 8+ funciona con la versión actual de Aspose.Page.

## ¿Qué es una elipse PostScript?
Una elipse PostScript es una forma vectorial definida por un rectángulo delimitador. A diferencia de las imágenes raster, se escala sin pérdida de calidad, lo que la hace ideal para impresión de alta resolución y conversión a PDF. Como la forma se describe matemáticamente, puede renderizarse a cualquier tamaño o resolución preservando bordes nítidos y curvas suaves.

## ¿Por qué usar Aspose.Page para crear una elipse PostScript?
Aspose.Page le brinda control determinista sobre cada primitiva de dibujo. Soporta **3 sistemas operativos principales (Windows, Linux, macOS)**, **0 dependencias nativas**, y puede renderizar **más de 50 primitivas vectoriales** por segundo en un servidor típico. La biblioteca es puro Java, por lo que puede integrarse en cualquier aplicación Java 8+ sin bibliotecas nativas adicionales.

## Requisitos previos
Antes de comenzar, asegúrese de tener:

1. Un entorno de desarrollo Java funcional (JDK 8 o posterior).  
2. La biblioteca Aspose.Page for Java añadida a su proyecto. Puede descargarla **[desde la página de lanzamiento de Aspose.Page para Java](https://releases.aspose.com/page/java/)**.  

## Importar paquetes
En su archivo fuente Java, importe las clases necesarias para dibujar y guardar contenido PostScript.

El paquete `java.awt` suministra los tipos gráficos básicos como `Color`, `Ellipse2D` y `BasicStroke`. El paquete `com.aspose.page` proporciona la clase `PsDocument` que escribe la salida PostScript.

- **`Color`** – representa un color sRGB usado para pintar.  
- **`Ellipse2D`** – describe una forma de elipse definida por un rectángulo delimitador.  
- **`BasicStroke`** – especifica el ancho de línea, patrón de guiones y estilo de extremo para dibujar contornos.  
- **`PsDocument`** – representa un documento PostScript y proporciona métodos para dibujar gráficos y gestionar páginas.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Cómo establecer el color de pintura para una elipse
El primer paso es indicar al documento qué color usar para la siguiente operación de dibujo. El método `setPaint` establece un color sólido que se aplicará ya sea a un relleno o a un trazo, según la llamada posterior.

### Paso 1: Configurar el documento PostScript
Cree un flujo de salida, configure el tamaño de página e instancie un `PsDocument`.

`PsDocument` es la clase central que representa un archivo PostScript en memoria. Todos los comandos de dibujo se canalizan a través de este objeto, y gestiona el diseño de página, la administración de recursos y la generación final del archivo.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Paso 2: Rellenar la elipse – usar set paint color
Para **rellenar la elipse**, primero debe llamar a `setPaint` con el color de relleno deseado, luego invocar `fill` con una instancia de `Ellipse2D`.

`setPaint` establece el color de dibujo actual usado para operaciones de relleno o trazo posteriores.  
`Ellipse2D` define los límites geométricos de la elipse; su constructor recibe las coordenadas X‑Y de la esquina superior izquierda más el ancho y la altura.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Paso 3: Dibujar el contorno de la elipse y establecer el grosor del trazo
Después de rellenar, puede cambiar la pintura a otro color, definir un `BasicStroke` para controlar el ancho de línea y dibujar el contorno de la elipse.

`BasicStroke` especifica el ancho de línea, patrón de guiones y estilo de extremo para dibujar contornos. Ajustando su propiedad `width` controla cuán grueso aparece el borde de la elipse.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Paso 4: Cerrar y guardar el documento
Finalice la página y escriba el archivo PostScript en disco.

Llamar a `document.close()` vacía todos los comandos de dibujo pendientes y libera recursos. El archivo `.ps` resultante puede abrirse con cualquier visor PostScript o convertirse a PDF.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Ahora tiene un archivo PostScript que contiene dos elipses: una rellena de naranja y otra con contorno rojo. Siéntase libre de experimentar con diferentes coordenadas, tamaños y colores para adaptarse a sus necesidades de diseño.

## Problemas comunes y solución de problemas
- **Ruta de archivo incorrecta** – Asegúrese de que `dataDir` termine con un separador (`/` o `\\`) apropiado para su SO.  
- **Licencia faltante** – Sin una licencia válida, la biblioteca funciona en modo de evaluación y puede añadir marcas de agua.  
- **Color no aplicado** – Recuerde establecer `document.setPaint(...)` *antes* de cada llamada a `fill` o `draw`; la configuración de pintura no persiste automáticamente entre operaciones separadas.

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Page para Java con otras bibliotecas Java?**  
R: Sí, Aspose.Page for Java está diseñada para integrarse sin problemas con otras bibliotecas Java.

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?**  
R: Obtenga una licencia temporal **[desde la página de licencia temporal de Aspose](https://purchase.aspose.com/temporary-license/)** para propósitos de prueba.

**P: ¿Es Aspose.Page adecuada para proyectos comerciales?**  
R: ¡Absolutamente! Visite **[la página de compra de Aspose](https://purchase.aspose.com/buy)** para explorar opciones de licencia para uso comercial.

**P: ¿Dónde puedo buscar ayuda o discutir consultas relacionadas con Aspose.Page?**  
R: Únase a la comunidad en **[el Foro de Aspose.Page](https://forum.aspose.com/c/page/39)** para discusiones y asistencia.

**P: ¿Hay recursos gratuitos para aprender más sobre Aspose.Page para Java?**  
R: Utilice **[la página de prueba gratuita de Aspose](https://releases.aspose.com/)** y explore ejemplos en la documentación.

## Conclusión
Aspose.Page for Java facilita **establecer el color de pintura**, **rellenar una elipse** y **dibujar el contorno de una elipse**, ya sea que necesite una forma simple rellena o un gráfico complejo con trazo. Con los pasos anteriores puede añadir rápidamente gráficos vectoriales de nivel profesional a cualquier documento imprimible. Para una exploración más profunda—como combinar múltiples formas, aplicar degradados o convertir a PDF—consulte la **[documentación oficial de Aspose.Page Java](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## Tutoriales relacionados

- [Cómo dibujar un rectángulo en Java PostScript con Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Cómo agregar texto Unicode en Java PostScript con Aspose.Page](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Crear degradado radial en PostScript con Aspose.Page para Java](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}