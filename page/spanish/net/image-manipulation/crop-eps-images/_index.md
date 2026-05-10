---
date: 2026-03-16
description: Aprende a recortar imágenes EPS y cambiar el tamaño de archivos de imagen
  EPS en .NET usando Aspose.Page. Sigue esta guía paso a paso para recortar EPS y
  cambiar el tamaño de la imagen EPS sin esfuerzo.
linktitle: Crop EPS Images
second_title: Aspose.Page .NET API
title: Cómo recortar imágenes EPS con Aspose.Page para .NET
url: /es/net/image-manipulation/crop-eps-images/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cómo recortar imágenes EPS con Aspose.Page para .NET

## Introducción

Si necesitas saber **cómo recortar imágenes EPS** en una aplicación .NET, has llegado al lugar correcto. En este tutorial te guiaremos paso a paso para recortar y redimensionar archivos EPS usando la potente biblioteca Aspose.Page para .NET. Ya sea que estés afinando una herramienta de informes o preparando gráficos para un servicio web, dominar esta técnica te ahorrará tiempo y te brindará resultados perfectos a nivel de píxel.

## Respuestas rápidas
- **¿Qué biblioteca maneja el recorte de EPS?** Aspose.Page para .NET  
- **¿Método principal?** `doc.CropEps(outputStream, newBoundingBox)`  
- **¿Puedo también redimensionar el EPS?** Sí – usa `ResizeEps` con pulgadas, milímetros o porcentajes.  
- **¿Requisitos previos?** .NET (Framework 4.5+ / .NET Core 3.1+), Aspose.Page instalado, un archivo EPS.  
- **¿Tiempo típico de implementación?** Aproximadamente 10 minutos para un flujo básico de recorte y redimensionado.

## Requisitos previos

Antes de sumergirte en el código, asegúrate de tener:

- Conocimientos básicos de desarrollo .NET.  
- Biblioteca Aspose.Page para .NET instalada. Si no la tienes, puedes descargarla [aquí](https://releases.aspose.com/page/net/).  
- Una imagen EPS de ejemplo (reemplaza `"input.eps"` en el código con tu archivo real).

## Importar espacios de nombres

Comencemos importando los espacios de nombres que nos dan acceso a las clases de manejo de EPS.

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using Aspose.Page.EPS.XMP;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
```

## Cómo recortar imágenes EPS – Guía paso a paso

### Paso 1: Inicializar `PsDocument`

```csharp
PsDocument doc = new PsDocument(inputEpsStream);
```

Creamos una instancia de `PsDocument` a partir del flujo de entrada EPS. Este objeto representa el archivo EPS en memoria y nos brinda acceso a los métodos de recorte y redimensionado.

### Paso 2: Extraer el cuadro delimitador original

```csharp
int[] initialBoundingBox = doc.ExtractEpsBoundingBox();
```

El cuadro delimitador (bounding box) indica las dimensiones actuales del lienzo EPS. Conocer estos valores te ayuda a definir un rectángulo de recorte seguro.

### Paso 3: Crear un flujo de salida

```csharp
using (Stream outputEpsStream = new FileStream(dataDir + "output_crop.eps", FileMode.Create, FileAccess.Write))
```

Abrimos un flujo escribible donde se guardará el EPS recortado. Usar un bloque `using` garantiza que el flujo se cierre correctamente.

### Paso 4: Definir un nuevo cuadro delimitador

```csharp
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
```

Reemplaza los números con las coordenadas que deseas conservar. Asegúrate de que los nuevos valores permanezcan dentro del cuadro delimitador original; de lo contrario, la operación fallará.

### Paso 5: Recortar y guardar el EPS

```csharp
doc.CropEps(outputEpsStream, newBoundingBox);
```

Esta única línea realiza el recorte y escribe el resultado en `output_crop.eps`. El método modifica el documento en memoria, por lo que puedes encadenar más operaciones si lo necesitas.

## Redimensionar imagen EPS

Después de recortar, a menudo deseas cambiar el tamaño del EPS para visualización o impresión. Aspose.Page admite tres unidades de medida.

### Redimensionar en pulgadas

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(5.791f, 3.625f), Units.Inches);
```

### Redimensionar en milímetros

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(196, 123), Units.Millimeters);
```

### Redimensionar en porcentajes

```csharp
doc.ResizeEps(outputEpsStream, new SizeF(200, 200), Units.Percents);
```

Cada llamada sobrescribe la salida anterior, así que asegúrate de crear un flujo nuevo si necesitas archivos separados para cada tamaño.

## Problemas comunes y solución de problemas

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| **Valores del cuadro delimitador fuera de rango** | El nuevo cuadro supera las dimensiones originales | Verifica los valores de `initialBoundingBox` y elige coordenadas dentro de ese rango. |
| **El archivo de salida está vacío** | El flujo de salida no se vacía o cierra | Asegúrate de que el bloque `using` finalice antes de acceder al archivo, o llama a `outputEpsStream.Flush()`. |
| **Escalado inesperado** | Mezcla de unidades (p. ej., pulgadas vs. milímetros) | Siempre especifica el enum `Units` correcto que coincida con tus valores de tamaño. |

## Preguntas frecuentes

### P1: ¿Puedo usar Aspose.Page para .NET con otros formatos de imagen?

R1: Aspose.Page se centra principalmente en imágenes EPS, pero Aspose ofrece diversas bibliotecas para diferentes formatos. Consulta su documentación para formatos específicos.

### P2: ¿Cómo puedo obtener una licencia temporal para Aspose.Page para .NET?

R2: Visita [este enlace](https://purchase.aspose.com/temporary-license/) para obtener una licencia temporal de prueba.

### P3: ¿Existen limitaciones en el tamaño de imagen que puedo procesar con Aspose.Page para .NET?

R3: Aspose.Page está diseñado para manejar imágenes de varios tamaños. Sin embargo, el rendimiento puede variar según la complejidad de la imagen.

### P4: ¿Hay un foro comunitario para discusiones sobre Aspose.Page?

R5: Sí, puedes participar en la comunidad de Aspose.Page [aquí](https://forum.aspose.com/c/page/39).

### P5: ¿Dónde puedo encontrar documentación detallada para Aspose.Page para .NET?

R5: Consulta la documentación [aquí](https://reference.aspose.com/page/net/).

---

**Última actualización:** 2026-03-16  
**Probado con:** Aspose.Page 24.11 para .NET  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}