---
date: 2025-12-08
description: Aprenda cómo agregar patrones de trama a documentos Java PostScript usando
  Aspose.Page Java. Esta guía paso a paso le muestra cómo añadir gráficos con patrones
  de trama de manera eficiente.
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: Añadir patrón de trama en PostScript Java'
url: /es/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Añadir patrón de tramado en Java PostScript

## Introducción
Si trabajas con **Aspose.Page Java** y necesitas enriquecer tu salida PostScript con gráficos texturizados, los patrones de tramado son una solución rápida y flexible. En este tutorial recorreremos **cómo añadir tramado** a un documento PostScript, explicaremos por qué son útiles y te daremos un ejemplo de código completo, listo para ejecutar. Al final, podrás crear formas y texto rellenos con tramado visualmente atractivos con solo unas pocas líneas de Java.

## Respuestas rápidas
- **¿Qué biblioteca necesito?** Aspose.Page for Java (el SDK “aspose page java”).  
- **¿Qué efecto visual estamos añadiendo?** Patrones de tramado (p. ej., líneas diagonales, cruzado).  
- **¿Necesito una licencia para ejecutar el ejemplo?** Una prueba gratuita funciona para desarrollo; se requiere una licencia para producción.  
- **¿Cuántas líneas de código?** Aproximadamente 70 líneas, divididas en pasos claros.  
- **¿Puedo usar el mismo enfoque para PDFs?** Sí—Aspose.Page admite varios formatos de salida, incluido PDF.

## Requisitos previos
Antes de comenzar, asegúrate de tener:

- **Entorno de desarrollo Java** – JDK 8 o superior y un IDE de tu elección.  
- **Biblioteca Aspose.Page for Java** – Descarga el JAR más reciente del sitio oficial [here](https://releases.aspose.com/page/java/).  
- **Acceso de escritura** a una carpeta donde se guardará el archivo PostScript generado.

## Importar paquetes
Primero, incorpora las clases necesarias a tu proyecto. Estas importaciones te dan acceso a primitivas de dibujo, manejo de colores y la API de Aspose.Page.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Paso 1: Configurar parámetros iniciales
Crea el flujo de salida, configura el tamaño de página (A4) y define algunas variables de diseño que se reutilizarán al dibujar cada cuadrado relleno con tramado.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Paso 2: Guardar estado gráfico y trasladar
Guardar el estado gráfico nos permite volver al sistema de coordenadas original más tarde, mientras que `translate` mueve el origen a un punto de partida conveniente.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Paso 3: Crear cuadrado para cada patrón
Define un rectángulo reutilizable que representará cada celda rellena con tramado.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Paso 4: Configurar lápiz para contorno del cuadrado de patrón
Un `BasicStroke` de 2 puntos brinda un contorno nítido alrededor de cada cuadrado.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Paso 5: Iterar a través de los patrones de tramado
Recorre cada valor del enum `HatchStyle`, rellena cada cuadrado con la textura correspondiente y luego dibuja su contorno. Este es el núcleo de la funcionalidad de **añadir patrón de tramado**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Paso 6: Restaurar estado gráfico
Vuelve al sistema de coordenadas original después de terminar de dibujar la cuadrícula de cuadrados.

```java
document.writeGraphicsRestore();
```

## Paso 7: Rellenar texto con patrón de tramado
Aquí demostramos cómo pintar texto usando una textura de tramado. El ejemplo rellena la palabra “ABC” con un patrón diagonal‑cruzado.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Paso 8: Contornear texto con patrón de tramado
Ahora contorneamos el mismo texto, pero esta vez usando un estilo de tramado al 70 % y un trazo más grueso.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Paso 9: Cerrar y guardar documento
Finaliza la página, escribe el archivo en disco y libera los recursos.

```java
document.closePage();
document.save();
```

Sigue estos pasos y tendrás un archivo PostScript que muestra un conjunto completo de patrones de tramado aplicados tanto a formas como a texto—todo impulsado por **aspose page java**.

## ¿Por qué usar patrones de tramado con Aspose.Page Java?
- **Distinción visual** – Los rellenos de tramado funcionan incluso cuando las impresoras están limitadas a salida monocromática.  
- **Rendimiento** – Las texturas se generan al vuelo, evitando archivos de imagen grandes.  
- **Soporte multiplataforma** – El mismo código puede dirigirse a PDF, EPS o SVG con cambios mínimos.

## Problemas comunes y consejos
- **Errores de ruta de archivo** – Asegúrate de que `dataDir` termine con el separador de archivos apropiado (`/` o `\`).  
- **Colores no compatibles** – Algunos intérpretes PostScript antiguos pueden no manejar ciertos espacios de color; usa RGB básico para máxima compatibilidad.  
- **Advertencias de licencia** – Ejecutar el ejemplo sin una licencia válida incrustará una marca de agua en la salida.

## Conclusión
Incorporar patrones de tramado puede mejorar drásticamente la legibilidad y estética de dibujos técnicos, mapas o cualquier gráfico generado por Java. Con **Aspose.Page Java**, obtienes una API concisa que abstrae los comandos de bajo nivel de PostScript, permitiéndote enfocarte en el diseño en lugar de en los detalles del formato de archivo.

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Page Java con otros frameworks de Java?**  
R: Sí, la biblioteca es independiente del framework y funciona con Spring, Jakarta EE, Android (limitado) y Java SE puro.

**P: ¿Existe una versión de prueba disponible para Aspose.Page Java?**  
R: Absolutamente. Descarga una prueba gratuita de 30 días [here](https://releases.aspose.com/).

**P: ¿Cómo obtengo una licencia temporal para desarrollo?**  
R: Solicita una licencia temporal [here](https://purchase.aspose.com/temporary-license/). Elimina las marcas de agua de evaluación.

**P: ¿Dónde puedo encontrar más tutoriales y soporte de la comunidad?**  
R: Visita el foro oficial [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) para ejemplos adicionales y preguntas y respuestas.

**P: ¿Hay documentación completa para todas las clases y métodos?**  
R: Sí, la referencia completa de la API está disponible [here](https://reference.aspose.com/page/java/).

---

**Última actualización:** 2025-12-08  
**Probado con:** Aspose.Page for Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
