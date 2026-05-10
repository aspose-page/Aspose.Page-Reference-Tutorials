---
date: 2026-02-13
description: Aprende a crear un degradado PostScript con un degradado radial de paradas
  de color usando Aspose.Page para Java. Esta guía paso a paso te muestra cómo agregar
  un degradado de paradas de color en tus documentos.
linktitle: Mastering Radial Gradients in Java
second_title: Aspose.Page Java API
title: Crear gradiente PostScript – Gradiente radial en Java
url: /es/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar un degradado radial en Java PostScript con Aspose.Page

## Introducción
Si alguna vez necesitaste **crear un degradado PostScript** con una transición de color suave y llamativa, aprender a añadir un degradado radial es el punto de partida perfecto. En este tutorial recorreremos cada paso necesario para generar un archivo PostScript que contenga un hermoso degradado radial, usando la biblioteca **Aspose.Page for Java**. Al final comprenderás la API, verás un ejemplo completo y ejecutable, y sabrás cómo ajustar colores, posiciones y radios para adaptarlos a cualquier diseño.

## Respuestas rápidas
- **¿Qué biblioteca crea degradados radiales en PostScript?** Aspose.Page for Java.  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un ejemplo básico.  
- **¿Necesito una licencia para ejecutar el código?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Qué versión de Java es compatible?** Java 8 o superior.  
- **¿Puedo cambiar la forma del degradado?** Sí – ajuste el radio y el punto central en el constructor `RadialGradientPaint`.

## Cómo crear un degradado PostScript con relleno radial
A continuación encontrarás una guía concisa paso a paso que muestra exactamente cómo **crear contenido de degradado PostScript** usando un relleno radial. Cada paso incluye una breve explicación seguida del bloque de código original (sin cambios).

## ¿Qué es un degradado radial?
Un degradado radial pinta colores que irradian desde un punto central, mezclándose gradualmente hacia los bordes. A diferencia de los degradados lineales, la transición de color sigue un patrón circular (o elíptico), lo que es ideal para resaltados, focos o rellenos de fondo suaves.

## ¿Por qué usar Aspose.Page para degradados radiales?
- **Control total sobre la salida PostScript** – no es necesario crear manualmente comandos PS de bajo nivel.  
- **Multiplataforma** – funciona en cualquier SO que ejecute Java.  
- **Gestión de color avanzada** – admite múltiples paradas de color, diferentes espacios de color y métodos de ciclo.  
- **Listo para integración** – combine con otras funciones de Aspose.Page como texto, imágenes y formas vectoriales.

## Requisitos previos
Antes de sumergirnos en el código, asegúrate de tener lo siguiente listo:

- **Java Development Kit (JDK) 8+** – verifique con `java -version`.  
- **Aspose.Page for Java** – descargue el JAR más reciente desde la página oficial de [descarga de Aspose.Page](https://releases.aspose.com/page/java/).  
- **IDE de su elección** – Eclipse, IntelliJ IDEA o VS Code con extensiones Java.  
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

> **Consejo profesional:** ajuste las coordenadas del rectángulo (`200, 100, 200, 200`) para posicionar el degradado donde desee en la página.

### Paso 2: Definir colores y fracciones
Un degradado radial se construye a partir de *paradas de color* (los colores) y *fracciones* (las posiciones relativas de esas paradas). Aquí creamos un arreglo de seis colores y sus fracciones correspondientes.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Por qué es importante:** al ajustar `fractions` controla la rapidez con la que los colores hacen la transición, lo que permite efectos sutiles o dramáticos.

### Agregar degradado de paradas de color a su relleno radial
Cuando necesites **añadir un degradado de paradas de color**, los arreglos `colors` y `fractions` son la clave. Siéntete libre de reordenar, añadir o eliminar entradas para adaptarlas a tu diseño visual.

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

### Paso 4: Establecer el Paint y rellenar el rectángulo
Con la pintura lista, indicamos al `PsDocument` que la use y luego rellenamos el rectángulo que definimos anteriormente.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

En este punto la página PostScript contiene un rectángulo rellenado suavemente con el degradado radial que configuramos.

### Paso 5: Cerrar y guardar el documento
Finalmente, cierra la página actual y escribe el archivo en disco.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Abre `RadialGradient1_outPS.ps` en cualquier visor PostScript (p. ej., Ghostscript) y verás el degradado renderizado exactamente como se definió.

## Problemas comunes y soluciones
| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| El degradado aparece como un color sólido | El arreglo `fractions` no comienza en `0.0f` o no termina en `1.0f` | Asegúrese de que la primera fracción sea `0.0f` y la última sea `1.0f`. |
| Los colores se ven deslavados | Uso del `ColorSpaceType` incorrecto | Cambie a `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` para una salida más vibrante. |
| No se genera el archivo de salida | La ruta de `FileOutputStream` es inválida o no tiene permisos de escritura | Verifique que `dataDir` exista y que la aplicación tenga permisos de escritura. |

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Page for Java en proyectos comerciales?**  
R: Sí. Se requiere una licencia comercial para uso en producción. Puedes adquirir una en la [página de licencias de Aspose](https://purchase.aspose.com/buy).

**P: ¿Dónde puedo encontrar la referencia oficial de la API?**  
R: La documentación completa está disponible [aquí](https://reference.aspose.com/page/java/).

**P: ¿Existe una prueba gratuita disponible para pruebas?**  
R: Absolutamente. Descarga una versión de prueba desde la [página de lanzamientos de Aspose.Page](https://releases.aspose.com/).

**P: ¿Cómo obtengo una licencia temporal para evaluación?**  
R: Una licencia temporal puede solicitarse [aquí](https://purchase.aspose.com/temporary-license/).

**P: ¿Dónde puedo obtener soporte de la comunidad?**  
R: Únete al foro de la comunidad Aspose.Page en [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusión
Ahora sabes **cómo agregar un degradado radial** a un documento Java PostScript usando Aspose.Page. Ajustando el tamaño del rectángulo, las paradas de color y el radio del degradado puedes crear innumerables efectos visuales, desde sutiles rellenos de fondo hasta gráficos de foco audaces. Siéntete libre de experimentar con diferentes valores de `AffineTransform` para rotar o sesgar el degradado, y combina esta técnica con texto e imágenes para obtener salidas PDF o EPS más ricas.

---

**Última actualización:** 2026-02-13  
**Probado con:** Aspose.Page for Java latest (al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}