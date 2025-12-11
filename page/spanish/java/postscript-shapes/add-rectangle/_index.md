---
date: 2025-12-11
description: Aprenda a dibujar formas de rectángulo en Java PostScript usando Aspose.Page.
  Esta guía paso a paso muestra cómo establecer la pintura, establecer el color del
  rectángulo en Java y crear gráficos vibrantes.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Cómo dibujar un rectángulo en Java PostScript con Aspose.Page
url: /es/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo dibujar rectángulo en Java PostScript con Aspose.Page

## Introduction
Si necesitas **cómo dibujar rectángulo** dentro de un archivo Java PostScript, has llegado al lugar correcto. En este tutorial recorreremos el uso de Aspose.Page for Java para añadir rectángulos coloridos, controlar su relleno y trazo, y guardar el resultado como un documento PostScript. Verás exactamente **cómo establecer la pintura**, cómo definir la geometría del rectángulo y por qué este enfoque es ideal para generar gráficos imprimibles programáticamente.

## Quick Answers
- **¿Qué biblioteca se requiere?** Aspose.Page for Java  
- **¿Puedo cambiar los colores del rectángulo?** Yes – use `setPaint` with any `java.awt.Color`  
- **¿Necesito una licencia para desarrollo?** Un trial gratuito funciona para pruebas; se requiere una licencia para producción  
- **¿Qué tamaño de página se usa en el ejemplo?** A4 (predeterminado `PsSaveOptions`)  
- **¿El código es compatible con Java 8+?** Absolutely – it uses standard AWT classes  

## Prerequisites
Antes de sumergirse en el tutorial, asegúrese de contar con los siguientes requisitos:
- Comprensión básica de la programación en Java.  
- Biblioteca Aspose.Page for Java instalada. Si no lo está, descárguela desde la [documentación de Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Un entorno de desarrollo Java configurado en su máquina.

## Import Packages
En su proyecto Java, comience importando los paquetes necesarios:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## How to Draw Rectangle in Java PostScript
A continuación se muestra el flujo de trabajo completo dividido en pasos claros. Cada paso incluye una breve explicación seguida del bloque de código original (sin cambios).

### Step 1: Set Paint for Filling Rectangle  
**Cómo establecer la pintura** – elegimos un color de relleno naranja para el primer rectángulo.

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

### Step 2: Set Paint for Stroking Rectangle  
**Establecer color del rectángulo java** – ahora cambiamos la pintura a rojo y definimos un ancho de trazo.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Step 3: Close Current Page and Save Document  
Después de dibujar, cerramos la página y guardamos el archivo.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Why Use Aspose.Page for Rectangle Graphics?
- **Cross‑platform**: Genera PostScript estándar que funciona en cualquier impresora.  
- **Fine‑grained control**: Puede establecer colores de relleno, colores de trazo y anchuras de línea de forma independiente.  
- **No external dependencies**: Utiliza solo las clases de geometría AWT incorporadas.  

## Common Issues & Tips
- **Errores de ruta de archivo** – asegúrese de que `dataDir` termine con un separador de archivos (`/` o `\\`).  
- **Excepciones de licencia** – la versión de prueba agrega una marca de agua; obtenga una licencia completa para uso en producción.  
- **Visibilidad del color** – algunas impresoras pueden interpretar ciertos valores RGB de manera diferente; pruebe primero con un rectángulo negro simple.

## Conclusion
En esta guía demostramos **cómo dibujar rectángulo** en un documento Java PostScript, cubrimos **cómo establecer la pintura** y mostramos cómo **establecer color del rectángulo java** usando Aspose.Page. Siéntase libre de experimentar con diferentes formas, colores y estilos de línea para crear gráficos imprimibles ricos para informes, facturas o impresiones personalizadas.

## Frequently Asked Questions

### Can I use Aspose.Page for Java with other programming languages?
¿Puedo usar Aspose.Page for Java con otros lenguajes de programación?  
Aspose.Page admite principalmente Java, pero existen bibliotecas similares para otros lenguajes.

### Is there a trial version of Aspose.Page for Java available?
¿Hay una versión de prueba de Aspose.Page for Java disponible?  
Sí, puede explorar las funciones de Aspose.Page for Java con la [versión de prueba gratuita](https://releases.aspose.com/).

### Where can I find additional help and discussions?
¿Dónde puedo encontrar ayuda adicional y discusiones?  
Visite el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para interactuar con la comunidad y obtener asistencia.

### How can I obtain a temporary license for Aspose.Page for Java?
¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?  
Obtenga una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### Where can I purchase a licensed version of Aspose.Page for Java?
¿Dónde puedo comprar una versión con licencia de Aspose.Page for Java?  
Compre una versión con licencia [aquí](https://purchase.aspose.com/buy).

**Additional Q&A**

**Q:** *Can I change the rectangle size dynamically?*  
**A:** Yes – simply modify the `Rectangle2D.Float(x, y, width, height)` parameters before calling `fill` or `draw`.

**Q:** *Is it possible to add text inside the rectangle?*  
**A:** Absolutely. After drawing the rectangle, use `document.drawString(...)` with the desired font and position.

**Q:** *Does Aspose.Page support other shapes like circles or polygons?*  
**A:** Yes, the API provides methods such as `drawEllipse` and `drawPolygon` for a variety of vector graphics.

---

**Last Updated:** 2025-12-11  
**Tested With:** Aspose.Page for Java 24.12 (latest)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}