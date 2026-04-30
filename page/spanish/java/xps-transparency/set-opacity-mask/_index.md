---
date: 2026-04-30
description: Aprende cómo crear documentos XPS en Java y agregar una máscara de opacidad
  usando Aspose.Page Java. Guía paso a paso con ejemplos de código.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Establecer máscara de opacidad en Java XPS
second_title: Aspose.Page Java API
title: Crear documento XPS en Java – Establecer máscara de opacidad con Aspose.Page
url: /es/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Establecer máscara de opacidad en Java XPS usando Aspose.Page Java

## Introducción
En este tutorial crearás **create XPS document Java** archivos y aprenderás cómo aplicar una máscara de opacidad que le da a tus gráficos un aspecto pulido y semi‑transparente. Recorreremos todo el proceso—desde inicializar un documento XPS, agregar un lienzo, dibujar un rectángulo, hasta adjuntar una máscara de opacidad basada en una imagen—usando la intuitiva API Aspose.Page Java. Al final, podrás generar archivos XPS profesionales de forma programática y reutilizar la máscara en cualquier forma que necesites.

## Respuestas rápidas
- **¿Qué hace una máscara de opacidad?** Define niveles de transparencia variables para una forma, permitiendo que el contenido subyacente se muestre.  
- **¿Qué biblioteca se requiere?** Aspose.Page for Java (aspose page java).  
- **¿Necesito una licencia?** Una licencia temporal funciona para pruebas; se requiere una licencia completa para producción.  
- **¿Cuántas líneas de código?** Aproximadamente 20 líneas de Java más algunas declaraciones de configuración.  
- **¿Puedo reutilizar la máscara en varias formas?** Sí, puedes asignar el mismo `ImageBrush` a varios caminos.

## ¿Qué es una máscara de opacidad en XPS?
Una máscara de opacidad es un mapa de bits o vector que controla el alfa (transparencia) de cada píxel en una forma. Cuando se aplica a un rectángulo, partes del rectángulo se vuelven totalmente opacas, parcialmente transparentes o totalmente transparentes, creando efectos visuales sofisticados sin capas de dibujo adicionales.

## ¿Por qué usar Aspose.Page Java para **create XPS document java**?
- **Pure Java API** – Sin dependencias nativas, por lo que el mismo código se ejecuta en Windows, Linux o macOS.  
- **Full XPS spec compliance** – Las máscaras se renderizan exactamente como lo define el estándar XPS.  
- **Object‑oriented design** – Similar a .NET, lo que facilita su adopción si has usado Aspose en otros lenguajes.  
- **High performance** – Optimizado para documentos grandes y procesamiento por lotes.

## Casos de uso comunes
- **Watermarking** – Aplica un logotipo semi‑transparente en todas las páginas.  
- **Dynamic theming** – Cambia el estilo visual de los elementos UI en los informes generados.  
- **Print‑ready previews** – Muestra cómo se verá un diseño con diferentes opacidades antes de enviarlo a la impresora.

## Requisitos previos
Antes de comenzar, asegúrate de tener:
- Una comprensión básica de la programación Java.  
- Biblioteca Aspose.Page for Java instalada. Puedes descargarla **[aquí](https://releases.aspose.com/page/java/)**.  
- Una licencia válida para Aspose.Page. Si no tienes una, obtén una licencia temporal **[aquí](https://purchase.aspose.com/temporary-license/)**.  
- Un entorno de desarrollo capaz de compilar y ejecutar aplicaciones Java (p.ej., IntelliJ IDEA, Eclipse o VS Code).

## Importar paquetes
Comienza importando las clases necesarias de la biblioteca Aspose.Page. Esto garantiza que la API esté disponible para tu proyecto.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Guía paso a paso

### Paso 1: Crear un nuevo documento XPS
Primero, instancia un nuevo documento XPS que contendrá todos nuestros gráficos.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Paso 2: Agregar un lienzo
Un lienzo actúa como superficie de dibujo dentro de la página XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Paso 3: Agregar un rectángulo y aplicar un relleno sólido
Aquí creamos una ruta de rectángulo y le damos un relleno rojo sólido. Este rectángulo recibirá más tarde la máscara de opacidad.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Paso 4: Agregar máscara de opacidad usando un ImageBrush
Cargamos una imagen TIFF, definimos los rectángulos de origen y destino, y configuramos el pincel en modo mosaico para que la máscara se repita si es necesario.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Paso 5: Guardar el documento XPS resultante
Finalmente, guarda el documento en disco. El archivo de salida contendrá el rectángulo con la máscara de opacidad aplicada.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Sigue estos pasos cuidadosamente para incorporar la funcionalidad **add opacity mask** en tu documento Java XPS usando Aspose.Page.

## Problemas comunes y solución de problemas
- **Image not found** – Verifica que `dataDir` apunte a la carpeta correcta y que `R08SY_NN.tif` exista.  
- **Mask appears solid** – Asegúrate de que la imagen de origen contenga valores alfa variables; una imagen totalmente opaca no mostrará transparencia.  
- **Tile mode not respected** – El rectángulo de destino debe ser más pequeño que el rectángulo de origen para que el mosaico sea perceptible.

## Preguntas frecuentes

**P: ¿Es Aspose.Page compatible con todos los entornos de desarrollo Java?**  
R: Sí, Aspose.Page está diseñado para funcionar sin problemas con varios IDEs y herramientas de compilación de Java.

**P: ¿Puedo usar Aspose.Page sin una licencia?**  
R: Aunque puedes evaluar la biblioteca con una licencia temporal, se requiere una licencia completa para uso en producción.

**P: ¿Hay limitaciones en la versión de prueba?**  
R: La versión de prueba puede imponer restricciones de tamaño o de funciones; consulta la documentación oficial para más detalles.

**P: ¿Cómo puedo obtener soporte para Aspose.Page?**  
R: Visita el **[foro de Aspose.Page](https://forum.aspose.com/c/page/39)** para ayuda de la comunidad o compra una licencia para asistencia premium.

**P: ¿Existe una garantía de devolución de dinero para Aspose.Page?**  
R: Consulta la **[página de compra](https://purchase.aspose.com/buy)** para información sobre políticas de reembolso.

---

**Última actualización:** 2026-04-30  
**Probado con:** Aspose.Page Java 24.11 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}