---
date: 2026-02-15
description: Aprenda cómo crear documentos PostScript en Java y generar archivos de
  documentos PostScript con traslación y rotación de imágenes usando Aspose.Page para
  Java.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Crear PostScript Java – Añadir imagen en PostScript Java
url: /es/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear PostScript Java – Añadir Imagen en PostScript Java

## Introducción
En este tutorial, aprenderás cómo **create postscript java** documentos e incrustar imágenes usando la biblioteca Aspose.Page for Java. Repasaremos cada paso, desde la inicialización de un nuevo archivo PostScript hasta la aplicación de transformaciones **translate and rotate image**. Al final, podrás generar archivos PostScript de forma programática y controlar la ubicación de la imagen con precisión de píxel, ideal para informes automatizados, flujos de trabajo de impresión o cualquier escenario donde necesites **generate postscript document** desde Java.

## Respuestas rápidas
- **¿Qué biblioteca se requiere?** Aspose.Page for Java  
- **¿Puedo añadir varias imágenes?** Sí – repite los pasos de transformación y dibujo  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia para producción  
- **¿Qué versión de Java es compatible?** Java 8 y posteriores  
- **¿Se admite la rotación de imágenes?** Absolutamente – usa `AffineTransform.rotate()`  

## ¿Qué es create postscript java?
Una operación **create postscript java** produce un archivo de descripción de página PostScript que codifica texto, gráficos vectoriales e imágenes raster. Con Aspose.Page puedes crear estos archivos directamente desde código Java, dándote control total programático sobre el diseño, escalado y rotación sin necesidad de un intérprete PostScript externo.

## ¿Por qué usar Aspose.Page para la manipulación de imágenes?
- **API de alto nivel:** Abstrae los comandos de PostScript de bajo nivel en métodos Java simples.  
- **Multiplataforma:** Funciona en cualquier SO que soporte Java.  
- **Control total del estado gráfico:** Guardar, restaurar, trasladar, escalar y rotar gráficos a voluntad.  
- **Sin dependencias externas:** Gestiona la carga de imágenes, conversión de formatos e incrustación internamente.

## Requisitos previos
Antes de sumergirnos en el código, asegúrate de contar con:

- Java Development Kit (JDK) instalado en tu sistema.  
- Biblioteca Aspose.Page for Java. Puedes descargarla [aquí](https://releases.aspose.com/page/java/).  
- Un conocimiento básico de programación Java.  

## Importar paquetes
Para comenzar, importa los paquetes necesarios en tu proyecto Java. Usa el siguiente fragmento de código como referencia:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Paso 1: Escribir Guardado de Gráficos
El primer paso consiste en escribir el guardado de gráficos en el documento. Esto garantiza que cualquier transformación o modificación realizada posteriormente pueda revertirse si es necesario.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddImage_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
document.writeGraphicsSave();
```

## Paso 2: Trasladar y Transformar (translate and rotate image)
A continuación, traslada el documento y crea un objeto `BufferedImage` a partir del archivo de imagen. Aplica una serie de transformaciones como escalado y rotación usando `AffineTransform`. Aquí es donde ocurre la operación **translate and rotate image**.

```java
document.translate(100, 100);
// Create a BufferedImage object from the image file
BufferedImage image = ImageIO.read(new File(dataDir + "TestImage Format24bppRgb.jpg"));
// Create image transform
AffineTransform transform = new AffineTransform();
transform.translate(35, 300);
transform.scale(3, 3);
transform.rotate(-45);
```

## Paso 3: Añadir Imagen al Documento
Ahora, añade la imagen transformada al documento.

```java
document.drawImage(image, transform, null);
```

## Paso 4: Escribir Restauración de Gráficos
Después de añadir la imagen, escribe la restauración de gráficos para finalizar los cambios realizados.

```java
document.writeGraphicsRestore();
```

## Paso 5: Cerrar la Página Actual y Guardar
Cierra la página actual y guarda el documento.

```java
document.closePage();
document.save();
```

Puedes repetir estos pasos para añadir varias imágenes o personalizar las transformaciones según tus requisitos.

## Problemas comunes y soluciones
- **FileNotFoundException:** Asegúrate de que la ruta `dataDir` termine con un separador de archivos (`/` o `\\`) y que el nombre del archivo de imagen coincida exactamente.  
- **ImageIO.read devuelve null:** Verifica que el formato de la imagen sea compatible (p. ej., JPEG, PNG).  
- **Ángulo de rotación incorrecto:** `AffineTransform.rotate` espera radianes. Convierte grados a radianes (`Math.toRadians(degrees)`) si es necesario.  

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Page for Java con otros lenguajes de programación?**  
R: Aspose.Page se centra principalmente en Java, pero también existen versiones disponibles para otros lenguajes de programación.

**P: ¿Hay una prueba gratuita disponible para Aspose.Page for Java?**  
R: Sí, puedes acceder a la prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?**  
R: Puedes obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**P: ¿Dónde puedo encontrar soporte comunitario y discusiones relacionadas con Aspose.Page for Java?**  
R: Visita el [Aspose.Page Forum](https://forum.aspose.com/c/page/39) para soporte comunitario.

**P: ¿Hay recursos adicionales para comprar Aspose.Page for Java?**  
R: Puedes comprar la biblioteca [aquí](https://purchase.aspose.com/buy).

## Conclusión
¡Felicidades! Has aprendido cómo **create postscript java** documentos e incrustar imágenes usando Aspose.Page for Java. Explora la [documentación](https://reference.aspose.com/page/java/) para obtener más funciones avanzadas, como gráficos vectoriales, renderizado de texto y tamaños de página personalizados.

---

**Last Updated:** 2026-02-15  
**Tested With:** Aspose.Page for Java 23.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}