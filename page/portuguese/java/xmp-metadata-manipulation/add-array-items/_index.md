---
title: Adicionar itens de array em metadados XMP usando Java
linktitle: Adicionar itens de array em metadados XMP usando Java
second_title: API Java Aspose.Page
description: Aprimore arquivos EPS com Aspose.Page para Java. Aprenda a adicionar itens de array aos metadados XMP sem esforço. Siga nosso guia passo a passo agora!
weight: 10
url: /pt/java/xmp-metadata-manipulation/add-array-items/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar itens de array em metadados XMP usando Java

## Introdução
Bem-vindo ao nosso guia passo a passo sobre como usar Aspose.Page for Java para adicionar itens de array em metadados XMP. Aspose.Page é uma poderosa biblioteca Java que permite manipular e trabalhar com vários formatos de documentos, incluindo arquivos EPS. Neste tutorial, focaremos na tarefa específica de adicionar itens de array em metadados XMP usando Java.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos:
- Biblioteca Aspose.Page para Java instalada.
- Compreensão básica de programação Java.
- Um arquivo EPS válido com metadados XMP existentes ou comentários de metadados PS.
## Importar pacotes
Para começar, você precisa importar os pacotes necessários para trabalhar com Aspose.Page. Inclua as seguintes linhas no início do seu arquivo Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
## Etapa 1: Obtenha metadados XMP
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Inicializar fluxo de arquivo EPS de entrada
FileInputStream psStream = new FileInputStream(dataDir + "xmp3.eps");
PsDocument document = new PsDocument(psStream);
// Obtenha metadados XMP. Se o arquivo EPS não contiver metadados XMP, obteremos um novo preenchido com valores de comentários de metadados PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
Nesta etapa, recuperamos os metadados XMP existentes do arquivo EPS. Se o arquivo EPS ainda não contém metadados XMP, Aspose.Page gera um novo e o preenche com valores de comentários de metadados PS.
## Etapa 2: adicionar item de matriz "dc:title"
```java
// Adicione mais um item da matriz "dc:title"
xmp.addArrayItem("dc:title", new XmpValue("NewTitle"));
```
Agora, adicionamos um novo item do array à propriedade “dc:title” nos metadados XMP. Substitua “NewTitle” pelo título desejado.
## Etapa 3: adicionar item de matriz "dc: creator"
```java
// Adicione mais um item de array "dc:creator"
xmp.addArrayItem("dc:creator", new XmpValue("NewCreator"));
```
Da mesma forma, adicionamos um novo item de array à propriedade “dc:creator” nos metadados XMP. Substitua “NewCreator” pelas informações do criador desejado.
## Etapa 4: inicializar o fluxo de arquivos EPS de saída
```java
// Inicializar fluxo de arquivo EPS de saída
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp3_changed.eps");
```
Prepare o fluxo de arquivo EPS de saída onde o documento modificado com metadados XMP atualizados será salvo.
## Etapa 5: Salvar documento com metadados XMP alterados
```java
//Salvar documento com metadados XMP alterados
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
Salve o documento com os metadados XMP atualizados no arquivo EPS de saída.
## Conclusão
Parabéns! Você aprendeu como adicionar itens de array em metadados XMP usando Aspose.Page para Java. Esta poderosa biblioteca simplifica o processo de manipulação de arquivos EPS e fornece ampla funcionalidade para processamento de documentos.
## perguntas frequentes

### Posso usar Aspose.Page for Java com outros formatos de documentos?
Sim, Aspose.Page oferece suporte a vários formatos de documento, incluindo EPS, PDF e XPS.
### Existe uma avaliação gratuita disponível para Aspose.Page for Java?
 Sim, você pode acessar o teste gratuito[aqui](https://releases.aspose.com/).
### Onde posso encontrar a documentação do Aspose.Page for Java?
 A documentação está disponível[aqui](https://reference.aspose.com/page/java/).
### Como posso comprar Aspose.Page para Java?
 Você pode comprar o produto[aqui](https://purchase.aspose.com/buy).
### As licenças temporárias estão disponíveis para Aspose.Page for Java?
 Sim, você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
