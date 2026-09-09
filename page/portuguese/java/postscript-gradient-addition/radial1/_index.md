---
date: 2026-09-09
description: Aprenda como criar radial gradient em Java PostScript usando Aspose.Page.
  Este guia passo a passo mostra como adicionar um color stops gradient, definir radii
  e gerar um PS file rapidamente.
keywords:
- how to create radial gradient
- add color stops gradient
- Aspose.Page Java
- Java PostScript gradient
- radial gradient tutorial
lastmod: 2026-09-09
linktitle: Dominando radial gradients em Java
og_description: Aprenda como criar radial gradient em Java PostScript usando Aspose.Page.
  Este guia explica como adicionar color stops gradient, definir radii e gerar um
  PS file em minutos.
og_image_alt: Guide showing how to add a radial gradient to a Java PostScript file
  with Aspose.Page
og_title: Como criar radial gradient em Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  headline: How to create radial gradient in Java PostScript
  type: TechArticle
- description: Learn how to create radial gradient in Java PostScript using Aspose.Page.
    This step‑by‑step guide shows you how to add a color stops gradient, set radii,
    and generate a PS file quickly.
  name: How to create radial gradient in Java PostScript
  steps:
  - name: create a rectangle and open a PS document
    text: '`PsDocument` is Aspose.Page''s class that represents a PostScript document
      and provides methods to draw shapes, text, and images. We start by creating
      an output stream, configuring the page size (A4 by default), and defining a
      rectangle that will host the gradient. > **Pro tip:** Adjust the rectangle'
  - name: define colors and fractions
    text: 'A radial gradient is built from *color stops* (the colors) and *fractions*
      (the relative positions of those stops). Here we create an array of six colors
      and their corresponding fractions. > **Why this matters:** By tweaking `fractions`
      you control how quickly the colors transition, enabling subtle '
  - name: create radial gradient paint
    text: '`RadialGradientPaint` is the core class that describes a radial color gradient,
      including center point, radius, focus point, fractions, colors, cycle method,
      and color space. Now we build the `RadialGradientPaint` object using the arrays
      defined above. > **Note:** `transform` can be `null` if you do'
  - name: set paint and fill the rectangle
    text: With the paint ready, we tell the `PsDocument` to use it and then fill the
      rectangle we defined earlier. At this point the PostScript page contains a rectangle
      smoothly filled with the radial gradient we configured.
  - name: close and save the document
    text: Finally, close the current page and write the file to disk. Open `RadialGradient1_outPS.ps`
      in any PostScript viewer (e.g., Ghostscript) and you’ll see the gradient rendered
      exactly as defined.
  type: HowTo
