---
title: Aplicar licencia medida con Aspose.Page para .NET
linktitle: Aplicar licencia medida
second_title: Aspose.Página .NET API
description: Explore la perfecta integración de Aspose.Page para .NET con esta guía paso a paso sobre cómo aplicar una licencia medida. Optimice el procesamiento de documentos sin esfuerzo.
type: docs
weight: 10
url: /es/net/getting-started/apply-metered-license/
---
## Introducción

Libere todo el potencial de Aspose.Page para .NET aplicando una licencia medida. Este tutorial lo guiará a través del proceso de configuración y aplicación de la licencia medida, garantizando un uso fluido y optimizado de esta potente biblioteca .NET.

## Requisitos previos

Antes de profundizar en los pasos, asegúrese de cumplir con los siguientes requisitos previos:

-  Una licencia válida de Aspose.Page para .NET: puede obtenerla en[compra.aspose.com](https://purchase.aspose.com/buy).
-  Biblioteca Aspose.Page instalada: consulte la[documentación](https://reference.aspose.com/page/net/) para obtener instrucciones de instalación.
- Entorno de desarrollo .NET: asegúrese de tener un entorno .NET funcional configurado en su máquina.

## Importar espacios de nombres

En su proyecto .NET, importe los espacios de nombres necesarios para acceder a las funcionalidades de Aspose.Page:

```csharp
using Aspose.Page;
using Aspose.Page.EPS;
using Aspose.Page.EPS.Device;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

## Paso 1: Establecer claves públicas y privadas medidas

 Inicializar el`Aspose.Page.Metered` class y establezca las claves públicas y privadas medidas. Reemplazar`<type public key here>` y`<type private key here>` con tus llaves reales.

```csharp
Aspose.Page.Metered metered = new Aspose.Page.Metered();
metered.SetMeteredKey("<type public key here>", "<type private key here>");
```

## Paso 2: cargue el archivo EPS y cree el documento

 Especifique la ruta a su archivo EPS y cree una secuencia para leer su contenido. Luego, cree una instancia del`PsDocument` clase de la corriente.

```csharp
string dataDir = "Your Document Directory";
System.IO.Stream psStream = new System.IO.FileStream(dataDir + "input.eps", System.IO.FileMode.Open, System.IO.FileAccess.Read);
PsDocument document = new PsDocument(psStream);
```

## Paso 3: Convertir EPS a imagen PNG

 Crear un`ImageDevice` para convertir el archivo EPS a una imagen PNG. Guarde el archivo EPS como una imagen usando el`ImageSaveOptions`.

```csharp
ImageDevice device = new ImageDevice();
document.Save(device, new ImageSaveOptions());
```

## Paso 4: recuperar bytes de imagen

Obtenga los bytes de la imagen, donde cada matriz de bytes representa una página. En este caso, tenemos una página.

```csharp
byte[][] imagesBytes = device.ImagesBytes;
```

## Paso 5: guarde los bytes de la imagen en un archivo

Guarde los bytes de la imagen en un archivo, lo que garantiza una conversión exitosa de EPS a PNG.

```csharp
using (FileStream fos = File.OpenWrite(dataDir + "eps_out.png"))
{
    fos.Write(imagesBytes[0], 0, imagesBytes[0].Length);
}
```

## Paso 6: Verificar la licencia medida

Compruebe visualmente si la licencia medida se aplica correctamente. Si la imagen resultante no contiene el mensaje de evaluación rojo, indica que la licencia medida se aplica sin ningún problema.

¡Ahora está listo para aprovechar todas las capacidades de Aspose.Page para .NET con una licencia medida!

## Conclusión

Esta guía paso a paso le ha proporcionado los conocimientos necesarios para aplicar sin problemas una licencia medida utilizando Aspose.Page para .NET. Mejore sus capacidades de procesamiento de documentos y explore las amplias funciones que ofrece esta poderosa biblioteca.

## Preguntas frecuentes

### P1: ¿Cómo obtengo una licencia medida para Aspose.Page para .NET?

 A1: Visita[compra.aspose.com](https://purchase.aspose.com/buy) para adquirir una licencia válida.

### P2: ¿Dónde puedo encontrar la documentación de Aspose.Page para .NET?

 A2: Consulte[Aspose.Página .NET](https://reference.aspose.com/page/net/) para documentación completa.

### P3: ¿Existe un foro para discusiones y soporte de Aspose.Page?

 A3: Sí, visita[foro](https://forum.aspose.com/c/page/39) involucrarse con la comunidad y buscar ayuda.

### P4: ¿Puedo probar Aspose.Page para .NET antes de comprarlo?

 R4: ¡Absolutamente! Accede a la prueba gratuita en[aquí](https://releases.aspose.com/).

### P5: ¿Cómo puedo obtener una licencia temporal de Aspose.Page para .NET?

 A5: Visita[licencia temporal/](https://purchase.aspose.com/temporary-license/) para obtener una licencia temporal.