---
date: 2026-10-25
description: Aprenda a definir tamanho de página personalizado e adicionar páginas
  a documentos Java PostScript usando Aspose.Page. Siga nosso guia passo a passo para
  uma manipulação de documentos sem interrupções.
keywords:
- set custom page size
- Aspose.Page Java
- PostScript page manipulation
- add pages PostScript
lastmod: 2026-10-25
linktitle: Adicionando páginas em PostScript
og_description: Aprenda a definir tamanho de página personalizado em PostScript usando
  Aspose.Page para Java. Siga instruções passo a passo para adicionar páginas, definir
  dimensões e salvar o documento de forma eficiente.
og_image_alt: Aspose.Page Java tutorial showing how to set custom page size in a PostScript
  document
og_title: Defina tamanho de página personalizado em PostScript com Aspose.Page Java
schemas:
- author: Aspose
  dateModified: '2026-10-25'
  description: Learn how to set custom page size and add pages to Java PostScript
    documents using Aspose.Page. Follow our step‑by‑step guide for seamless document
    manipulation.
  headline: Aspose.Page Java Tutorial – set custom page size while Adding Pages in
    PostScript
  type: TechArticle
- questions:
  - answer: Yes—you can open pages with custom dimensions using `document.openPage(width,
      height)`.
    question: Can I set different page sizes for each page?
  - answer: A valid Aspose.Page license is required for non‑evaluation deployments.
    question: Do I need a license for production use?
  - answer: The library works with Java 8 and newer.
    question: Which Java versions are supported?
  - answer: Document instances are not thread‑safe; create a separate `PsDocument`
      per thread.
    question: Is the API thread‑safe?
  - answer: Aspose.Page handles multi‑megabyte files efficiently; memory usage scales
      with content, not page count.
    question: How large can a PostScript file be?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java PostScript
- custom page size
- add pages
- document generation
title: Tutorial Aspose.Page Java – definir tamanho de página personalizado ao adicionar
  páginas em PostScript
url: /pt/java/postscript-page-manipulation/add-pages2/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial Aspose.Page Java – definir tamanho de página personalizado ao adicionar páginas em PostScript

## Introdução
Em aplicações Java modernas, **set custom page size** para saída PostScript é frequentemente necessário—seja ao gerar faturas, tickets ou gráficos personalizados. Este tutorial mostra como definir tamanho de página personalizado para cada página, adicionar várias páginas e gerar um arquivo PostScript que corresponda às suas necessidades exatas de layout. Você receberá um exemplo completo e executável que pode ser inserido em qualquer projeto Java 8+.

## Respostas rápidas
- **Posso definir tamanhos de página diferentes para cada página?** Sim—você pode abrir páginas com dimensões personalizadas usando `document.openPage(width, height)`.  
- **Preciso de uma licença para uso em produção?** Uma licença válida do Aspose.Page é necessária para implantações não‑avaliativas.  
- **Quais versões do Java são suportadas?** A biblioteca funciona com Java 8 e versões mais recentes.  
- **A API é thread‑safe?** Instâncias de Document não são thread‑safe; crie um `PsDocument` separado por thread.  
- **Qual o tamanho máximo de um arquivo PostScript?** Aspose.Page lida com arquivos multi‑megabyte de forma eficiente; o uso de memória escala com o conteúdo, não com a contagem de páginas.  
- **Posso usar a sobrecarga open page width/height?** Absolutamente—`openPage(double width, double height)` permite especificar quaisquer dimensões em pontos.  

## Pré‑requisitos
Antes de começarmos, certifique‑se de que você tem:

- Um entendimento básico de programação Java.  
- Aspose.Page for Java adicionado ao seu projeto (Maven/Gradle ou JAR manual).  
- Um ambiente de desenvolvimento Java (IDE, JDK 8+).  

