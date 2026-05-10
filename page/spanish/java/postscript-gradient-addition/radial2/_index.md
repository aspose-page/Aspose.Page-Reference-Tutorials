---
date: 2026-02-13
description: Aprende a rellenar una forma con degradado y dibujar un círculo con degradado
  en Java PostScript usando Aspose.Page. Guía paso a paso con código y consejos.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Rellenar forma con degradado: ejemplo radial de Java PostScript'
url: /es/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rellenar forma con degradado: ejemplo radial de PostScript en Java

## Introducción
En este tutorial aprenderá a **rellenar forma con degradado** creando un ejemplo de degradado radial para un documento PostScript usando Aspose.Page para Java. Recorreremos cada paso, desde la configuración del proyecto hasta la renderización de un círculo relleno con un degradado radial suave, para que pueda agregar gráficos llamativos a sus aplicaciones Java al instante.

## Respuestas rápidas
- **¿Qué crea este tutorial?** Un archivo PostScript (`.ps`) que contiene un círculo relleno con un degradado radial.  
- **¿Qué biblioteca se requiere?** Aspose.Page para Java (última versión).  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un ejemplo funcional.  
- **¿Necesito una licencia?** Se requiere una licencia temporal o completa para uso en producción; una prueba gratuita funciona para desarrollo.  
- **¿Puedo reutilizar el código para PDF o SVG?** Sí—Aspose.Page admite varios formatos de salida con cambios mínimos.

## Cómo rellenar forma con degradado en PostScript
Antes de sumergirnos en el código, aclaremos por qué “rellenar forma con degradado” es importante. Usar degradados brinda a sus gráficos una sensación profesional y tridimensional sin necesidad de imágenes rasterizadas. Con Aspose.Page puede aplicar la misma lógica de degradado a cualquier forma vectorial—círculos, rectángulos o rutas personalizadas—en todos los formatos de salida compatibles (PostScript, PDF, SVG).

## ¿Qué es un degradado radial?
Un degradado radial transiciona los colores desde un punto central hacia el exterior, creando una mezcla circular y suave. Es ideal para resaltados, fondos de botones o cualquier elemento visual que necesite un efecto de “brillo” natural.

## ¿Por qué usar Aspose.Page para degradados radiales?
- **Renderizado independiente del dispositivo** – funciona igual en PostScript, PDF, SVG y más.  
- **Integración completa con Java** – sin código nativo, solo APIs Java simples.  
- **Salida de alta calidad** – admite anti‑aliasing y control del espacio de color.

## Requisitos previos
Antes de comenzar, asegúrese de contar con:

- Familiaridad básica con la programación en Java.  
- JDK 8 o superior instalado en su máquina.  
- Biblioteca Aspose.Page para Java (descárguela desde la [documentación de Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## Importar paquetes
Primero, importe las clases que necesitaremos. Estas incluyen tipos gráficos estándar de AWT y la API de Aspose.Page.

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
Defina la carpeta donde se guardará el archivo PostScript generado. Reemplace el marcador de posición con una ruta real en su sistema.

```java
String dataDir = "Your Document Directory";
```

## Paso 2: Crear el flujo de salida
Abra un `FileOutputStream` que apunte al archivo `.ps` de destino. Este flujo alimenta los datos binarios generados por Aspose.Page.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Paso 3: Crear opciones de guardado
Instancie `PsSaveOptions`. Puede personalizar el tamaño de página, compresión, etc., pero los valores predeterminados son adecuados para este ejemplo.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Paso 4: Crear el documento PS
Cree el objeto `PsDocument`, pasando el flujo de salida y las opciones de guardado. La bandera `false` indica a Aspose.Page que no abra automáticamente una página (lo haremos manualmente).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Paso 5: Crear un círculo
Dibujaremos un círculo usando `Ellipse2D.Float`. Los parámetros son `(x, y, width, height)`. Establecer `width = height` crea un círculo perfecto.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Cómo dibujar un círculo con degradado
Ahora que tenemos una forma, el siguiente paso es **dibujar círculo con degradado**. Al aplicar un `RadialGradientPaint` al círculo, la operación de relleno usará automáticamente el degradado que definimos.

## Paso 6: Definir colores del degradado
Prepare dos matrices: una para los colores que aparecerán en el degradado y otra para las posiciones fraccionarias correspondientes (0 = centro, 1 = borde).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Paso 7: Crear AffineTransform
El `AffineTransform` escala y traslada el degradado para ajustarlo a nuestro círculo. La matriz `(scaleX, 0, 0, scaleY, translateX, translateY)` realiza el trabajo.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Paso 8: Crear RadialGradientPaint
Ahora construimos el objeto `RadialGradientPaint`. Recibe el punto central, radio, punto focal, fracciones de color, matriz de colores, método de ciclo, espacio de color y la transformación que acabamos de definir.

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

## Paso 9: Establecer el paint y rellenar el círculo
Aplique el paint de degradado al documento y rellene el círculo definido previamente. Este es el núcleo de nuestro **ejemplo de degradado radial** y demuestra cómo **rellenar forma con degradado**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Paso 10: Cerrar la página y guardar el documento
Finalice la página, escriba el contenido en disco y cierre el flujo. Su archivo PostScript está ahora listo para visualizarse con cualquier visor PS.

```java
document.closePage();
document.save();
```

¡Felicidades! Ha creado con éxito un ejemplo de degradado radial en Java PostScript usando Aspose.Page. Ahora dispone de un patrón reutilizable para **rellenar forma con degradado**, que puede adaptarse a otras formas y formatos de salida.

## Problemas comunes y soluciones
| Problema | Solución |
|----------|----------|
| **FileNotFoundException** al abrir el flujo de salida | Verifique que `dataDir` apunte a una carpeta existente y que tenga permisos de escritura. |
| El degradado se ve plano o falta | Asegúrese de que la matriz `fractions` coincida con la longitud de la matriz `colors` y de que el `AffineTransform` escale correctamente. |
| Los colores aparecen invertidos | Intercambie el orden de los colores en la matriz `colors` o ajuste las coordenadas del punto `focus`. |

## Preguntas frecuentes

**Q: ¿Dónde puedo encontrar la documentación de Aspose.Page para Java?**  
A: La referencia completa de la API está disponible [aquí](https://reference.aspose.com/page/java/).

**Q: ¿Cómo puedo descargar Aspose.Page para Java?**  
A: Obtenga el último JAR desde la [página de lanzamientos](https://releases.aspose.com/page/java/).

**Q: ¿Hay una prueba gratuita disponible?**  
A: Sí—descargue una versión de prueba [aquí](https://releases.aspose.com/).

**Q: ¿Puedo obtener una licencia temporal para pruebas?**  
A: Absolutamente, solicite una en la [página de licencia temporal](https://purchase.aspose.com/temporary-license/).

**Q: ¿Dónde puedo obtener soporte de la comunidad?**  
A: Únase a la discusión en el [foro de Aspose.Page](https://forum.aspose.com/c/page/39).

## Conclusión
En esta guía construimos un **ejemplo completo de degradado radial** para un documento PostScript usando Aspose.Page para Java. Siguiendo los pasos, ahora dispone de un patrón reutilizable para **rellenar forma con degradado**, que puede adaptar a PDF, SVG o cualquier otro formato compatible con Aspose.Page. Experimente con diferentes colores, radios y formas para enriquecer sus proyectos gráficos en Java.

---

**Última actualización:** 2026-02-13  
**Probado con:** Aspose.Page for Java 24.11 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}