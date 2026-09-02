---
date: 2026-05-15
description: Aprenda como editar metadados XMP e como alterar valores XMP em arquivos
  EPS com Aspose.Page for Java – um guia claro passo a passo.
keywords:
- how to edit xmp
- how to change xmp
- Aspose.Page XMP Java
- edit EPS metadata
- XMP manipulation Java
linktitle: Alterar Valor Nomeado em XMP usando Java
schemas:
- author: Aspose
  dateModified: '2026-05-15'
  description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  headline: how to edit xmp – Change Named Value in XMP using Java
  type: TechArticle
- description: Learn how to edit XMP metadata and how to change XMP values in EPS
    files with Aspose.Page for Java – a clear step‑by‑step guide.
  name: how to edit xmp – Change Named Value in XMP using Java
  steps:
  - name: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
    text: '**Java Development Environment** – A JDK (8 or higher) and an IDE or build
      tool (Maven/Gradle).'
  - name: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
    text: '**Aspose.Page for Java Library** – Download and integrate the Aspose.Page
      for Java library into your project. You can find the library and detailed documentation
      [here](https://reference.aspose.com/page/java/).'
  - name: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
    text: '**Sample EPS File** – Have a sample EPS file ready for experimentation.
      If you don''t have one, use the provided example file named **"xmp4.eps."**'
  type: HowTo
- questions:
  - answer: Aspose.Page primarily supports Java, but Aspose offers equivalent libraries
      for .NET, C++, and Python that expose similar XMP manipulation capabilities.
    question: Can I use Aspose.Page for Java with other programming languages?
  - answer: Yes, you can explore a free trial of Aspose.Page for Java [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for
      community support and discussions.
    question: Where can I find additional support and discussions about Aspose.Page
      for Java?
  - answer: You can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
    question: How can I obtain a temporary license for Aspose.Page for Java?
  - answer: To buy Aspose.Page for Java, visit the [purchase page](https://purchase.aspose.com/buy).
    question: Where can I purchase Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
title: como editar xmp – Alterar Valor Nomeado em XMP usando Java
url: /pt/java/xmp-metadata-manipulation/change-named-value/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como editar XMP – Alterar Valor Nomeado em XMP usando Java

Nos fluxos de trabalho modernos de documentos, **Aspose.Page for Java** facilita a leitura, edição e gravação de metadados XMP dentro de arquivos EPS. **Este tutorial mostra como editar metadados XMP** em documentos EPS usando a API Aspose.Page, para que você possa manter as informações do seu documento precisas, pesquisáveis e em conformidade com os padrões da indústria. Seja atualizando dimensões da página, informações do autor ou tags personalizadas, os passos abaixo orientam o processo em Java.

## Respostas Rápidas
- **O que este tutorial cobre?** Alterar um valor XMP nomeado em um arquivo EPS com Aspose.Page for Java.  
- **Qual versão da biblioteca é necessária?** Qualquer versão recente do Aspose.Page for Java (a API tem sido estável por vários anos).  
- **Preciso de uma licença?** Uma licença temporária ou completa é necessária para produção; um teste gratuito funciona para testes.  
- **Quanto tempo leva a implementação?** Aproximadamente 10‑15 minutos para um desenvolvedor familiarizado com Java I/O.  
- **Posso usar isso com outros formatos de arquivo?** A API XMP também está disponível para PDF, SVG e outros formatos suportados pelo Aspose.Page.

## O que são metadados XMP?
XMP (Extensible Metadata Platform) é um formato padronizado baseado em XML para incorporar metadados ricos — como criador, título e propriedades personalizadas — diretamente dentro dos arquivos. Em documentos EPS, o XMP convive com os comentários tradicionais de PostScript, permitindo que aplicativos leiam e modifiquem metadados sem alterar o conteúdo visual.

## Por que usar Aspose.Page for Java para editar XMP?
Aspose.Page oferece **controle total sobre mais de 150 propriedades de esquema XMP** e funciona de forma consistente em formatos EPS, PDF e SVG. Ele processa arquivos de até **500 MB** sem carregar todo o documento na memória, e inclui validação incorporada que garante que o EPS resultante permaneça em conformidade com os padrões. Nenhum analisador XML externo ou bibliotecas nativas são necessários.

## Introdução
Aspose.Page for Java é uma biblioteca robusta que facilita a manipulação e o processamento de arquivos EPS. Quando se trata de lidar com metadados XMP dentro desses arquivos, o Aspose.Page capacita os desenvolvedores com um conjunto abrangente de recursos. Neste tutorial, focaremos em alterar um valor nomeado em XMP, oferecendo um guia claro e conciso para desenvolvedores que desejam aprimorar suas capacidades de processamento de documentos.

## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de que você tem os seguintes pré-requisitos:
1. **Ambiente de Desenvolvimento Java** – Um JDK (8 ou superior) e uma IDE ou ferramenta de construção (Maven/Gradle).  
2. **Biblioteca Aspose.Page for Java** – Baixe e integre a biblioteca Aspose.Page for Java ao seu projeto. Você pode encontrar a biblioteca e a documentação detalhada [aqui](https://reference.aspose.com/page/java/).  
3. **Arquivo EPS de Exemplo** – Tenha um arquivo EPS de exemplo pronto para experimentação. Se você não tiver um, use o arquivo de exemplo fornecido chamado **"xmp4.eps"**.

## Importar Pacotes
As declarações `import` trazem as classes essenciais do Aspose.Page para o escopo.

A classe `PsDocument` é o objeto central do Aspose.Page que representa um documento EPS na memória.  
A classe `XmpMetadata` fornece acesso ao pacote XMP incorporado no arquivo EPS.  

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.xmp.XmpMetadata;
import com.aspose.eps.xmp.XmpValue;
import com.aspose.page.BaseExamplesTest;
import com.aspose.page.License;
```

## Como editar metadados XMP?
Carregue o arquivo EPS, recupere seu pacote XMP, modifique a propriedade desejada e salve o documento — tudo em algumas linhas simples. Essa abordagem funciona para qualquer valor XMP nomeado, seja um campo padrão Dublin Core ou um namespace personalizado que você definiu.

## Etapa 1: Inicializar Fluxo de Arquivo EPS de Entrada
`FileInputStream` abre um fluxo somente leitura para o arquivo EPS de origem, permitindo que o Aspose.Page ingira o documento sem bloquear o sistema de arquivos.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
        
// Initialize input EPS file stream
FileInputStream psStream = new FileInputStream(dataDir + "xmp4.eps");
```

## Etapa 2: Inicializar PsDocument
`PsDocument` é o objeto principal que encapsula o conteúdo EPS e fornece acesso aos seus metadados, páginas e recursos.

```java
PsDocument document = new PsDocument(psStream);
```

## Etapa 3: Obter Metadados XMP
`XmpMetadata` representa o pacote XMP dentro do arquivo EPS e oferece métodos para ler, modificar ou excluir propriedades individuais.

```java
// Get XMP metadata. If EPS file doesn't contain XMP metadata, we get a new one filled with values from PS metadata comments (%%Creator, %%CreateDate, %%Title, etc.)
XmpMetadata xmp = document.getXmpMetadata();
```

## Etapa 4: Definir Novo Valor no XMP
`setProperty` define o valor de uma propriedade XMP especificada no pacote de metadados.

```java
// Set new string value "Inches" for named value "stDim:unit" of structure "xmpTPg:MaxPageSize" 
xmp.setNamedValue("xmpTPg:MaxPageSize", "stDim:unit", new XmpValue("Inches"));
```

## Etapa 5: Inicializar Fluxo de Arquivo EPS de Saída
`FileOutputStream` cria um fluxo gravável para salvar o arquivo EPS modificado.

```java
// Initialize output EPS file stream
FileOutputStream outPsStream = new FileOutputStream(dataDir + "xmp4_changed.eps");
```

## Etapa 6: Salvar Documento com Metadados XMP Alterados
`save` grava o PsDocument em memória, incluindo o XMP atualizado, no fluxo de saída.

```java
// Save document with changed XMP metadata
try {			
    document.save(outPsStream);
} finally {
    outPsStream.close();
}
```

## Etapa 7: Fechar Fluxo de Entrada EPS
`close` libera o manipulador de arquivo e libera os recursos associados ao fluxo de entrada.

```java
// Close input EPS stream
psStream.close();
```

## Problemas Comuns e Soluções
- **FileNotFoundException** – Verifique se `dataDir` aponta para a pasta correta e se `xmp4.eps` existe.  
- **LicenseException** – Se você vir erros de licença, certifique-se de que um arquivo de licença válido do Aspose.Page esteja carregado antes de criar o `PsDocument`.  
- **Metadata Not Updated** – Após salvar, abra o EPS resultante em um visualizador de metadados (por exemplo, Adobe Bridge) para confirmar que o novo valor aparece.

## Perguntas Frequentes
**P: Posso usar Aspose.Page for Java com outras linguagens de programação?**  
R: Aspose.Page suporta principalmente Java, mas a Aspose oferece bibliotecas equivalentes para .NET, C++ e Python que expõem capacidades semelhantes de manipulação de XMP.

**P: Existe um teste gratuito disponível para Aspose.Page for Java?**  
R: Sim, você pode experimentar um teste gratuito do Aspose.Page for Java [aqui](https://releases.aspose.com/).

**P: Onde posso encontrar suporte adicional e discussões sobre Aspose.Page for Java?**  
R: Visite o [forum Aspose.Page](https://forum.aspose.com/c/page/39) para suporte da comunidade e discussões.

**P: Como posso obter uma licença temporária para Aspose.Page for Java?**  
R: Você pode adquirir uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**P: Onde posso comprar Aspose.Page for Java?**  
R: Para comprar Aspose.Page for Java, visite a [página de compra](https://purchase.aspose.com/buy).

---

**Última atualização:** 2026-05-15  
**Testado com:** Aspose.Page for Java (última versão)  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como ler metadados XMP usando Java – Guia Aspose.Page](/page/java/xmp-metadata-manipulation/get-metadata/)
- [Tutorial Aspose Page Java – Adicionar metadados XMP a arquivos EPS](/page/java/xmp-metadata-manipulation/add-metadata/)
- [aspose.page modificar xmp – Alterar valores em XMP usando Java](/page/java/xmp-metadata-manipulation/change-values/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}