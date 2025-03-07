---
title: Agregar espacio de nombres en XMP usando Java
linktitle: Agregar espacio de nombres en XMP usando Java
second_title: API de Java de Aspose.Page
description: Desbloquee el poder de la manipulación de documentos con Aspose.Page para Java. Aprenda a agregar espacios de nombres XMP sin esfuerzo en esta guía completa.
weight: 13
url: /es/java/xmp-metadata-manipulation/add-namespace/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar espacio de nombres en XMP usando Java


## Introducción

En el ámbito de la manipulación de documentos, Aspose.Page para Java se destaca como una herramienta sólida que ofrece una amplia gama de funcionalidades. Una característica poderosa es la capacidad de agregar espacios de nombres en XMP (Plataforma de metadatos extensible) usando Java. Este tutorial lo guiará a través del proceso, dividiéndolo en pasos fáciles de seguir.

## Requisitos previos

Antes de profundizar en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:

-  Aspose.Page para Java: asegúrese de tener la biblioteca instalada. Puedes descargarlo[aquí](https://releases.aspose.com/page/java/).

- Entorno de desarrollo Java: configure un entorno Java en su sistema.

- Archivo de documento: Tener un archivo EPS con metadatos XMP. Si no contiene metadatos XMP, la biblioteca creará uno basado en los comentarios de metadatos de PS.

## Importar paquetes

Para comenzar, importe los paquetes necesarios a su proyecto Java:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Paso 1: obtenga metadatos XMP

```java

// La ruta al directorio de documentos.
String dataDir = "Your Document Directory";

// Inicializar flujo de archivos EPS de entrada
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Obtenga metadatos XMP. Si el archivo EPS no contiene metadatos XMP, cree uno nuevo con valores de los comentarios de metadatos de PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Paso 2: registrar un nuevo espacio de nombres

```java
// Agregue un nuevo espacio de nombres XML "http://www.some.org/schema/tmp#" con el prefijo "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

## Paso 3: agregar nueva propiedad

```java
// Agregue la nueva propiedad "tmp:newKey" en el nuevo espacio de nombres XML
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

## Paso 4: guardar el documento

```java
// Inicializar flujo de archivos EPS de salida
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");

//Guardar documento con metadatos XMP modificados
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Paso 5: Cerrar transmisiones

```java
// Cerrar flujo EPS de entrada
psStream.close();
```

Ahora ha agregado exitosamente un espacio de nombres en XMP usando Aspose.Page para Java. No dude en explorar más funciones y liberar todo el potencial de esta biblioteca.

## Conclusión

Aspose.Page para Java simplifica la compleja tarea de manipular metadatos XMP en archivos EPS. Al seguir esta guía paso a paso, habrá adquirido una habilidad valiosa para mejorar sus capacidades de procesamiento de documentos.

## Preguntas frecuentes

### ¿Puedo utilizar Aspose.Page para Java con otros lenguajes de programación?
Aspose.Page admite principalmente Java, pero hay versiones disponibles para otros lenguajes como .NET.

### ¿Hay una prueba gratuita disponible?
 Sí, puedes explorar una prueba gratuita.[aquí](https://releases.aspose.com/).

### ¿Dónde puedo encontrar documentación completa?
 Consulte la documentación.[aquí](https://reference.aspose.com/page/java/).

### ¿Cómo puedo obtener una licencia temporal?
 Puedes adquirir una licencia temporal[aquí](https://purchase.aspose.com/temporary-license/).

### ¿Existen foros comunitarios para Aspose.Page?
 Sí, puedes interactuar con la comunidad en el[Foro de Aspose.Page](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
