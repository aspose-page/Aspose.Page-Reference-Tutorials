---
date: 2026-05-25
description: Aprenda cómo agregar degradado a documentos XPS en Java usando Aspose.Page.
  Esta guía paso a paso muestra cómo agregar un degradado diagonal, aplicar pinceles
  de degradado lineal y producir archivos XPS profesionales.
keywords:
- how to add gradient
- Aspose.Page Java
- diagonal gradient XPS
linktitle: Agregar degradado diagonal en Java XPS
schemas:
- author: Aspose
  dateModified: '2026-05-25'
  description: Learn how to add gradient to XPS documents in Java using Aspose.Page.
    This step‑by‑step guide shows how to add a diagonal gradient, apply linear gradient
    brushes, and produce professional XPS files.
  headline: 'How to Add Gradient: Diagonal Gradient in Java XPS'
  type: TechArticle
- questions:
  - answer: Create a `XpsLinearGradientBrush`, define gradient stops, and assign it
      to the shape’s `Fill` property as shown in Step 6.
    question: How do I **how to add gradient** to an existing XPS shape?
  - answer: It generates a brush definition in the XPS package that references the
      start/end points and a collection of gradient stops, which the viewer renders
      as a smooth color transition.
    question: What does **apply linear gradient** actually do behind the scenes?
  - answer: Yes, the Aspose.Page API includes methods for adding images, text, and
      custom shapes—simply explore the `XpsDocument` class for additional helpers.
    question: Is there a quick way to **how to use aspose** for other XPS features?
  - answer: Absolutely. Define any geometry using `createPathGeometry` and then set
      its `Fill` to a gradient brush.
    question: Can I **add gradient path** to non‑rectangular shapes?
  - answer: Only marginally; gradient definitions are lightweight XML entries within
      the XPS package.
    question: Does the gradient affect file size significantly?
  type: FAQPage
second_title: Aspose.Page Java API
title: 'Cómo agregar degradado: Degradado diagonal en Java XPS'
url: /es/java/xps-gradient-addition/diagonal/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar degradado: Degradado diagonal en Java XPS

## Introducción
En el desarrollo moderno de Java, dominar **cómo agregar degradado** a documentos XPS brinda a sus informes un aspecto pulido y llamativo que destaca. Este tutorial le guía paso a paso para crear un archivo XPS desde cero, añadir un degradado diagonal y guardar el resultado, todo con Aspose.Page para Java. Comprenderá por qué los degradados son importantes, verá las llamadas exactas a la API y obtendrá consejos prácticos para evitar errores comunes.

## Respuestas rápidas
- **¿Cuál es la biblioteca principal?** Aspose.Page para Java  
- **¿Qué método agrega el degradado?** `createLinearGradientBrush` con paradas de degradado  
- **¿Necesito una licencia?** Una versión de prueba funciona para desarrollo; se requiere una licencia comercial para producción  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10‑15 minutos para un degradado diagonal básico  
- **¿Puedo usarlo con otros frameworks de Java?** Sí, la API es independiente del framework  

## ¿Qué es un degradado diagonal en un documento XPS?
Un degradado diagonal es una transición de color suave que va de una esquina de una forma a la esquina opuesta, creando un efecto visual inclinado. En XPS, este efecto se define mediante un pincel de degradado lineal que contiene paradas de degradado ordenadas que especifican colores y posiciones relativas a lo largo de la línea diagonal.

## ¿Por qué agregar un degradado diagonal con Aspose.Page?
Aspose.Page ofrece **100 % de fidelidad de renderizado** para degradados en más de 20 visores XPS, y soporta **más de 30 características XPS** como texto, imágenes y formas vectoriales. La API abstrae el complejo marcado XPS, permitiéndole centrarse en el diseño mientras garantiza que el mismo archivo se vea idéntico en plataformas Windows, macOS y Linux.

