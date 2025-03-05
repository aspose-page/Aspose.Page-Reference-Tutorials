---
title: Agregue rectángulo a PostScript (PS) con Aspose.Page para .NET
linktitle: Agregar rectángulo a PostScript (PS)
second_title: Aspose.Página .NET API
description: Mejore la creación de documentos en .NET con Aspose.Page. Aprenda a agregar rectángulos a archivos PostScript (PS) paso a paso.
type: docs
weight: 12
url: /es/net/drawing-shapes/add-rectangle-to-postscript-ps/
---
## Introducción

Si busca mejorar sus capacidades de creación de documentos en .NET, Aspose.Page proporciona una poderosa solución para manejar documentos PostScript. En este tutorial, lo guiaremos a través del proceso de agregar rectángulos a un documento PostScript usando Aspose.Page para .NET.

## Requisitos previos

Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

-  Aspose.Page para la biblioteca .NET: descargue e instale la biblioteca Aspose.Page para .NET desde[aquí](https://releases.aspose.com/page/net/).

- Entorno de desarrollo: asegúrese de tener un entorno de desarrollo .NET configurado en su máquina.

## Importar espacios de nombres

Antes de comenzar a codificar, asegúrese de importar los espacios de nombres necesarios para acceder a las clases y métodos requeridos:

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Ahora, dividamos el ejemplo en varios pasos:

## Paso 1: configure su directorio de documentos

```csharp
// ExInicio:1
// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";
```

En este paso, reemplace "Su directorio de documentos" con la ruta donde desea guardar su documento PostScript.

## Paso 2: crear un flujo de salida para un documento PostScript

```csharp
//Crear flujo de salida para un documento PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddRectangle_outPS.ps", FileMode.Create))
```

Aquí, creamos una secuencia de salida para el documento PostScript y especificamos el nombre del archivo ("AddRectangle_outPS.ps"). Ajuste el nombre del archivo y la ubicación según sus preferencias.

## Paso 3: configurar las opciones de guardar y crear un documento PS

```csharp
//Crea opciones de guardado con tamaño A4
PsSaveOptions options = new PsSaveOptions();

// Crear un nuevo documento PS de 1 página
PsDocument document = new PsDocument(outPsStream, options, false);
```

Configure las opciones de guardado, especificando el tamaño de página deseado (A4 en este caso). Luego, cree un nuevo documento PostScript de una sola página.

## Paso 4: agregar rectángulo y rellenar

```csharp
//Crear ruta de gráficos desde el primer rectángulo
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 100, 150, 100));

//Establecer pintura
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));

//Rellena el rectángulo
document.Fill(path);
```

Aquí, creamos una ruta de gráficos que representa el primer rectángulo, configuramos el color de pintura (en este caso, naranja) y rellenamos el rectángulo.

## Paso 5: agregue otro rectángulo y trazo

```csharp
//Crear ruta de gráficos desde el segundo rectángulo.
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddRectangle(new System.Drawing.RectangleF(250, 300, 150, 100));

//Establecer trazo
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));

//Traza (delinea) el rectángulo
document.Draw(path);
```

De manera similar al paso anterior, creamos una ruta gráfica para el segundo rectángulo, configuramos el color del trazo (rojo con un grosor de 3) y delineamos el rectángulo.

## Paso 6: cierre la página y guarde el documento

```csharp
//Cerrar la página actual
document.ClosePage();

//guardar el documento
document.Save();
```

Finalmente, cierre la página actual y guarde el documento completo.

## Conclusión

¡Felicidades! Ha agregado rectángulos con éxito a un documento PostScript usando Aspose.Page para .NET. Este tutorial cubrió los pasos esenciales, desde configurar su entorno de desarrollo hasta guardar el documento final.

## Preguntas frecuentes

### P1: ¿Puedo personalizar los colores de los rectángulos?

R1: Sí, puede personalizar los colores ajustando los parámetros en el`SolidBrush` y`Pen` clases.

### P2: ¿Aspose.Page es compatible con otros formatos de documentos?

R2: Sí, Aspose.Page admite varios formatos de documentos, incluidos XPS y PostScript.

### P3: ¿Cómo puedo agregar texto al documento?

 A3: Puedes usar el`TextFragment` clase en Aspose.Page para agregar texto a su documento.

### P4: ¿Dónde puedo encontrar ejemplos y documentación adicionales?

 A4: Explore la documentación[aquí](https://reference.aspose.com/page/net/) y visitar el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para el apoyo de la comunidad.

### P5: ¿Puedo probar Aspose.Page antes de comprar?

 R5: Sí, puedes obtener una versión de prueba gratuita[aquí](https://releases.aspose.com/) , y para uso prolongado, considere un[licencia temporal](https://purchase.aspose.com/temporary-license/).
