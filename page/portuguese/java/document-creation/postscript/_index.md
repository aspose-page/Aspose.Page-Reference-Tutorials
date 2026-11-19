---
date: 2026-11-19
description: Aprenda a criar arquivos PostScript em Java, definir o tamanho de página
  A4 e adicionar fontes personalizadas usando Aspose.Page. Experimente a versão de
  avaliação gratuita hoje!
keywords:
- create postscript file java
- add custom fonts java
- set a4 page size java
- aspose.page java
- postscript generation java
lastmod: 2026-11-19
linktitle: Criar documento em Java com PostScript
og_description: Aprenda a criar arquivo PostScript em Java, definir o tamanho de página
  A4 e adicionar fontes personalizadas com Aspose.Page. Guia rápido para desenvolvedores.
og_image_alt: Screenshot of Java code generating an A4 PostScript file with custom
  fonts using Aspose.Page
og_title: Criar arquivo PostScript em Java com tamanho A4 usando Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size
  steps:
  - name: set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: create save options with A4 size
    text: '`PsSaveOptions` defines how the PostScript document is saved, including
      page size, margins, and compression. **Definition:** `PsPageSize` is an enumeration
      that contains standard page‑size constants such as A4, Letter, and Legal. Setting
      `options.setPageSize(PsPageSize.A4)` configures the document f'
  - name: set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: create a multipaged or single‑paged PS document
    text: '`PsDocument` represents a PostScript document that can contain one or many
      pages. Instantiating it with `new PsDocument(outputStream, options)` creates
      the document object. Set `multiPaged` to `true` for multi‑page output, then
      call `document.newPage()` for each additional page you need.'
  - name: close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- create postscript
- Aspose.Page
- Java document processing
- custom fonts
- A4 page size
- author: Aspose
  dateModified: '2026-11-19'
  description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to create PostScript file in Java with A4 size using Aspose.Page
  type: TechArticle