## Importar pacotes
As classes a seguir são necessárias: `FileOutputStream` para gravar arquivos, `PsDocument` para criar documentos PostScript e `PsSaveOptions` para configurar opções de saída.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Etapa 1: criar um documento PostScript multipáginas
`PsDocument` é a classe principal que representa um documento PostScript que pode conter várias páginas.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddPages2_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Set variable that indicates if resulting PostScript document will be multipaged
boolean multiPaged = true;
// Create new multipaged PS Document with one page opened
PsDocument document = new PsDocument(outPsStream, options, multiPaged);
```

## Etapa 2: adicionar conteúdo à primeira página
Com o documento pronto, você pode adicionar qualquer conteúdo necessário à primeira página. Quando terminar, feche a página para bloquear seu conteúdo.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Como definir tamanho de página personalizado
Você define um tamanho de página personalizado chamando `document.openPage(width, height)` com as dimensões desejadas em pontos antes de desenhar qualquer conteúdo. `openPage(width, height)` abre uma nova página com a largura e altura especificadas, dando controle total sobre a área da página. Se o tamanho de página padrão não for o que você precisa, pode **set custom page size** ao abrir uma nova página. Isso é útil para recibos, etiquetas ou qualquer layout não‑padrão.

## Etapa 3: adicionar uma segunda página com tamanho diferente
A seguir, abrimos uma segunda página e fornecemos explicitamente uma largura e altura personalizadas (em pontos). Isso demonstra como definir um tamanho de página personalizado para páginas individuais, permitindo que você trabalhe com **different page sizes** dentro do mesmo documento.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Etapa 4: salvar o documento
Finalmente, persista as alterações salvando o documento. Todas as páginas—incluindo as com tamanhos personalizados—são gravadas no arquivo de saída.

```java
// Save the document
document.save();
```

Seguindo estas etapas, você pode adicionar páginas de forma contínua e **set custom page size** em um documento PostScript Java usando Aspose.Page, proporcionando controle total sobre o layout de cada página.

## Por que usar Aspose.Page para definir tamanho de página personalizado?
Aspose.Page fornece controle preciso sobre as dimensões da página, permitindo definir qualquer largura e altura em pontos, combinar múltiplos tamanhos de página em um único documento e transmitir conteúdo de forma eficiente para geração de PostScript de alto desempenho. Isso o torna ideal para faturas, tickets e processamento em lote de grande escala onde o uso de memória deve permanecer baixo.

Aspose.Page permite definir dimensões exatas da página em pontos, combinar múltiplos tamanhos em um único arquivo e transmitir conteúdo de forma eficiente, o que oferece controle preciso e alto desempenho para gerar PostScript.  
- **Precisão:** As dimensões são definidas em pontos, proporcionando controle exato sobre a largura e altura da página.  
- **Flexibilidade:** Misture e combine **different page sizes** em um único arquivo PostScript.  
- **Desempenho:** A biblioteca transmite o conteúdo diretamente para o arquivo de saída, lidando com arquivos de até 500 MB enquanto mantém o uso de heap abaixo de 100 MB, tornando-a adequada para cenários de **generate PostScript file** em grande escala.  
- **API rica:** Suporta mais de 30 primitivas gráficas, 10 formatos de imagem e objetos de texto ilimitados por página—tudo enquanto respeita as dimensões personalizadas que você definiu.

## Problemas comuns e soluções
| Problema | Solução |
|----------|---------|
| **Page dimensions appear swapped** | Lembre‑se de que `openPage(width, height)` espera a largura primeiro, depois a altura (ambas em pontos). |
| **Content overflows the page** | Use o sistema de coordenadas `PsGraphics` para posicionar os elementos dentro dos limites personalizados, ou escale seu desenho. |
| **Out‑of‑memory errors on huge documents** | Habilite o streaming gravando diretamente em um `FileOutputStream` como mostrado, e evite carregar imagens grandes na memória de uma só vez. |

## Perguntas frequentes
### Posso adicionar páginas de tamanhos diferentes em um único documento PostScript?
Sim, como demonstrado neste tutorial, você pode adicionar páginas com tamanhos variados em um documento PostScript multipáginas.  

### Existem limitações no número de páginas que posso adicionar?
Aspose.Page suporta a adição de um número praticamente ilimitado de páginas a um documento.  

### Posso adicionar conteúdo personalizado, como imagens ou gráficos, às páginas?
Absolutamente! Aspose.Page permite adicionar uma ampla variedade de conteúdo, incluindo texto, imagens e outros elementos gráficos.  

### O Aspose.Page é adequado para lidar com documentos grandes?
Sim, o Aspose.Page foi projetado para lidar de forma eficiente tanto com documentos pequenos quanto grandes.  

### Onde posso encontrar recursos adicionais e suporte para Aspose.Page?
Explore a [Aspose.Page documentation](https://reference.aspose.com/page/java/), or visit the [Aspose.Page forum](https://forum.aspose.com/c/page/39) for community support.  

**Additional Q&A**

**Q:** *Quais formatos de imagem são suportados ao desenhar em uma página PostScript?*  
**A:** Você pode incorporar imagens PNG, JPEG, BMP e GIF diretamente usando a API de desenho.  

**Q:** *Como altero o DPI padrão do documento?*  
**A:** Defina `PsSaveOptions.setResolution(int dpi)` antes de criar o `PsDocument`.  

**Q:** *Posso criptografar um arquivo PostScript com senha?*  
**A:** O próprio PostScript não suporta criptografia, mas você pode envolver a saída em um PDF e aplicar configurações de segurança, se necessário.  

---

**Última atualização:** 2026-10-25  
**Testado com:** Aspose.Page for Java 24.10  
**Autor:** Aspose  

## Tutoriais Relacionados

- [Como definir tamanho de página A4 e criar PostScript em Java com Aspose.Page](/page/java/document-creation/postscript/)
- [Como converter PostScript para PDF usando Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)
- [Como desenhar retângulo em PostScript Java com Aspose.Page](/page/java/postscript-shapes/add-rectangle/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}