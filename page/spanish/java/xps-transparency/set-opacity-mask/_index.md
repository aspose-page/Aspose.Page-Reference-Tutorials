---
title: Establecer máscara de opacidad en Java XPS
linktitle: Establecer máscara de opacidad en Java XPS
second_title: API de Java de Aspose.Page
description: Descubra el poder de configurar máscaras de opacidad en Java XPS con Aspose.Page. Siga nuestra guía paso a paso para disfrutar de una experiencia documental visualmente mejorada.
weight: 11
url: /es/java/xps-transparency/set-opacity-mask/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Establecer máscara de opacidad en Java XPS

## Introducción
Bienvenido a nuestra guía completa sobre cómo configurar máscaras de opacidad en Java XPS usando Aspose.Page. En este tutorial, lo guiaremos a través del proceso de creación de un documento XPS, agregando un lienzo y aplicando una máscara de opacidad a un rectángulo utilizando las potentes funciones de Aspose.Page para Java.
## Requisitos previos
Antes de sumergirse en este tutorial, asegúrese de tener lo siguiente:
- Un conocimiento básico de la programación Java.
-  Aspose.Page para la biblioteca Java instalada. Puedes descargarlo[aquí](https://releases.aspose.com/page/java/).
-  Una licencia válida para Aspose.Page. Si no tienes una, puedes obtener una licencia temporal.[aquí](https://purchase.aspose.com/temporary-license/).
- Un entorno de desarrollo configurado para ejecutar aplicaciones Java.
## Importar paquetes
Comience importando los paquetes necesarios a su proyecto Java. Asegúrese de tener la biblioteca Aspose.Page correctamente integrada. A continuación se muestra un fragmento para guiarlo:
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Ahora, dividamos el código de ejemplo en varios pasos:
## Paso 1: cree un nuevo documento XPS
```java
// Crear un nuevo documento XPS
XpsDocument doc = new XpsDocument();
```
## Paso 2: agregue un lienzo
```java
// Nuevo lienzo
XpsCanvas canvas = doc.addCanvas();
```
## Paso 3: agrega un rectángulo con máscara de opacidad
```java
// Rectángulo en el centro izquierdo con opacidad enmascarada por ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## Paso 4: Establecer máscara de opacidad con ImageBrush
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## Paso 5: guarde el documento XPS resultante
```java
// Guarde el documento XPS resultante
doc.save(dataDir + "OpacityMask_out.xps"); 
```
Siga estos pasos cuidadosamente para incorporar máscaras de opacidad en su documento Java XPS usando Aspose.Page.
## Conclusión
¡Felicidades! Ha aprendido con éxito cómo configurar máscaras de opacidad en Java XPS con Aspose.Page. Esta característica agrega una capa de riqueza visual a sus documentos, haciéndolos más atractivos y dinámicos.
## Preguntas frecuentes
### ¿Aspose.Page es compatible con todos los entornos de desarrollo Java?
Sí, Aspose.Page está diseñado para funcionar perfectamente con varios entornos de desarrollo Java.
### ¿Puedo utilizar Aspose.Page sin licencia?
Si bien puedes usar Aspose.Page sin una licencia, se recomienda obtener una para obtener toda la gama de funciones y soporte.
### ¿Existe alguna limitación en la versión de prueba?
La versión de prueba puede tener algunas limitaciones de funciones. Es recomendable consultar la documentación para obtener más detalles.
### ¿Cómo puedo obtener soporte para Aspose.Page?
 Puedes visitar el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para obtener soporte comunitario o comprar una licencia para obtener asistencia premium.
### ¿Existe una garantía de devolución de dinero para Aspose.Page?
 Referirse a[pagina de compra](https://purchase.aspose.com/buy) para obtener información sobre las políticas de reembolso.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
