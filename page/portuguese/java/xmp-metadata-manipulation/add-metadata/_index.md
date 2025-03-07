---
title: Adicione metadados em XMP usando Java
linktitle: Adicione metadados em XMP usando Java
second_title: API Java Aspose.Page
description: Explore a integração perfeita do Aspose.Page for Java e aprenda como adicionar metadados XMP aos seus arquivos EPS sem esforço. Eleve seu jogo de gerenciamento de documentos hoje mesmo!
weight: 11
url: /pt/java/xmp-metadata-manipulation/add-metadata/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicione metadados em XMP usando Java

## Introdução
Você deseja aprimorar os metadados do seu documento adicionando informações XMP usando Java? Não procure mais! Este guia passo a passo orientará você no processo de adição de metadados a um arquivo EPS usando a biblioteca Aspose.Page para Java. Aspose.Page é uma ferramenta poderosa que simplifica tarefas de manipulação de documentos em aplicativos Java.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos:
- Conhecimento básico de programação Java.
-  Biblioteca Aspose.Page para Java instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/page/java/).
- Um arquivo EPS que você deseja modificar.
## Importar pacotes
Primeiramente, importe os pacotes necessários para o seu programa Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.page.BaseExamplesTest;
```
## Etapa 1: Obtenha metadados XMP
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Inicializar fluxo de arquivo EPS de entrada
FileInputStream psStream = new FileInputStream(dataDir + "xmp2.eps");
PsDocument document = new PsDocument(psStream);
// Obtenha metadados XMP. Se o arquivo EPS não contiver metadados XMP, um novo será criado usando valores de comentários de metadados PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Certifique-se de substituir “Seu diretório de documentos” pelo caminho real onde seus documentos estão armazenados.

## Etapa 2: recuperar o valor do CreatorTool
```java
// Obtenha o valor "CreatorTool"
if (xmp.containsKey("xmp:CreatorTool"))
    System.out.println("CreatorTool: " + xmp.get("xmp:CreatorTool").toStringValue());
```
## Etapa 3: recuperar o valor CreateDate
```java
// Obtenha o valor "CreateDate"
if (xmp.containsKey("xmp:CreateDate"))
    System.out.println("CreateDate: " + xmp.get("xmp:CreateDate").toStringValue());
```
## Etapa 4: recuperar o valor do título
```java
// Obtenha o valor "Título"
if (xmp.containsKey("dc:title"))
    System.out.println("Title: " + xmp.get("dc:title").toArray()[0].toStringValue());
```
## Etapa 5: recuperar o valor do formato
```java
//Obtenha o valor "formato"
if (xmp.containsKey("dc:format"))
    System.out.println("Format: " + xmp.get("dc:format").toStringValue());
```
## Etapa 6: recuperar o valor do criador
```java
// Obtenha o valor do "criador"
if (xmp.containsKey("dc:creator"))
    System.out.println("Creator: " + xmp.get("dc:creator").toArray()[0].toStringValue());
```
## Etapa 7: recuperar o valor MetadataDate
```java
// Obtenha o valor "MetadataDate"
if (xmp.containsKey("xmp:MetadataDate"))
    System.out.println("MetadataDate: " + xmp.get("xmp:MetadataDate").toStringValue());
```
## Etapa 8: Salvar documento com novos metadados XMP
```java
// Inicializar fluxo de arquivo EPS de saída
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp2_changed.eps");
// Salve o documento com novos metadados XMP
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Finalmente, não se esqueça de fechar o fluxo EPS de entrada:
```java
// Fechar fluxo EPS de entrada
psStream.close();
```
Agora, você adicionou metadados com sucesso ao seu arquivo EPS usando Aspose.Page for Java!
## Conclusão
Neste tutorial, exploramos o processo de adição de metadados XMP a um arquivo EPS usando a biblioteca Aspose.Page para Java. Esta ferramenta poderosa permite manipular documentos perfeitamente, aprimorando sua experiência geral de gerenciamento de documentos.
## Perguntas frequentes
### P: O uso do Aspose.Page for Java é gratuito?
 R: Aspose.Page for Java é um produto comercial. Você pode explorar seus recursos por meio de uma avaliação gratuita[aqui](https://releases.aspose.com/).
### P: Onde posso encontrar a documentação do Aspose.Page for Java?
 R: A documentação está disponível[aqui](https://reference.aspose.com/page/java/).
### P: Como posso obter uma licença temporária para Aspose.Page for Java?
 R: Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### P: Quais formatos de arquivo o Aspose.Page for Java suporta?
R: Aspose.Page for Java suporta vários formatos, incluindo EPS, PDF e XPS.
### P: Posso comprar Aspose.Page para Java?
 R: Sim, você pode comprar Aspose.Page para Java[aqui](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
