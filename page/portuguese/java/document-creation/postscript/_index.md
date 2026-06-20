---
date: 2026-06-20
description: Aprenda a definir o tamanho de página A4, criar arquivos PostScript em
  Java e adicionar fontes personalizadas usando Aspose.Page. Experimente a avaliação
  gratuita hoje!
keywords:
- set a4 page size
- add custom fonts java
- java create postscript
linktitle: Criar documento em Java com PostScript
schemas:
- author: Aspose
  dateModified: '2026-06-20'
  description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  headline: How to set A4 page size and create PostScript in Java with Aspose.Page
  type: TechArticle
- description: Learn how to set A4 page size, create PostScript files in Java, and
    add custom fonts using Aspose.Page. Try the free trial today!
  name: How to set A4 page size and create PostScript in Java with Aspose.Page
  steps:
  - name: Set Document Directory
    text: The `OUTPUT_DIR` constant tells the library where to write the generated
      file.
  - name: Define Fonts Folder
    text: '`FONTS_FOLDER` points to the directory that holds your custom TrueType
      or OpenType fonts.'
  - name: Create Output Stream for PostScript Document
    text: '`FileOutputStream` opens a stream that will receive the final PostScript
      A4 output.'
  - name: Create Save Options with A4 Size
    text: '`PsSaveOptions` lets you specify the target page size. **Definition:**
      `PsPageSize` is an enumeration that contains standard page‑size constants such
      as A4, Letter, and Legal. Setting `options.setPageSize(PsPageSize.A4)` configures
      the document for standard A4 dimensions.'
  - name: Set Page Margins and Add Custom Fonts Folder
    text: '`options.setMargins(0, 0, 0, 0)` removes all margins for a full‑bleed page,
      and `options.setAdditionalFontsFolder(FONTS_FOLDER)` registers your custom fonts.'
  - name: Create a Multipaged or Single‑Paged PS Document
    text: '`PsDocument document = new PsDocument(outputStream, options)` creates the
      document. `PsDocument` represents a PostScript document that can contain one
      or many pages. Set `multiPaged` to `true` for multi‑page output.'
  - name: Close Current Page and Save Document
    text: Calling `document.close()` finalises the file and writes the **PostScript
      A4 size** output to disk.
  type: HowTo