## Requisitos previos
- Conocimientos básicos de programación en Java.  
- JDK instalado en su máquina.  
- Biblioteca Aspose.Page para Java – descárguela **[aquí](https://releases.aspose.com/page/java/)**.  
- Un IDE como IntelliJ IDEA o Eclipse.

## Importar paquetes
Comience importando las clases que necesitará. Estas importaciones le dan acceso a geometría, manejo de degradados y creación de documentos XPS.

```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
```

## Paso 1: Configurar su proyecto
Cree un nuevo proyecto Java en su IDE preferido y añada los archivos JAR de Aspose.Page a la ruta de compilación del proyecto.

## Paso 2: Definir el directorio del documento
Especifique dónde se guardará el archivo XPS generado.

```java
String dataDir = "Your Document Directory";
```

## Paso 3: Crear documento XPS
`XpsDocument` es el objeto central que representa un archivo XPS en memoria. Instanciarlo le proporciona un lienzo para añadir páginas, formas y pinceles.

```java
XpsDocument doc = new XpsDocument();
```

## Paso 4: Añadir ruta con degradado diagonal
Cree una ruta rectangular que recibirá el degradado. La geometría de la ruta utiliza un simple comando mover‑línea‑cerrar.  
XpsPath define una forma vectorial en el documento XPS, como un rectángulo o una geometría personalizada.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
```

## Paso 5: Definir paradas de degradado lineal
Configure los colores y sus posiciones. Cada parada define un punto en el degradado donde aparece un color específico.  
XpsGradientStop representa una única parada de color en un degradado, especificando un color y su desplazamiento.

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 142, 4), 0f));
// ... repeat for other colors and positions
stops.add(doc.createGradientStop(doc.createColor(0, 199, 80), 1f));
```

## Paso 6: Aplicar degradado lineal a la ruta
`XpsLinearGradientBrush` es el tipo de pincel de Aspose.Page para transiciones de color lineales. Toma dos puntos que definen la dirección del degradado y una colección de paradas de degradado que dictan los colores a lo largo de esa línea.

```java
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 10f), new Point2D.Float(228f, 100f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```

## Paso 7: Guardar el documento
Persista el archivo XPS en disco. El archivo contendrá el rectángulo rellenado con el degradado diagonal que definió.

```java
doc.save(dataDir + "LinearGradient.xps");
```

## ¿Cómo agregar degradado en Java XPS?
Cargue el `XpsDocument`, cree un `XpsLinearGradientBrush` con punto de inicio `(0,0)` y punto final `(width,height)`, añada las paradas de degradado, asigne el pincel a la propiedad `Fill` de una forma y, finalmente, llame a `save`. Este flujo conciso le permite incrustar un degradado diagonal con solo unas cuantas llamadas a la API, manteniendo su código limpio y mantenible.

## Problemas comunes y consejos
- **Dirección del degradado** – asegúrese de que los puntos de inicio y fin del pincel reflejen la diagonal deseada; intercambiarlos invierte el degradado.  
- **Precisión del color** – Aspose usa ARGB; incluya el canal alfa si necesita transparencia.  
- **Ruta del archivo** – siempre use una ruta absoluta o verifique que la ruta relativa apunte a un directorio existente y con permisos de escritura.

## Preguntas frecuentes adicionales

**P: ¿Cómo **cómo agregar degradado** a una forma XPS existente?**  
R: Cree un `XpsLinearGradientBrush`, defina las paradas de degradado y asígnelo a la propiedad `Fill` de la forma como se muestra en el Paso 6.

**P: ¿Qué hace realmente **aplicar degradado lineal** tras bastidores?**  
R: Genera una definición de pincel en el paquete XPS que referencia los puntos de inicio/fin y una colección de paradas de degradado, que el visor renderiza como una transición de color suave.

**P: ¿Existe una forma rápida de **cómo usar aspose** para otras características XPS?**  
R: Sí, la API de Aspose.Page incluye métodos para añadir imágenes, texto y formas personalizadas; simplemente explore la clase `XpsDocument` para encontrar ayudantes adicionales.

**P: ¿Puedo **agregar ruta de degradado** a formas no rectangulares?**  
R: Absolutamente. Defina cualquier geometría usando `createPathGeometry` y luego establezca su `Fill` a un pincel de degradado.

**P: ¿El degradado afecta significativamente el tamaño del archivo?**  
R: Solo marginalmente; las definiciones de degradado son entradas XML ligeras dentro del paquete XPS.

---

**Última actualización:** 2026-05-25  
**Probado con:** Aspose.Page para Java 24.11  
**Autor:** Aspose

## Tutoriales relacionados

- [Aspose Page XPS Gradient Addition](/page/java/xps-gradient-addition/)
- [Java XPS Text Addition - Aspose.Page Tutorial](/page/java/xps-text-manipulation/add-text/)
- [How to Add Image to Java XPS Documents – A Simple Guide with Aspose.Page](/page/java/xps-image-manipulation/add-image/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}