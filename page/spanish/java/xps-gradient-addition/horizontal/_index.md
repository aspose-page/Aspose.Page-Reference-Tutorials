---
date: 2026-03-13
description: Aprende cómo agregar degradado a documentos XPS en Java usando Aspose.Page
  y cómo personalizar los puntos de degradado para lograr efectos horizontales impresionantes.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Cómo agregar un degradado – Degradado horizontal en Java XPS
url: /es/java/xps-gradient-addition/horizontal/
weight: 11
---

 final content.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar un degradado – Degradado horizontal en Java XPS

## Introducción
Bienvenido a esta guía paso a paso sobre **cómo agregar un degradado** a un documento XPS usando Java. En este tutorial aprenderá a añadir un degradado horizontal, por qué es importante para el acabado visual y cómo **personalizar las paradas del degradado** para un control preciso del color. Aspose.Page para Java hace que trabajar con documentos XPS (XML Paper Specification) sea sencillo, permitiéndole centrarse en el diseño en lugar de en la manipulación de bajo nivel del archivo.

## Respuestas rápidas
- **¿Qué biblioteca se necesita?** Aspose.Page for Java  
- **¿Qué versión de Java funciona?** Cualquier runtime Java 8+  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción  
- **¿Puedo cambiar la dirección del degradado?** Sí, solo modifique los puntos de inicio/fin del pincel lineal  
- **¿Es posible agregar varios degradados?** Absolutamente, repita los pasos de creación de la ruta con diferentes pinceles  

## ¿Qué es un degradado horizontal en XPS?
Un degradado horizontal es una transición suave de colores de izquierda a derecha a través de una forma. En XPS se representa mediante un pincel de degradado lineal que interpola entre **paradas de degradado** definidas. Este efecto visual se utiliza comúnmente en banners, botones y rellenos de fondo.

## ¿Por qué usar Aspose.Page para Java?
- **Compatibilidad total con XPS** – crear, editar y renderizar sin herramientas de terceros.  
- **API sencilla** – objetos de alto nivel como `XpsDocument`, `XpsPath` y `XpsGradientBrush` ocultan la complejidad XML.  
- **Rendimiento** – optimizado para documentos grandes y procesamiento por lotes.  

## Requisitos previos
Antes de comenzar, asegúrese de tener:

1. **Entorno de desarrollo Java** – Instale el último JDK desde [java.com](https://www.java.com).  
2. **Biblioteca Aspose.Page para Java** – Descargue el JAR de la [documentación de Aspose.Page para Java](https://reference.aspose.com/page/java/).  

## Importar paquetes
Comience importando las clases necesarias. Estas importaciones le dan acceso a la creación de documentos, manejo de degradados y geometría básica.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Paso 1: Inicializar el documento XPS
Cree una nueva instancia de `XpsDocument` y apunte a la carpeta donde desea guardar el resultado.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Paso 2: Crear degradado horizontal
Defina una lista de **paradas de degradado** que controlan el color y la posición de cada punto de transición. El ejemplo a continuación crea un degradado vibrante similar a un arco iris.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### Cómo personalizar las paradas del degradado
- **Color** – Use `doc.createColor(alpha, red, green, blue)` para establecer cualquier valor ARGB.  
- **Posición** – El segundo argumento (`float` entre `0` y `1`) define dónde aparece la parada a lo largo de la línea del degradado. Ajuste estos valores para mover los colores a la izquierda o a la derecha.

## Paso 3: Añadir ruta con degradado
Cree una ruta rectangular, aplique una transformación si es necesario y rellénela con el pincel de degradado lineal. El pincel usa dos puntos (`(10,0)` a `(228,0)`) para producir un efecto horizontal. Como las coordenadas Y son idénticas, este pincel actúa como un **pincel de degradado horizontal**.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Consejo profesional:** Reutilizar la misma lista `stops` para varias rutas puede mejorar el rendimiento, pero recuerde llamar a `clear()` antes de añadir nuevas paradas.

## Paso 4: Guardar el documento
Persista el archivo XPS en disco. Ahora puede abrirlo con cualquier visor XPS para ver el degradado horizontal en acción.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Cómo aplicar varios degradados
Si desea **aplicar varios degradados** dentro del mismo documento XPS, simplemente repita los pasos “Crear degradado horizontal” y “Añadir ruta con degradado” para cada nueva forma. Use una lista nueva de objetos `XpsGradientStop` (o limpie la lista existente) y asigne un nuevo `LinearGradientBrush` con sus propios puntos de inicio/fin. Este enfoque le permite superponer degradados, crear fondos complejos o resaltar diferentes elementos UI en una sola página.

## Por qué importa – Beneficios del pincel de degradado horizontal
- **Profundidad visual:** Un pincel de degradado horizontal añade una sutil sensación tridimensional sin imágenes adicionales.  
- **Eficiencia de tamaño de archivo:** Los degradados se almacenan como definiciones vectoriales, manteniendo el archivo XPS ligero.  
- **Escalabilidad:** Al ser vectorial, el degradado se escala limpiamente en pantallas de alta resolución.  

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| El degradado aparece sólido | No se añadieron paradas de degradado o el pincel no está configurado | Asegúrese de que `path.setFill(...)` use un `LinearGradientBrush` y que las paradas se añadan mediante `getGradientStops().addAll(stops)`. |
| Los colores se ven apagados | Valor alfa incorrecto (primer parámetro) | Use `255` para colores totalmente opacos a menos que se desee transparencia. |
| El tamaño de la ruta es incorrecto | Los valores de la matriz de transformación son incorrectos | Ajuste los parámetros de la matriz (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Preguntas frecuentes

**P: ¿Puedo aplicar varios degradados en un solo documento XPS?**  
R: Sí, puede agregar múltiples rutas, cada una con su propio pincel de degradado, para crear diseños complejos en capas.

**P: ¿Aspose.Page es compatible con las últimas versiones de Java?**  
R: Aspose.Page for Java se actualiza regularmente y funciona con Java 8 y versiones posteriores.

**P: ¿Hay otros tipos de degradado disponibles en Aspose.Page?**  
R: Además de los degradados lineales, Aspose.Page también admite degradados radiales para transiciones de color circulares.

**P: ¿Puedo personalizar los colores y posiciones de las paradas de degradado?**  
R: ¡Absolutamente! Tiene control total sobre el color ARGB de cada parada y su posición relativa (rango 0‑1).

**P: ¿Existe un foro comunitario para Aspose.Page donde pueda buscar ayuda?**  
R: Sí, puede visitar el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para conectarse con la comunidad y obtener asistencia.

---

**Última actualización:** 2026-03-13  
**Probado con:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}