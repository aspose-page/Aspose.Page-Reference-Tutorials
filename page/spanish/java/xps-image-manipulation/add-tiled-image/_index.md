---
date: 2026-05-30
description: Aprenda a crear un documento XPS en Java usando Aspose.Page y añada una
  imagen en mosaico sin esfuerzo con esta guía paso a paso. Cómo crear archivos XPS
  rápidamente.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Añadir imagen en mosaico en Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Cómo crear un documento XPS con una imagen en mosaico en Java
url: /es/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear un documento XPS con una imagen en mosaico en Java

## Introducción
Crear documentos XPS de forma programática es una habilidad esencial para los desarrolladores Java que necesitan una salida imprimible e independiente del dispositivo. **Cómo crear XPS** de manera eficiente es posible con Aspose.Page para Java, que abstrae los detalles de bajo nivel de la especificación XML Paper y le permite centrarse en el diseño visual. En esta guía verá exactamente cómo crear un documento XPS, agregar una imagen en mosaico como fondo o patrón, y guardar el resultado, todo con código conciso y listo para producción.

## Respuestas rápidas
- **¿Qué hace Aspose.Page?** Proporciona una API de alto nivel para generar y manipular documentos XPS en Java.  
- **¿Puedo mosaicar una imagen?** Sí – use `XpsImageBrush` con `XpsTileMode.Tile`.  
- **¿Necesito una licencia?** Se requiere una licencia temporal o comercial para uso en producción.  
- **¿Qué versión de Java es compatible?** Cualquier JDK 8+ es compatible.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10–15 minutos para un escenario básico de imagen en mosaico.

## ¿Qué es “crear documento XPS”?
`XpsDocument` es el objeto de nivel superior de Aspose.Page que representa un único archivo XPS en memoria. Encapsula páginas, recursos y metadatos, permitiéndole construir el documento programáticamente. Crear un documento XPS significa instanciar esta clase, agregar elementos visuales y finalmente llamar a `save` para escribir el archivo de diseño fijo en disco. Este enfoque elimina el manejo manual de XML y garantiza el cumplimiento de la especificación XML Paper.

## ¿Por qué agregar una imagen en mosaico?
El mosaico repite un gráfico a lo largo de un área definida, lo que es ideal para fondos, marcas de agua o rellenos de patrón. Usando `XpsTileMode.Tile` la imagen se repite automáticamente sin duplicación manual, ahorrando tiempo de desarrollo y asegurando una renderización consistente en cualquier dispositivo. Las imágenes en mosaico también mantienen bajo el tamaño del archivo porque el mismo recurso bitmap se reutiliza en lugar de incrustarse múltiples veces.

## Requisitos previos
Antes de comenzar, asegúrese de tener:

1. **Java Development Kit (JDK)** – JDK 8 o superior instalado.  
2. **Aspose.Page for Java** – descargue desde el [sitio web](https://releases.aspose.com/page/java/).  
3. **Un directorio con permisos de escritura** – donde se guardará el archivo XPS generado.

## Importar paquetes
En su proyecto Java, importe las clases necesarias:

`XpsDocument` es el objeto principal que representa un archivo XPS.  
`XpsImageBrush` pinta formas usando una fuente de imagen.  
`XpsTileMode` especifica cómo se mosaica una imagen.  
`Rectangle2D` describe una región rectangular para posicionamiento.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Guía paso a paso

### Paso 1: Configura tu proyecto
Agregue los archivos JAR de Aspose.Page al classpath de su proyecto y verifique que las declaraciones de importación se compilen sin errores.

### Paso 2: Crear documento XPS
`XpsDocument` es el contenedor central que contiene páginas, rutas y recursos. Instáncielo con el tamaño de página deseado, luego podrá comenzar a agregar elementos gráficos.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Paso 3: Definir la ruta de la imagen en mosaico
Coloque la imagen que desea mosaicar (p. ej., `R08LN_NN.jpg`) dentro del directorio referenciado por `dataDir`. La imagen se usará como patrón de pincel.

### Paso 4: Agregar imagen en mosaico
Cree una ruta rectangular y rellénela con un `XpsImageBrush`. Al establecer el modo de mosaico a `Tile`, la imagen se repite a lo largo del rectángulo. Ajuste los rectángulos de origen y destino para controlar el tamaño y la posición del mosaico.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Paso 5: Guardar el documento
Persista el archivo XPS en disco. El archivo de salida contendrá la imagen en mosaico que acaba de definir y podrá abrirse con cualquier visor XPS.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Repita estos pasos siempre que necesite **agregar una imagen en mosaico** a otras páginas o formas dentro del mismo documento XPS.

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| La imagen no se muestra | Verifique que la ruta del archivo (`dataDir + "R08LN_NN.jpg"`) sea correcta y que la imagen sea accesible. |
| El patrón de mosaico aparece estirado | Ajuste los valores de `Rectangle2D` de origen y destino para controlar el tamaño del mosaico. |
| La opacidad no tiene efecto | Asegúrese de que la opacidad del pincel se establezca **después** de la configuración del modo de mosaico. |

## Preguntas frecuentes

**Q:** ¿Aspose.Page es compatible con todas las versiones de Java?  
**A:** Aspose.Page es compatible con Java 8 hasta Java 21; puede encontrar la matriz de compatibilidad completa [aquí](https://reference.aspose.com/page/java/).

**Q:** ¿Puedo usar Aspose.Page para proyectos comerciales?  
**A:** Sí, se requiere una licencia comercial para uso en producción. Las opciones de compra se enumeran [aquí](https://purchase.aspose.com/buy).

**Q:** ¿Hay una versión de prueba gratuita disponible?  
**A:** Se puede descargar una versión de prueba totalmente funcional desde la página de lanzamientos de Aspose [aquí](https://releases.aspose.com/).

**Q:** ¿Dónde puedo obtener soporte de la comunidad?  
**A:** Únase al foro de la comunidad de Aspose.Page en [forum](https://forum.aspose.com/c/page/39) para hacer preguntas y compartir ejemplos.

**Q:** ¿Cómo obtener una licencia temporal para evaluación?  
**A:** Las licencias temporales se proporcionan a solicitud a través del portal de Aspose [aquí](https://purchase.aspose.com/temporary-license/).

## Conclusión
Ahora dispone de un flujo de trabajo completo y listo para producción **para crear documentos XPS** con imágenes en mosaico usando Aspose.Page para Java. Al aprovechar `XpsImageBrush` y `XpsTileMode.Tile`, puede generar gráficos ricos y repetibles sin inflar el tamaño del archivo. Experimente con diferentes tamaños de mosaico, niveles de opacidad y formas para crear diseños de documentos sofisticados. Como siguiente paso, explore la incorporación de formas vectoriales o superposiciones de texto para mejorar aún más sus archivos XPS.

---

**Última actualización:** 2026-05-30  
**Probado con:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriales relacionados

- [Cómo agregar una imagen a documentos XPS de Java – Guía simple con Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - Agregar páginas al tutorial XPS](/page/java/xps-page-manipulation/add-page/)
- [Convertir XPS a PDF en Java usando Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}