- questions:
  - answer: Yes. A commercial license is required for production use. You can purchase
      one from the [Aspose licensing page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for Java in commercial projects?
  - answer: The full documentation is available [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).
    question: Where can I find the official API reference?
  - answer: Absolutely. Download a trial version from the [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is a free trial available for testing?
  - answer: A temporary license can be requested from the [temporary license request
      page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for evaluation?
  - answer: Join the Aspose.Page community forum at [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- radial gradient
- Aspose.Page
- Java PostScript
- gradient programming
- color stops
title: Como criar radial gradient em Java PostScript
url: /pt/java/postscript-gradient-addition/radial1/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar gradiente radial em Java PostScript com Aspose.Page

## Introdução
Se você precisa **criar um gradiente radial** dentro de um arquivo PostScript, você está no lugar certo. Neste tutorial, percorreremos cada passo necessário para gerar um documento PostScript que contém um gradiente radial suave, usando **Aspose.Page for Java**. Ao final, você entenderá a API, verá um exemplo completo executável e saberá como ajustar cores, posições e raios para qualquer cenário de design.

## Respostas rápidas
- **Qual biblioteca cria gradientes radiais em PostScript?** Aspose.Page for Java.  
- **Quanto tempo leva a implementação?** Cerca de 10‑15 minutos para um exemplo básico.  
- **Preciso de uma licença para executar o código?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção.  
- **Qual versão do Java é suportada?** Java 8 ou superior.  
- **Posso mudar a forma do gradiente?** Sim – ajuste o raio e o ponto central no construtor `RadialGradientPaint`.

## Como criar gradiente radial em Java

Carregue seu projeto Java, importe as classes necessárias e siga o guia passo a passo abaixo. A resposta principal é que você instancia um `RadialGradientPaint` com seus pontos de cor e então o aplica a um retângulo desenhado em um `PsDocument`. Essa abordagem de dois objetos lida com todos os comandos de PostScript de baixo nível para você.

## O que é um gradiente radial?
`RadialGradientPaint` é uma classe Java AWT que define uma transição de cor circular a partir de um ponto central para fora. Ela cria uma mescla suave de múltiplos pontos de cor, tornando-a ideal para holofotes, fundos suaves ou qualquer efeito onde as cores irradiam de um ponto focal.

## Por que usar Aspose.Page para gradientes radiais?
Aspose.Page oferece controle programático total sobre a saída PostScript enquanto lida com a parte pesada da sintaxe de PS de baixo nível. Ele suporta **mais de 50 formatos de entrada e saída**, pode renderizar documentos com centenas de páginas sem carregar o arquivo inteiro na memória, e funciona em qualquer sistema operacional que suporte Java 8+. Essa capacidade quantificada o torna uma escolha confiável para geração de gráficos de nível empresarial.

## Pré-requisitos
- **Java Development Kit (JDK) 8+** – verifique com `java -version`.  
- **Aspose.Page for Java** – baixe o JAR mais recente na página oficial [Aspose.Page download page](https://releases.aspose.com/page/java/).  
- **IDE de sua escolha** – Eclipse, IntelliJ IDEA ou VS Code com extensões Java.  
- **Uma pasta gravável** – onde o arquivo `.ps` gerado será salvo.

## Importar pacotes
Primeiro, importe as classes que precisaremos. O pacote `java.awt` fornece os objetos de pintura de gradiente, enquanto `com.aspose.eps` contém as classes de manipulação de documentos PostScript.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Guia passo a passo

### Passo 1: criar um retângulo e abrir um documento PS
`PsDocument` é a classe da Aspose.Page que representa um documento PostScript e fornece métodos para desenhar formas, texto e imagens. Começamos criando um fluxo de saída, configurando o tamanho da página (A4 por padrão) e definindo um retângulo que hospedará o gradiente.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient1_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 200);
```

> **Dica profissional:** Ajuste as coordenadas do retângulo (`200, 100, 200, 200`) para posicionar o gradiente em qualquer lugar da página.

### Passo 2: definir cores e frações
Um gradiente radial é construído a partir de *pontos de cor* (as cores) e *frações* (as posições relativas desses pontos). Aqui criamos um array de seis cores e suas frações correspondentes.

```java
// Create arrays of colors and fractions for the gradient
Color[] colors = { Color.GREEN, Color.BLUE, Color.BLACK, Color.YELLOW, new Color(245, 245, 220), Color.RED };
float[] fractions = { 0.0f, 0.2f, 0.3f, 0.4f, 0.9f, 1.0f };
```

> **Por que isso importa:** Ao ajustar `fractions` você controla a rapidez com que as cores transicionam, permitindo efeitos sutis ou dramáticos.

### Passo 3: criar pintura de gradiente radial
`RadialGradientPaint` é a classe central que descreve um gradiente de cor radial, incluindo ponto central, raio, ponto focal, frações, cores, método de ciclo e espaço de cor. Agora construímos o objeto `RadialGradientPaint` usando os arrays definidos acima.

```java
// Create radial gradient paint
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(300, 200),      // center of the gradient
        100,                              // radius
        new Point2D.Float(300, 200),      // focus point (same as center for a symmetric gradient)
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

> **Observação:** `transform` pode ser `null` se você não precisar de escala ou rotação adicionais. Sinta-se à vontade para experimentar `AffineTransform` para gradientes inclinados.

### Passo 4: definir a pintura e preencher o retângulo
Com a pintura pronta, instruímos o `PsDocument` a usá-la e então preenchemos o retângulo que definimos anteriormente.

```java
// Set paint
document.setPaint(paint);
// Fill the rectangle
document.fill(rectangle);
```

Neste ponto a página PostScript contém um retângulo preenchido suavemente com o gradiente radial que configuramos.

### Passo 5: fechar e salvar o documento
Finalmente, feche a página atual e grave o arquivo no disco.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Abra `RadialGradient1_outPS.ps` em qualquer visualizador PostScript (por exemplo, Ghostscript) e você verá o gradiente renderizado exatamente como definido.

## Problemas comuns e soluções
| Sintoma | Causa provável | Correção |
|---------|----------------|----------|
| O gradiente aparece como cor sólida | o array `fractions` não começa em `0.0f` ou não termina em `1.0f` | Certifique-se de que a primeira fração seja `0.0f` e a última seja `1.0f`. |
| As cores parecem desbotadas | Uso do `ColorSpaceType` errado | Troque para `MultipleGradientPaint.ColorSpaceType.LINEAR_RGB` para uma saída mais vibrante. |
| Nenhum arquivo de saída gerado | O caminho do `FileOutputStream` é inválido ou não gravável | Verifique se `dataDir` existe e se a aplicação tem permissões de gravação. |

## Perguntas frequentes

**Q: Posso usar Aspose.Page for Java em projetos comerciais?**  
A: Sim. Uma licença comercial é necessária para uso em produção. Você pode adquirir uma na [página de licenciamento da Aspose](https://purchase.aspose.com/buy).

**Q: Onde posso encontrar a referência oficial da API?**  
A: A documentação completa está disponível [Aspose.Page Java API reference](https://reference.aspose.com/page/java/).

**Q: Existe uma avaliação gratuita disponível para testes?**  
A: Absolutamente. Baixe uma versão de avaliação na [página de lançamentos do Aspose.Page](https://releases.aspose.com/).

**Q: Como obtenho uma licença temporária para avaliação?**  
A: Uma licença temporária pode ser solicitada na [página de solicitação de licença temporária](https://purchase.aspose.com/temporary-license/).

**Q: Onde posso obter suporte da comunidade?**  
A: Participe do fórum da comunidade Aspose.Page em [forum.aspose.com/c/page/39](https://forum.aspose.com/c/page/39).

## Conclusão
Agora você sabe **como criar gradiente radial** em um documento Java PostScript usando Aspose.Page. Ajustando o tamanho do retângulo, os pontos de cor e o raio do gradiente, você pode criar inúmeros efeitos visuais — desde preenchimentos de fundo sutis até gráficos de holofote ousados. Sinta-se à vontade para experimentar diferentes valores de `AffineTransform` para girar ou inclinar o gradiente, e combinar esta técnica com texto e imagens para saídas PDF ou EPS mais ricas.

---

**Última atualização:** 2026-09-09  
**Testado com:** Aspose.Page for Java latest (as of writing)  
**Autor:** Aspose

## Tutoriais relacionados

- [Preencher Forma com Gradiente: Exemplo Radial Java PostScript](/page/java/postscript-gradient-addition/radial2/)
- [Criar Gradiente PostScript em Java – Adicionar Gradiente Vertical](/page/java/postscript-gradient-addition/vertical/)
- [Tutorial de Transparência Aspose.Page – Adicionar Transparência em Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}