---
title: Agregar elipse en Java PostScript
linktitle: Agregar elipse en Java PostScript
second_title: API de Java de Aspose.Page
description: Domine la creación de impresionantes documentos PostScript en Java con Aspose.Page. Aprenda a agregar elipses paso a paso para obtener contenido visualmente atractivo.
type: docs
weight: 10
url: /es/java/postscript-shapes/add-ellipse/
---
## Introducción
En el dinámico mundo del desarrollo de Java, la creación de documentos visualmente atractivos es un requisito común. Aspose.Page para Java es una poderosa biblioteca que permite a los desarrolladores manipular archivos PostScript sin esfuerzo. En este tutorial, exploraremos cómo agregar puntos suspensivos a documentos PostScript usando Aspose.Page para Java. ¡Síguenos para mejorar tus habilidades de creación de documentos!
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener configurados los siguientes requisitos previos:
1. Entorno de desarrollo Java: asegúrese de tener un entorno de desarrollo Java funcional instalado en su máquina.
2.  Biblioteca Aspose.Page para Java: descargue e incluya la biblioteca Aspose.Page en su proyecto Java. Puedes encontrar la biblioteca.[aquí](https://releases.aspose.com/page/java/).
## Importar paquetes
En su código Java, importe los paquetes necesarios para utilizar la funcionalidad Aspose.Page. He aquí un ejemplo:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```
## Paso 1: configure su documento
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear flujo de salida para un documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Crea opciones de guardado con tamaño A4
PsSaveOptions options = new PsSaveOptions();
// Cree un nuevo documento PS con la página abierta
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Paso 2: rellena la elipse con color
```java
// Set de pintura para rellenar elipse.
document.setPaint(Color.ORANGE);
// Llena la primera elipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```
## Paso 3: delinear la elipse con un trazo
```java
// Establecer pintura para acariciar la elipse.
document.setPaint(Color.RED);
// Establecer trazo
document.setStroke(new BasicStroke(3));
// Traza (delinea) la segunda elipse.
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```
## Paso 4: cerrar y guardar el documento
```java
// Cerrar la página actual
document.closePage();
// guardar el documento
document.save();
```
¡Ahora ha agregado exitosamente puntos suspensivos a su documento PostScript usando Aspose.Page para Java! Experimente con diferentes coordenadas y dimensiones para personalizar sus imágenes.
## Conclusión
 Aspose.Page para Java simplifica el proceso de creación y manipulación de documentos PostScript. Este tutorial le ha proporcionado el conocimiento para agregar elipses, proporcionando una base sólida para visualizaciones más complejas. Sumérgete en el[documentación](https://reference.aspose.com/page/java/) para más detalles y capacidades.
## Preguntas frecuentes
### P: ¿Puedo usar Aspose.Page para Java con otras bibliotecas de Java?
R: Sí, Aspose.Page para Java está diseñado para integrarse perfectamente con otras bibliotecas de Java.
### P: ¿Cómo puedo obtener una licencia temporal de Aspose.Page para Java?
 R: Obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/) con fines de prueba.
### P: ¿Aspose.Page es adecuado para proyectos comerciales?
 R: ¡Absolutamente! Visita[aquí](https://purchase.aspose.com/buy) para explorar opciones de licencia para uso comercial.
### P: ¿Dónde puedo buscar ayuda o discutir consultas relacionadas con Aspose.Page?
 R: Únase a la comunidad en el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para discusiones y ayuda.
### P: ¿Existen recursos gratuitos para obtener más información sobre Aspose.Page para Java?
 R: Utilice el[prueba gratis](https://releases.aspose.com/) y explore ejemplos en la documentación.