---
date: 2026-09-19
description: Aprenda cómo agregar valores con nombre XMP a archivos EPS usando Aspose.Page
  for Java – una guía paso a paso con ejemplos de código.
keywords:
- how to add xmp
- add named value XMP Java
- Aspose.Page XMP metadata
- EPS XMP manipulation
- Java metadata API
lastmod: 2026-09-19
linktitle: Agregar valor con nombre en XMP usando Java
og_description: Cómo agregar valores con nombre XMP a archivos EPS usando Aspose.Page
  for Java. Siga esta guía concisa para inyectar metadatos personalizados en minutos.
og_image_alt: Screenshot of Java code adding XMP named value to an EPS file with Aspose.Page
og_title: Cómo agregar un valor con nombre XMP en archivos EPS usando Java
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  headline: How to add XMP named value in EPS files using Java
  type: TechArticle
- description: Learn how to add XMP named values to EPS files using Aspose.Page for
    Java – a step‑by‑step guide with code examples.
  name: How to add XMP named value in EPS files using Java
  steps:
  - name: Initialize input EPS file stream
    text: '**FileInputStream** is a Java I/O class that reads raw bytes from a file.
      Load the source EPS file into a `FileInputStream`. This stream feeds the document
      into Aspose’s API. > **Pro tip:** Keep the `dataDir` variable configurable so
      the same code works across environments.'
  - name: Obtain XMP metadata
    text: '**XmpMetadata** represents the XMP packet associated with an EPS document.
      Retrieve the existing XMP packet; if the EPS file lacks one, Aspose creates
      a fresh XMP object populated from the PS comments.'
  - name: Add named value
    text: '**NamedValue** is a key‑value pair stored within the XMP metadata namespace.
      Insert a custom named value into the XMP structure. In this example we add a
      new key under the `xmpTPg:MaxPageSize` namespace. > **Why this matters:** Named
      values let you store arbitrary key‑value pairs that downstream app'
  - name: Initialize output EPS file stream
    text: '**FileOutputStream** is a Java I/O class that writes raw bytes to a file.
      Prepare a `FileOutputStream` where the modified EPS will be saved.'
  - name: Save document
    text: The `save` method persists the changes. It writes the updated XMP packet
      back into the EPS file, guaranteeing that the new named value becomes part of
      the document’s metadata.
  - name: Close input EPS stream
    text: Closing the original file handle prevents resource leaks and ensures that
      the file is not locked for subsequent operations. By following these six steps,
      you have successfully **added a named value in XMP metadata** using **Aspose.Page
      for Java**.
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to work seamlessly with other Java
      libraries, providing flexibility in your development environment.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Yes, you can access a free trial of Aspose.Page for Java on the [Aspose
      releases page](https://releases.aspose.com/).
    question: Is a free trial available for Aspose.Page for Java?
  - answer: Visit the [temporary license page](https://purchase.aspose.com/temporary-license/)
      to obtain a temporary license for Aspose.Page for Java.
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: Explore the [documentation](https://reference.aspose.com/page/java/) for
      comprehensive tutorials and examples.
    question: Where can I find more tutorials and examples for Aspose.Page for Java?
  - answer: Absolutely, Aspose.Page for Java is designed to handle large‑scale projects
      efficiently, providing robust document manipulation capabilities.
    question: Is Aspose.Page for Java suitable for large‑scale projects?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- XMP metadata
- Aspose.Page
- Java EPS
- document automation
title: Cómo agregar un valor con nombre XMP en archivos EPS usando Java
url: /es/java/xmp-metadata-manipulation/add-named-value/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Agregar valor nombrado en los metadatos XMP usando Java

## Introducción
En el desarrollo moderno de Java, aprender **cómo agregar XMP** metadata dentro de archivos EPS es esencial para preservar la procedencia del documento y mejorar la capacidad de búsqueda. Con **Aspose.Page for Java**, puedes inyectar sin esfuerzo valores nombrados personalizados en el paquete XMP. Este tutorial te guía paso a paso—con fragmentos de código—para que puedas comenzar a agregar metadata XMP a tus documentos EPS hoy mismo.

## Respuestas rápidas
- **¿Qué biblioteca se necesita?** Aspose.Page for Java (Aspose)  
- **¿Qué tipo de archivo es el objetivo?** archivos EPS que contienen metadatos XMP  
- **¿Caso de uso principal?** Agregar valores nombrados personalizados (p. ej., límites de tamaño de página) a XMP  
- **¿Requisitos previos?** JDK 8+ y la biblioteca Aspose.Page for Java  
- **¿Tiempo típico de implementación?** 5–10 minutos una vez configurada la biblioteca  

## ¿Qué es asp?
Aspose es la abreviatura de Aspose, una suite de APIs que permite a los desarrolladores crear, editar, convertir y renderizar una amplia gama de formatos de documentos sin requerir software externo. El componente Aspose.Page for Java se centra específicamente en el procesamiento de PostScript y EPS, proporcionando acceso programático al contenido de la página, gráficos y metadata como XMP.

## ¿Por qué agregar valores nombrados a los metadatos XMP?
Los valores nombrados te permiten almacenar pares clave‑valor arbitrarios directamente dentro del paquete XMP, haciéndolos instantáneamente legibles por herramientas posteriores. Esto mejora la amigabilidad con los motores de búsqueda, habilita la automatización de flujos de trabajo y satisface requisitos de cumplimiento al incrustar información regulatoria sin alterar el contenido visual.

## Por qué esto es importante
Agregar valores nombrados a XMP te permite almacenar pares clave‑valor arbitrarios que pueden leerse sin analizar todo el archivo EPS. Esta capacidad es especialmente valiosa en pipelines de publicación automatizada, sistemas de gestión de activos digitales y flujos de trabajo impulsados por cumplimiento donde la metadata dirige acciones posteriores.

## Requisitos previos
Antes de profundizar, asegúrate de contar con lo siguiente:

- **Java Development Kit (JDK):** Un JDK reciente (8 o superior) instalado en su máquina.  
- **Aspose.Page for Java Library:** Descárgala desde el [Aspose.Page for Java download](https://releases.aspose.com/page/java/). Añade el JAR al classpath de tu proyecto.  
- **Un archivo EPS** que ya contiene metadatos XMP o que se generará automáticamente.

## Importar paquetes
Comienza importando los paquetes Java necesarios. Estas importaciones te dan acceso a flujos de archivos, al modelo de documento EPS y a las clases de manejo de XMP.

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Cómo agregar un valor nombrado XMP en archivos EPS usando Java
Para agregar un valor nombrado, carga el archivo EPS con un `FileInputStream`, recupera o crea su objeto `XmpMetadata`, inserta el `NamedValue` deseado en el espacio de nombres apropiado y luego escribe el documento modificado de vuelta usando un `FileOutputStream`. Aspose.Page maneja automáticamente la creación del paquete XMP si falta, asegurando que la nueva metadata se incruste correctamente.

### Paso 1: Inicializar el flujo de archivo EPS de entrada
**FileInputStream** es una clase de I/O de Java que lee bytes crudos de un archivo. Carga el archivo EPS fuente en un `FileInputStream`. Este flujo alimenta el documento a la API de Aspose.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
PsDocument document = new PsDocument(psStream);
```

> **Consejo profesional:** Mantenga la variable `dataDir` configurable para que el mismo código funcione en diferentes entornos.

### Paso 2: Obtener los metadatos XMP
**XmpMetadata** representa el paquete XMP asociado a un documento EPS. Recupera el paquete XMP existente; si el archivo EPS no tiene uno, Aspose crea un nuevo objeto XMP poblado a partir de los comentarios PS.

```java
XmpMetadata xmp = document.getXmpMetadata();
```

### Paso 3: Agregar valor nombrado
**NamedValue** es un par clave‑valor almacenado dentro del espacio de nombres de metadata XMP. Inserta un valor nombrado personalizado en la estructura XMP. En este ejemplo añadimos una nueva clave bajo el espacio de nombres `xmpTPg:MaxPageSize`.

```java
xmp.addNamedValue("xmpTPg:MaxPageSize", "stDim:newKey", new XmpValue("NewValue"));
```

> **Por qué esto es importante:** Los valores nombrados permiten almacenar pares clave‑valor arbitrarios que las aplicaciones posteriores pueden leer sin analizar todo el documento.

### Paso 4: Inicializar el flujo de archivo EPS de salida
**FileOutputStream** es una clase de I/O de Java que escribe bytes crudos a un archivo. Prepara un `FileOutputStream` donde se guardará el EPS modificado.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

### Paso 5: Guardar el documento
El método `save` persiste los cambios. Escribe el paquete XMP actualizado de vuelta al archivo EPS, garantizando que el nuevo valor nombrado forme parte de la metadata del documento.

```java
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

### Paso 6: Cerrar el flujo de archivo EPS de entrada
Cerrar el manejador de archivo original evita fugas de recursos y asegura que el archivo no quede bloqueado para operaciones posteriores.

```java
psStream.close();
```

Al seguir estos seis pasos, has **agregado exitosamente un valor nombrado en los metadatos XMP** usando **Aspose.Page for Java**.

## Problemas comunes y soluciones
| Problema | Causa | Solución |
|----------|-------|----------|
| `NullPointerException` en `xmp` | El archivo EPS no tiene XMP y Aspose no pudo generar uno | Asegúrese de que el EPS contenga al menos un comentario PS o cree manualmente una nueva instancia de `XmpMetadata`. |
| El archivo de salida está vacío | El flujo de salida no se vació/cerró | Verifique que `outPsStream.close()` se llame en un bloque `finally` (como se muestra). |
| Error de clave duplicada | El mismo valor nombrado se añadió dos veces | Compruebe si la clave ya existe con `xmp.containsNamedValue(...)` antes de agregarla. |

## Preguntas frecuentes

**P: ¿Puedo usar Aspose.Page for Java con otras bibliotecas Java?**  
R: Sí, Aspose.Page for Java está diseñada para trabajar sin problemas con otras bibliotecas Java, proporcionando flexibilidad en su entorno de desarrollo.

**P: ¿Está disponible una prueba gratuita de Aspose.Page for Java?**  
R: Sí, puedes acceder a una prueba gratuita de Aspose.Page for Java en la [página de lanzamientos de Aspose](https://releases.aspose.com/).

**P: ¿Cómo puedo obtener una licencia temporal para Aspose.Page for Java?**  
R: Visita la [página de licencia temporal](https://purchase.aspose.com/temporary-license/) para obtener una licencia temporal para Aspose.Page for Java.

**P: ¿Dónde puedo encontrar más tutoriales y ejemplos de Aspose.Page for Java?**  
R: Explora la [documentación](https://reference.aspose.com/page/java/) para tutoriales y ejemplos completos.

**P: ¿Es Aspose.Page for Java adecuado para proyectos a gran escala?**  
R: Absolutamente, Aspose.Page for Java está diseñada para manejar proyectos a gran escala de manera eficiente, ofreciendo capacidades robustas de manipulación de documentos.

## Conclusión
En esta guía demostramos cómo **Aspose.Page for Java** facilita **agregar valores nombrados a los metadatos XMP** dentro de archivos EPS. Con los pasos anteriores, puedes enriquecer tus documentos con metadata personalizada, mejorar la capacidad de búsqueda y habilitar un procesamiento posterior más inteligente.

---

**Last Updated:** 2026-09-19  
**Probado con:** Aspose.Page for Java 24.12 (latest at time of writing)  
**Autor:** Aspose

## Tutoriales relacionados

- [Cómo agregar espacio de nombres XMP en archivos EPS usando Aspose.Page – Tutorial Java](/page/java/xmp-metadata-manipulation/add-namespace/)
- [Agregar metadatos XMP a archivos EPS usando Java](/page/java/xmp-metadata-manipulation/add-simple-properties/)
- [Leer XMP usando Aspose.Page – Guía Java](/page/java/xmp-metadata-manipulation/get-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}