---
date: 2026-02-18
description: Aprende cómo establecer el color de pintura y crear una elipse PostScript
  en Java usando Aspose.Page. Esta guía muestra cómo rellenar una elipse en Java,
  dibujar el contorno de la elipse y establecer el grosor del trazo.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Establecer el color de pintura para dibujar una elipse PostScript en Java
url: /es/java/postscript-shapes/add-ellipse/
weight: 10
---

 sure no extra spaces.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Establecer color de pintura para dibujar una elipse PostScript en Java

## Introducción
Si necesita **set paint color** mientras dibuja gráficos vectoriales, la biblioteca Aspose.Page for Java le brinda control total sobre cada trazo y relleno. En este tutorial descubrirá cómo **set paint color**, **fill ellipse Java** y **draw ellipse outline** usando un enfoque simple, paso a paso. Al final, podrá agregar elipses PostScript de alta calidad a facturas, informes o cualquier documento imprimible.

## Respuestas rápidas
- **¿Qué biblioteca es la mejor para dibujar gráficos PostScript en Java?** Aspose.Page for Java.  
- **¿Puedo rellenar una elipse con un color sólido?** Sí – use `document.setPaint(Color.YOUR_COLOR)` antes de `fill`.  
- **¿Cómo dibujo solo el contorno de una elipse?** Establezca la pintura y el trazo, luego llame a `document.draw(...)`.  
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia comercial; una licencia temporal está disponible para pruebas.  
- **¿Qué versión de Java es compatible?** Cualquier entorno de ejecución Java 8+ funciona con la versión actual de Aspose.Page.

## ¿Qué es una elipse PostScript?
Una elipse PostScript es una forma vectorial definida por un rectángulo delimitador. A diferencia de las imágenes raster, se escala sin pérdida de calidad, lo que la hace ideal para impresión de alta resolución y conversión a PDF.

## ¿Por qué usar Aspose.Page para crear una elipse PostScript?
- **Control total** sobre primitivas de dibujo (líneas, curvas, elipses).  
- **Multiplataforma** – funciona en Windows, Linux y macOS.  
- **Sin dependencias externas** – API Java pura, sin código nativo.  
- **Integración fácil** con aplicaciones Java existentes y herramientas de compilación.

## Requisitos previos
Antes de comenzar, asegúrese de tener:

1. Un entorno de desarrollo Java funcional (JDK 8 o posterior).  
2. La biblioteca Aspose.Page for Java añadida a su proyecto. Puede descargarla **[here](https://releases.aspose.com/page/java/)**.  

## Importar paquetes
En su archivo fuente Java, importe las clases necesarias para dibujar y guardar contenido PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Cómo establecer el color de pintura para una elipse
Establecer el color de pintura es el primer paso antes de cualquier operación de relleno o trazo. El método `setPaint` determina el color que se usará para el siguiente comando de dibujo.

### Paso 1: Configurar el documento PostScript
Cree un flujo de salida, configure el tamaño de página e instancie un `PsDocument`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Paso 2: Cómo rellenar una elipse – usar set paint color
Para **fill ellipse**, debe primero llamar a `setPaint` con el color de relleno deseado, luego invocar `fill` con una instancia `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Paso 3: Dibujar el contorno de la elipse y establecer el grosor del trazo
Después de rellenar, puede cambiar la pintura a otro color, definir un `BasicStroke` para controlar el ancho de línea y dibujar el contorno de la elipse.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Paso 4: Cerrar y guardar el documento
Finalice la página y escriba el archivo PostScript en disco.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Ahora tiene un archivo PostScript que contiene dos elipses: una rellena de naranja y otra con contorno rojo. Siéntase libre de experimentar con diferentes coordenadas, tamaños y colores para adaptarse a sus necesidades de diseño.

## Problemas comunes y solución de errores
- **Ruta de archivo incorrecta** – Asegúrese de que `dataDir` termine con un separador (`/` o `\\`) apropiado para su SO.  
- **Licencia faltante** – Sin una licencia válida, la biblioteca se ejecuta en modo de evaluación y puede agregar marcas de agua.  
- **Color no aplicado** – Recuerde establecer `document.setPaint(...)` *antes* de cada llamada a `fill` o `draw`; la configuración de pintura no persiste automáticamente entre operaciones separadas.

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Page for Java con otras bibliotecas Java?**  
A: Sí, Aspose.Page for Java está diseñada para integrarse sin problemas con otras bibliotecas Java.

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?**  
A: Obtenga una licencia temporal **[here](https://purchase.aspose.com/temporary-license/)** para propósitos de prueba.

**Q: ¿Es Aspose.Page adecuada para proyectos comerciales?**  
A: ¡Absolutamente! Visite **[here](https://purchase.aspose.com/buy)** para explorar opciones de licencia para uso comercial.

**Q: ¿Dónde puedo buscar ayuda o discutir consultas relacionadas con Aspose.Page?**  
A: Únase a la comunidad en el **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** para discusiones y asistencia.

**Q: ¿Hay recursos gratuitos para aprender más sobre Aspose.Page for Java?**  
A: Utilice la **[free trial](https://releases.aspose.com/)** y explore ejemplos en la documentación.

## Conclusión
Aspose.Page for Java facilita **set paint color**, **fill ellipse** y **draw ellipse outline**, ya sea que necesite una forma simple rellena o un gráfico complejo con trazo. Con los pasos anteriores puede agregar rápidamente gráficos vectoriales de nivel profesional a cualquier documento imprimible. Para una exploración más profunda—como combinar múltiples formas, aplicar degradados o convertir a PDF—consulte la **[documentation](https://reference.aspose.com/page/java/)** oficial.

---

**Última actualización:** 2026-02-18  
**Probado con:** Aspose.Page for Java 24.11  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}