---
date: 2025-12-28
description: Aprende a crear documentos XPS en Java usando Aspose.Page y agrega imágenes
  en mosaico sin esfuerzo con esta guía paso a paso.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Cómo crear un documento XPS con una imagen en mosaico en Java
url: /es/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear documento XPS y agregar una imagen en mosaico en Java

## Introducción
En el desarrollo moderno de Java, la capacidad de **crear documentos XPS** de forma programática es una habilidad valiosa, especialmente cuando necesitas enriquecerlos con gráficos como imágenes en mosaico. Aspose.Page para Java hace que este proceso sea sencillo, permitiéndote centrarte en el diseño visual en lugar del manejo de archivos de bajo nivel. En este tutorial aprenderás exactamente cómo crear un documento XPS, **agregar una imagen en mosaico**, y guardar el resultado, todo con ejemplos de código claros y paso a paso.

## Respuestas rápidas
- **¿Qué hace Aspose.Page?** Proporciona una API de alto nivel para generar y manipular documentos XPS en Java.  
- **¿Puedo crear un mosaico de una imagen?** Sí – usa `XpsImageBrush` con `XpsTileMode.Tile`.  
- **¿Necesito una licencia?** Se requiere una licencia temporal o comercial para uso en producción.  
- **¿Qué versión de Java es compatible?** Cualquier JDK 8+ es compatible.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10–15 minutos para un escenario básico de imagen en mosaico.

## ¿Qué significa “crear documento XPS”?
Un archivo XPS (XML Paper Specification) es un formato de documento de diseño fijo similar al PDF. Crear un documento XPS programáticamente te permite generar archivos imprimibles e independientes del dispositivo directamente desde código Java.

## ¿Por qué agregar una imagen en mosaico?
Crear un mosaico de una imagen repite el gráfico en un área definida, lo que es perfecto para fondos, marcas de agua o rellenos de patrón. Usando `XpsTileMode.Tile` de Aspose.Page puedes lograrlo con solo unas pocas líneas de código.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

1. **Java Development Kit (JDK)** – JDK 8 o superior instalado.  
2. **Aspose.Page para Java** – descárgalo desde el [sitio web](https://releases.aspose.com/page/java/).  
3. **Un directorio con permisos de escritura** – donde se guardará el archivo XPS generado.

## Importar paquetes
En tu proyecto Java, importa las clases necesarias:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Guía paso a paso

### Paso 1: Configura tu proyecto
Agrega los archivos JAR de Aspose.Page al classpath de tu proyecto y verifica que las declaraciones de importación se compilen sin errores.

### Paso 2: Crear documento XPS
Instancia un nuevo objeto `XpsDocument`. Este es el contenedor principal que albergará todas las páginas, rutas y recursos.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Paso 3: Definir la ruta de la imagen en mosaico
Coloca la imagen que deseas usar en mosaico (por ejemplo, `R08LN_NN.jpg`) dentro del directorio referenciado por `dataDir`. La imagen se utilizará como patrón de pincel.

### Paso 4: Agregar la imagen en mosaico
Crea una ruta rectangular y llénala con un `XpsImageBrush`. Al establecer el modo de mosaico en `Tile`, la imagen se repite a lo largo del rectángulo.

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
Persistir el archivo XPS en disco. El archivo de salida contendrá la imagen en mosaico que acabas de definir.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Repite estos pasos siempre que necesites **agregar una imagen en mosaico** a otras páginas o formas dentro del mismo documento XPS.

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| La imagen no se muestra | Verifica que la ruta del archivo (`dataDir + "R08LN_NN.jpg"`) sea correcta y que la imagen sea accesible. |
| El patrón de mosaico aparece estirado | Ajusta los valores de `Rectangle2D` de origen y destino para controlar el tamaño del mosaico. |
| La opacidad no tiene efecto | Asegúrate de que la opacidad del pincel se establezca **después** de la configuración del modo de mosaico. |

## Preguntas frecuentes

### ¿Aspose.Page es compatible con todas las versiones de Java?
Aspose.Page está diseñado para funcionar con varias versiones de Java. Asegura la compatibilidad revisando la documentación [aquí](https://reference.aspose.com/page/java/).

### ¿Puedo usar Aspose.Page en proyectos comerciales?
Sí, Aspose.Page ofrece licencias comerciales. Adquiérelas [aquí](https://purchase.aspose.com/buy).

### ¿Hay una versión de prueba gratuita disponible?
Sí, explora las funciones de Aspose.Page con una prueba gratuita [aquí](https://releases.aspose.com/).

### ¿Dónde puedo encontrar soporte comunitario y discusiones?
Participa en la comunidad de Aspose.Page en el [foro](https://forum.aspose.com/c/page/39).

### ¿Cómo puedo obtener una licencia temporal para Aspose.Page?
Obtén una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

---

**Última actualización:** 2025-12-28  
**Probado con:** Aspose.Page para Java 24.12 (última)  
**Autor:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
