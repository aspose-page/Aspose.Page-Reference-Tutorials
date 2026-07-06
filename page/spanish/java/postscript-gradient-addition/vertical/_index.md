---
date: 2026-02-13
description: Aprende a crear degradados en PostScript con Java usando Aspose.Page.
  Esta guía paso a paso te muestra cómo añadir un degradado vertical a tus documentos
  PostScript sin esfuerzo.
linktitle: Add Vertical Gradient in Java PostScript
second_title: Aspose.Page Java API
title: Crear degradado PostScript en Java – Añadir degradado vertical
url: /es/java/postscript-gradient-addition/vertical/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear degradado PostScript en Java – Añadir degradado vertical

## Introducción
En este tutorial exhaustivo, aprenderás a **crear degradado PostScript en Java** con Aspose.Page for Java. Añadir un degradado vertical puede hacer que tus documentos se vean más vibrantes y profesionales, y con solo unas pocas líneas de código puedes lograr efectos visuales impresionantes. Te guiaremos paso a paso, explicaremos por qué cada elemento es importante y te daremos consejos prácticos para evitar errores comunes. Al final de esta guía podrás generar archivos PostScript con transiciones de color verticales suaves y llamativas.

## Respuestas rápidas
- **¿Qué biblioteca se necesita?** Aspose.Page for Java  
- **¿Puedo personalizar los colores?** Sí, se puede usar cualquier `java.awt.Color`  
- **¿Se admite la rotación?** Sí, puedes rotar el degradado con un `AffineTransform`  
- **¿Qué formato de salida se produce?** Un archivo PostScript estándar (.ps)  
- **¿Necesito una licencia para producción?** Sí, se requiere una licencia comercial  

## ¿Por qué añadir un degradado vertical a un documento PostScript?
Los degradados verticales dan profundidad a tus páginas sin inflar el tamaño del archivo. Son perfectos para:

* Encabezados o pies de página de informes que necesiten un sutil fondo.  
* Resaltar secciones en manuales técnicos o libros blancos.  
* Proporcionar un aspecto moderno a gráficos, diagramas o folletos promocionales.

Como el degradado se define en forma vectorial, la salida permanece nítida a cualquier resolución.

## Requisitos previos
Antes de sumergirte en el tutorial, asegúrate de contar con los siguientes requisitos:
- Java Development Kit (JDK) instalado en tu máquina.  
- Biblioteca Aspose.Page for Java. Puedes descargarla [aquí](https://releases.aspose.com/page/java/).

## Importar paquetes
En tu proyecto Java, importa los paquetes necesarios para comenzar:
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

Ahora, recorramos el proceso de añadir un degradado vertical paso a paso.

## Cómo crear un degradado PostScript en Java
A continuación se muestra una guía paso a paso que indica exactamente cómo **crear degradado PostScript en Java** usando la API de Aspose.Page.

### Paso 1: Configurar el directorio de tu documento
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Paso 2: Crear el flujo de salida para el documento PostScript
```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "VerticalGradient_outPS.ps");
```

### Paso 3: Crear opciones de guardado con tamaño A4
```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
```

### Paso 4: Crear un nuevo documento PS
```java
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Paso 5: Crear un rectángulo
```java
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```

### Paso 6: Configurar colores y fracciones para el degradado
```java
// Create arrays of colors and fractions for the gradient.
Color[] colors = { Color.RED, Color.GREEN, Color.BLUE, Color.ORANGE, new Color(85, 107, 47) };
float[] fractions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
```

### Paso 7: Crear la transformación del degradado
```java
// Create the gradient transform. Scale components in the transform must be equal to width and height of the rectangle.
// Translation components are offsets of the rectangle.
AffineTransform transform = new AffineTransform(200, 0, 0, 100, 200, 100);
// Rotate the gradient on 90 degrees around an origin
transform.rotate(90 * (Math.PI / 180));
```

### Paso 8: Crear el pincel de degradado lineal vertical
```java
// Create vertical linear gradient paint.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

### Paso 9: Establecer el pincel y rellenar el rectángulo
```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

### Paso 10: Cerrar la página actual y guardar el documento
```java
// Close current page
document.closePage();
// Save the document
document.save();
```

¡Felicidades! Has añadido correctamente un degradado vertical a tu documento PostScript en Java usando Aspose.Page for Java.

## Problemas comunes y soluciones
- **El degradado se ve plano:** Asegúrate de que la escala del `AffineTransform` coincida con las dimensiones del rectángulo.  
- **Los colores se ven deslavados:** Verifica que estés usando el `ColorSpaceType` correcto (SRGB) y que el arreglo de fracciones esté ordenado de 0.0 a 1.0.  
- **El archivo no se genera:** Comprueba que el directorio de salida (`dataDir`) exista y que la aplicación tenga permisos de escritura.  

## Preguntas frecuentes
### ¿Puedo usar Aspose.Page for Java con otras bibliotecas Java?
Sí, Aspose.Page for Java está diseñado para trabajar sin problemas con otras bibliotecas Java.

### ¿Hay una versión de prueba gratuita disponible para Aspose.Page for Java?
Sí, puedes obtener una prueba gratuita [aquí](https://releases.aspose.com/).

### ¿Dónde puedo encontrar documentación adicional?
La documentación detallada está disponible [aquí](https://reference.aspose.com/page/java/).

### ¿Cómo puedo comprar Aspose.Page for Java?
Puedes comprar Aspose.Page for Java [aquí](https://purchase.aspose.com/buy).

### ¿Existe un foro para discusiones sobre Aspose.Page?
Sí, puedes unirte al foro de la comunidad [aquí](https://forum.aspose.com/c/page/39).

## Preguntas frecuentes adicionales

**P: ¿Puedo crear otras direcciones de degradado (horizontal, diagonal)?**  
R: Por supuesto. Ajusta los puntos de inicio y fin en `LinearGradientPaint` y modifica el ángulo de rotación en el `AffineTransform`.

**P: ¿Esto funciona también con salida PDF?**  
R: La misma lógica de degradado se puede aplicar al guardar en PDF usando `PdfSaveOptions` en lugar de `PsSaveOptions`.

**P: ¿Cómo cambio el tamaño del degradado de forma dinámica?**  
R: Calcula las dimensiones del rectángulo en tiempo de ejecución y pasa esos valores tanto al `Rectangle2D` como al constructor del `AffineTransform`.

---

**Última actualización:** 2026-02-13  
**Probado con:** Aspose.Page for Java 24.11 (última)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}