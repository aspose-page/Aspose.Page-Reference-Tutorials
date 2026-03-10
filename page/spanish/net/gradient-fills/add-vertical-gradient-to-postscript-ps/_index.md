---
date: 2026-02-25
description: Aprenda cómo usar un pincel de degradado lineal en C# para añadir degradado
  a archivos PS y rellenar un rectángulo con degradado usando Aspose.Page para .NET.
linktitle: Add Vertical Gradient to PostScript (PS)
second_title: Aspose.Page .NET API
title: c# Pincel de Degradado Lineal – Añadir Degradado Vertical a PostScript (PS)
  con Aspose.Page
url: /es/net/gradient-fills/add-vertical-gradient-to-postscript-ps/
weight: 14
---

 final content.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# Linear Gradient Brush – Añadir Gradiente Vertical a PostScript (PS) con Aspose.Page

## Introducción

En el ámbito de la manipulación y creación de documentos, **Aspose.Page for .NET** se destaca como una herramienta poderosa para desarrolladores. En esta guía descubrirá cómo **añadir gradiente a archivos PS** utilizando un **C# linear gradient brush** para **rellenar un rectángulo con gradiente**. Al final de este tutorial, tendrá una comprensión clara, paso a paso, del código necesario y por qué esta técnica produce un gradiente vertical suave en su salida PostScript.

## Respuestas rápidas
- **¿Qué hace un C# linear gradient brush?** Crea una transición suave entre varios colores a lo largo de una forma.
- **¿Puedo usarlo con cualquier versión de .NET?** Sí, Aspose.Page soporta .NET Framework 4.5+ y .NET Core/5+.
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial para compilaciones que no sean de evaluación.
- **¿El gradiente es realmente vertical?** El pincel está rotado 90°, garantizando un flujo vertical.
- **¿Dónde se guarda la salida?** En la ruta que especifique en `dataDir` (p. ej., `VerticalGradient_outPS.ps`).

## ¿Qué es un C# Linear Gradient Brush?

Un **C# linear gradient brush** es un objeto GDI+ (`LinearGradientBrush`) que pinta una transición de color lineal entre puntos definidos. Cuando se combina con la API de dibujo de Aspose.Page, le permite renderizar gradientes sofisticados directamente en un documento PostScript (PS).

## ¿Por qué usar un Linear Gradient Brush para PostScript?

- **Salida de alta calidad:** Los gradientes se renderizan a nivel de impresora, preservando la fidelidad.
- **Control total:** Puede establecer puntos de color personalizados, rotación y escalado.
- **Código reutilizable:** La misma lógica del pincel funciona para PDF, SVG y otros formatos compatibles con Aspose.Page.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de contar con lo siguiente:

