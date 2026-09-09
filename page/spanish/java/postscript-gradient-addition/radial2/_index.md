---
date: 2026-09-09
description: Aprenda cómo crear un gradiente en Java PostScript y añadir gradiente
  a una forma usando Aspose.Page. Siga esta guía paso a paso con código y consejos.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Gradiente radial de Java PostScript con Aspose.Page
og_description: Aprenda cómo crear un gradiente en Java PostScript y añadir gradiente
  a una forma usando Aspose.Page. Siga esta guía paso a paso con código y consejos.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Cómo crear un gradiente en Java PostScript con relleno radial
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Cómo crear un gradiente en Java PostScript con relleno radial
url: /es/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un degradado en Java PostScript con relleno radial

## Introducción
En este tutorial aprenderás **cómo crear degradados** gráficos en un documento PostScript usando Java y Aspose.Page. Recorreremos cada paso—desde la configuración del proyecto hasta la renderización de un círculo relleno con un degradado radial suave—para que puedas **añadir degradado a objetos de forma** instantáneamente y elevar la calidad visual de tus aplicaciones Java.

## Respuestas rápidas
- **¿Qué crea este tutorial?** Un archivo PostScript (`.ps`) que contiene un círculo relleno con un degradado radial.  
- **¿Qué biblioteca se requiere?** Aspose.Page for Java (última versión).  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un ejemplo funcional.  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para uso en producción; una prueba gratuita funciona para desarrollo.  
- **¿Puedo reutilizar el código para PDF o SVG?** Sí—Aspose.Page admite varios formatos de salida con cambios mínimos.

## Cómo rellenar una forma con degradado en PostScript
Puedes rellenar una forma con un degradado radial en PostScript creando un `PsDocument`, definiendo un `RadialGradientPaint`, aplicándolo a la forma objetivo y finalmente guardando el documento. Este flujo de trabajo conciso te permite producir gráficos vectoriales de aspecto profesional sin imágenes rasterizadas, y el mismo código puede reutilizarse para salida PDF o SVG. El proceso es sencillo y funciona de manera consistente en todos los formatos compatibles.

## ¿Qué es un degradado radial?
Un degradado radial transiciona los colores desde un punto central hacia afuera, creando una mezcla suave y circular. Es ideal para resaltados, fondos de botones o cualquier elemento visual que necesite un efecto de “brillo” natural. Al variar las paradas de color y el radio, puedes simular iluminación, profundidad y propiedades de material en forma vectorial pura.

## ¿Por qué usar Aspose.Page para degradados radiales?
Aspose.Page te permite generar gráficos vectoriales independientes del dispositivo con una única API Java. Soporta más de 50 formatos de entrada y salida—including PostScript, PDF y SVG—manteniendo la precisión del color y el antialiasing para una salida de alta resolución. La biblioteca también ofrece clases de degradado fáciles de usar, haciendo que los efectos visuales complejos sean simples de implementar.

## Requisitos previos
Before we dive in, make sure you have:

