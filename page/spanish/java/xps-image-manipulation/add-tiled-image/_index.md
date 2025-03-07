---
title: Agregar imagen en mosaico en Java XPS
linktitle: Agregar imagen en mosaico en Java XPS
second_title: API de Java de Aspose.Page
description: Explore la manipulación perfecta de documentos Java XPS con Aspose.Page. Aprenda a agregar imágenes en mosaico sin esfuerzo utilizando esta guía paso a paso.
weight: 11
url: /es/java/xps-image-manipulation/add-tiled-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar imagen en mosaico en Java XPS

## Introducción
En el dinámico mundo del desarrollo de Java, la necesidad de una manipulación y creación de documentos eficiente es cada vez mayor. Aspose.Page para Java surge como una herramienta poderosa que brinda a los desarrolladores la capacidad de trabajar con documentos XPS sin problemas. Este tutorial se centra en una tarea específica: agregar una imagen en mosaico a un documento Java XPS.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
1. Kit de desarrollo de Java (JDK): asegúrese de tener JDK instalado en su sistema.
2.  Aspose.Page para Java: descargue e instale Aspose.Page para Java desde[sitio web](https://releases.aspose.com/page/java/).
3. Su directorio de documentos: elija o cree un directorio donde desee guardar su documento XPS.
## Importar paquetes
En su proyecto Java, importe los paquetes necesarios para utilizar las funcionalidades de Aspose.Page:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Ahora, analicemos el proceso de agregar una imagen en mosaico a un documento Java XPS en pasos claros y manejables.
## Paso 1: configura tu proyecto
Comience configurando su proyecto Java, asegurándose de que Aspose.Page para Java esté integrado correctamente.
## Paso 2: crear un documento XPS
Inicialice un nuevo documento XPS usando el siguiente código:
```java
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
// Crear nuevo documento XPS
XpsDocument doc = new XpsDocument();
```
## Paso 3: definir la ruta de la imagen en mosaico
Especifique la ruta a la imagen en mosaico que desea agregar al documento XPS.
## Paso 4: agregar imagen en mosaico
Utilice el siguiente fragmento de código para agregar una imagen en mosaico al documento XPS:
```java
// Imagen de mosaico
// Rectángulo relleno de ImageBrush en la parte superior derecha debajo
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## Paso 5: guarde el documento
Finalmente, guarde el documento XPS resultante usando el siguiente código:
```java
// Guarde el documento XPS resultante
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Repita estos pasos para incorporar sin esfuerzo una imagen en mosaico en su documento Java XPS usando Aspose.Page.
## Conclusión
Aspose.Page para Java agiliza el proceso de trabajo con documentos XPS y ofrece a los desarrolladores una solución eficaz para la manipulación de documentos. Siguiendo esta guía paso a paso, puede agregar fácilmente una imagen en mosaico a su documento Java XPS.

## Preguntas frecuentes
### ¿Aspose.Page es compatible con todas las versiones de Java?
 Aspose.Page está diseñado para funcionar con varias versiones de Java. Garantice la compatibilidad consultando la documentación[aquí](https://reference.aspose.com/page/java/).
### ¿Puedo utilizar Aspose.Page para proyectos comerciales?
Sí, Aspose.Page ofrece licencias comerciales. Cómpralos[aquí](https://purchase.aspose.com/buy).
### ¿Hay una prueba gratuita disponible?
 Sí, explore las funciones de Aspose.Page con una prueba gratuita[aquí](https://releases.aspose.com/).
### ¿Dónde puedo encontrar apoyo y debates de la comunidad?
 Interactúe con la comunidad Aspose.Page en el[foro](https://forum.aspose.com/c/page/39).
### ¿Cómo puedo obtener una licencia temporal para Aspose.Page?
 Adquirir una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
