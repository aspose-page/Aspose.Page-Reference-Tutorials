---
date: 2026-04-24
description: Aprenda cómo establecer el color del rectángulo y agregar un rectángulo
  en Java XPS usando Aspose.Page. Esta guía cubre cómo agregar un rectángulo en Java
  y cambiar el trazo del rectángulo.
keywords:
- set rectangle color
- add rectangle java
- change rectangle stroke
linktitle: Agregar rectángulo en Java XPS
second_title: Aspose.Page Java API
title: Establecer el color del rectángulo y añadir rectángulo en Java XPS
url: /es/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Establecer color del rectángulo y agregar rectángulo en Java XPS

## Introducción
En esta guía, aprenderás a **establecer el color del rectángulo** y **agregar un rectángulo** en Java XPS usando la biblioteca Aspose.Page. Ya sea que necesites dibujar formas simples para un informe o crear gráficos vectoriales complejos, dominar el estilo de los rectángulos te brinda un control preciso sobre tus documentos XPS.  

## Respuestas rápidas
- **¿Qué biblioteca se requiere?** Aspose.Page for Java  
- **¿Puedo cambiar el trazo del rectángulo?** Sí, usando `setStroke` y `setStrokeThickness`  
- **¿Se admite un perfil de color CMYK?** Absolutamente – puedes cargar perfiles ICC como se muestra  
- **¿Necesito una licencia para producción?** Sí, se requiere una licencia comercial para uso no‑evaluación  
- **¿Cuánto tiempo lleva la implementación?** Normalmente menos de 10 minutos para un rectángulo básico

## Qué es **set rectangle color**?
Establecer el color de un rectángulo significa definir el color de relleno o de trazo que la forma mostrará en el documento XPS final. Con Aspose.Page puedes usar RGB, CMYK o incluso perfiles de color ICC personalizados para lograr una coincidencia de color exacta.

## Por qué usar Aspose.Page para **add rectangle java** y **change rectangle stroke**?
- **API completa** – admite tanto colores sólidos como degradados.  
- **Multiplataforma** – funciona en cualquier entorno Java sin dependencias nativas.  
- **Amplio soporte de geometría** – crea rutas complejas, aplica transformaciones y gestiona el grosor del trazo fácilmente.  

## Requisitos previos
Antes de sumergirnos en el código, asegúrate de tener:

- Conocimientos básicos de programación Java.  
- Biblioteca Aspose.Page instalada. Si no lo está, descárgala desde la [documentación de Aspose.Page Java](https://reference.aspose.com/page/java/).  
- Un entorno de desarrollo Java funcional (IDE, JDK, etc.).  

## Importar paquetes
Para comenzar, importa los paquetes necesarios en tu proyecto Java. Asegúrate de que la biblioteca Aspose.Page esté correctamente añadida a tu classpath. Aquí tienes un ejemplo básico:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Ahora, desglosaremos el ejemplo proporcionado en varios pasos para **agregar un rectángulo** y **establecer su color** en Java XPS.

## Paso 1: Establecer el directorio del documento
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```
Reemplaza `"Your Document Directory"` con la ruta absoluta donde deseas leer/escribir archivos XPS.

## Paso 2: Crear un nuevo documento XPS
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```
Esta línea inicializa un nuevo documento XPS que contendrá nuestras formas.

## Paso 3: Agregar un rectángulo con trazo de color sólido CMYK
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Este paso agrega un **rectángulo con trazo** de color sólido CMYK. El método `setStroke` define el color del contorno del rectángulo, mientras que `setStrokeThickness` controla el ancho de la línea—perfecto para **cambiar el trazo del rectángulo**.

### Consejo profesional:
Si prefieres un color RGB, reemplaza la llamada `createColor` con `doc.createColor(0, 0, 255)` para un relleno azul sólido.

## Paso 4: Guardar el documento XPS resultante
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```
Finalmente, guarda el documento XPS en disco. El archivo `AddRectangle_out.xps` ahora contiene un rectángulo cuyo color y trazo definiste.

## Problemas comunes y soluciones
| Problema | Causa | Solución |
|----------|-------|----------|
| **Rectángulo no visible** | Geometría de ruta incorrecta o grosor del trazo establecido en 0 | Verifica la cadena de ruta (`"M 20,10 L 220,10 220,100 20,100 Z"`) y asegura que `setStrokeThickness` sea mayor que 0. |
| **Color incorrecto** | Usando un perfil ICC que no coincide con el espacio de color deseado | Usa `doc.createColor(r, g, b)` para RGB o verifica nuevamente la ruta del archivo ICC. |
| **Archivo no guardado** | `dataDir` apunta a una carpeta inexistente o no tiene permiso de escritura | Crea la carpeta previamente o elige una ubicación con permisos de escritura. |

## Preguntas frecuentes

**P:** *¿Puedo agregar varios rectángulos en un solo documento XPS?*  
R: Sí. Simplemente repite los pasos de creación de geometría y estilo para cada rectángulo que necesites.

**P:** *¿Cómo puedo cambiar el color de relleno del rectángulo en lugar del trazo?*  
R: Usa `path.setFill(...)` con un pincel de color sólido, similar a cómo se usa `setStroke`.

**P:** *¿Es Aspose.Page adecuado para manipulaciones complejas de documentos XPS?*  
R: Absolutamente. La biblioteca admite funciones avanzadas como degradados, transformaciones y fuentes incrustadas.

**P:** *¿Dónde puedo encontrar ejemplos adicionales y soporte de la comunidad?*  
R: Explora el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para más ejemplos de código y ayuda de la comunidad.

**P:** *¿Puedo probar Aspose.Page antes de comprar?*  
R: Sí, puedes explorar una [prueba gratuita](https://releases.aspose.com/) para evaluar las capacidades de la API.

**Última actualización:** 2026-04-24  
**Probado con:** Aspose.Page for Java 24.12  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}