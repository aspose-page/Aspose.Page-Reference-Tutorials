---
date: 2026-01-02
description: Aprenda cómo agregar una máscara de opacidad a documentos XPS con Aspose.Page
  Java. Guía paso a paso para crear un rectángulo de máscara de opacidad y mejorar
  la calidad visual.
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: Establecer máscara de opacidad en Java XPS usando Aspose.Page Java
url: /es/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Establecer máscara de opacidad en Java XPS usando Aspose.Page Java

## Introducción
Bienvenido a nuestra guía completa sobre **aspose page java** máscaras de opacidad. En este tutorial aprenderá a crear un documento XPS, agregar un lienzo y aplicar una máscara de opacidad a un rectángulo, todo con la potente API Aspose.Page Java. Al final podrá agregar rectángulos con máscara de opacidad que le darán a sus archivos XPS un aspecto pulido y semitransparente.

## Respuestas rápidas
- **¿Qué hace una máscara de opacidad?** Define niveles de transparencia variables para una forma, permitiendo que el contenido subyacente se muestre.
- **¿Qué biblioteca se requiere?** Aspose.Page para Java (aspose page java).
- **¿Necesito una licencia?** Una licencia temporal funciona para pruebas; se requiere una licencia completa para producción.
- **¿Cuántas líneas de código?** Aproximadamente 20 líneas de Java más algunas declaraciones de configuración.
- **¿Puedo reutilizar la máscara en múltiples formas?** Sí, puede asignar el mismo ImageBrush a varios caminos.

## ¿Qué es una máscara de opacidad en XPS?
Una máscara de opacidad es un mapa de bits o vector que controla el alfa (transparencia) de cada píxel en una forma. Cuando se aplica a un rectángulo, partes del rectángulo se vuelven totalmente opacas, parcialmente transparentes o totalmente transparentes, creando efectos visuales sofisticados.

## ¿Por qué usar Aspose.Page Java para máscaras de opacidad?
- **API completa al estilo .NET en Java** – modelo de objetos intuitivo.
- **Sin dependencias externas** – funciona con Java puro.
- **Renderizado de alta fidelidad** – las máscaras se renderizan exactamente como en la especificación XPS.
- **Multiplataforma** – se ejecuta en Windows, Linux o macOS sin cambios.

## Requisitos previos
- Una comprensión básica de la programación Java.  
- Biblioteca Aspose.Page para Java instalada. Puede descargarla **[aquí](https://releases.aspose.com/page/java/)**.  
- Una licencia válida para Aspose.Page. Si no tiene una, obtenga una licencia temporal **[aquí](https://purchase.aspose.com/temporary-license/)**.  
- Un entorno de desarrollo capaz de compilar y ejecutar aplicaciones Java (p. ej., IntelliJ IDEA, Eclipse o VS Code).

## Importar paquetes
Comience importando las clases necesarias de la biblioteca Aspose.Page. Esto garantiza que la API esté disponible para su proyecto.

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
Primero, instancie un nuevo documento XPS que contendrá todos nuestros gráficos.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Paso 2: Agregar un lienzo
Un lienzo actúa como una superficie de dibujo dentro de la página XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Paso 3: Agregar un rectángulo y aplicar un relleno sólido
Aquí creamos una ruta de rectángulo y le damos un relleno rojo sólido. Este rectángulo recibirá más adelante la máscara de opacidad.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Paso 4: Agregar máscara de opacidad usando ImageBrush
Cargamos una imagen TIFF, definimos los rectángulos de origen y destino, y configuramos el pincel en modo mosaico para que la máscara se repita si es necesario.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Paso 5: Guardar el documento XPS resultante
Finalmente, guarde el documento en disco. El archivo de salida contendrá el rectángulo con la máscara de opacidad aplicada.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Siga estos pasos cuidadosamente para incorporar la funcionalidad de **add opacity mask** en su documento Java XPS usando Aspose.Page.

## Problemas comunes y solución de problemas
- **Imagen no encontrada** – Verifique que `dataDir` apunte a la carpeta correcta y que `R08SY_NN.tif` exista.
- **La máscara aparece sólida** – Asegúrese de que la imagen de origen contenga valores alfa variables; una imagen totalmente opaca no mostrará transparencia.
- **Modo mosaico no respetado** – El rectángulo de destino debe ser más pequeño que el rectángulo de origen para que el mosaico sea perceptible.

## Preguntas frecuentes

**Q: ¿Es Aspose.Page compatible con todos los entornos de desarrollo Java?**  
A: Sí, Aspose.Page está diseñado para funcionar sin problemas con varios IDEs y herramientas de compilación Java.

**Q: ¿Puedo usar Aspose.Page sin una licencia?**  
A: Aunque puede evaluar la biblioteca con una licencia temporal, se requiere una licencia completa para uso en producción.

**Q: ¿Hay limitaciones en la versión de prueba?**  
A: La versión de prueba puede imponer restricciones de tamaño o de funcionalidades; consulte la documentación oficial para más detalles.

**Q: ¿Cómo puedo obtener soporte para Aspose.Page?**  
A: Visite el **[foro de Aspose.Page](https://forum.aspose.com/c/page/39)** para ayuda de la comunidad o adquiera una licencia para asistencia premium.

**Q: ¿Existe una garantía de devolución de dinero para Aspose.Page?**  
A: Consulte la **[página de compra](https://purchase.aspose.com/buy)** para obtener información sobre las políticas de reembolso.

---

**Última actualización:** 2026-01-02  
**Probado con:** Aspose.Page Java 24.11 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}