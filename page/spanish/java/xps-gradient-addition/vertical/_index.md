---
date: 2025-12-25
description: Aprende cómo agregar un degradado vertical en Java XPS usando Aspose.Page.
  Sigue esta guía paso a paso para mejorar el atractivo visual de tu documento.
linktitle: How to Add Vertical Gradient in Java XPS
second_title: Aspose.Page Java API
title: Cómo agregar un degradado vertical en Java XPS
url: /es/java/xps-gradient-addition/vertical/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar un degradado vertical en Java XPS

## Introducción
En este tutorial descubrirás **cómo agregar un degradado vertical** a documentos XPS al trabajar con Java. Aplicar un degradado vertical puede mejorar drásticamente el impacto visual de tus informes, facturas o cualquier contenido imprimible. Recorreremos cada paso, desde la configuración del proyecto hasta guardar el archivo XPS final, usando la poderosa biblioteca Aspose.Page for Java.

## Respuestas rápidas
- **¿Qué hace un degradado vertical?** Crea una transición de color suave de arriba a abajo de una forma.  
- **¿Qué biblioteca se requiere?** Aspose.Page for Java (descargable desde el sitio oficial).  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción.  
- **¿Es compatible con Java 8+?** Sí, la API soporta Java 8 y versiones posteriores.  
- **¿Cuánto tiempo lleva la implementación?** Normalmente menos de 10 minutos una vez que el entorno está configurado.

## Requisitos previos
Antes de sumergirnos en el código, asegúrate de tener lo siguiente:

- Un entorno de desarrollo Java funcional (JDK 8 o más reciente).  
- Biblioteca Aspose.Page for Java. Puedes descargarla desde [aquí](https://releases.aspose.com/page/java/).  
- Una comprensión básica de los conceptos de programación Java.  

## Importar paquetes
Comienza importando los paquetes necesarios para tu proyecto Java. Asegúrate de que la biblioteca Aspose.Page for Java esté añadida al classpath de tu proyecto.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Import Aspose.Page for Java
```

## Paso 1: Inicializar el documento
Comienza creando un nuevo documento XPS. Este objeto contendrá todos los elementos de dibujo que agregues más adelante.

```java
// Initialize document
XpsDocument doc = new XpsDocument();
```

## Paso 2: Crear una ruta con un degradado vertical
A continuación, define una ruta rectangular y aplica un degradado lineal vertical. Las paradas del degradado determinan los colores y sus posiciones a lo largo del eje vertical.

```java
// Create a path with geometry
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Define vertical gradient stops
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
// Apply the vertical gradient to the path
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Paso 3: Guardar el documento
Finalmente, escribe el archivo XPS en disco. El archivo resultante contendrá el rectángulo relleno con el degradado vertical que definiste.

```java
// Save the document
doc.save(dataDir + "VerticalGradient.xps");
```

¡Felicidades! Has aprendido con éxito **cómo agregar un degradado vertical** a un documento XPS en Java usando Aspose.Page.

## ¿Por qué usar un degradado vertical?
- **Estética mejorada:** Los degradados añaden profundidad y un aspecto moderno a las formas estáticas.  
- **Consistencia de marca:** Coincide los colores corporativos de forma fluida a través de las páginas.  
- **Fácil personalización:** Cambia colores o posiciones de paradas sin rediseñar los gráficos.

## Problemas comunes y solución de problemas
- **Degradado no visible:** Verifica que los puntos de inicio y fin del `LinearGradientBrush` estén configurados correctamente para una orientación vertical.  
- **Archivo no guardado:** Asegúrate de que `dataDir` apunte a una carpeta con permisos de escritura y que tengas permiso para escribir archivos.  
- **Biblioteca no encontrada:** Verifica que el JAR de Aspose.Page esté incluido en la ruta de compilación de tu proyecto.

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Page for Java en proyectos comerciales?**  
R: Sí, Aspose.Page for Java está disponible para uso comercial. Puedes comprarlo [aquí](https://purchase.aspose.com/buy).

**P: ¿Hay una prueba gratuita disponible para Aspose.Page for Java?**  
R: Sí, puedes acceder a una prueba gratuita [aquí](https://releases.aspose.com/).

**P: ¿Dónde puedo encontrar la documentación de Aspose.Page for Java?**  
R: La documentación está disponible [aquí](https://reference.aspose.com/page/java/).

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?**  
R: Obtén una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

**P: ¿Necesitas ayuda o tienes preguntas?**  
R: Visita el [foro](https://forum.aspose.com/c/page/39) de la comunidad Aspose.Page.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}