- Aspose.Page for .NET: Asegúrese de tener la biblioteca Aspose.Page instalada. Puede encontrar los recursos necesarios y la documentación [aquí](https://reference.aspose.com/page/net/).
- Entorno de desarrollo: Configure un entorno de desarrollo adecuado, incluido un Entorno de Desarrollo Integrado (IDE) para desarrollo .NET.
- Conocimientos básicos: Familiarícese con los conceptos básicos del desarrollo .NET, incluido el trabajo con flujos, rutas gráficas y manipulación de colores.

## Importar espacios de nombres

En su proyecto C#, incluya los espacios de nombres requeridos al inicio de su archivo de código:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

## Paso 1: Configurar el directorio del documento

Comience especificando la ruta a su directorio de documentos. Esta es la ubicación donde se guardará su documento PS.

```csharp
string dataDir = "Your Document Directory";
```

## Paso 2: Crear el flujo de salida para el documento PostScript

Genere un flujo de salida para el documento PostScript utilizando la clase `FileStream`.

```csharp
using (Stream outPsStream = new FileStream(dataDir + "VerticalGradient_outPS.ps", FileMode.Create))
```

## Paso 3: Crear opciones de guardado y documento PS

Cree opciones de guardado con tamaño A4 e inicialice un nuevo documento PS de 1 página.

```csharp
PsSaveOptions options = new PsSaveOptions();
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Paso 4: Definir dimensiones del rectángulo

Especifique las dimensiones y la posición del rectángulo donde se aplicará el gradiente vertical.

```csharp
float offsetX = 200;
float offsetY = 100;
float width = 200;
float height = 100;
```

## Paso 5: Crear ruta gráfica

Construya una ruta gráfica a partir del rectángulo definido.

```csharp
GraphicsPath path = new GraphicsPath();
path.AddRectangle(new RectangleF(offsetX, offsetY, width, height));
```

## Paso 6: Definir colores de interpolación

Establezca una matriz de colores de interpolación y posiciones para el gradiente.

```csharp
Color[] colors = { Color.Red, Color.Green, Color.Blue, Color.Orange, Color.DarkOliveGreen };
float[] positions = { 0.0f, 0.1873f, 0.492f, 0.734f, 1.0f };
ColorBlend colorBlend = new ColorBlend();
colorBlend.Colors = colors;
colorBlend.Positions = positions;
```

## Paso 7: Crear Linear Gradient Brush

Forme un linear gradient brush con el rectángulo como límites, colores de inicio y fin.

```csharp
LinearGradientBrush brush = new LinearGradientBrush(new RectangleF(0, 0, width, height), Color.Beige, Color.DodgerBlue, 0f);
brush.InterpolationColors = colorBlend;
```

## Paso 8: Establecer la transformación del pincel

Establezca una transformación para el pincel, asegurándose de que los componentes de escala X e Y coincidan con el ancho y la altura del rectángulo.

```csharp
Matrix brushTransform = new Matrix(width, 0, 0, height, offsetX, offsetY);
brushTransform.Rotate(90);
brush.Transform = brushTransform;
```

## Paso 9: Establecer la pintura y rellenar el rectángulo

Establezca la pintura para el documento y **rellene el rectángulo con gradiente** usando la ruta definida previamente.

```csharp
document.SetPaint(brush);
document.Fill(path);
```

## Paso 10: Cerrar la página actual y guardar el documento

Cierre la página actual y guarde el documento PostScript.

```csharp
document.ClosePage();
document.Save();
```

¡Felicidades! Ha añadido con éxito **un gradiente vertical a un documento PostScript** utilizando un **C# linear gradient brush** con Aspose.Page for .NET. Experimente con diferentes parámetros y colores para lograr varios efectos visuales en sus documentos.

## Problemas comunes y soluciones

| Problema | Por qué ocurre | Cómo solucionarlo |
|----------|----------------|-------------------|
| El gradiente aparece horizontal | Rotación del pincel no aplicada | Asegúrese de que `brushTransform.Rotate(90);` se llame antes de asignar a `brush.Transform`. |
| Los colores se ven deslavados | Flujo de salida de baja resolución | Utilice un `PsSaveOptions` de mayor resolución o aumente el tamaño del documento. |
| El archivo de salida está vacío | Flujo no vaciado | Verifique que `document.Save();` se llame fuera del bloque `using`. |

## Preguntas frecuentes

**Q1: ¿Puedo aplicar múltiples gradientes a diferentes regiones del mismo documento?**  
A: Sí, puede. Simplemente repita los pasos para cada región con sus dimensiones y esquema de colores específicos.

**Q2: ¿Cómo puedo integrar este código en mi proyecto .NET existente?**  
A: Copie y pegue el código en su archivo de proyecto y asegúrese de que la biblioteca Aspose.Page esté referenciada.

**Q3: ¿Hay otros tipos de gradiente disponibles en Aspose.Page para .NET?**  
A: Aspose.Page soporta varios tipos de gradiente, incluidos radiales y de ruta. Consulte la documentación para más detalles.

**Q4: ¿Puedo usar Aspose.Page para proyectos comerciales?**  
A: Sí, puede. Visite [aquí](https://purchase.aspose.com/buy) para explorar opciones de licencia.

**Q5: ¿Existe un foro comunitario para Aspose.Page donde pueda buscar ayuda?**  
A: ¡Por supuesto! Diríjase al [foro de Aspose.Page](https://forum.aspose.com/c/page/39) para conectar con otros desarrolladores y obtener asistencia.

**Última actualización:** 2026-02-25  
**Probado con:** Aspose.Page 24.11 for .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}