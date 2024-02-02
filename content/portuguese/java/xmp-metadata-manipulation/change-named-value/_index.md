---
title: Alterar valor nomeado em XMP usando Java
linktitle: Alterar valor nomeado em XMP usando Java
second_title: API Java Aspose.Page
description: Descubra Aspose.Page para Java - altere facilmente metadados XMP em arquivos EPS com nosso guia passo a passo para processamento simplificado de documentos.
type: docs
weight: 16
url: /pt/java/xmp-metadata-manipulation/change-named-value/
---
No domínio da manipulação de documentos, Aspose.Page for Java se destaca como uma ferramenta poderosa, permitindo que os desenvolvedores trabalhem perfeitamente com metadados XMP em arquivos EPS. Este guia passo a passo orientará você no processo de alteração de um valor nomeado em XMP usando Aspose.Page para Java. Antes de nos aprofundarmos nos detalhes, vamos preparar o cenário com uma introdução.
## Introdução
Aspose.Page for Java é uma biblioteca Java robusta que facilita a manipulação e processamento de arquivos EPS. Quando se trata de lidar com metadados XMP nesses arquivos, Aspose.Page capacita os desenvolvedores com um conjunto abrangente de recursos. Neste tutorial, focaremos na alteração de um valor nomeado em XMP, oferecendo um guia claro e conciso para desenvolvedores que buscam aprimorar seus recursos de processamento de documentos.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
1. Ambiente de desenvolvimento Java: certifique-se de ter um ambiente de desenvolvimento Java configurado em sua máquina.
2.  Biblioteca Aspose.Page for Java: Baixe e integre a biblioteca Aspose.Page for Java ao seu projeto. Você pode encontrar a biblioteca e documentação detalhada[aqui](https://reference.aspose.com/page/java/).
3. Arquivo EPS de amostra: tenha um arquivo EPS de amostra pronto para experimentação. Se não tiver um, você pode usar o arquivo de exemplo fornecido chamado “xmp4.eps”.
## Importar pacotes
Para iniciar o processo, importe os pacotes necessários em seu código Java. Esses pacotes são essenciais para interagir com Aspose.Page for Java. Inclua as seguintes linhas no início do seu arquivo Java:
```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```
Agora, vamos dividir o processo de alteração de um valor nomeado em XMP usando Aspose.Page for Java em várias etapas:
## Etapa 1: inicializar o fluxo de arquivos EPS de entrada
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
        
// Inicializar fluxo de arquivo EPS de entrada
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```
## Etapa 2: inicializar PsDocument
```java
PsDocument document = new PsDocument(psStream);
```
## Etapa 3: Obtenha metadados XMP
```java
// Obtenha metadados XMP. Se o arquivo EPS não contiver metadados XMP, obteremos um novo preenchido com valores de comentários de metadados PS (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```
## Etapa 4: definir novo valor em XMP
```java
// Defina o novo valor de string "Inches" para o valor nomeado "stDim:unit" da estrutura "xmpTPg:MaxPageSize"
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```
## Etapa 5: inicializar o fluxo de arquivos EPS de saída
```java
// Inicializar fluxo de arquivo EPS de saída
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```
## Etapa 6: Salvar documento com metadados XMP alterados
```java
//Salvar documento com metadados XMP alterados
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```
## Etapa 7: feche o fluxo EPS de entrada
```java
// Fechar fluxo EPS de entrada
psStream.close();
```
Este guia passo a passo garante uma abordagem sistemática para alterar um valor nomeado em XMP usando Aspose.Page para Java. Seguindo essas etapas, você pode integrar perfeitamente essa funcionalidade aos seus aplicativos Java.
## Conclusão
Concluindo, Aspose.Page for Java simplifica o processo de trabalho com metadados XMP em arquivos EPS. Este tutorial equipou você com o conhecimento necessário para alterar com eficiência um valor nomeado em XMP, aprimorando seus recursos de processamento de documentos.
## perguntas frequentes
### Posso usar Aspose.Page for Java com outras linguagens de programação?
Aspose.Page oferece suporte principalmente a Java, mas Aspose fornece bibliotecas semelhantes para várias linguagens de programação.
### Existe uma avaliação gratuita disponível para Aspose.Page for Java?
 Sim, você pode explorar uma avaliação gratuita do Aspose.Page para Java[aqui](https://releases.aspose.com/).
### Onde posso encontrar suporte e discussões adicionais sobre Aspose.Page for Java?
 Visite a[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para apoio e discussões da comunidade.
### Como posso obter uma licença temporária para Aspose.Page for Java?
 Você pode adquirir uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso comprar Aspose.Page para Java?
 Para comprar Aspose.Page para Java, visite o[página de compra](https://purchase.aspose.com/buy).