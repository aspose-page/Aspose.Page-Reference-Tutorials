---
date: 2025-12-09
description: Aprenda cómo crear documentos PostScript en Java y trasladar y rotar
  imágenes usando Aspose.Page para una manipulación de imágenes sin problemas.
linktitle: Add Image in Java PostScript
second_title: Aspose.Page Java API
title: Crear documento PostScript en Java – Añadir imagen en PostScript Java
url: /es/java/postscript-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear documento PostScript Java – Añadir imagen en PostScript Java

## Introducción
En este tutorial, aprenderá cómo **crear un documento PostScript Java** e incrustar imágenes usando la biblioteca Aspose.Page for Java. Recorreremos cada paso, desde la configuración del documento hasta la aplicación de transformaciones como operaciones de **trasladar y rotar imagen**. Al final, podrá generar archivos PostScript ricos programáticamente y personalizar la ubicación de la imagen para que se ajuste a sus necesidades exactas de diseño.

## Respuestas rápidas
- **¿Qué biblioteca se requiere?** Aspose.Page for Java  
- **¿Puedo añadir varias imágenes?** Sí – repita los pasos de transformación y dibujo  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia para producción  
- **¿Qué versión de Java es compatible?** Java 8 y posteriores  
- **¿Se admite la rotación de imágenes?** Absolutamente – use `AffineTransform.rotate()`  

## ¿Qué es crear un documento PostScript en Java?
Un documento PostScript es un archivo de lenguaje de descripción de página que describe texto, gráficos e imágenes. Usando Aspose.Page, puede generar programáticamente estos archivos en Java, dándole control total sobre el diseño, el estado gráfico y el manejo de imágenes sin necesidad de un intérprete PostScript.

## ¿Por qué usar Aspose.Page para la manipulación de imágenes?
- **API de alto nivel:** Simplifica comandos PostScript complejos.  
- **Multiplataforma:** Funciona en cualquier SO que soporte Java.  
- **Control total del estado gráfico:** Guarde, restaure, traslade, escale y rote gráficos fácilmente.  
- **Sin dependencias externas:** Gestiona la carga y conversión de imágenes internamente.

## Requisitos previos
Antes de sumergirnos en el código, asegúrese de tener:

- Java Development Kit (JDK) instalado en su sistema.  
- Biblioteca Aspose.Page for Java. Puede descargarla [aquí](https://releases.aspose.com/page/java/).  
- Una comprensión básica de la programación Java.  

## Importar paquetes
Para comenzar, importe los paquetes necesarios en su proyecto Java. Use el siguiente fragmento de código como referencia:

```java
import java.awt.geom.AffineTransform;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.FileOutputStream;
import javax.imageio.ImageIO;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Paso 1: Escribir guardado de gráficos
El primer paso implica escribir el guardado de gráficos en el documento. Esto asegura que cualquier transformación o modificación realizada después pueda revertirse si es necesario.

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

## Paso 2: Trasladar y transformar (trasladar y rotar imagen)
A continuación, traslade el documento y cree un objeto `BufferedImage` a partir del archivo de imagen. Aplique una serie de transformaciones como escalado y rotación usando `AffineTransform`. Aquí es donde ocurre la operación de **trasladar y rotar imagen**.

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

## Paso 3: Añadir imagen al documento
Ahora, añada la imagen transformada al documento.

```java
document.drawImage(image, transform, null);
```

## Paso 4: Escribir restauración de gráficos
Después de añadir la imagen, escriba la restauración de gráficos para finalizar los cambios realizados.

```java
document.writeGraphicsRestore();
```

## Paso 5: Cerrar página actual y guardar
Cierre la página actual y guarde el documento.

```java
document.closePage();
document.save();
```

Puede repetir estos pasos para añadir varias imágenes o personalizar las transformaciones según sus requisitos.

## Problemas comunes y soluciones
- **FileNotFoundException:** Asegúrese de que la ruta `dataDir` termine con un separador de archivos (`/` o `\\`) y que el nombre del archivo de imagen coincida exactamente.  
- **ImageIO.read devuelve null:** Verifique que el formato de la imagen sea compatible (p. ej., JPEG, PNG).  
- **Ángulo de rotación incorrecto:** `AffineTransform.rotate` espera radianes. Convierta grados a radianes (`Math.toRadians(degrees)`) si es necesario.  

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Page for Java con otros lenguajes de programación?**  
R: Aspose.Page principalmente soporta Java, pero también hay versiones disponibles para otros lenguajes de programación.

**P: ¿Hay una prueba gratuita disponible para Aspose.Page for Java?**  
R: Sí, puede acceder a la prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?**  
R: Puede obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**P: ¿Dónde puedo encontrar soporte comunitario y discusiones relacionadas con Aspose.Page for Java?**  
R: Visite el [Foro Aspose.Page](https://forum.aspose.com/c/page/39) para soporte comunitario.

**P: ¿Hay recursos adicionales para comprar Aspose.Page for Java?**  
R: Puede comprar la biblioteca [aquí](https://purchase.aspose.com/buy).

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo **crear un documento PostScript Java** e incrustar imágenes usando Aspose.Page for Java. Explore la [documentación](https://reference.aspose.com/page/java/) para obtener funciones y características más avanzadas, como gráficos vectoriales, renderizado de texto y tamaños de página personalizados.

---

**Última actualización:** 2025-12-09  
**Probado con:** Aspose.Page for Java 23.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}