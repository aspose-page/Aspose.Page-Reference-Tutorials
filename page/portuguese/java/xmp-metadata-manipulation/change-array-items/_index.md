---
title: Alterar itens da matriz em XMP usando Java
linktitle: Alterar itens da matriz em XMP usando Java
second_title: API Java Aspose.Page
description: Aprenda como alterar itens de array em XMP usando Aspose.Page para Java. Modifique metadados sem esforço com nosso guia passo a passo. Aprimore seus documentos EPS agora!
weight: 15
url: /pt/java/xmp-metadata-manipulation/change-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Alterar itens da matriz em XMP usando Java

## Introdução
Bem-vindo ao nosso guia completo sobre como alterar itens de array em XMP usando Aspose.Page para Java! Aspose.Page é uma biblioteca Java poderosa que permite trabalhar perfeitamente com metadados XMP em arquivos EPS. Neste tutorial, orientaremos você no processo de modificação de itens de array nos metadados XMP, ajudando você a aprimorar e personalizar seus documentos EPS.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Java Development Kit (JDK) instalado em seu sistema.
-  Biblioteca Aspose.Page para Java. Você pode baixá-lo em[aqui](https://releases.aspose.com/page/java/).
## Importar pacotes
Para começar, vamos importar os pacotes necessários para o seu projeto Java. Certifique-se de ter a biblioteca Aspose.Page incluída em seu projeto.
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;

```
## Etapa 1: Obtenha metadados XMP
Em primeiro lugar, recupere os metadados XMP do seu arquivo EPS. Se o arquivo EPS ainda não contiver metadados XMP, um novo será criado com valores de comentários de metadados PS, como %%Creator, %%CreateDate, %%Title, etc.
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Inicializar fluxo de arquivo EPS de entrada
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Obtenha metadados XMP. Se o arquivo EPS não contiver metadados XMP, um novo será preenchido com valores dos comentários de metadados PS.
XmpMetadata xmp = document.getXmpMetadata();
```
## Etapa 2: definir o item da matriz "dc:title"
Agora, vamos definir o item do array “dc:title” no índice 0 com um novo valor.
```java
// Defina o item da matriz "dc:title" pelo índice 0
xmp.setArrayItem("dc:title", 0, new XmpValue("NewTitle"));
```
## Etapa 3: definir o item da matriz "dc: creator"
Da mesma forma, defina o item da matriz "dc:creator" no índice 0 com um novo valor de criador.
```java
// Defina o item da matriz "dc: creator" pelo índice 0
xmp.setArrayItem("dc:creator", 0, new XmpValue("NewCreator"));
```
## Etapa 4: inicializar o fluxo de arquivos EPS de saída
Prepare o fluxo de arquivo EPS de saída onde o documento modificado será salvo.
```java
// Inicializar fluxo de arquivo EPS de saída
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
## Etapa 5: Salvar documento com metadados XMP alterados
Salve o documento com os metadados XMP atualizados.
```java
//Salvar documento com metadados XMP alterados
try {
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Conclusão
Parabéns! Você aprendeu com sucesso como alterar itens de array em XMP usando Aspose.Page para Java. Este tutorial forneceu orientação passo a passo, garantindo que você possa aprimorar facilmente seus documentos EPS com metadados personalizados.

## Perguntas frequentes
### Posso usar Aspose.Page for Java com outras linguagens de programação?
Aspose.Page foi projetado principalmente para Java, mas Aspose fornece bibliotecas semelhantes para outras linguagens.
### Onde posso encontrar documentação detalhada para Aspose.Page for Java?
 A documentação está disponível[aqui](https://reference.aspose.com/page/java/).
### Existe uma avaliação gratuita disponível para Aspose.Page for Java?
 Sim, você pode obter um teste gratuito[aqui](https://releases.aspose.com/).
### Como posso obter uma licença temporária para Aspose.Page for Java?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso comprar a versão completa do Aspose.Page for Java?
 Você pode comprar a versão completa[aqui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
