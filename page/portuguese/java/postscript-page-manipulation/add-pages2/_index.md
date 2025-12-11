---
date: 2025-12-11
description: Aprenda como definir tamanho de página personalizado e adicionar páginas
  a documentos PostScript Java usando Aspose.Page. Siga nosso guia passo a passo para
  uma manipulação de documentos perfeita.
linktitle: Adding Pages in PostScript
second_title: Aspose.Page Java API
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
Em aplicações Java modernas, **definir um tamanho de página personalizado** para a saída PostScript é frequentemente necessário—seja ao gerar faturas, tickets ou gráficos personalizados. Aspose.Page for Java torna essa tarefa simples. Neste tutorial você aprenderá como adicionar páginas e definir tamanhos de página personalizados em um documento PostScript, passo a passo, para que possa produzir exatamente o layout correto a cada vez.

## Respostas Rápidas
- **Posso definir tamanhos de página diferentes para cada página?** Sim, você pode abrir páginas com dimensões personalizadas usando `document.openPage(width, height)`.  
- **Preciso de uma licença para uso em produção?** Uma licença válida do Aspose.Page é necessária para implantações que não sejam de avaliação.  
- **Quais versões do Java são suportadas?** A biblioteca funciona com Java 8 e versões mais recentes.  
- **A API é thread‑safe?** Instâncias de Document não são thread‑safe; crie um `PsDocument` separado por thread.  
- **Qual o tamanho máximo de um arquivo PostScript?** Aspose.Page lida com arquivos de vários megabytes de forma eficiente; o uso de memória escala com o conteúdo, não com a quantidade de páginas.

## Pré‑requisitos
Antes de começarmos, certifique‑se de que você tem:

- Um entendimento básico de programação Java.  
- Aspose.Page for Java adicionado ao seu projeto (Maven/Gradle ou JAR manual).  
- Um ambiente de desenvolvimento Java (IDE, JDK 8+).  

## Importar Pacotes
Para começar, importe as classes necessárias da biblioteca Aspose.Page.

```java
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Etapa 1: Criar um Documento PostScript Multipágina
Primeiro, crie um novo `PsDocument` configurado para múltiplas páginas. Isso configura o fluxo de saída e informa à biblioteca que estaremos trabalhando com um arquivo multipágina.

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

## Etapa 2: Adicionar Conteúdo à Primeira Página
Com o documento pronto, você pode adicionar qualquer conteúdo necessário à primeira página. Quando terminar, feche a página para bloquear seu conteúdo.

```java
// Add content to the first page
// Close the first page
document.closePage();
```

## Como definir tamanho de página personalizado
Se o tamanho de página padrão não for o que você precisa, pode **definir um tamanho de página personalizado** ao abrir uma nova página. Isso é útil para recibos, etiquetas ou qualquer layout não‑padrão.

## Etapa 3: Adicionar uma Segunda Página com Tamanho Diferente
A seguir, abrimos uma segunda página e fornecemos explicitamente uma largura e altura personalizadas (em pontos). Isso demonstra como definir um tamanho de página personalizado para páginas individuais.

```java
// Add the second page with a different size
document.openPage(500, 300);
// Add content to the second page
// Close the second page
document.closePage();
```

## Etapa 4: Salvar o Documento
Finalmente, persista as alterações salvando o documento. Todas as páginas—incluindo aquelas com tamanhos personalizados—são gravadas no arquivo de saída.

```java
// Save the document
document.save();
```

Seguindo estas etapas, você pode adicionar páginas e **definir tamanhos de página personalizados** em um documento PostScript Java usando Aspose.Page, proporcionando controle total sobre o layout de cada página.

## Conclusão
Aspose.Page for Java oferece uma API robusta e amigável ao desenvolvedor para manipular documentos PostScript. Agora você sabe como adicionar múltiplas páginas, aplicar dimensões personalizadas e salvar o resultado—capacitando-o a gerar saídas formatadas com precisão para qualquer solução baseada em Java.

## Perguntas Frequentes
### Posso adicionar páginas de tamanhos diferentes em um único documento PostScript?
Sim, como demonstrado neste tutorial, você pode adicionar páginas com tamanhos variados em um documento PostScript multipágina.  
### Existem limitações no número de páginas que posso adicionar?
Aspose.Page suporta a adição de um número praticamente ilimitado de páginas a um documento.  
### Posso adicionar conteúdo personalizado, como imagens ou gráficos, às páginas?
Absolutamente! Aspose.Page permite adicionar uma ampla variedade de conteúdo, incluindo texto, imagens e outros elementos gráficos.  
### O Aspose.Page é adequado para lidar com documentos grandes?
Sim, Aspose.Page foi projetado para lidar de forma eficiente tanto com documentos pequenos quanto grandes.  
### Onde posso encontrar recursos adicionais e suporte para Aspose.Page?
Explore a [documentação do Aspose.Page](https://reference.aspose.com/page/java/), ou visite o [fórum do Aspose.Page](https://forum.aspose.com/c/page/39) para suporte da comunidade.  

**Additional Q&A**

**Q:** *Quais formatos de imagem são suportados ao desenhar em uma página PostScript?*  
**A:** Você pode incorporar imagens PNG, JPEG, BMP e GIF diretamente usando a API de desenho.  

**Q:** *Como altero o DPI padrão do documento?*  
**A:** Defina `PsSaveOptions.setResolution(int dpi)` antes de criar o `PsDocument`.  

**Q:** *Posso criptografar um arquivo PostScript com senha?*  
**A:** O PostScript em si não suporta criptografia, mas você pode envolver a saída em um PDF e aplicar configurações de segurança, se necessário.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2025-12-11  
**Testado com:** Aspose.Page for Java 24.10  
**Autor:** Aspose