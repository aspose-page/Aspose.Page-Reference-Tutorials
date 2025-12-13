---
date: 2025-12-13
description: Aprende cómo agregar texto en una página ASP con Java, establecer el
  estilo de fuente en Java y cómo añadir texto Unicode usando Aspose.Page. Sigue nuestra
  guía paso a paso.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: página asp añadir texto – Unicode en Java PostScript
url: /es/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# asp page add text – Unicode en Java PostScript

## Introducción
Si necesitas **asp page add text** en un flujo de trabajo Java PostScript mientras preservas caracteres Unicode, has llegado al lugar correcto. En este tutorial recorreremos cómo agregar texto Unicode, establecer el estilo de fuente y guardar el resultado usando **Aspose.Page for Java**. Al final comprenderás cómo establecer font style java y cómo agregar texto unicode de manera eficiente en tus proyectos.

## Respuestas rápidas
- **¿Qué biblioteca puede agregar texto Unicode en Java PostScript?** Aspose.Page for Java.  
- **¿Qué método principal agrega texto?** `doc.addGlyphs(...)` con un objeto `XpsGlyphs`.  
- **¿Necesito una fuente especial para Unicode?** Cualquier fuente TrueType/OpenType que soporte los puntos de código requeridos (p. ej., Arial).  
- **¿Puedo cambiar el estilo de fuente?** Sí, usando `XpsFontStyle` (Regular, Bold, Italic, etc.).  
- **¿Se requiere una licencia para producción?** Sí, se necesita una licencia válida de Aspose.Page para uso que no sea de prueba.

## ¿Qué es asp page add text?
`asp page add text` se refiere al proceso de insertar cadenas de texto en un documento PostScript o XPS usando la API de Aspose.Page. La API abstrae los comandos de PostScript de bajo nivel, permitiéndote trabajar con objetos de alto nivel como `XpsGlyphs`.

## ¿Por qué usar Aspose.Page para set font style java y agregar texto Unicode?
- **Soporte completo de Unicode** – Maneja escrituras de derecha a izquierda y glifos complejos.  
- **API simple** – Llamadas de una sola línea para agregar texto y aplicar estilos.  
- **Multiplataforma** – Funciona en cualquier entorno compatible con Java.  
- **Sin dependencias externas** – No se necesita motores de renderizado adicionales.

## Requisitos previos
Antes de sumergirnos en el tutorial, asegúrate de contar con los siguientes requisitos:

1. **Java Development Kit (JDK)** – Asegúrate de que Java esté instalado en tu máquina.  
2. **Aspose.Page for Java** – Descarga e instala la biblioteca Aspose.Page desde el [download link](https://releases.aspose.com/page/java/).  
3. **Entorno de Desarrollo Integrado (IDE)** – Elige tu IDE Java preferido, como IntelliJ IDEA o Eclipse.

## Importar paquetes
En tu proyecto Java, importa los paquetes necesarios para Aspose.Page. Añade las siguientes líneas a tu código:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Paso 1: Configura tu proyecto
Crea un nuevo proyecto Java en tu IDE y configura la estructura del proyecto. Asegúrate de incluir la biblioteca Aspose.Page en las dependencias de tu proyecto.

## Paso 2: Inicializa el documento XPS
Comienza inicializando un nuevo documento XPS dentro de tu proyecto:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Paso 3: Agregar texto Unicode
Ahora, agreguemos texto Unicode a tu documento XPS usando la biblioteca Aspose.Page. Utiliza el siguiente fragmento de código:

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

Este segmento de código agrega el texto Unicode **"AVAJ rof SPX.esopsA"** al documento XPS en las coordenadas (400, 200) con la fuente y estilo especificados. Observa cómo la llamada `setBidiLevel(1)` habilita el renderizado de derecha a izquierda para una visualización Unicode correcta.

## Paso 4: Guardar el documento
Guarda el documento XPS resultante usando el siguiente código:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

## Conclusión
¡Felicidades! Has realizado con éxito **asp page add text** y establecido el estilo de fuente en un escenario Java PostScript usando Aspose.Page. Este método te brinda un control detallado sobre el renderizado y estilo Unicode, lo que lo hace ideal para informes, facturas y gráficos internacionalizados.

Siéntete libre de explorar más funciones y capacidades de Aspose.Page en la [documentation](https://reference.aspose.com/page/java/).

## Preguntas frecuentes

**Q:** ¿Puedo usar Aspose.Page for Java con otros lenguajes de programación?  
**A:** Aspose.Page está diseñado principalmente para Java, pero Aspose ofrece bibliotecas para varios lenguajes de programación.

**Q:** ¿Hay una prueba gratuita disponible?  
**A:** Sí, puedes acceder a una prueba gratuita de Aspose.Page [aquí](https://releases.aspose.com/).

**Q:** ¿Dónde puedo encontrar soporte y discusiones sobre Aspose.Page?  
**A:** Visita el [Aspose.Page forum](https://forum.aspose.com/c/page/39) para soporte y discusiones.

**Q:** ¿Cómo puedo obtener una licencia temporal para Aspose.Page?  
**A:** Puedes adquirir una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

Q:** ¿Cuáles son los estilos de fuente disponibles en Aspose.Page?  
**A:** Aspose.Page admite estilos de fuente como Regular, Bold, Italic y BoldItalic.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última actualización:** 2025-12-13  
**Probado con:** Aspose.Page for Java (latest)  
**Autor:** Aspose  

---