---
date: 2025-12-17
description: Aprende cómo agregar texto Unicode en Java PostScript usando Aspose.Page
  – una guía paso a paso sobre cómo añadir cadenas Unicode sin esfuerzo.
linktitle: Add Text using Unicode String in Java PostScript
second_title: Aspose.Page Java API
title: Cómo agregar texto Unicode en Java PostScript con Aspose.Page
url: /es/java/postscript-text-manipulation/add-text-unicode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo agregar texto Unicode en Java PostScript con Aspose.Page

## Introducción
Si te preguntas **cómo agregar caracteres Unicode** a un flujo de trabajo PostScript (o XPS) basado en Java, has llegado al lugar correcto. En este tutorial recorreremos paso a paso los pasos exactos necesarios para incrustar cadenas Unicode usando la biblioteca Aspose.Page para Java. Al final de la guía podrás insertar texto específico de cualquier idioma —árabe, chino, emojis, lo que sea— directamente en tu salida PostScript.

## Respuestas rápidas
- **¿Qué biblioteca se necesita?** Aspose.Page for Java  
- **¿Puedo agregar scripts de derecha a izquierda?** Sí, establece el nivel Bidi como se muestra en el código  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita sirve para pruebas; se requiere una licencia comercial para producción  
- **¿Qué IDE funciona mejor?** Cualquier IDE de Java (IntelliJ IDEA, Eclipse, NetBeans)  
- **¿El código es multiplataforma?** Absolutamente—funciona en Windows, macOS o Linux

## ¿Qué significa “cómo agregar Unicode” en el contexto de PostScript?
Agregar Unicode significa insertar caracteres que están representados por puntos de código más allá del rango ASCII básico. Aspose.Page abstrae los detalles de codificación de bajo nivel, permitiéndote centrarte en el contenido del texto y su ubicación visual.

## ¿Por qué usar Aspose.Page para texto Unicode?
- **Soporte completo de Unicode** – Maneja scripts complejos, ligaduras y lenguas de derecha a izquierda.  
- **Sin dependencias externas** – No es necesario gestionar archivos de fuentes manualmente; la API funciona con fuentes del sistema.  
- **API sencilla** – Unas pocas llamadas a métodos son suficientes para renderizar texto multilingüe.

## Requisitos previos
Antes de profundizar, asegúrate de tener lo siguiente listo:

1. **Java Development Kit (JDK)** – Cualquier versión reciente (8 o superior).  
2. **Aspose.Page for Java** – Descarga e instala la biblioteca desde el [download link](https://releases.aspose.com/page/java/).  
3. **IDE de tu elección** – IntelliJ IDEA, Eclipse, o cualquier otro IDE de Java que prefieras.

## Importar paquetes
Agrega las clases necesarias de Aspose.Page a tu archivo fuente Java:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsFontStyle;
import com.aspose.xps.XpsGlyphs;
import com.aspose.xps.XpsSolidColorBrush;
import java.awt.Color;
```

## Paso 1: Configurar su proyecto
Crea un nuevo proyecto Java, añade el JAR de Aspose.Page a la ruta de compilación del proyecto y crea una carpeta donde se guardará el archivo XPS generado. Esta carpeta se referencia más adelante como `dataDir`.

## Paso 2: Inicializar documento XPS
Instancia un documento XPS vacío que contendrá el contenido:

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

## Paso 3: Agregar texto Unicode
Ahora realmente agregaremos la cadena Unicode. El ejemplo a continuación escribe la frase invertida “AVAJ rof SPX.esopsA”, que contiene solo caracteres ASCII, pero puedes reemplazarla con cualquier texto Unicode (p. ej., árabe “مرحبا” o chino “你好”).

```java
XpsSolidColorBrush textFill = doc.createSolidColorBrush(Color.BLACK);
XpsGlyphs glyphs = doc.addGlyphs("Arial", 20, XpsFontStyle.Regular, 400f, 200f, "AVAJ rof SPX.esopsA");
glyphs.setBidiLevel(1);
glyphs.setFill(textFill);
```

> **Consejo:** Para renderizar correctamente lenguas de derecha a izquierda, establece `glyphs.setBidiLevel(1);`. Para scripts de izquierda a derecha puedes omitir esta línea.

## Paso 4: Guardar el documento
Persistir el archivo XPS en disco:

```java
doc.save(dataDir + "AddEncodingText_out.xps");
```

Después de ejecutar el programa, abre el `AddEncodingText_out.xps` generado con cualquier visor XPS para ver el texto Unicode renderizado en las coordenadas especificadas.

## Problemas comunes y soluciones
| Problema | Razón | Solución |
|----------|-------|----------|
| El texto aparece como cuadros | Fuente no encontrada o no soporta los caracteres | Utilice una fuente que incluya los glifos necesarios (p.ej., “Arial Unicode MS”) |
| El texto de derecha a izquierda se muestra de izquierda a derecha | Nivel Bidi no configurado | Llame a `glyphs.setBidiLevel(1);` |
| Archivo no guardado | Ruta `dataDir` inválida o faltan permisos de escritura | Asegúrese de que el directorio exista y la aplicación tenga permisos de escritura |

## Preguntas frecuentes
### ¿Puedo usar Aspose.Page para Java con otros lenguajes de programación?
Aspose.Page está diseñado principalmente para Java, pero Aspose ofrece bibliotecas para varios lenguajes de programación.

### ¿Hay una versión de prueba gratuita disponible?
Sí, puedes acceder a una prueba gratuita de Aspose.Page [aquí](https://releases.aspose.com/).

### ¿Dónde puedo encontrar soporte y discusiones sobre Aspose.Page?
Visita el [Aspose.Page forum](https://forum.aspose.com/c/page/39) para soporte y discusiones.

### ¿Cómo puedo obtener una licencia temporal para Aspose.Page?
Puedes adquirir una licencia temporal [aquí](https://purchase.aspose.com/temporary-license/).

### ¿Cuáles son los estilos de fuente disponibles en Aspose.Page?
Aspose.Page soporta estilos de fuente como Regular, Bold, Italic y BoldItalic.

## Conclusión
Ahora dominas **cómo agregar texto Unicode** a un documento Java PostScript (XPS) usando Aspose.Page. Esta capacidad abre la puerta a informes multilingües, facturas internacionalizadas y cualquier escenario donde se requieran caracteres no ASCII. Siéntete libre de explorar características adicionales como rotación de texto, rutas de recorte o incrustación de fuentes personalizadas—los detalles están disponibles en la documentación oficial [documentation](https://reference.aspose.com/page/java/).

---

**Última actualización:** 2025-12-17  
**Probado con:** Aspose.Page for Java 23.12 (latest at time of writing)  
**Autor:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
