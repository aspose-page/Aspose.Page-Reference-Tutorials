---
title: Personalizar Java PostScript agregar rectángulos con Aspose.Page
linktitle: Agregar rectángulo en Java PostScript
second_title: API de Java de Aspose.Page
description: Explore la guía paso a paso sobre cómo agregar rectángulos vibrantes a documentos Java PostScript usando Aspose.Page para Java. ¡Mejore la personalización de sus documentos sin esfuerzo!
type: docs
weight: 11
url: /es/java/postscript-shapes/add-rectangle/
---
## Introducción
¿Está buscando mejorar sus documentos Java PostScript con rectángulos vibrantes? ¡No busque más! En esta guía paso a paso, exploraremos cómo usar Aspose.Page para Java para agregar rectángulos a sus documentos PostScript. Aspose.Page es una biblioteca potente que proporciona funciones sólidas para trabajar con archivos PostScript, lo que la convierte en una opción ideal para los desarrolladores que buscan manipular y personalizar sus documentos.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Conocimientos básicos de programación Java.
-  Aspose.Page para la biblioteca Java instalada. Si no, descárgalo del[Aspose.Page para la documentación de Java](https://reference.aspose.com/page/java/).
- Un entorno de desarrollo Java configurado en su máquina.
## Importar paquetes
En su proyecto Java, comience importando los paquetes necesarios:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Tutorial: Agregar rectángulos en Java PostScript
## Paso 1: configurar la pintura para rellenar el rectángulo
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear flujo de salida para un documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Crea opciones de guardado con tamaño A4
PsSaveOptions options = new PsSaveOptions();
// Cree un nuevo documento PS con la página abierta
PsDocument document = new PsDocument(outPsStream, options, false);
// Establecer pintura para rellenar rectángulo.
document.setPaint(Color.ORANGE);        
// Rellena el primer rectángulo.
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```
## Paso 2: configurar la pintura para trazar el rectángulo
```java
// Establecer pintura para trazar un rectángulo.
document.setPaint(Color.RED);
// Establecer trazo
document.setStroke(new BasicStroke(3));
// Traza (delinea) el segundo rectángulo.
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```
## Paso 3: cierre la página actual y guarde el documento
```java
// Cerrar la página actual
document.closePage();
// guardar el documento
document.save();
```
¡Felicidades! Ha agregado con éxito rectángulos vibrantes a su documento Java PostScript usando Aspose.Page.
## Conclusión
En este tutorial, exploramos el proceso de mejorar sus documentos Java PostScript con rectángulos usando Aspose.Page para Java. Esta poderosa biblioteca abre un mundo de posibilidades para los desarrolladores que buscan personalizar y manipular sus documentos sin esfuerzo.
¡Diviértete experimentando con diferentes formas y colores para que tus documentos sean visualmente atractivos!
## Preguntas frecuentes

### ¿Puedo utilizar Aspose.Page para Java con otros lenguajes de programación?
Aspose.Page admite principalmente Java, pero hay bibliotecas similares disponibles para otros lenguajes.
### ¿Existe una versión de prueba de Aspose.Page para Java disponible?
 Sí, puede explorar las características de Aspose.Page para Java con el[versión de prueba gratuita](https://releases.aspose.com/).
### ¿Dónde puedo encontrar ayuda y debates adicionales?
 Visita el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para interactuar con la comunidad y obtener ayuda.
### ¿Cómo puedo obtener una licencia temporal de Aspose.Page para Java?
 Obtenga una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
### ¿Dónde puedo comprar una versión con licencia de Aspose.Page para Java?
 Comprar una versión con licencia[aquí](https://purchase.aspose.com/buy).