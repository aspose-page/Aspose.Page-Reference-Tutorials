---
date: 2025-12-18
description: Aprenda a agregar una cuadrícula y un rectángulo transparente en documentos
  XPS de Java con Aspose.Page. Guía paso a paso para guardar documentos XPS de manera
  eficiente.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Cómo agregar una cuadrícula usando Visual Brush en Java
url: /es/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar una cuadrícula usando Visual Brush en Java

## Introducción
Si estás buscando **how to add grid** elementos en tus documentos XPS generados con Java, has llegado al lugar correcto. En este tutorial te guiaremos para agregar una cuadrícula con un Visual Brush, superponer un rectángulo transparente y finalmente **save XPS document** usando la API Aspose.Page para Java. Al final tendrás un visual pulido que puede reutilizarse en informes, facturas o cualquier aplicación con muchos documentos.

## Respuestas rápidas
- **What does a Visual Brush do?** Pinta un área definida con contenido visual reutilizable, perfecto para patrones repetidos como cuadrículas.  
- **Can I change the grid color?** Sí – modifica la configuración del pincel de color sólido del brush.  
- **How do I add a transparent rectangle on top of the grid?** Usa `setOpacity` en una ruta rellenada con un color sólido.  
- **What method saves the file?** `doc.save(...)` escribe el archivo XPS en el disco.  
- **Do I need a license?** Se requiere una licencia temporal o completa para uso en producción.

## ¿Qué es una cuadrícula Visual Brush?
Un Visual Brush te permite definir un visual pequeño (el patrón de cuadrícula) y luego mosaicarlo en un área más grande. Este enfoque es más eficiente en memoria que dibujar cada línea individualmente y te brinda una repetibilidad pixel‑perfecta.

## ¿Por qué usar Aspose.Page para esta tarea?
- **Cross‑platform** – Funciona en cualquier SO que soporte Java.  
- **High‑fidelity rendering** – Control preciso sobre colores, opacidad y mosaico.  
- **No external dependencies** – Todo se maneja a través de la biblioteca Aspose.Page.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

- Conocimientos básicos de programación en Java.  
- Biblioteca Aspose.Page instalada – puedes descargarla desde la [documentación de Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- JDK 8 o posterior configurado en tu máquina de desarrollo.

## Importar paquetes
Primero, importa las clases requeridas para que el compilador sepa dónde encontrar los tipos que usaremos:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Guía paso a paso

### Paso 1: Configura tu proyecto
Crea una nueva instancia de `XpsDocument` y apunta a la carpeta donde deseas guardar el archivo de salida.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Paso 2: Crear un Visual Brush de cuadrícula magenta
Definimos una pequeña forma magenta que se mosaicoará en el área de la cuadrícula.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Paso 3: Definir la geometría para el Brush de cuadrícula
Configura el área rectangular que recibirá el visual mosaico.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Paso 4: Crear un nuevo Canvas para el documento
Agrega un canvas al documento y colócalo donde aparecerá la cuadrícula.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Paso 5: Añadir la cuadrícula al Canvas
Aplica el visual brush a la geometría, habilitando el mosaico.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Paso 6: Añadir un rectángulo rojo transparente (función secundaria)
Aquí demostramos **add transparent rectangle** sobre la cuadrícula para enfatizar.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Paso 7: Guardar el documento XPS resultante
Finalmente, escribe el documento en disco—este es el paso de **save XPS document**.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Sigue estos pasos y tendrás una cuadrícula de aspecto profesional con una superposición transparente, todo generado programáticamente.

## Problemas comunes y consejos

- **Incorrect tile size:** Asegúrate de que el `Rectangle2D` usado para el brush coincida con el tamaño de repetición deseado; de lo contrario el patrón puede estirarse.  
- **Opacity not applied:** Recuerda llamar a `setOpacity` en la ruta que deseas transparente; no afectará al brush mismo.  
- **File not saved:** Verifica que `dataDir` apunte a una carpeta existente y que tu aplicación tenga permisos de escritura.

## Preguntas frecuentes

**Q:** ¿Es Aspose.Page adecuado para la generación profesional de documentos?  
**A:** Sí, Aspose.Page es una biblioteca robusta diseñada para la generación de XPS y PDF de alta calidad en Java.

**Q:** ¿Puedo personalizar los colores de la cuadrícula usando Visual Brush?  
**A:** ¡Absolutamente! Cambia los parámetros de `createColor` en la llamada `setFill` del brush a cualquier valor RGBA que necesites.

**Q:** ¿Dónde puedo encontrar soporte adicional para Aspose.Page?  
**A:** Visita el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para obtener ayuda de la comunidad y respuestas oficiales.

**Q:** ¿Hay una prueba gratuita disponible para Aspose.Page?  
**A:** Sí, puedes acceder a la [prueba gratuita](https://releases.aspose.com/) para explorar todas las funciones antes de comprar.

**Q:** ¿Cómo puedo obtener una licencia temporal para pruebas?  
**A:** Obtén una [licencia temporal](https://purchase.aspose.com/temporary-license/) que funciona para desarrollo y evaluación.

---

**Última actualización:** 2025-12-18  
**Probado con:** Aspose.Page for Java 23.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}