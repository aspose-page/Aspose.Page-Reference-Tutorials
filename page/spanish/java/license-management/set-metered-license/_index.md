---
date: 2026-02-05
description: Aprende cómo guardar EPS como PNG usando Aspose.Page para Java mientras
  configuras una licencia medida. Guía paso a paso con ejemplo de código completo.
linktitle: Set Metered License in Java
second_title: Aspose.Page Java API
title: Guardar EPS como PNG con Aspose.Page Java (licencia medida)
url: /es/java/license-management/set-metered-license/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Guardar EPS como PNG con Aspose.Page Java (Metered License)

## Introducción
Si necesitas **guardar EPS como PNG** en una aplicación Java y buscas una manera sencilla de gestionar la licencia, estás en el lugar correcto. Este tutorial te guía paso a paso para configurar una licencia medida para Aspose.Page, cargar un archivo PostScript (EPS) y convertirlo a una imagen PNG, todo con instrucciones claras y concisas que puedes seguir de inmediato. Al final también comprenderás cómo **renderizar EPS a PNG** de forma eficiente y cómo escribir código **write PNG file Java** que funcione en entornos de producción.

## Respuestas rápidas
- **¿Qué significa “save EPS as PNG”?** Convierte un archivo vectorial EPS en una imagen raster PNG.  
- **¿Por qué usar una licencia medida?** Te permite pagar solo por las páginas que procesas, ideal para cargas de trabajo variables.  
- **¿Necesito conexión a internet?** No, las claves medidas se validan localmente.  
- **¿Qué versión de Java se requiere?** Java 8 o superior.  
- **¿Cuánto tiempo lleva la configuración?** Aproximadamente 10 minutos para una implementación básica.  

## ¿Qué es “save EPS as PNG”?
Guardar EPS como PNG transforma un documento Escalable Encapsulated PostScript en un formato de mapa de bits ampliamente compatible. PNG conserva la transparencia y ofrece compresión sin pérdida, lo que lo hace ideal para gráficos web, miniaturas y vistas previas de impresión.

## ¿Por qué renderizar EPS a PNG con Aspose.Page?
- **Pure Java API** – sin dependencias nativas, por lo que puedes ejecutarlo donde sea que la JVM esté soportada.  
- **Renderizado de alta fidelidad** – los gráficos vectoriales se rasterizan con precisión, preservando la calidad de las líneas.  
- **Licenciamiento medido** – solo pagas por lo que conviertes, lo que mantiene los costos predecibles.  
- **Múltiples opciones de salida** – además de PNG puedes generar JPEG, TIFF y más, dándote flexibilidad para diferentes proyectos.

## Requisitos previos
Antes de comenzar, asegúrate de contar con:

