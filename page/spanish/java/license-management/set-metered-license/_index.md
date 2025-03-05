---
title: Integración sencilla de licencia medida con Aspose.Page Java
linktitle: Establecer licencia medida en Java
second_title: API de Java de Aspose.Page
description: Explore la perfecta integración de Aspose.Page con Java. Configure licencias medidas sin esfuerzo y mejore sus capacidades de procesamiento de documentos.
type: docs
weight: 10
url: /es/java/license-management/set-metered-license/
---
## Introducción
Bienvenido a nuestra guía completa sobre cómo configurar una licencia medida en Java usando Aspose.Page. Si busca mejorar sus capacidades de procesamiento de documentos y garantizar una integración perfecta con Aspose.Page, está en el lugar correcto. En este tutorial, lo guiaremos a través del proceso, dividiendo cada paso en partes fácilmente digeribles.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Conocimientos básicos de programación Java.
-  Biblioteca Aspose.Page instalada. Puedes descargarlo desde[aquí](https://releases.aspose.com/page/java/).
- Claves públicas y privadas medidas, que puede obtener a través de su cuenta Aspose.
## Importar paquetes
Comencemos importando los paquetes necesarios para nuestro programa Java. Asegúrese de tener la biblioteca Aspose.Page integrada en su proyecto.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;

```
## Paso 1: inicializar el formato de imagen y documento
El primer paso es configurar el documento y definir el formato de imagen deseado.
```java
// establecer claves públicas y privadas medidas
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Acceda a la propiedad setMeteredKey y pase claves públicas y privadas como parámetros
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```
## Paso 2: inicializar el flujo de entrada PostScript
En este paso, inicializamos el flujo de entrada PostScript para su procesamiento.
```java
// Inicializar flujo de entrada PostScript
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```
## Paso 3: Verifique la licencia del documento
Antes de continuar, es fundamental verificar si el documento tiene la licencia adecuada.
```java
// Compruebe si el documento tiene licencia.
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```
## Paso 4: Inicializar opciones y dispositivo de imagen
Ahora, inicialicemos las opciones y el dispositivo de imagen con los parámetros predeterminados.
```java
// Inicialice el objeto de opciones con los parámetros predeterminados.
ImageSaveOptions options = new ImageSaveOptions();
// Inicialice el objeto ImageDevice con los parámetros predeterminados.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```
## Paso 5: guarde el archivo EPS como imagen
Guarde el archivo EPS como una imagen utilizando las opciones y el dispositivo definidos.
```java
// Guardar archivo EPS como imagen
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```
## Paso 6: obtenga y guarde bytes de imagen
Recupere bytes de imagen y guárdelos en un archivo.
```java
// Obtener bytes de imágenes. Matriz de un byte para una página. En nuestro caso, tenemos una página.
byte[][] imagesBytes = device.getImagesBytes();
// Guardar bytes de imagen en un archivo
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```
## Conclusión
¡Felicidades! Ha configurado con éxito una licencia medida en Java utilizando Aspose.Page. Este tutorial proporciona una guía paso a paso para garantizar un proceso de integración sin problemas.
## Preguntas frecuentes
### P: ¿Cómo obtengo claves públicas y privadas medidas?
Puede obtener estas claves a través de su cuenta Aspose.
### P: ¿La biblioteca Aspose.Page es gratuita?
 Aspose.Page ofrece versiones de prueba gratuitas y de pago. Visita[aquí](https://releases.aspose.com/) para una prueba gratuita.
### P: ¿Puedo utilizar Aspose.Page para proyectos comerciales?
 Sí, Aspose.Page ofrece licencias comerciales. Puedes comprarlos[aquí](https://purchase.aspose.com/buy).
### P: ¿Dónde puedo encontrar documentación adicional?
 Consulte la documentación.[aquí](https://reference.aspose.com/page/java/).
### P: ¿Cómo puedo obtener licencias temporales?
 Se pueden obtener licencias temporales.[aquí](https://purchase.aspose.com/temporary-license/).