---
date: 2025-12-08
description: Aprende a agregar un degradado radial en Java PostScript con Aspose.Page.
  Esta guía paso a paso te muestra cómo crear efectos de degradado impresionantes
  en tus documentos.
language: es
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: Cómo agregar un degradado radial en Java PostScript con Aspose.Page
url: /java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar un degradado radial en Java PostScript con Aspose.Page

## Introducción
Si alguna vez necesitaste darle a tu salida PostScript una transición de color suave y llamativa, aprender **cómo agregar un degradado radial** es el punto de partida perfecto. En este tutorial recorreremos cada paso necesario para generar un archivo PostScript que contenga un hermoso degradado radial, usando la biblioteca **Aspose.Page for Java**. Al final comprenderás la API, verás un ejemplo completo ejecutable y sabrás cómo ajustar colores, posiciones y radios para adaptarlos a cualquier diseño.

## Respuestas rápidas
- **¿Qué biblioteca crea degradados radiales en PostScript?** Aspose.Page for Java.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un ejemplo básico.  
- **¿Necesito una licencia para ejecutar el código?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Qué versión de Java es compatible?** Java 8 o superior.  
- **¿Puedo cambiar la forma del degradado?** Sí – ajusta el radio y el punto central en el constructor `RadialGradientPaint`.

## ¿Qué es un degradado radial?
Un degradado radial pinta colores que irradian desde un punto central, mezclándose gradualmente hacia los bordes. A diferencia de los degradados lineales, la transición de color sigue un patrón circular (o elíptico), lo que es ideal para resaltados, focos o rellenos suaves de fondo.

## ¿Por qué usar Aspose.Page para degradados radiales?
- **Control total sobre la salida PostScript** – no es necesario crear manualmente comandos PS de bajo nivel.  
- **Multiplataforma** – funciona en cualquier SO que ejecute Java.  
- **Gestión de color avanzada** – admite múltiples paradas de color, diferentes espacios de color y métodos de ciclo.  
- **Listo para integración** – combina con otras funciones de Aspose.Page como texto, imágenes y formas vectoriales.

## Requisitos previos
Antes de sumergirnos en el código, asegúrate de tener lo siguiente listo:

- **Java Development Kit (JDK) 8+** – verifica con `java -version`.  
- **Aspose.Page for Java** – descarga el JAR más reciente desde la página oficial de [descarga de Aspose.Page](https://releases.aspose.com/page/java/).  
- **IDE de tu elección** – Eclipse, IntelliJ IDEA o VS Code con extensiones Java.  
- **Una carpeta con permisos de escritura** – donde se guardará el archivo `.ps` generado.

## Importar paquetes
Primero, importa las clases que necesitaremos. El paquete `java.awt` proporciona los objetos de pintura de degradado, mientras que `com.aspose.eps` contiene las clases de manejo de documentos PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Guía paso a paso

### Paso 1: Crear un rectángulo y abrir un documento PS
Comenzamos creando un flujo de salida, configurando el tamaño de página (A4 por defecto) y definiendo un rectángulo que alojará el degradado.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Consejo profesional:** Ajusta las coordenadas del rectángulo (`200, 100, 200, 200`) para posicionar el degradado en cualquier parte de la página.

### Paso 2: Definir colores y fracciones
Un degradado radial se construye a partir de *paradas de color* (los colores) y *fracciones* (las posiciones relativas de esas paradas). Aquí creamos una matriz de seis colores y sus fracciones correspondientes.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Por qué es importante:** Al ajustar `fractions` controlas la rapidez con la que los colores hacen la transición, permitiendo efectos sutiles o dramáticos.

### Paso 3: Crear RadialGradientPaint
Ahora construimos el objeto `RadialGradientPaint`. El constructor recibe el punto central del degradado, el radio, el punto focal, las fracciones, los colores, el método de ciclo, el espacio de color y una transformación opcional.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Nota:** `transform` puede ser `null` si no necesitas escalado o rotación adicional. Siéntete libre de experimentar con `AffineTransform` para degradados sesgados.

### Paso 4: Establecer la pintura y rellenar el rectángulo
Con la pintura lista, indicamos al `PsDocument` que la use y luego rellenamos el rectángulo que definimos antes.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

En este punto la página PostScript contiene un rectángulo suavemente rellenado con el degradado radial que configuramos.

### Paso 5: Cerrar y guardar el documento
Finalmente, cierra la página actual y escribe el archivo en disco.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Abre `RadialGradient1_outPS.ps` en cualquier visor de PostScript (p.ej., Ghostscript) y verás el degradado renderizado exactamente como se definió.

## Problemas comunes y soluciones
| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| El degradado aparece como un color sólido | La matriz `fractions` no comienza en `0.0f` o no termina en `1.0f` | Asegúrate de que la primera fracción sea `0.0f` y la última sea `1.0f`. |
| Los colores se ven deslavados | Uso del `ColorSpaceType` incorrecto | Cambia a `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` para una salida más vibrante. |
| No se genera el archivo de salida | La ruta de `FileOutputStream` es inválida o no tiene permisos de escritura | Verifica que `dataDir` exista y que la aplicación tenga permisos de escritura. |

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Page for Java en proyectos comerciales?**  
R: Sí. Se requiere una licencia comercial para uso en producción. Puedes adquirir una en la [página de licencias de Aspose](https://purchase.aspose.com/buy).

**P: ¿Dónde puedo encontrar la referencia oficial de la API?**  
R: La documentación completa está disponible [aquí](https://reference.aspose.com/page/java/).

**P: ¿Hay una prueba gratuita disponible para pruebas?**  
R: Por supuesto. Descarga una versión de prueba desde la [página de lanzamientos de Aspose.Page](https://releases.aspose.com/).

**P: ¿Cómo obtengo una licencia temporal para evaluación?**  
R: Puedes solicitar una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**P: ¿Dónde puedo obtener soporte de la comunidad?**  
R: Únete al foro de la comunidad de Aspose.Page en [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusión
Ahora sabes **cómo agregar un degradado radial** a un documento Java PostScript usando Aspose.Page. Al ajustar el tamaño del rectángulo, las paradas de color y el radio del degradado, puedes crear innumerables efectos visuales, desde sutiles rellenos de fondo hasta gráficos de foco audaces. Siéntete libre de experimentar con diferentes valores de `AffineTransform` para rotar o sesgar el degradado, y combina esta técnica con texto e imágenes para obtener salidas PDF o EPS más ricas.

---

**Última actualización:** 2025-12-08  
**Probado con:** Aspose.Page for Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}