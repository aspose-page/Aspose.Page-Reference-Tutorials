---
date: 2025-12-11
description: Aprende a crear una elipse en PostScript con Java usando Aspose.Page.
  Esta guía paso a paso te muestra cómo rellenar la elipse con color y dibujar la
  elipse usando Java.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Cómo crear una elipse PostScript en Java con Aspose.Page
url: /es/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo crear una elipse PostScript en Java con Aspose.Page

## Introducción
Crear una **elipse PostScript** de forma programática le brinda un control fino sobre los gráficos vectoriales en informes, facturas o cualquier documento imprimible. En este tutorial aprenderá a **crear elipses PostScript** utilizando la biblioteca Aspose.Page para Java, rellenar una elipse con color y dibujar el contorno de una elipse. Al final estará listo para incrustar gráficos personalizados directamente en su salida PostScript.

## Respuestas rápidas
- **¿Qué biblioteca es la mejor para dibujar gráficos PostScript en Java?** Aspose.Page for Java.  
- **¿Puedo rellenar una elipse con un color sólido?** Sí – use `document.setPaint(Color.YOUR_COLOR)` antes de `fill`.  
- **¿Cómo dibujo solo el contorno de una elipse?** Establezca el paint y el stroke, luego llame a `document.draw(...)`.  
- **¿Necesito una licencia para uso en producción?** Se requiere una licencia comercial; una licencia temporal está disponible para pruebas.  
- **¿Qué versión de Java es compatible?** Cualquier runtime Java 8+ funciona con la versión actual de Aspose.Page.

## ¿Qué es una elipse PostScript?
Una elipse PostScript es una forma vectorial definida por un rectángulo delimitador. A diferencia de las imágenes raster, se escala sin pérdida de calidad, lo que la hace ideal para impresión de alta resolución y conversión a PDF.

## ¿Por qué usar Aspose.Page para crear una elipse PostScript?
- **Control total** sobre primitivas de dibujo (líneas, curvas, elipses).  
- **Multiplataforma** – funciona en Windows, Linux y macOS.  
- **Sin dependencias externas** – API Java pura, sin código nativo.  
- **Integración fácil** con aplicaciones Java existentes y herramientas de compilación.

## Requisitos previos
Antes de comenzar, asegúrese de contar con:

1. Un entorno de desarrollo Java funcional (JDK 8 o posterior).  
2. La biblioteca Aspose.Page for Java añadida a su proyecto. Puede descargarla **[aquí](https://releases.aspose.com/page/java/)**.  

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

## Guía paso a paso

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

### Paso 2: Rellenar la elipse con color
Establezca el paint al color de relleno deseado y llame a `fill` con una instancia de `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Paso 3: Contornear la elipse con trazo
Cambie el paint al color del trazo, defina un `BasicStroke` para el grosor de la línea y dibuje el contorno de la elipse.

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

Ahora tiene un archivo PostScript que contiene dos elipses: una rellena de naranja y otra contorneada en rojo. Siéntase libre de experimentar con diferentes coordenadas, tamaños y colores para adaptarlos a sus necesidades de diseño.

## Problemas comunes y solución de problemas
- **Ruta de archivo incorrecta** – Asegúrese de que `dataDir` termine con un separador (`/` o `\\`) apropiado para su SO.  
- **Licencia faltante** – Sin una licencia válida, la biblioteca se ejecuta en modo de evaluación y puede agregar marcas de agua.  
- **Color no aplicado** – Recuerde establecer `document.setPaint(...)` *antes* de cada llamada a `fill` o `draw`; la configuración de paint no persiste automáticamente entre operaciones separadas.

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Page for Java con otras bibliotecas Java?**  
R: Sí, Aspose.Page for Java está diseñada para integrarse sin problemas con otras bibliotecas Java.

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?**  
R: Obtenga una licencia temporal **[aquí](https://purchase.aspose.com/temporary-license/)** para propósitos de prueba.

**P: ¿Aspose.Page es adecuada para proyectos comerciales?**  
R: ¡Absolutamente! Visite **[aquí](https://purchase.aspose.com/buy)** para explorar opciones de licencia para uso comercial.

**P: ¿Dónde puedo buscar ayuda o discutir consultas relacionadas con Aspose.Page?**  
R: Únase a la comunidad en el **[Foro de Aspose.Page](https://forum.aspose.com/c/page/39)** para discusiones y asistencia.

**P: ¿Existen recursos gratuitos para aprender más sobre Aspose.Page for Java?**  
R: Utilice la **[prueba gratuita](https://releases.aspose.com/)** y explore ejemplos en la documentación.

## Conclusión
Aspose.Page for Java facilita la **creación de elipses PostScript**, ya sea que necesite una forma simple rellena o un contorno complejo. Con los pasos anteriores puede agregar rápidamente gráficos vectoriales de nivel profesional a cualquier documento imprimible. Para una exploración más profunda —como combinar múltiples formas, aplicar degradados o convertir a PDF— consulte la **[documentación](https://reference.aspose.com/page/java/)** oficial.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2025-12-11  
**Probado con:** Aspose.Page for Java 24.11  
**Autor:** Aspose