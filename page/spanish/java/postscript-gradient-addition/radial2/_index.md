---
date: 2025-12-08
description: Aprenda a crear un ejemplo de degradado radial en Java PostScript usando
  Aspose.Page. Guía paso a paso con código completo y solución de problemas.
language: es
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Ejemplo de degradado radial: Java PostScript con Aspose.Page'
url: /java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ejemplo de degradado radial: Java PostScript con Aspose.Page

## Introducción
En este tutorial crearás un **ejemplo de degradado radial** para un documento PostScript usando Aspose.Page para Java. Recorreremos cada paso, desde la configuración del proyecto hasta la generación de un círculo relleno con un degradado radial suave, para que puedas añadir gráficos llamativos a tus aplicaciones Java al instante.

## Respuestas rápidas
- **¿Qué crea este tutorial?** Un archivo PostScript (`.ps`) que contiene un círculo relleno con un degradado radial.  
- **¿Qué biblioteca se requiere?** Aspose.Page para Java (última versión).  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un ejemplo funcional.  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para uso en producción; una versión de prueba funciona para desarrollo.  
- **¿Puedo reutilizar el código para PDF o SVG?** Sí—Aspose.Page admite varios formatos de salida con cambios mínimos.

## ¿Qué es un degradado radial?
Un degradado radial transiciona los colores desde un punto central hacia el exterior, creando una mezcla circular y suave. Es ideal para resaltados, fondos de botones o cualquier elemento visual que necesite un efecto de “brillo” natural.

## ¿Por qué usar Aspose.Page para degradados radiales?
- **Renderizado independiente del dispositivo** – funciona igual en PostScript, PDF, SVG y más.  
- **Integración completa con Java** – sin código nativo, solo APIs Java simples.  
- **Salida de alta calidad** – admite anti‑aliasing y control del espacio de color.

## Requisitos previos
Antes de comenzar, asegúrate de contar con:

- Familiaridad básica con la programación en Java.  
- JDK 8 o superior instalado en tu máquina.  
- Biblioteca Aspose.Page para Java (descárgala desde la [documentación de Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## Importar paquetes
Primero, importa las clases que necesitaremos. Estas incluyen tipos gráficos estándar de AWT y la API de Aspose.Page.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Paso 1: Configurar el directorio del documento
Define la carpeta donde se guardará el archivo PostScript generado. Reemplaza el marcador de posición con una ruta real en tu sistema.

```java
String dataDir = "Your Document Directory";
```

## Paso 2: Crear el flujo de salida
Abre un `FileOutputStream` que apunte al archivo `.ps` de destino. Este flujo alimenta los datos binarios generados por Aspose.Page.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Paso 3: Crear opciones de guardado
Instancia `PsSaveOptions`. Puedes personalizar el tamaño de página, compresión, etc., pero los valores predeterminados son adecuados para este ejemplo.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Paso 4: Crear el documento PS
Crea el objeto `PsDocument`, pasando el flujo de salida y las opciones de guardado. La bandera `false` indica a Aspose.Page que no abra automáticamente una página (lo haremos manualmente).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Paso 5: Crear un círculo
Dibujaremos un círculo usando `Ellipse2D.Float`. Los parámetros son `(x, y, ancho, alto)`. Establecer ancho = alto crea un círculo perfecto.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Paso 6: Definir los colores del degradado
Prepara dos arreglos: uno para los colores que aparecerán en el degradado y otro para las posiciones fraccionarias correspondientes (0 = centro, 1 = borde).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Paso 7: Crear AffineTransform
El `AffineTransform` escala y traslada el degradado para ajustarlo a nuestro círculo. La matriz `(scaleX, 0, 0, scaleY, translateX, translateY)` realiza la tarea.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Paso 8: Crear RadialGradientPaint
Ahora construimos el objeto `RadialGradientPaint`. Recibe el punto central, el radio, el punto de foco, las fracciones de color, el arreglo de colores, el método de ciclo, el espacio de color y la transformación que acabamos de definir.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Paso 9: Establecer el Paint y rellenar el círculo
Aplica el paint de degradado al documento y rellena el círculo previamente definido. Este es el núcleo de nuestro **ejemplo de degradado radial**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Paso 10: Cerrar la página y guardar el documento
Finaliza la página, escribe el contenido en disco y cierra el flujo. Tu archivo PostScript está listo para visualizarse con cualquier visor PS.

```java
document.closePage();
document.save();
```

¡Felicidades! Has creado con éxito un ejemplo de degradado radial en Java PostScript usando Aspose.Page.

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **FileNotFoundException** al abrir el flujo de salida | Verifica que `dataDir` apunte a una carpeta existente y que tengas permisos de escritura. |
| El degradado se ve plano o falta | Asegúrate de que el arreglo `fractions` coincida con la longitud del arreglo `colors` y de que el `AffineTransform` escale correctamente. |
| Los colores aparecen invertidos | Intercambia el orden de los colores en el arreglo `colors` o ajusta las coordenadas del punto `focus`. |

## Preguntas frecuentes

**Q: ¿Dónde puedo encontrar la documentación de Aspose.Page para Java?**  
A: La referencia completa de la API está disponible [aquí](https://reference.aspose.com/page/java/).

**Q: ¿Cómo puedo descargar Aspose.Page para Java?**  
A: Obtén el último JAR desde la [página de lanzamientos](https://releases.aspose.com/page/java/).

**Q: ¿Hay una versión de prueba gratuita disponible?**  
A: Sí—descarga una versión de prueba [aquí](https://releases.aspose.com/).

**Q: ¿Puedo obtener una licencia temporal para pruebas?**  
A: Absolutamente, solicítala en la [página de licencia temporal](https://purchase.aspose.com/temporary-license/).

**Q: ¿Dónde puedo obtener soporte de la comunidad?**  
A: Únete a la discusión en el [foro de Aspose.Page](https://forum.aspose.com/c/page/39).

## Conclusión
En esta guía construimos un **ejemplo de degradado radial** completo para un documento PostScript usando Aspose.Page para Java. Siguiendo los pasos, ahora dispones de un patrón reutilizable para crear degradados sofisticados, que puedes adaptar a PDF, SVG u otros formatos compatibles. Experimenta con diferentes colores, radios y formas para enriquecer tus proyectos gráficos en Java.

---

**Última actualización:** 2025-12-08  
**Probado con:** Aspose.Page para Java 24.11 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}