- description: Learn how to create PostScript files in Java, set A4 page size, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to create PostScript file in Java with A4 size using Aspose.Page
  steps:
  - name: Set document directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define fonts folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create output stream for PostScript document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create save options with A4 size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set page margins and add custom fonts folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a multipaged or single‑paged PS document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close current page and save document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [Aspose.Page free trial page](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [API reference documentation](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [license purchase page](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page community forum [Aspose.Page community forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
title: Como criar arquivo PostScript em Java com tamanho A4
url: /pt/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar arquivo PostScript em Java com tamanho A4

## Introdução
Se você precisar **create PostScript file Java** enquanto define as dimensões padrão da página A4, o Aspose.Page for Java oferece uma API concisa e de alto desempenho que abstrai a sintaxe de baixo nível do PostScript. Neste tutorial, percorreremos cada passo — desde o carregamento da biblioteca e a configuração de `PsSaveOptions` até a incorporação de suas próprias fontes TrueType ou OpenType. Ao final, você terá um trecho pronto para execução que pode inserir em qualquer projeto Java.

## Respostas rápidas
- **Qual biblioteca cria PostScript em Java?** Aspose.Page for Java.  
- **Qual tamanho de página este guia aborda?** A4 (210 mm × 297 mm).  
- **Posso incorporar minhas próprias fontes?** Sim – defina a pasta de fontes adicionais nas opções de salvamento.  
- **Preciso de uma licença para produção?** É necessária uma licença comercial; uma versão de avaliação está disponível.  
- **Quais versões do Java são suportadas?** Java 8, 11 e 17 são totalmente suportadas.

## Como definir o tamanho de página A4 e criar PostScript em Java?
Carregue a biblioteca Aspose.Page, configure `PsSaveOptions` com as constantes A4 e escreva o documento em um arquivo — tudo em menos de dez linhas de código. Essa abordagem garante as dimensões corretas da página e permite adicionar fontes personalizadas sem configuração extra.

## O que é tamanho A4 em PostScript?
O tamanho A4 em PostScript é o padrão ISO 216 (210 mm × 297 mm) expresso na linguagem de descrição de página PostScript. Ele define a área imprimível que impressoras e visualizadores interpretam, garantindo layout consistente em todas as plataformas. Como o PostScript descreve o conteúdo da página de forma independente do dispositivo, usar o tamanho A4 garante que o documento aparecerá da mesma forma em qualquer impressora ou visualizador compatível com A4 em todo o mundo.

## Por que usar Aspose.Page para definir o tamanho da página PostScript?
Aspose.Page suporta mais de 30 operadores PostScript e pode gerar arquivos de até 500 MB sem carregar todo o documento na memória. Ele processa um documento de 200 páginas em menos de 2 segundos, oferecendo controle preciso sobre as dimensões da página enquanto lida com grandes cargas de trabalho de forma eficiente. A biblioteca também abstrai a sintaxe complexa do PostScript e gerencia recursos automaticamente, tornando-a ideal tanto para folhetos simples quanto para relatórios multi‑página complexos.

## Como adicionar fontes personalizadas em Java
Incorporar suas próprias tipografias garante que o documento gerado apareça exatamente como projetado em qualquer impressora ou visualizador, e o Aspose.Page descobre automaticamente as fontes colocadas na pasta especificada. Ao registrar uma pasta de fontes adicional, você pode usar qualquer fonte TrueType ou OpenType, evitar substituições de fallback e manter a consistência da marca em todos os dispositivos de saída.

## Pré-requisitos
Antes de começar, certifique-se de que você tem:

- Conhecimento prático de programação Java.  
- Aspose.Page for Java instalado. Você pode baixá-lo na [Aspose.Page Java download page](https://releases.aspose.com/page/java/).  
- Uma pasta chamada `necessary_fonts` (ou qualquer nome que preferir) que contenha as fontes personalizadas que deseja incorporar.

## Importar pacotes
No seu projeto Java, importe as classes necessárias do Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Now let’s break the example into clear, numbered steps.

### Etapa 1: definir diretório do documento
A constante `OUTPUT_DIR` informa à biblioteca onde gravar o arquivo gerado.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Etapa 2: definir pasta de fontes
`FONTS_FOLDER` aponta para o diretório que contém suas fontes TrueType ou OpenType personalizadas.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Etapa 3: criar fluxo de saída para documento PostScript
`FileOutputStream` abre um fluxo que receberá a saída final do PostScript A4.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Etapa 4: criar opções de salvamento com tamanho A4
`PsSaveOptions` define como o documento PostScript é salvo, incluindo tamanho da página, margens e compressão.  
**Definição:** `PsPageSize` é uma enumeração que contém constantes de tamanhos de página padrão, como A4, Letter e Legal.  
Definir `options.setPageSize(PsPageSize.A4)` configura o documento para as dimensões padrão A4.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Etapa 5: definir margens da página e adicionar pasta de fontes personalizadas
`options.setMargins(0, 0, 0, 0)` remove todas as margens para uma página sem bordas, e `options.setAdditionalFontsFolder(FONTS_FOLDER)` registra suas fontes personalizadas.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Etapa 6: criar um documento PS multipágina ou de página única
`PsDocument` representa um documento PostScript que pode conter uma ou várias páginas. Instanciá‑lo com `new PsDocument(outputStream, options)` cria o objeto documento. Defina `multiPaged` como `true` para saída multipágina, então chame `document.newPage()` para cada página adicional que precisar.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Etapa 7: fechar página atual e salvar documento
Chamar `document.close()` finaliza o arquivo e grava a saída **PostScript A4 size** no disco.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Problemas comuns e dicas
- **Fonte não aparece?** Verifique se o arquivo de fonte está em um formato TrueType ou OpenType suportado e se `FONTS_FOLDER` termina com uma barra (`/`).  
- **As margens ainda aparecem?** Chame `options.setMargins(...)` **antes** de construir o `PsDocument`.  
- **Saída multipágina aparece em branco?** Lembre‑se de invocar `document.newPage()` para cada página extra que precisar.  
- **Arquivos grandes causam erros de falta de memória?** Aspose.Page transmite os dados, então você pode gerar arquivos com segurança de até 500 MB; apenas garanta que o heap da JVM seja de pelo menos 1 GB para cargas de trabalho muito grandes.

## Perguntas frequentes

**Q: Posso usar fontes personalizadas no meu documento PostScript?**  
A: Sim, defina a pasta de fontes adicionais nas opções de salvamento (veja a Etapa 5) e o Aspose.Page incorporará as fontes automaticamente.

**Q: Existe uma versão de avaliação disponível para Aspose.Page for Java?**  
A: Sim, você pode obter uma avaliação gratuita na [Aspose.Page free trial page](https://releases.aspose.com/).

**Q: Como posso acessar a referência completa da API?**  
A: Consulte a documentação [API reference documentation](https://reference.aspose.com/page/java/).

**Q: Onde posso comprar uma licença para Aspose.Page for Java?**  
A: Você pode comprar uma licença na [license purchase page](https://purchase.aspose.com/buy).

**Q: Onde posso solicitar ajuda à comunidade?**  
A: Visite o fórum da comunidade Aspose.Page [Aspose.Page community forum](https://forum.aspose.com/c/page/39).

**Q: Posso gerar arquivos PostScript multipágina?**  
A: Absolutamente — defina `multiPaged` como `true` na Etapa 6 e chame `document.newPage()` para cada página extra.

## Conclusão
Seguindo estas etapas, você agora sabe **how to create PostScript file Java** e definir **A4 page size** usando o Aspose.Page, além de poder **add custom fonts java** e controlar as opções de tamanho de página. O Aspose.Page cuida do trabalho pesado, permitindo que você se concentre no conteúdo dos seus documentos em vez das complexidades da linguagem PostScript.

---

**Última atualização:** 2026-11-19  
**Testado com:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

## Tutoriais relacionados

- [Tutorial Aspose.Page Java – definir tamanho de página personalizado ao adicionar páginas em PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Como adicionar texto em PostScript com Aspose.Page for Java](/page/java/postscript-text-manipulation/)
- [Tutorial Aspose Page Java - Converter PostScript para PDF](/page/java/postscript-conversion/to-pdf/)

```java
document.closePage();
document.save();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}