- questions:
  - answer: Yes, set the additional fonts folder in the save options (see Step 5)
      and Aspose.Page will embed the fonts automatically.
    question: Can I use custom fonts in my PostScript document?
  - answer: Yes, you can get a free trial [here](https://releases.aspose.com/).
    question: Is there a trial version available for Aspose.Page for Java?
  - answer: Refer to the documentation [here](https://reference.aspose.com/page/java/).
    question: How can I access the full API reference?
  - answer: You can buy a license [here](https://purchase.aspose.com/buy).
    question: Where do I purchase a license for Aspose.Page for Java?
  - answer: Visit the Aspose.Page forum [forum](https://forum.aspose.com/c/page/39).
    question: Where can I ask the community for help?
  type: FAQPage
second_title: Aspose.Page Java API
title: Como definir o tamanho de página A4 e criar PostScript em Java com Aspose.Page
url: /pt/java/document-creation/postscript/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como definir o tamanho de página A4 e criar PostScript em Java com Aspose.Page

## Introdução
Se você precisa **definir o tamanho de página a4** ao gerar arquivos PostScript a partir de Java, Aspose.Page oferece uma API rápida e confiável que oculta os detalhes de baixo nível. Neste tutorial, percorreremos todo o fluxo de trabalho — criando um documento PostScript, configurando as dimensões da página A4 e **adicionando fontes personalizadas** quando necessário. Ao final, você terá um trecho de código pronto para uso que pode inserir em qualquer projeto Java.

## Respostas Rápidas
- **Qual biblioteca cria PostScript em Java?** Aspose.Page for Java.  
- **Qual tamanho de página este guia aborda?** A4 (210 mm × 297 mm).  
- **Posso incorporar minhas próprias fontes?** Yes – set the additional fonts folder in the save options.  
- **Preciso de uma licença para produção?** A commercial license is required; a free trial is available.  
- **Quais versões do Java são suportadas?** Java 8 and later.

## Como definir o tamanho de página a4 e criar postscript em Java
Carregue a biblioteca Aspose.Page, configure `PsSaveOptions` com as constantes A4 e escreva o documento em um arquivo — tudo em menos de dez linhas de código. Essa abordagem direta garante as dimensões corretas da página e permite adicionar fontes personalizadas sem configuração extra.

## Qual é o tamanho A4 do PostScript?
O tamanho A4 do PostScript é o padrão ISO 216 (210 mm × 297 mm) expresso na linguagem de descrição de página PostScript. Ele define a área imprimível que impressoras e visualizadores interpretam, garantindo layout consistente em todas as plataformas. Como o PostScript descreve o conteúdo da página de forma independente do dispositivo, usar o tamanho A4 garante que o documento aparecerá da mesma forma em qualquer impressora ou visualizador compatível com A4 em todo o mundo.

## Por que usar Aspose.Page para definir o tamanho da página postscript?
Aspose.Page suporta **30+ operadores PostScript** e pode gerar arquivos de até **500 MB** sem carregar o documento inteiro na memória. Isso oferece controle preciso sobre as dimensões da página ao lidar com grandes cargas de trabalho de forma eficiente. A biblioteca também abstrai a sintaxe complexa do PostScript, gerencia recursos automaticamente e fornece streaming de alto desempenho, tornando-a ideal tanto para folhetos simples de uma página quanto para relatórios complexos de várias páginas.

## Como adicionar fontes personalizadas em Java
Incorporar suas próprias tipografias garante que o documento gerado tenha exatamente a aparência projetada em qualquer impressora ou visualizador, e o Aspose.Page descobre automaticamente as fontes colocadas na pasta especificada. Ao registrar uma pasta adicional de fontes, você pode usar qualquer fonte TrueType ou OpenType, evitar substituições de fallback e manter a consistência da marca em todos os dispositivos de saída.

## Pré-requisitos
- Um conhecimento prático de programação Java.  
- Aspose.Page para Java instalado. Você pode baixá-lo [aqui](https://releases.aspose.com/page/java/).  
- Uma pasta chamada `necessary_fonts` (ou qualquer nome que preferir) que contém as fontes personalizadas que você deseja incorporar.

## Importar Pacotes
No seu projeto Java, importe as classes necessárias do Aspose.Page:

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

Now let’s break the example into clear, numbered steps.

### Etapa 1: Definir Diretório do Documento
A constante `OUTPUT_DIR` informa à biblioteca onde gravar o arquivo gerado.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PageConstants;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

### Etapa 2: Definir Pasta de Fontes
`FONTS_FOLDER` aponta para o diretório que contém suas fontes TrueType ou OpenType personalizadas.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

### Etapa 3: Criar Fluxo de Saída para o Documento PostScript
`FileOutputStream` abre um fluxo que receberá a saída final do PostScript A4.

```java
String FONTS_FOLDER = dataDir + "necessary_fonts/";
```

### Etapa 4: Criar Opções de Salvamento com Tamanho A4
`PsSaveOptions` permite especificar o tamanho da página de destino.  
**Definição:** `PsPageSize` é uma enumeração que contém constantes de tamanhos de página padrão, como A4, Letter e Legal.  
Definir `options.setPageSize(PsPageSize.A4)` configura o documento para as dimensões padrão A4.

```java
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "CreateDocument_outPS.ps");
```

### Etapa 5: Definir Margens da Página e Adicionar Pasta de Fontes Personalizadas
`options.setMargins(0, 0, 0, 0)` remove todas as margens para uma página sem bordas, e `options.setAdditionalFontsFolder(FONTS_FOLDER)` registra suas fontes personalizadas.

```java
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setPageSize(PageConstants.getSize(PageConstants.SIZE_A4, PageConstants.ORIENTATION_PORTRAIT));
```

### Etapa 6: Criar um Documento PS Multipágina ou de Página Única
`PsDocument document = new PsDocument(outputStream, options)` cria o documento. `PsDocument` representa um documento PostScript que pode conter uma ou várias páginas. Defina `multiPaged` como `true` para saída multipágina.

```java
options.setMargins(PageConstants.getMargins(PageConstants.MARGINS_ZERO));
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
```

### Etapa 7: Fechar a Página Atual e Salvar o Documento
Chamar `document.close()` finaliza o arquivo e grava a saída **PostScript A4 size** no disco.

```java
boolean multiPaged = false;
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Problemas Comuns & Dicas
- **Fonte não aparece?** Verifique se o arquivo de fonte está em um formato TrueType ou OpenType suportado e se `FONTS_FOLDER` termina com uma barra (`/`).  
- **Margens ainda aparecem?** Chame `options.setMargins(...)` **antes** de construir o `PsDocument`.  
- **Saída multipágina aparece em branco?** Lembre-se de invocar `document.newPage()` para cada página adicional que precisar.

## Perguntas Frequentes

**Q: Posso usar fontes personalizadas no meu documento PostScript?**  
A: Sim, defina a pasta de fontes adicionais nas opções de salvamento (veja a Etapa 5) e o Aspose.Page incorporará as fontes automaticamente.

**Q: Existe uma versão de avaliação disponível para Aspose.Page para Java?**  
A: Sim, você pode obter uma avaliação gratuita [aqui](https://releases.aspose.com/).

**Q: Como posso acessar a referência completa da API?**  
A: Consulte a documentação [aqui](https://reference.aspose.com/page/java/).

**Q: Onde posso comprar uma licença para Aspose.Page para Java?**  
A: Você pode comprar uma licença [aqui](https://purchase.aspose.com/buy).

**Q: Onde posso solicitar ajuda à comunidade?**  
A: Visite o fórum Aspose.Page [forum](https://forum.aspose.com/c/page/39).

**Q: Posso gerar arquivos PostScript multipágina?**  
A: Absolutamente — defina `multiPaged` como `true` na Etapa 6 e chame `document.newPage()` para cada página extra.

## Conclusão
Seguindo estas etapas, você agora sabe **como definir o tamanho de página a4** e criar arquivos **PostScript** em Java com Aspose.Page, além de poder **adicionar fontes personalizadas java** e controlar as opções de tamanho de página. Aspose.Page cuida do trabalho pesado, permitindo que você se concentre no conteúdo dos seus documentos.

---
**Última atualização:** 2026-06-20  
**Testado com:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Tutorial Aspose.Page Java – definir tamanho de página personalizado ao adicionar páginas em PostScript](/page/java/postscript-page-manipulation/add-pages2/)
- [Como adicionar texto em PostScript com Aspose.Page para Java](/page/java/postscript-text-manipulation/)
- [Tutorial Aspose Page Java - Converter PostScript para PDF](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

```java
document.closePage();
document.save();
```