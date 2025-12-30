---
date: 2025-12-30
description: Aprende a crear documentos XPS en Java añadiendo rectángulos con Aspose.Page.
  Sigue esta guía paso a paso para una manipulación fluida de documentos XPS.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: Crear documento XPS en Java – Añadir rectángulo con Aspose.Page
url: /es/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Crear documento XPS Java – Añadir rectángulo

## Introducción
En este tutorial exhaustivo **creará documentos XPS Java** y aprenderá a añadir rectángulos usando la biblioteca Aspose.Page. Ya sea que esté creando informes, facturas o gráficos personalizados, dominar la creación de rectángulos le brinda un control preciso sobre el diseño XPS. Recorreremos cada paso, explicaremos el porqué de cada línea de código y le mostraremos cómo personalizar colores y trazos para obtener resultados profesionales.

## Respuestas rápidas
- **¿Qué biblioteca se recomienda?** Aspose.Page para Java  
- **¿Cuánto tiempo lleva la implementación?** Aproximadamente 10 minutos para un rectángulo básico  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia comercial para producción  
- **¿Qué versión de Java es compatible?** Java 8 y posteriores  
- **¿Puedo añadir múltiples formas?** Sí – repita los pasos para cada forma

## Requisitos previos
Antes de comenzar, asegúrese de tener:

- Conocimientos básicos del lenguaje de programación Java.  
- Biblioteca Aspose.Page instalada. Si no la tiene, puede descargarla desde la [documentación de Aspose.Page Java](https://reference.aspose.com/page/java/).  
- Un entorno de desarrollo Java funcional (IDE, JDK y Maven/Gradle si lo prefiere).

## Importar paquetes
Para comenzar, importe los paquetes necesarios en su proyecto Java. Asegúrese de que la biblioteca Aspose.Page esté correctamente añadida a su classpath. Aquí hay un ejemplo básico:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Ahora, desglosaremos el ejemplo proporcionado en varios pasos para añadir un rectángulo en Java XPS.

## Paso 1: Establecer el directorio del documento
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

Reemplace `"Your Document Directory"` con la ruta a la carpeta donde desea almacenar los archivos XPS.

## Paso 2: Crear un nuevo documento XPS
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Esta línea **crea** un documento XPS nuevo que podrá poblar más adelante con formas, texto o imágenes.

## Paso 3: Añadir un rectángulo con trazo de color sólido CMYK
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

Este paso añade un rectángulo con trazo de color sólido CMYK. Puede cambiar la cadena de geometría (`"M 20,10 L 220,10 220,100 20,100 Z"`) para modificar el tamaño o la posición, y ajustar los valores de color en `createColor` según su diseño.

## Paso 4: Guardar el documento XPS resultante
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Finalmente, guarde el documento XPS modificado con el rectángulo añadido en el directorio que especificó anteriormente.

## Casos de uso comunes
- **Encabezados de informes** – Use rectángulos como bloques de fondo para títulos.  
- **Tablas de facturas** – Resalte celdas o secciones con bordes de color.  
- **Gráficos personalizados** – Combine varios rectángulos para crear formas complejas.

## Consejos de solución de problemas
- **Error de archivo no encontrado:** Verifique que `dataDir` apunte a una carpeta existente y que el perfil ICC (`uswebuncoated.icc`) esté presente.  
- **Colores incorrectos:** Asegúrese de que el perfil ICC coincida con el espacio de color que desea usar (CMYK vs. RGB).  
- **Dimensiones inesperadas:** Ajuste la cadena de geometría para reflejar las coordenadas correctas.

## Conclusión
¡Felicidades! Ha aprendido con éxito a **crear documentos XPS Java** y a añadir rectángulos usando Aspose.Page. Esta base le permite crear documentos XPS más ricos, personalizar gráficos e integrar formas en flujos de trabajo más amplios.

## Preguntas frecuentes
### ¿Puedo añadir varios rectángulos en un solo documento XPS?
Sí, puede añadir tantos rectángulos como necesite repitiendo los pasos descritos en el tutorial.

### ¿Cómo puedo cambiar el color del rectángulo?
Modifique los valores de color en el método `createColor` para obtener el color deseado.

### ¿Es Aspose.Page adecuado para manejar manipulaciones complejas de documentos XPS?
¡Absolutamente! Aspose.Page ofrece un conjunto robusto de funciones para gestionar diversas tareas con documentos XPS.

### ¿Dónde puedo encontrar ejemplos adicionales y soporte?
Explore el [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para más ejemplos y solicite ayuda a la comunidad.

### ¿Puedo probar Aspose.Page antes de comprar?
Sí, puede explorar una [prueba gratuita](https://releases.aspose.com/) para experimentar las capacidades de Aspose.Page.

## Preguntas frecuentes

**P: ¿Este enfoque funciona con Java 11 o versiones más nuevas?**  
R: Sí, la biblioteca Aspose.Page es compatible con Java 8 y posteriores, incluyendo Java 11, 17 y versiones posteriores.

**P: ¿Puedo incrustar imágenes dentro del área del rectángulo?**  
R: Puede añadir un elemento `XpsImage` y posicionarlo sobre o dentro del rectángulo usando las mismas coordenadas de geometría.

**P: ¿Cómo establezco un color de relleno en lugar de solo un trazo?**  
R: Llame a `path.setFill(...)` con un pincel de color sólido creado mediante `doc.createSolidColorBrush(...)`.

**P: ¿Es posible rotar el rectángulo?**  
R: Aplique una matriz de transformación al path usando `path.setTransform(...)` para lograr rotación o escalado.

**P: ¿Qué licencia se requiere para uso en producción?**  
R: Se requiere una licencia comercial de Aspose.Page para despliegue; la prueba gratuita está limitada a evaluación y desarrollo.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2025-12-30  
**Probado con:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose  

---