---
date: 2026-04-24
description: Aprende cómo crear un documento XPS en Java con una elipse de degradado
  radial. Esta guía paso a paso muestra cómo establecer el grosor del trazo y definir
  la geometría de la ruta usando Aspose.Page.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Agregar elipse en Java XPS
second_title: Aspose.Page Java API
title: Crear documento XPS en Java – Añadir elipse con degradado radial
url: /es/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar elipse con degradado radial con Aspose.Page

## Introducción
En este tutorial, aprenderá a **crear XPS document Java** con una hermosa elipse trazada con degradado radial usando Aspose.Page para Java. Aspose.Page es una biblioteca robusta que abstrae los detalles de bajo nivel de XPS, permitiéndole centrarse en el diseño en lugar de en las complejidades del formato de archivo. Al final de esta guía tendrá un archivo XPS listo para usar que podrá incrustar en informes, facturas o cualquier flujo de trabajo de generación de documentos.

## Respuestas rápidas
- **¿Qué produce este código?** Un archivo XPS de una sola página que contiene una elipse con trazo de degradado radial multicolor.  
- **¿Qué API principal se usa?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, etc.).  
- **¿Necesito una licencia para ejecutar el ejemplo?** Una licencia temporal funciona para evaluación; se requiere una licencia completa para producción.  
- **¿Cuáles son las propiedades clave que configuramos?** Pincel de trazo (degradado radial), método de propagación, paradas de degradado y grosor del trazo.  
- **¿Puedo cambiar el tamaño de la elipse?** Sí, modifique la cadena de geometría del trazado o las coordenadas del pincel de degradado.

## ¿Qué es “create XPS document Java”?
Crear un documento XPS en Java significa generar programáticamente un archivo XML Paper Specification (XPS) —un formato de documento de diseño fijo similar a PDF— directamente desde código Java. Aspose.Page proporciona un modelo de objetos de alto nivel (`XpsDocument`, `XpsCanvas`, etc.) que abstrae el marcado XML, haciendo que el proceso sea tan simple como trabajar con objetos Java estándar.

## ¿Por qué usar una elipse con degradado radial?
Un degradado radial brinda una sensación tridimensional, perfecta para resaltar visualmente, logotipos o elementos decorativos en informes. En comparación con un trazo de color sólido, el degradado añade profundidad sin aumentar significativamente el tamaño del archivo, y el formato XPS conserva la calidad vectorial para cualquier escalado.

## Requisitos previos
Antes de comenzar, asegúrese de contar con los siguientes requisitos:
- Java Development Kit (JDK) instalado en su máquina.
- Biblioteca Aspose.Page for Java descargada. Puede obtenerla [aquí](https://releases.aspose.com/page/java/).
- Un editor de código de su elección (Eclipse, IntelliJ, etc.) para escribir y ejecutar código Java.

## Importar paquetes
Asegúrese de tener los paquetes necesarios importados en su proyecto Java para usar Aspose.Page. Añada las siguientes declaraciones de importación al inicio de su archivo Java:

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```

## Paso 1: Configurar el directorio del documento
Defina la ruta a su directorio de documentos donde se guardará el archivo XPS:

```java
String dataDir = "Your Document Directory";
```

## Paso 2: Crear documento XPS
Inicialice un nuevo documento XPS usando el siguiente código:

```java
XpsDocument doc = new XpsDocument();
```

## Paso 3: Definir paradas del degradado radial
Cree una lista de paradas de degradado para la elipse trazada con degradado radial:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Paso 4: Crear geometría de trazado
Defina una elipse trazada con degradado radial usando geometría de trazado:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Paso 5: Añadir lienzo y trazado
Añada un nuevo lienzo al documento y adjunte el trazado con la geometría definida:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Paso 6: Configurar trazo y degradado
Configure el trazo del trazado con un pincel de degradado radial:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Paso 7: Configurar grosor del trazo
Especifique el **grosor del trazo** del trazado:

```java
path.setStrokeThickness(12f);
```

## Paso 8: Guardar el documento
Guarde el documento XPS resultante:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

¡Felicidades! Ha añadido con éxito una elipse con trazo de degradado radial mientras **crea un XPS document Java** con Aspose.Page.

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **La elipse aparece plana** | Usando `XpsSpreadMethod.Pad` en lugar de `Reflect` | Cambie el método de propagación a `XpsSpreadMethod.Reflect` como se muestra en el Paso 6. |
| **No se genera archivo de salida** | `dataDir` apunta a una carpeta que no existe | Asegúrese de que el directorio exista o use una ruta absoluta. |
| **Los colores del degradado se ven incorrectos** | Orden incorrecto de las paradas del degradado | Verifique que los valores `offset` (0 → 1) aumenten monotonamente. |
| **Errores de compilación** | Faltan los JAR de Aspose.Page en el classpath | Agregue `aspose-page-xx.jar` a las dependencias de su proyecto. |

## Preguntas frecuentes

**Q: ¿Puedo usar Aspose.Page for Java con otras bibliotecas Java?**  
A: Sí, Aspose.Page for Java puede integrarse con otras bibliotecas Java sin problemas.

**Q: ¿Es Aspose.Page adecuado para el procesamiento de documentos a gran escala?**  
A: ¡Absolutamente! Aspose.Page está diseñado para manejar eficientemente el procesamiento de documentos a gran escala.

**Q: ¿Dónde puedo encontrar más tutoriales y ejemplos para Aspose.Page for Java?**  
A: Visite la documentación de [Aspose.Page for Java](https://reference.aspose.com/page/java/) para tutoriales y ejemplos completos.

**Q: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?**  
A: Puede obtener una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**Q: ¿Existen foros comunitarios para discusiones sobre Aspose.Page?**  
A: Sí, únase al [foro de la comunidad Aspose.Page](https://forum.aspose.com/c/page/39) para interactuar con otros desarrolladores y obtener asistencia.

---

**Última actualización:** 2026-04-24  
**Probado con:** Aspose.Page for Java 24.11 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}