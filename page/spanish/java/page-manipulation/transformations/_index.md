---
date: 2025-12-07
description: Aprenda a escalar rectángulos, trasladar formas y aplicar transformaciones
  afines en Java usando Aspose.Page para crear documentos PostScript.
language: es
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Cómo escalar un rectángulo y aplicar transformaciones con Aspose.Page
url: /java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo escalar un rectángulo y aplicar transformaciones con Aspose.Page

## Introducción
Bienvenido a una guía completa sobre cómo utilizar las potentes características de **Aspose.Page for Java** para realizar una variedad de transformaciones de página. En este tutorial aprenderá **how to scale rectangle**, traducirá formas, rotará objetos y **apply affine transform** técnicas mientras crea un **PostScript document**. Estas capacidades le permiten crear aplicaciones Java ricas y con intensivas gráficas sin tener que manejar código de renderizado de bajo nivel.

## Respuestas rápidas
- **¿Cómo escalo un rectángulo en Java con Aspose.Page?** Use el método `document.scale()` antes de dibujar la forma.  
- **¿Puedo mover (trasladar) una forma sin afectar a otros gráficos?** Sí—guarde el estado gráfico, llame a `document.translate(x, y)`, dibuje y luego restaure el estado.  
- **¿Qué clase crea un archivo PostScript?** `PsDocument` junto con `PsSaveOptions`.  
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia válida de Aspose.Page para implementaciones comerciales.  
- **¿Qué versión de Java es compatible?** Aspose.Page funciona con Java 8 y posteriores.

## Requisitos previos
Antes de sumergirnos en la guía paso a paso, asegúrese de contar con los siguientes requisitos:

- Conocimientos básicos de programación Java.  
- Biblioteca Aspose.Page for Java instalada. Puede descargarla desde la [documentación de Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Un entorno de desarrollo integrado (IDE) para Java configurado en su máquina.

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

## ¿Qué es “how to scale rectangle” en Aspose.Page?
Escalar un rectángulo cambia su tamaño a lo largo de los ejes X y Y mientras conserva su forma. Aspose.Page expone el método `scale(float sx, float sy)`, que aplica una **affine transform** al estado gráfico actual. Esta es la técnica central detrás de la palabra clave **how to scale rectangle**.

## Cómo traducir una forma con Aspose.Page
La traslación mueve una forma a una nueva ubicación sin alterar sus dimensiones. Esta es la esencia de **how to translate shape**. Guardando el estado gráfico, aplicando `translate(dx, dy)`, dibujando y luego restaurando el estado, mantiene los demás objetos sin cambios.

## Ejemplo 1: Sin transformaciones
El primer ejemplo dibuja un rectángulo simple sin aplicar ninguna transformación. Sirve como referencia para comparar con los ejemplos posteriores.

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
Aquí demostramos **how to translate shape** moviendo el contexto gráfico 250 unidades a la derecha antes de dibujar un segundo rectángulo.

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
Este ejemplo responde a la pregunta principal **how to scale rectangle**. Reducimos el rectángulo al 50 % de su ancho original y al 75 % de su altura.

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
La rotación es otra operación afín común. Aunque los fragmentos de código para rotación se omiten por brevedad, el patrón es idéntico: guarde el estado gráfico, llame a `document.rotate(angle)`, dibuje la forma y luego restaure. Esto demuestra **rotate shape java** y **how to rotate rectangle** en la práctica.

## ¿Por qué usar Aspose.Page para estas transformaciones?
- **Device‑independent**: Escriba una vez, genere PostScript o XPS sin código específico de plataforma.  
- **Fine‑grained control**: El acceso directo al estado gráfico le permite combinar traslación, escalado, cizallado y rotación.  
- **Performance**: API de bajo consumo adecuada para el procesamiento por lotes de documentos grandes.  

## Casos de uso comunes
- Generar facturas imprimibles con códigos de barras y logotipos dinámicos.  
- Crear diagramas técnicos donde se requieran escalado y posicionamiento precisos.  
- Automatizar la producción de informes multipágina en formato PostScript.

## Conclusión
En este tutorial, exploramos varias transformaciones en la manipulación de páginas Java usando Aspose.Page for Java, centrándonos en **how to scale rectangle**, **how to translate shape** y otras operaciones afines. Siguiendo estos ejemplos, podrá mejorar sus aplicaciones Java con capacidades avanzadas de manipulación de páginas y **create PostScript document** que cumplen con los estándares profesionales de publicación.

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
Visite el [foro de Aspose.Page for Java](https://forum.aspose.com/c/page/39) para discusiones de la comunidad.

## Preguntas frecuentes

**Q: ¿Cuál es la diferencia entre `translate` y `scale`?**  
A: `translate` mueve el origen del sistema de coordenadas, mientras que `scale` cambia el tamaño de los objetos dibujados a lo largo de los ejes X y/o Y.

**Q: ¿Puedo combinar múltiples transformaciones en un solo estado gráfico?**  
A: Sí—llamando a `translate`, `scale`, `rotate` o `shear` secuencialmente antes de dibujar, crea una transformación afín combinada.

**Q: ¿Cómo restablezco las transformaciones después de dibujar una forma?**  
A: Use `document.writeGraphicsRestore()` para volver al estado gráfico previamente guardado.

**Q: ¿Es posible rotar un rectángulo alrededor de su centro?**  
A: Absolutamente. Traslade el rectángulo al origen, aplique `rotate(angle)`, luego trasládelo de nuevo antes de dibujar.

**Q: ¿Aspose.Page admite anti‑aliasing para gráficos más suaves?**  
A: Sí—configure las opciones de renderizado apropiadas en `PsSaveOptions` para habilitar anti‑aliasing.

---

**Last Updated:** 2025-12-07  
**Tested With:** Aspose.Page for Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}