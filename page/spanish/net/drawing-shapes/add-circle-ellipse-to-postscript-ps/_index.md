---
title: Agregue una elipse circular a PostScript (PS) con Aspose.Page
linktitle: Agregar círculo elipse a PostScript (PS)
second_title: Aspose.Página .NET API
description: Aprenda cómo agregar elipses circulares sin esfuerzo a documentos PostScript (PS) usando Aspose.Page para .NET. Siga nuestra guía paso a paso para una integración perfecta.
weight: 10
url: /es/net/drawing-shapes/add-circle-ellipse-to-postscript-ps/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregue una elipse circular a PostScript (PS) con Aspose.Page

## Introducción

Bienvenido a este completo tutorial sobre cómo agregar elipses circulares a documentos PostScript (PS) usando Aspose.Page para .NET. Aspose.Page es una potente biblioteca que permite a los desarrolladores trabajar con PostScript y otros formatos de documentos sin problemas. En esta guía, lo guiaremos a través del proceso de incorporar fácilmente elipses circulares en sus documentos PS.

## Requisitos previos

Antes de sumergirnos en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

1.  Aspose.Page para la biblioteca .NET: descargue e instale la biblioteca Aspose.Page para .NET desde[aquí](https://releases.aspose.com/page/net/).

2. Entorno de desarrollo: asegúrese de tener un entorno de desarrollo .NET funcional configurado en su máquina.

Ahora comencemos con la guía paso a paso.

## Importar espacios de nombres

En el primer paso, debe importar los espacios de nombres necesarios para que la funcionalidad Aspose.Page esté disponible en su código.

```csharp
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
```

Ahora, dividamos el ejemplo proporcionado en varios pasos para guiarlo a través del proceso de agregar elipses circulares a un documento PostScript.

## Paso 1: configurar el directorio de documentos

```csharp
// ExInicio:1
// La ruta al directorio de documentos.
string dataDir = "Your Document Directory";
```

Asegúrese de reemplazar "Su directorio de documentos" con la ruta real a su directorio de documentos.

## Paso 2: crear un flujo de salida para un documento PostScript

```csharp
//Crear flujo de salida para un documento PostScript
using (Stream outPsStream = new FileStream(dataDir + "AddEllipse_outPS.ps", FileMode.Create))
```

Aquí, se crea un FileStream para escribir el documento PostScript y el modo de archivo se configura para crear un nuevo archivo.

## Paso 3: cree opciones de guardado y documento PS

```csharp
//Crea opciones de guardado con tamaño A4
PsSaveOptions options = new PsSaveOptions();

// Crear un nuevo documento PS de 1 página
PsDocument document = new PsDocument(outPsStream, options, false);
```

Este paso implica crear opciones de guardado con tamaño A4 e inicializar un nuevo documento PS de 1 página.

## Paso 4: cree una ruta de gráficos para la primera elipse

```csharp
//Crear ruta de gráficos desde la primera elipse
System.Drawing.Drawing2D.GraphicsPath path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 100, 150, 100));
```

Se crea una ruta gráfica para la primera elipse, especificando su posición y dimensiones.

## Paso 5: configure la pintura y rellene la elipse

```csharp
//Establecer pintura
document.SetPaint(new System.Drawing.SolidBrush(Color.Orange));
//Llena la elipse
document.Fill(path);
```

Aquí se establece la pintura y la primera elipse se rellena con el color especificado.

## Paso 6: cree una ruta de gráficos para la segunda elipse

```csharp
//Crear ruta de gráficos desde la segunda elipse
path = new System.Drawing.Drawing2D.GraphicsPath();
path.AddEllipse(new System.Drawing.RectangleF(250, 300, 150, 100));
```

De manera similar, se crea una ruta gráfica para la segunda elipse, definiendo su posición y dimensiones.

## Paso 7: establece el trazo y dibuja la elipse

```csharp
//Establecer trazo
document.SetStroke(new System.Drawing.Pen(new System.Drawing.SolidBrush(Color.Red), 3));
//Traza (delinea) la elipse
document.Draw(path);
```

En este paso, se establece el trazo y se delinea la segunda elipse con el color y el grosor de línea especificados.

## Paso 8: cierre la página actual y guarde el documento

```csharp
//Cerrar la página actual
document.ClosePage();

//guardar el documento
document.Save();
```

Finalmente, se cierra la página actual y se guarda el documento completo, completando el proceso.

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo agregar elipses circulares a documentos PostScript usando Aspose.Page para .NET. Este tutorial proporciona una guía detallada paso a paso para ayudarle a integrar esta funcionalidad en sus proyectos sin problemas.

## Preguntas frecuentes

### P1: ¿Puedo utilizar Aspose.Page para .NET con otros formatos de documentos?

 R1: Aspose.Page se centra principalmente en PostScript, pero Aspose proporciona otras bibliotecas para varios formatos de documentos. Comprobar el[Asponer documentación](https://reference.aspose.com/page/net/) para más detalles.

### P2: ¿Dónde puedo encontrar apoyo adicional y debates comunitarios?

 A2: Visita el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39) para discusiones y apoyo de la comunidad.

### P3: ¿Hay una prueba gratuita disponible para Aspose.Page para .NET?

 R3: Sí, puedes acceder al[prueba gratis](https://releases.aspose.com/)para explorar las características de Aspose.Page para .NET.

### P4: ¿Cómo puedo obtener una licencia temporal para Aspose.Page?

 A4: Obtener una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/) para fines de prueba y evaluación.

### P5: ¿Dónde puedo comprar Aspose.Page para .NET?

 R5: Compre Aspose.Page para .NET en el[comprar pagina](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
