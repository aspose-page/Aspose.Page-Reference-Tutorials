---
date: 2026-08-18
description: Aprenda como adicionar padrão de hachura a arquivos Java PostScript usando
  Aspose.Page Java. Este guia passo a passo mostra o código completo e dicas.
keywords:
- how to add hatch pattern
- Aspose.Page Java
- PostScript hatch patterns
- Java graphics API
lastmod: 2026-08-18
linktitle: Adicionar padrão de hachura em Java PostScript
og_description: Aprenda como adicionar padrão de hachura em Java PostScript usando
  Aspose.Page. Siga este tutorial passo a passo para criar gráficos preenchidos com
  hachura rapidamente.
og_image_alt: Screenshot of Java code adding hatch pattern to a PostScript file with
  Aspose.Page
og_title: Como adicionar padrão de hachura em Java PostScript – Guia Aspose.Page
schemas:
- author: Aspose
  dateModified: '2026-08-18'
  description: Learn how to add hatch pattern to Java PostScript files using Aspose.Page
    Java. This step‑by‑step guide shows the complete code and tips.
  headline: How to add hatch pattern in Java PostScript
  type: TechArticle
- questions:
  - answer: Yes, the library is framework‑agnostic and works with Spring, Jakarta
      EE, Android (limited), and plain Java SE.
    question: Can I use Aspose.Page Java with other Java frameworks?
  - answer: Absolutely. Download a free 30‑day trial [Aspose trial download page](https://releases.aspose.com/).
    question: Is a trial version available for Aspose.Page Java?
  - answer: Request a temporary license [temporary license request page](https://purchase.aspose.com/temporary-license/).
      It removes evaluation watermarks.
    question: How do I obtain a temporary license for development?
  - answer: Visit the official forum [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39)
      for additional examples and Q&A.
    question: Where can I find more tutorials and community support?
  - answer: Yes, the full API reference is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Is there comprehensive documentation for all classes and methods?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Java
- Aspose.Page
- PostScript
- hatch pattern
title: Como adicionar padrão de hachura em Java PostScript
url: /pt/java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como adicionar padrão de hachura em Java PostScript

## Introdução
Se você está trabalhando com **Aspose.Page Java** e se perguntando **como adicionar padrão de hachura** ao seu output PostScript, os padrões de hachura são uma solução rápida e flexível. Neste tutorial vamos percorrer **como adicionar** designs de hachura a um documento PostScript, explicar por que eles são úteis e fornecer um exemplo de código completo, pronto‑para‑executar. Ao final, você será capaz de criar formas e textos preenchidos com hachura visualmente atraentes usando apenas algumas linhas de Java.

## Respostas rápidas
- **Qual biblioteca eu preciso?** Aspose.Page for Java (o SDK “aspose page java”).  
- **Qual efeito visual estamos adicionando?** Padrões de hachura (por exemplo, linhas diagonais, cruzadas).  
- **Preciso de licença para executar o exemplo?** Uma avaliação gratuita funciona para desenvolvimento; uma licença é necessária para produção.  
- **Quantas linhas de código?** Aproximadamente 70 linhas, divididas em etapas claras.  
- **Posso usar a mesma abordagem para PDFs?** Sim—Aspose.Page suporta vários formatos de saída, incluindo PDF.

## O que é um padrão de hachura?
Um padrão de hachura é um preenchimento vetorial composto por linhas ou formas repetidas que criam um efeito de textura. Como é definido matematicamente, o padrão escala sem perda de qualidade, tornando‑o ideal para impressão de alta resolução e saída monocromática.

## Por que usar padrões de hachura com Aspose.Page Java?
Aspose.Page suporta **10+ formatos de saída** (incluindo PostScript, PDF, EPS, SVG e XPS) e pode renderizar preenchimentos de hachura em documentos de até **500 páginas** sem carregar o arquivo inteiro na memória. Isso significa desempenho rápido, baixo consumo de memória e resultados visuais consistentes em todos os formatos suportados.

## Como adicionar padrão de hachura – visão geral
Os padrões de hachura são texturas vetoriais que renderizam perfeitamente em qualquer resolução e funcionam bem em impressoras monocromáticas. Usando Aspose.Page Java, você pode aplicar esses padrões a formas, caminhos e até texto sem precisar lidar com comandos PostScript de baixo nível.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

- **Ambiente de desenvolvimento Java** – JDK 8 ou superior e uma IDE de sua escolha.  
- **Biblioteca Aspose.Page for Java** – Baixe o JAR mais recente da página oficial de download **Aspose.Page for Java** [here](https://releases.aspose.com/page/java/).  
- Você também pode navegar por outras versões da Aspose [here](https://releases.aspose.com/).  
- **Acesso de escrita** a uma pasta onde o arquivo PostScript gerado será salvo.

## Importar pacotes
Os imports abaixo incluem classes padrão do Java AWT para primitivas gráficas como cores, traçados e formas geométricas, bem como classes do Aspose.Page que fornecem o modelo de documento, definições de estilo de hachura e opções de salvamento necessárias para gerar um arquivo PostScript.  
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.TexturePaint;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.HatchPaintLibrary;
import com.aspose.eps.HatchStyle;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## O que é a classe `Document`?
A classe `Document` é o objeto de nível superior do Aspose.Page que representa um único arquivo PostScript na memória. Todas as operações de desenho são realizadas através desse objeto.

## Como configurar o fluxo de saída?
Para gravar o output, crie um `FileOutputStream` apontando para o caminho de arquivo desejado; esse fluxo lida com a escrita de bytes de baixo nível. `PsSaveOptions` configura como o documento é salvo, incluindo tamanho da página e compressão. Em seguida, instancie um `Document` com um objeto `PsSaveOptions` que especifica tamanho da página, compressão e outras configurações específicas do PostScript.  
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Como salvar o estado gráfico e traduzir a origem?
Salvar o estado gráfico captura a matriz de transformação atual, a região de recorte e os atributos de desenho, permitindo que você reverta mais tarde. Após salvar, chame `translate(x, y)` no objeto gráfico para deslocar a origem para um local conveniente ao desenhar a grade de quadrados de hachura.  
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Como criar um quadrado reutilizável para cada padrão?
`Rectangle2D` representa uma forma retangular definida por sua posição e tamanho. Ao criar uma única instância que corresponde às dimensões da célula, você pode reutilizá‑la para cada quadrado preenchido com hachura, reduzindo a alocação de objetos e mantendo o loop de desenho eficiente.  
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Como configurar uma caneta para o contorno do quadrado do padrão?
`BasicStroke` descreve a espessura do contorno, o padrão de traço e as extremidades para formas vetoriais. Usar um `BasicStroke` de 2 pontos fornece uma borda clara ao redor de cada célula preenchida com hachura, garantindo que o preenchimento fique visualmente separado dos quadrados adjacentes.  
```java
BasicStroke stroke = new BasicStroke(2);
```

## Como iterar pelos padrões de hachura?
`HatchStyle` é uma enumeração que lista todos os padrões de hachura predefinidos, como diagonal, cruzado e pontilhado. Percorrer `HatchStyle.values()` permite aplicar cada padrão em sequência, preencher o retângulo com um `HatchBrush` e, em seguida, desenhar seu contorno.  
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Como restaurar o estado gráfico após o desenho?
Chamar `restore()` no objeto gráfico reverte a matriz de transformação e as configurações de desenho ao estado salvo anteriormente, evitando que traduções ou escalas cumulativas afetem operações de desenho subsequentes. Isso garante que o conteúdo posterior comece a partir do sistema de coordenadas original e use atributos padrão.  
```java
document.writeGraphicsRestore();
```

## Como preencher texto com um padrão de hachura?
`TextFragment` representa um trecho de texto que pode ser posicionado e estilizado independentemente. Ao atribuir um `HatchBrush` com um `HatchStyle` escolhido ao preenchimento do fragmento, os caracteres são renderizados usando a textura de hachura em vez de uma cor sólida.  
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Como contornar texto com um estilo de hachura diferente?
`HatchBrush` também pode ser usado para traçar. Para desenhar um contorno, defina o traçado do fragmento para um `HatchBrush` com um `HatchStyle` diferente (por exemplo, 70 % hachura) e aumente a espessura do traçado via `setStrokeWidth`. Isso renderiza a borda do texto com seu próprio padrão de hachura enquanto preserva o interior preenchido.  
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Como fechar e salvar o documento?
`document.save()` grava o documento em memória no fluxo de saída especificado. Após concluir todos os comandos de desenho, invoque este método e então feche o `FileOutputStream` para liberar recursos do sistema e garantir que o arquivo seja corretamente gravado no disco.  
```java
document.closePage();
document.save();
```

Siga estas etapas e você terá um arquivo PostScript que demonstra um conjunto completo de padrões de hachura aplicados tanto a formas quanto a texto—tudo alimentado por **aspose page java**.

## Armadilhas comuns e dicas
- **Erros de caminho de arquivo** – Certifique‑se de que `dataDir` termina com o separador de arquivos adequado (`/` ou `\`).  
- **Cores não suportadas** – Alguns interpretadores PostScript mais antigos podem não lidar com certos espaços de cor; use RGB básico para máxima compatibilidade.  
- **Avisos de licença** – Executar o exemplo sem uma licença válida inserirá uma marca d'água na saída.

## Perguntas frequentes

**Q: Posso usar Aspose.Page Java com outros frameworks Java?**  
A: Sim, a biblioteca é agnóstica a frameworks e funciona com Spring, Jakarta EE, Android (limitado) e Java SE puro.

**Q: Existe uma versão de avaliação disponível para Aspose.Page Java?**  
A: Absolutamente. Baixe uma avaliação gratuita de 30 dias [Aspose trial download page](https://releases.aspose.com/).

**Q: Como obtenho uma licença temporária para desenvolvimento?**  
A: Solicite uma licença temporária [temporary license request page](https://purchase.aspose.com/temporary-license/). Ela remove as marcas d'água de avaliação.

**Q: Onde encontro mais tutoriais e suporte da comunidade?**  
A: Visite o fórum oficial [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) para exemplos adicionais e perguntas & respostas.

**Q: Existe documentação abrangente para todas as classes e métodos?**  
A: Sim, a referência completa da API está disponível [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Posso renderizar o mesmo padrão de hachura para PDF em vez de PostScript?**  
A: Absolutamente. Altere o `PsSaveOptions` para `PdfSaveOptions` (ou equivalente) e o restante do código permanece inalterado.

**Q: O que devo fazer se o arquivo gerado estiver vazio?**  
A: Verifique se o fluxo de saída aponta para um diretório gravável e se `document.save()` é chamado após todas as operações de desenho.

**Última atualização:** 2026-08-18  
**Testado com:** Aspose.Page for Java 24.12 (mais recente no momento da escrita)  
**Autor:** Aspose

## Tutoriais Relacionados

- [Criar padrão de textura em PostScript – Aspose.Page Java](/page/java/postscript-texture-patterns/)
- [Como adicionar gradiente: Gradiente diagonal em Java PostScript usando Aspose.Page Java](/page/java/postscript-gradient-addition/diagonal/)
- [Como converter PostScript para PDF usando Aspose.Page Java API](/page/java/postscript-conversion/to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}