- Familiaridad básica con la programación Java.  
- JDK 8 o superior instalado en tu máquina.  
- Biblioteca Aspose.Page for Java (descargar desde la [documentación de Aspose.Page Java](https://reference.aspose.com/page/java/)).

## Importar paquetes
Primero, importa las clases que necesitaremos. Estas incluyen tipos gráficos estándar de AWT y la API de Aspose.Page.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Paso 1: configurar el directorio del documento
Define la carpeta donde se guardará el archivo PostScript generado. Reemplaza el marcador de posición con una ruta real en tu sistema.

```java
String dataDir = "Your Document Directory";
```

## Paso 2: crear el flujo de salida
FileOutputStream escribe bytes sin procesar en un archivo, permitiendo guardar datos binarios. Abrir uno dirigido a un archivo `.ps` permite que Aspose.Page transmita los datos PostScript generados directamente al disco.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Paso 3: crear opciones de guardado
PsSaveOptions configura cómo se guarda un archivo PostScript, incluyendo el tamaño de página y la compresión. Puedes personalizar estos ajustes, pero los valores predeterminados son adecuados para este ejemplo.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Paso 4: crear el documento ps
PsDocument representa un documento PostScript en memoria y proporciona métodos para añadir páginas y gráficos.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Paso 5: crear un círculo
`Ellipse2D.Float` describe una forma elíptica; cuando el ancho = alto se convierte en un círculo perfecto. Este objeto servirá como lienzo para nuestro relleno de degradado.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Cómo dibujar un círculo con degradado
Para dibujar un círculo con un degradado radial, cargas un `RadialGradientPaint` en el contexto gráfico y luego rellenas la elipse definida previamente. Esta única operación pinta la forma con una transición de color suave desde el centro hacia afuera, creando un efecto visualmente atractivo.

## Paso 6: definir los colores del degradado
Prepara dos arreglos: uno para los colores que aparecerán en el degradado y otro para las posiciones fraccionarias correspondientes (0 = centro, 1 = borde).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Paso 7: crear AffineTransform
AffineTransform es una matriz que puede trasladar, rotar, escalar o sesgar objetos gráficos. Aquí escala y traslada el degradado para que encaje precisamente dentro del círculo.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Paso 8: crear RadialGradientPaint
RadialGradientPaint crea un degradado de color radial basado en un punto central, un radio y paradas de color.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Paso 9: establecer el paint y rellenar el círculo
Aplica el paint de degradado al documento y rellena el círculo definido previamente. Este es el núcleo de nuestro **ejemplo de degradado radial** y demuestra cómo **rellenar una forma con degradado**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Paso 10: cerrar la página y guardar el documento
Finaliza la página, escribe el contenido en disco y cierra el flujo. Tu archivo PostScript ahora está listo para visualizarse con cualquier visor PS.

```java
document.closePage();
document.save();
```

¡Felicidades! Has creado con éxito un ejemplo de degradado radial en Java PostScript usando Aspose.Page. Ahora dispones de un patrón reutilizable para **rellenar una forma con degradado**, que puede adaptarse a otras formas y formatos de salida.

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **FileNotFoundException** al abrir el flujo de salida | Verifica que `dataDir` apunte a una carpeta existente y que tengas permisos de escritura. |
| El degradado se ve plano o falta | Asegúrate de que el arreglo `fractions` coincida con la longitud del arreglo `colors` y que el `AffineTransform` escale correctamente. |
| Los colores aparecen invertidos | Intercambia el orden de los colores en el arreglo `colors` o ajusta las coordenadas del punto `focus`. |

## Preguntas frecuentes

**Q: ¿Dónde puedo encontrar la documentación de Aspose.Page para Java?**  
A: La referencia completa de la API está disponible en la [documentación de Aspose.Page Java API](https://reference.aspose.com/page/java/).

**Q: ¿Cómo puedo descargar Aspose.Page para Java?**  
A: Obtén el último JAR desde la [página de lanzamientos](https://releases.aspose.com/page/java/).

**Q: ¿Hay una prueba gratuita disponible?**  
A: Sí—descarga una versión de prueba desde la [página de descarga de prueba gratuita de Aspose](https://releases.aspose.com/).

**Q: ¿Puedo obtener una licencia temporal para pruebas?**  
A: Absolutamente, solicítala en la [página de licencia temporal](https://purchase.aspose.com/temporary-license/).

**Q: ¿Dónde puedo obtener soporte de la comunidad?**  
A: Únete a la discusión en el [foro de Aspose.Page](https://forum.aspose.com/c/page/39).

## Conclusión
En esta guía construimos un **ejemplo completo de degradado radial** para un documento PostScript usando Aspose.Page para Java. Al seguir los pasos ahora dispones de un patrón reutilizable para **rellenar una forma con degradado**, que puedes adaptar a PDF, SVG o cualquier otro formato soportado por Aspose.Page. Experimenta con diferentes colores, radios y formas para enriquecer tus proyectos gráficos en Java.

---

**Última actualización:** 2026-09-09  
**Probado con:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Autor:** Aspose

## Tutoriales relacionados

- [Crear degradado PostScript en Java – Añadir degradado vertical](/page/java/postscript-gradient-addition/vertical/)
- [Crear patrón de textura en PostScript con Aspose.Page para Java](/page/java/postscript-texture-patterns/)
- [Tutorial de transparencia Aspose.Page – Añadir transparencia en Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}