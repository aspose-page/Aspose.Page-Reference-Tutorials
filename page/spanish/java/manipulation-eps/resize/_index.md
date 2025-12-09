---
date: 2025-12-02
description: Aprenda a cambiar el tamaño de archivos EPS en Java sin esfuerzo con
  Aspose.Page. Esta guía paso a paso le muestra cómo redimensionar EPS usando puntos,
  pulgadas, milímetros o porcentajes.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Cómo redimensionar archivos EPS en Java con Aspose.Page
url: /es/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo redimensionar archivos EPS en Java con Aspose.Page

## Introducción
Si buscas una forma fiable **de redimensionar EPS** programáticamente, has llegado al lugar correcto. En este tutorial recorreremos el proceso de redimensionar imágenes EPS en Java usando la biblioteca Aspose.Page. Ya sea que necesites duplicar el tamaño, reducirlo a una medida específica o trabajar con porcentajes, los pasos a continuación te dan control total sobre las dimensiones de salida.

## Respuestas rápidas
- **¿Qué biblioteca se necesita?** Aspose.Page for Java  
- **¿Puedo redimensionar usando puntos, pulgadas o milímetros?** Sí – la API admite las tres unidades más los porcentajes.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; se requiere una licencia para producción.  
- **¿Qué versión de Java se requiere?** Java 8 o posterior.  
- **¿El código es seguro para subprocesos?** Cada instancia de `PsDocument` está aislada, por lo que puedes procesar archivos en paralelo.

## Requisitos previos
Antes de sumergirnos en el código, asegúrate de contar con lo siguiente:

- Java Development Kit (JDK) instalado en tu máquina.  
- Biblioteca Aspose.Page for Java. Puedes descargarla **[here](https://releases.aspose.com/page/java/)**.  
- Un conocimiento básico de programación en Java.  

## Importar paquetes
En tu proyecto Java, incluye las importaciones necesarias para trabajar con objetos de Aspose.Page y flujos de E/S estándar.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Cómo redimensionar EPS usando puntos
A continuación se muestra un ejemplo completo, paso a paso, que duplica el tamaño de un archivo EPS usando puntos como unidad de medida.

### Paso 1: Configurar el flujo de entrada
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Paso 2: Inicializar el objeto `PsDocument`
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Paso 3: Extraer el tamaño actual de la imagen EPS
```java
Dimension oldSize = doc.extractEpsSize();
```

### Paso 4: Crear un flujo de salida para el archivo redimensionado
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Paso 5: Redimensionar y guardar el EPS usando puntos
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Cómo redimensionar EPS usando pulgadas
El mismo patrón de cinco pasos se aplica; simplemente reemplaza `Units.Points` por `Units.Inches` y ajusta el factor de escala según sea necesario.

## Cómo redimensionar EPS usando milímetros
Nuevamente, sigue los mismos pasos, cambiando la unidad a `Units.Millimeters`. Esto es útil cuando necesitas dimensiones métricas para flujos de trabajo de impresión.

## Cómo redimensionar EPS usando porcentajes
Para escalado basado en porcentajes, mantén la unidad como `Units.Percent`. Multiplica el ancho y alto originales por el porcentaje deseado (p. ej., `0.5` para una reducción del 50 %).

## Problemas comunes y consejos
- **Siempre cierra los flujos** – En código de producción, envuelve los flujos en try‑with‑resources para evitar bloqueos de archivos.  
- **Preserva la relación de aspecto** – Multiplica tanto el ancho como el alto por el mismo factor, a menos que intencionalmente quieras distorsionar.  
- **Verifica el DPI** – Redimensionar no cambia el DPI; si necesitas un DPI diferente, ajústalo por separado después de redimensionar.

## Conclusión
Ahora sabes **cómo redimensionar EPS** en Java usando Aspose.Page, ya sea que prefieras puntos, pulgadas, milímetros o porcentajes. Esta flexibilidad te permite integrar la manipulación de EPS en pipelines automatizados, utilidades de escritorio o servicios del lado del servidor.

## Preguntas frecuentes

**Q: ¿Puedo usar esta biblioteca para otros formatos de imagen?**  
A: No, Aspose.Page está especializada solo en archivos PostScript y EPS.

**Q: ¿Hay una prueba gratuita disponible para Aspose.Page for Java?**  
A: Sí, puedes explorar la prueba gratuita **[here](https://releases.aspose.com/)**.

**Q: ¿Dónde puedo encontrar ayuda adicional y discusiones?**  
A: Visita el **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** para soporte de la comunidad.

**Q: ¿Cómo puedo obtener una licencia temporal?**  
A: Puedes obtener una licencia temporal **[here](https://purchase.aspose.com/temporary-license/)**.

**Q: ¿Hay proyectos de ejemplo disponibles?**  
A: Sí, consulta la documentación **[here](https://reference.aspose.com/page/java/)**.

---

**Última actualización:** 2025-12-02  
**Probado con:** Aspose.Page for Java 24.12 (última versión al momento de escribir)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}