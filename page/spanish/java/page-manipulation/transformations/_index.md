---
date: 2026-02-07
description: Aprende cómo escalar un rectángulo con Aspose.Page para Java, cómo trasladar
  una forma y aplicar una transformación afín para crear documentos PostScript.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Cómo escalar un rectángulo con Aspose.Page para Java
url: /es/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo escalar un rectángulo con Aspose.Page para Java

## Introducción
Bienvenido a una guía completa sobre cómo utilizar las potentes funciones de **Aspose.Page for Java** para realizar una variedad de transformaciones de página. En este tutorial aprenderá **cómo escalar un rectángulo**, traducir formas, rotar objetos y **aplicar transformaciones afines** mientras crea un **documento PostScript**. Estas capacidades le permiten crear aplicaciones Java ricas y intensivas en gráficos sin tener que manejar código de renderizado de bajo nivel.

## Respuestas rápidas
- **¿Cómo escalo un rectángulo en Java con Aspose.Page?** Use el método `document.scale()` antes de dibujar la forma.  
- **¿Puedo mover (trasladar) una forma sin afectar otros gráficos?** Sí—guarde el estado gráfico, llame a `document.translate(x, y)`, dibuje y luego restaure el estado.  
- **¿Qué clase crea un archivo PostScript?** `PsDocument` junto con `PsSaveOptions`.  
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia válida de Aspose.Page para implementaciones comerciales.  
- **¿Qué versión de Java es compatible?** Aspose.Page funciona con Java 8 y posteriores.

## Requisitos previos
Antes de sumergirnos en la guía paso a paso, asegúrese de que tiene los siguientes requisitos previos:

- Conocimientos básicos de programación en Java.  
- Biblioteca Aspose.Page for Java instalada. Puede descargarla desde la [documentación de Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Un entorno de desarrollo integrado (IDE) de Java configurado en su máquina.

## Importar paquetes
En su proyecto Java, importe los paquetes necesarios para utilizar Aspose.Page for Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## ¿Qué es “cómo escalar un rectángulo” en Aspose.Page?
Escalar un rectángulo cambia su tamaño a lo largo de los ejes X e Y mientras preserva su forma. Aspose.Page expone el método `scale(float sx, float sy)`, que aplica una **transformación afín** al estado gráfico actual. Esta es la técnica central detrás de la palabra clave **cómo escalar un rectángulo**.

## Cómo trasladar una forma con Aspose.Page
La traslación mueve una forma a una nueva ubicación sin alterar sus dimensiones. Esta es la esencia de **cómo trasladar una forma**. Guardando el estado gráfico, aplicando `translate(dx, dy)`, dibujando y luego restaurando el estado, mantiene los demás objetos sin cambios.

## Ejemplo 1: Sin transformaciones
El primer ejemplo dibuja un rectángulo simple sin aplicar ninguna transformación. Esto sirve como referencia para comparar con los ejemplos posteriores.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Ejemplo 2: Traslación
Aquí demostramos **cómo trasladar una forma** moviendo el contexto gráfico 250 unidades a la derecha antes de dibujar un segundo rectángulo.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Ejemplo 3: Escalado
Este ejemplo responde a la pregunta principal **cómo escalar un rectángulo**. Reducimos el rectángulo al 50 % de su ancho original y al 75 % de su altura.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Cómo rotar una forma en Java (rotate shape java)
La rotación es otra operación afín común. Aunque los fragmentos de código para la rotación se omiten por brevedad, el patrón es idéntico: guarde el estado gráfico, llame a `document.rotate(angle)`, dibuje la forma y luego restaure. Esto demuestra **rotate shape java** y **cómo rotar un rectángulo** en la práctica.

## Por qué esto importa – Beneficios del mundo real
- **Salida independiente del dispositivo** – Escriba una vez y genere PostScript o XPS sin ajustes específicos de la plataforma.  
- **Control fino** – Combine traslación, escalado, cizallado y rotación para cumplir requisitos de diseño exactos.  
- **Orientado al rendimiento** – API de bajo consumo ideal para el procesamiento por lotes de documentos a gran escala.  

## Casos de uso comunes
- Generación de facturas imprimibles – por ejemplo, una solución **printable invoice java** que coloca logotipos y códigos de barras con precisión.  
- Creación de diagramas técnicos donde se requieren escalado y posicionamiento precisos.  
- Automatizar la producción de informes multipágina en formato PostScript.  

## Problemas comunes y soluciones
- **La transformación no se restablece** – Siempre combine `document.writeGraphicsSave()` con `document.writeGraphicsRestore()` para evitar efectos no deseados de arrastre.  
- **Colores inesperados** – Asegúrese de establecer la pintura después de cada transformación; el estado gráfico no conserva los ajustes de color anteriores después de una restauración.  
- **Tamaño de archivo demasiado grande** – Use `PsSaveOptions` para habilitar compresión o reducir la resolución de la imagen al incrustar gráficos rasterizados.  

## Preguntas frecuentes
### ¿Puedo usar Aspose.Page for Java para otros formatos de documento?
Aspose.Page se centra principalmente en la manipulación de páginas para los formatos PostScript y XPS.

### ¿Dónde puedo encontrar más ejemplos y documentación para Aspose.Page for Java?
Visite la [documentación de Aspose.Page for Java](https://reference.aspose.com/page/java/) para obtener información completa.

### ¿Hay una prueba gratuita disponible para Aspose.Page for Java?
Sí, puede acceder a una prueba gratuita [aquí](https://releases.aspose.com/).

### ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?
Obtenga una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### ¿Dónde puedo buscar soporte comunitario o hacer preguntas sobre Aspose.Page for Java?
Visite el [foro de Aspose.Page for Java](https://forum.aspose.com/c/page/39) para discusiones comunitarias.

## Preguntas frecuentes

**P: ¿Cuál es la diferencia entre `translate` y `scale`?**  
**R:** `translate` mueve el origen del sistema de coordenadas, mientras que `scale` cambia el tamaño de los objetos dibujados a lo largo de los ejes X y/o Y.

**P: ¿Puedo combinar múltiples transformaciones en un solo estado gráfico?**  
**R:** Sí—llamando a `translate`, `scale`, `rotate` o `shear` secuencialmente antes de dibujar, crea una transformación afín combinada.

**P: ¿Cómo restablezco las transformaciones después de dibujar una forma?**  
**R:** Use `document.writeGraphicsRestore()` para volver al estado gráfico guardado previamente.

**P: ¿Es posible rotar un rectángulo alrededor de su centro?**  
**R:** Absolutamente. Traslade el rectángulo al origen, aplique `rotate(angle)`, luego trasládelo de vuelta antes de dibujar.

**P: ¿Aspose.Page admite anti‑aliasing para gráficos más suaves?**  
**R:** Sí—establezca las opciones de renderizado apropiadas en `PsSaveOptions` para habilitar anti‑aliasing.

---

**Última actualización:** 2026-02-07  
**Probado con:** Aspose.Page for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}