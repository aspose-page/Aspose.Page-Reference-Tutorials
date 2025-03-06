---
title: Adicionar Namespace em XMP usando Java
linktitle: Adicionar Namespace em XMP usando Java
second_title: API Java Aspose.Page
description: Desbloqueie o poder da manipulação de documentos com Aspose.Page for Java. Aprenda a adicionar namespaces XMP sem esforço neste guia completo.
weight: 13
url: /pt/java/xmp-metadata-manipulation/add-namespace/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Namespace em XMP usando Java


## Introdução

No âmbito da manipulação de documentos, Aspose.Page for Java se destaca como uma ferramenta robusta, oferecendo uma ampla gama de funcionalidades. Um recurso poderoso é a capacidade de adicionar namespaces em XMP (Extensible Metadata Platform) usando Java. Este tutorial irá guiá-lo através do processo, dividindo-o em etapas fáceis de seguir.

## Pré-requisitos

Antes de se aprofundar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:

-  Aspose.Page para Java: certifique-se de ter a biblioteca instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/page/java/).

- Ambiente de Desenvolvimento Java: Configure um ambiente Java em seu sistema.

- Arquivo de documento: possui um arquivo EPS com metadados XMP. Se não contiver metadados XMP, a biblioteca criará um com base nos comentários dos metadados PS.

## Importar pacotes

Para começar, importe os pacotes necessários para o seu projeto Java:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;

import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
```

## Etapa 1: Obtenha metadados XMP

```java

// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";

// Inicializar fluxo de arquivo EPS de entrada
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");

PsDocument document = new PsDocument(psStream);
// Obtenha metadados XMP. Se o arquivo EPS não contiver metadados XMP, crie um novo preenchido com valores de comentários de metadados PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Etapa 2: registrar novo namespace

```java
// Adicione novo namespace XML "http://www.some.org/schema/tmp#" com o prefixo "tmp"
xmp.registerNamespaceURI("tmp", "http://www.some.org/schema/tmp#");
```

## Etapa 3: adicionar nova propriedade

```java
// Adicione a nova propriedade "tmp:newKey" no novo namespace XML
xmp.put("tmp:newKey", new XmpValue("NewValue"));
```

## Etapa 4: salvar o documento

```java
// Inicializar fluxo de arquivo EPS de saída
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");

//Salvar documento com metadados XMP alterados
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Etapa 5: fechar fluxos

```java
// Fechar fluxo EPS de entrada
psStream.close();
```

Agora você adicionou com sucesso um namespace em XMP usando Aspose.Page para Java. Sinta-se à vontade para explorar mais recursos e liberar todo o potencial desta biblioteca.

## Conclusão

Aspose.Page for Java simplifica a complexa tarefa de manipulação de metadados XMP em arquivos EPS. Seguindo este guia passo a passo, você adquiriu uma habilidade valiosa para aprimorar suas capacidades de processamento de documentos.

## Perguntas frequentes

### Posso usar Aspose.Page for Java com outras linguagens de programação?
Aspose.Page oferece suporte principalmente a Java, mas existem versões disponíveis para outras linguagens, como .NET.

### Existe um teste gratuito disponível?
 Sim, você pode explorar uma avaliação gratuita[aqui](https://releases.aspose.com/).

### Onde posso encontrar documentação abrangente?
 Consulte a documentação[aqui](https://reference.aspose.com/page/java/).

### Como posso obter uma licença temporária?
 Você pode adquirir uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).

### Existem fóruns da comunidade para Aspose.Page?
 Sim, você pode interagir com a comunidade no[Fórum Aspose.Page](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
