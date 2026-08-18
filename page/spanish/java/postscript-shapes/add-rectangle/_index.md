---
date: 2026-02-18
description: Aprende a dibujar formas de rectángulo en Java PostScript usando Aspose.Page.
  Esta guía paso a paso muestra cómo establecer la pintura, definir el color del rectángulo
  en Java y crear gráficos vibrantes mientras explica cómo dibujar rectángulos de
  manera eficiente.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Cómo dibujar un rectángulo en Java PostScript con Aspose.Page
url: /es/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo dibujar rectángulos en Java PostScript con Aspose.Page

## Introducción
Si necesitas **how to draw rectangle** formas dentro de un archivo Java PostScript, has llegado al lugar correcto. En este tutorial recorreremos el uso de Aspose.Page for Java para añadir rectángulos coloridos, controlar su relleno y trazo, y guardar el resultado como un documento PostScript. Verás exactamente **how to set paint**, cómo definir la geometría del rectángulo, y por qué este enfoque es ideal para generar gráficos imprimibles de forma programática. Al final de la guía también comprenderás el contexto más amplio de las técnicas **draw rectangle java** y cómo encajan en los flujos de trabajo **java awt rectangle drawing**.

## Respuestas rápidas
- **What library is required?** Aspose.Page for Java  
- **Can I change rectangle colors?** Sí – use `setPaint` con cualquier `java.awt.Color`  
- **Do I need a license for development?** Una versión de prueba gratuita funciona para pruebas; se requiere una licencia para producción  
- **Which page size is used in the example?** A4 (default `PsSaveOptions`)  
- **Is the code compatible with Java 8+?** Absolutamente – utiliza clases estándar de AWT  

## What Is “How to Draw Rectangle” in PostScript?
Dibujar un rectángulo en un documento PostScript significa definir una región rectangular y rellenarla, trazar su contorno, o ambas cosas. Con Aspose.Page puedes hacerlo usando las familiares clases de **java awt rectangle drawing**, lo que hace que el código sea fácil de leer y mantener.

## Why Use Aspose.Page for Rectangle Graphics?
- **Cross‑platform**: Genera PostScript estándar que funciona en cualquier impresora.  
- **Fine‑grained control**: Puedes establecer colores de relleno, colores de trazo y grosores de línea de forma independiente.  
- **No external dependencies**: Utiliza solo las clases de geometría AWT incorporadas, por lo que no necesitas bibliotecas gráficas adicionales.  

## Prerrequisitos
Antes de sumergirte en el tutorial, asegúrate de contar con los siguientes prerrequisitos:
- Conocimientos básicos de programación en Java.  
- Biblioteca Aspose.Page for Java instalada. Si no la tienes, descárgala desde la [documentación de Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Un entorno de desarrollo Java configurado en tu máquina.

## Importar paquetes
En tu proyecto Java, comienza importando los paquetes necesarios. Estas importaciones te dan acceso a las clases `Color`, `BasicStroke` y `Rectangle2D` de AWT, así como a las clases centrales de manejo de documentos de Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Guía paso a paso para dibujar rectángulos en Java PostScript

### Paso 1: Set Paint for Filling Rectangle  
**How to set paint** – elegimos un color de relleno naranja para el primer rectángulo. Esto demuestra la capacidad **set rectangle color java**.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Paso 2: Set Paint for Stroking Rectangle  
**Set rectangle color java** – ahora cambiamos el paint a rojo y definimos un ancho de trazo. Esta parte del ejemplo muestra cómo **draw rectangle java** con un grosor de línea personalizado.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Paso 3: Close Current Page and Save Document  
Después de dibujar, cerramos la página y persistimos el archivo. Cerrar la página garantiza que todos los comandos de dibujo se envíen al flujo PostScript.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Casos de uso comunes para dibujar rectángulos
- **Generación de facturas o recibos** – los rectángulos actúan como bordes o resaltan secciones.  
- **Creación de etiquetas** – dibuja cajas coloreadas para separar la información del producto.  
- **Gráficos simples** – usa rectángulos rellenos como elementos de diagramas de barras.  
- **Formularios imprimibles personalizados** – combina rectángulos con texto para construir campos de formulario.

## Problemas comunes y consejos
- **Errores de ruta de archivo** – asegúrate de que `dataDir` termine con un separador de archivo (`/` o `\\`).  
- **Excepciones de licencia** – la versión de prueba añade una marca de agua; obtén una licencia completa para uso en producción.  
- **Visibilidad del color** – algunas impresoras pueden interpretar ciertos valores RGB de forma diferente; prueba primero con un rectángulo negro simple.  
- **Uso de memoria** – para documentos grandes, considera vaciar el flujo después de cada página (`document.closePage()`).

## Preguntas frecuentes

**Q:** *¿Puedo usar Aspose.Page for Java con otros lenguajes de programación?*  
A: Aspose.Page soporta principalmente Java, pero existen bibliotecas similares disponibles para otros lenguajes.

**Q:** *¿Existe una versión de prueba de Aspose.Page for Java?*  
A: Sí, puedes explorar las funciones de Aspose.Page for Java con la [free trial version](https://releases.aspose.com/).

**Q:** *¿Dónde puedo encontrar ayuda adicional y foros de discusión?*  
A: Visita el [Aspose.Page forum](https://forum.aspose.com/c/page/39) para interactuar con la comunidad y obtener asistencia.

**Q:** *¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?*  
A: Obtén una licencia temporal [here](https://purchase.aspose.com/temporary-license/).

**Q:** *¿Dónde puedo comprar una versión con licencia de Aspose.Page for Java?*  
A: Compra una versión con licencia [here](https://purchase.aspose.com/buy).

**Preguntas y respuestas adicionales**

**Q:** *¿Puedo cambiar el tamaño del rectángulo de forma dinámica?*  
A: Sí – simplemente modifica los parámetros `Rectangle2D.Float(x, y, width, height)` antes de llamar a `fill` o `draw`.

**Q:** *¿Es posible añadir texto dentro del rectángulo?*  
A: Absolutamente. Después de dibujar el rectángulo, usa `document.drawString(...)` con la fuente y posición deseadas.

**Q:** *¿Aspose.Page admite otras formas como círculos o polígonos?*  
A: Sí, la API proporciona métodos como `drawEllipse` y `drawPolygon` para una variedad de gráficos vectoriales.

## Conclusión
En esta guía demostramos **how to draw rectangle** en un documento Java PostScript, cubrimos **how to set paint** y mostramos cómo **set rectangle color java** usando Aspose.Page. Ahora tienes una base sólida para crear gráficos imprimibles vibrantes, ya sea que estés construyendo facturas, etiquetas o formularios personalizados. Siéntete libre de experimentar con diferentes colores, estilos de línea y formas AWT adicionales para enriquecer tu salida.

---

**Last Updated:** 2026-02-18  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}