- Conocimientos básicos de programación Java.  
- Biblioteca Aspose.Page instalada – descárgala desde [here](https://releases.aspose.com/page/java/).  
- Claves públicas y privadas medidas, que puedes obtener a través de tu cuenta Aspose.

## Importar paquetes
Primero, importa las clases que necesitaremos. Mantén el bloque de importación exactamente como se muestra para que el código compile sin cambios.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
import com.aspose.eps.ImageFormat;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.ImageSaveOptions;
```

## Cómo guardar EPS como PNG usando Aspose.Page Java
A continuación tienes la guía paso a paso que combina la licencia, la carga, el renderizado y la escritura del archivo PNG final.

### Paso 1: Inicializar documento y formato de imagen
Aquí establecemos las claves medidas y definimos el formato de salida (PNG). Esta es la base para la operación **save EPS as PNG**.

```java
// set metered public and private keys
com.aspose.page.Metered metered = new com.aspose.page.Metered();
// Access the setMeteredKey property and pass public and private keys as parameters
metered.setMeteredKey(
    "<type public key here>",
    "<type private key here>");
// The path to the documents directory.
String dataDir = "Your Document Directory";
ImageFormat imageFormat = ImageFormat.PNG;
```

### Paso 2: Inicializar flujo de entrada PostScript
Abre el archivo EPS que deseas convertir. El flujo alimenta el documento a Aspose.Page.

```java
// Initialize PostScript input stream
FileInputStream psStream = new FileInputStream(dataDir + "input.ps");
PsDocument document = new PsDocument(psStream);
```

### Paso 3: Verificar licencia del documento
Siempre verifica que la licencia medida se haya aplicado correctamente antes de procesar.

```java
// Check if the document is licensed
if (document.isLicensed())
    System.out.println("Metered License is set successfully.");
else
    System.out.println("Metered License is not set.");
```

### Paso 4: Inicializar opciones y dispositivo de imagen
Crea el objeto de opciones que controla la configuración de conversión y el dispositivo que recibirá la imagen renderizada.

```java
// Initialize options object with default parameters.
ImageSaveOptions options = new ImageSaveOptions();
// Initialize ImageDevice object with default parameters.
com.aspose.eps.device.ImageDevice device = new com.aspose.eps.device.ImageDevice();
```

### Paso 5: Guardar archivo EPS como imagen
Esta es la llamada central **save EPS as PNG**. El documento se renderiza en el dispositivo de imagen usando las opciones configuradas.

```java
// Save EPS file as image
try {
    document.save(device, options);
} finally {
    psStream.close();
}
```

### Paso 6: Obtener y guardar bytes de la imagen
Extrae los bytes PNG del dispositivo y escríbelos en un archivo en disco. Este paso muestra cómo **write PNG file Java** de forma segura.

```java
// Get images bytes. One bytes array for one page. In our case, we have one page.
byte[][] imagesBytes = device.getImagesBytes();
// Save image bytes to file
FileOutputStream fs = new FileOutputStream(dataDir + "eps_out." + imageFormat.toString().toLowerCase());
try {
    fs.write(imagesBytes[0], 0, imagesBytes[0].length);
} catch (IOException ex) {
    System.out.println(ex.getMessage());
} finally {
    fs.close();
}
```

## Problemas comunes y soluciones
| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| **Licencia no reconocida** | Las claves son incorrectas o están en el orden equivocado. | Verifica las cadenas de clave pública/privada y asegúrate de que `setMeteredKey` se llame antes de cualquier procesamiento del documento. |
| **El archivo de salida está vacío** | `device.getImagesBytes()` devolvió `null`. | Confirma que el archivo EPS sea válido y que las `ImageSaveOptions` no estén configuradas con un lienzo de tamaño cero. |
| **OutOfMemoryError en EPS grande** | Renderizar archivos vectoriales grandes consume mucha memoria. | Procesa las páginas una a una o aumenta el heap de JVM (`-Xmx2g`). |

## Preguntas frecuentes

**P: ¿Cómo obtengo las claves públicas y privadas medidas?**  
R: Puedes obtener estas claves a través de tu cuenta Aspose.

**P: ¿La biblioteca Aspose.Page es gratuita?**  
R: Aspose.Page ofrece versiones de prueba gratuitas y versiones de pago. Visita [here](https://releases.aspose.com/) para una prueba gratuita.

**P: ¿Puedo usar Aspose.Page en proyectos comerciales?**  
R: Sí, Aspose.Page ofrece licencias comerciales. Puedes adquirirlas [here](https://purchase.aspose.com/buy).

**P: ¿Dónde encuentro documentación adicional?**  
R: Consulta la documentación [here](https://reference.aspose.com/page/java/).

**P: ¿Cómo puedo obtener licencias temporales?**  
R: Las licencias temporales pueden obtenerse [here](https://purchase.aspose.com/temporary-license/).

**P: ¿Qué pasa si necesito convertir archivos EPS de varias páginas?**  
R: Recorre cada página usando `device.getImagesBytes()` y escribe cada arreglo de bytes en un archivo PNG separado.

**P: ¿Puedo cambiar la calidad o profundidad de color del PNG?**  
R: Sí, configura `ImageSaveOptions` (p. ej., `options.setCompressionLevel(...)`) antes de llamar a `document.save(...)`.

---

**Última actualización:** 2025-12-03  
**Probado con:** Aspose.Page 24.12 for Java  
**Autor:** Aspose  

**Última actualización:** 2026-02-05  
**Probado con:** Aspose.Page 24.12 for Java (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}