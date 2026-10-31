---
date: 2026-10-31
description: Aprenda a definir a cor da tinta e preencher elipse em Java PostScript
  usando Aspose.Page. Este guia mostra como preencher elipse, desenhar o contorno
  da elipse e definir a espessura do traço com etapas de código claras.
keywords:
- how to fill ellipse
- how to set paint color
- Aspose.Page Java ellipse
- PostScript drawing Java
lastmod: 2026-10-31
linktitle: Adicionar Elipse em Java PostScript
og_description: Aprenda a preencher elipse e definir a cor da tinta em Java PostScript
  usando Aspose.Page. Siga o código passo a passo para desenhar elipses preenchidas
  e contornadas em segundos.
og_image_alt: Developer guide showing how to fill ellipse and set paint color in Java
  PostScript with Aspose.Page
og_title: Como preencher elipse e definir a cor da tinta em Java PostScript
schemas:
- author: Aspose
  dateModified: '2026-10-31'
  description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  headline: How to fill ellipse and set paint color in Java PostScript
  type: TechArticle
- description: Learn how to set paint color and fill ellipse in Java PostScript using
    Aspose.Page. This guide shows how to fill ellipse, draw ellipse outline, and set
    stroke thickness with clear code steps.
  name: How to fill ellipse and set paint color in Java PostScript
  steps:
  - name: Set up the PostScript document
    text: Create an output stream, configure page size, and instantiate a `PsDocument`.
      `PsDocument` is the core class that represents a PostScript file in memory.
      All drawing commands are routed through this object, and it handles page layout,
      resource management, and final file generation.
  - name: Fill ellipse – use set paint color
    text: To **fill ellipse**, you must first call `setPaint` with the desired fill
      color, then invoke `fill` with an `Ellipse2D` instance. `setPaint` sets the
      current drawing color used for subsequent fill or stroke operations. `Ellipse2D`
      defines the geometric bounds of the ellipse; its constructor takes th
  - name: Draw ellipse outline and set stroke thickness
    text: After filling, you can change the paint to a different color, define a `BasicStroke`
      to control line width, and draw the ellipse outline. `BasicStroke` specifies
      line width, dash pattern, and end‑cap style for drawing outlines. By adjusting
      its `width` property you control how bold the ellipse borde
  - name: Close and save the document
    text: Finalize the page and write the PostScript file to disk. Calling `document.close()`
      flushes all pending drawing commands and releases resources. The resulting `.ps`
      file can be opened with any PostScript viewer or converted to PDF. You now have
      a PostScript file that contains two ellipses—one filled
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page for Java is designed to seamlessly integrate with other
      Java libraries.
    question: Can I use Aspose.Page for Java with other Java libraries?
  - answer: Obtain a temporary license **[from the Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/)**
      for testing purposes.
    question: How can I get a temporary license for Aspose.Page for Java?
  - answer: Absolutely! Visit **[the Aspose purchase page](https://purchase.aspose.com/buy)**
      to explore licensing options for commercial use.
    question: Is Aspose.Page suitable for commercial projects?
  - answer: Join the community at the **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)**
      for discussions and assistance.
    question: Where can I seek help or discuss Aspose.Page‑related queries?
  - answer: Utilize the **[Aspose free trial page](https://releases.aspose.com/)**
      and explore examples in the documentation.
    question: Are there any free resources to learn more about Aspose.Page for Java?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript ellipse
- vector drawing
title: Como preencher elipse e definir a cor da tinta em Java PostScript
url: /pt/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como preencher elipse e definir a cor de pintura em Java PostScript

## Introdução
Se você precisar **definir a cor de pintura** ao desenhar gráficos vetoriais, a biblioteca Aspose.Page for Java oferece controle total sobre cada traço e preenchimento. Neste tutorial você descobrirá como **definir a cor de pintura**, **preencher elipse** e **desenhar o contorno da elipse** usando uma abordagem simples, passo a passo. Ao final, você poderá adicionar elipses PostScript de alta qualidade a faturas, relatórios ou qualquer documento imprimível.

## Respostas rápidas
- **Qual biblioteca é a melhor para desenhar gráficos PostScript em Java?** Aspose.Page for Java.  
- **Posso preencher uma elipse com uma cor sólida?** Sim – use `document.setPaint(Color.YOUR_COLOR)` antes de `fill`.  
- **Como desenho apenas o contorno de uma elipse?** Defina a cor e o traço, então chame `document.draw(...)`.  
- **Preciso de licença para uso em produção?** É necessária uma licença comercial; uma licença temporária está disponível para testes.  
- **Qual versão do Java é suportada?** Qualquer runtime Java 8+ funciona com a versão atual do Aspose.Page.

## O que é uma elipse PostScript?
Uma elipse PostScript é uma forma vetorial definida por um retângulo delimitador. Ao contrário de imagens raster, ela escala sem perda de qualidade, tornando‑se ideal para impressão de alta resolução e conversão para PDF. Como a forma é descrita matematicamente, pode ser renderizada em qualquer tamanho ou resolução preservando bordas nítidas e curvas suaves.

## Por que usar Aspose.Page para criar uma elipse PostScript?
Aspose.Page oferece controle determinístico sobre cada primitiva de desenho. Suporta **3 principais sistemas operacionais (Windows, Linux, macOS)**, **0 dependências nativas**, e pode renderizar **mais de 50 primitivas vetoriais** por segundo em um servidor típico. A biblioteca é pura Java, portanto pode ser incorporada em qualquer aplicação Java 8+ sem bibliotecas nativas adicionais.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. Um ambiente de desenvolvimento Java funcional (JDK 8 ou superior).  
2. A biblioteca Aspose.Page for Java adicionada ao seu projeto. Você pode baixá‑la **[da página de lançamento do Aspose.Page for Java](https://releases.aspose.com/page/java/)**.  

## Importar pacotes
No seu arquivo fonte Java, importe as classes necessárias para desenhar e salvar conteúdo PostScript.

O pacote `java.awt` fornece os tipos gráficos básicos, como `Color`, `Ellipse2D` e `BasicStroke`. O pacote `com.aspose.page` fornece a classe `PsDocument` que grava a saída PostScript.

- **`Color`** – representa uma cor sRGB usada para pintura.  
- **`Ellipse2D`** – descreve uma forma de elipse definida por um retângulo delimitador.  
- **`BasicStroke`** – especifica a largura da linha, padrão de traço e estilo de extremidade para desenhar contornos.  
- **`PsDocument`** – representa um documento PostScript e fornece métodos para desenhar gráficos e gerenciar páginas.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Como definir a cor de pintura para uma elipse
O primeiro passo é informar ao documento qual cor usar na próxima operação de desenho. O método `setPaint` define uma cor sólida que será aplicada a um preenchimento ou traço, dependendo da chamada subsequente.

### Etapa 1: Configurar o documento PostScript
Crie um fluxo de saída, configure o tamanho da página e instancie um `PsDocument`.

`PsDocument` é a classe central que representa um arquivo PostScript na memória. Todos os comandos de desenho são roteados através desse objeto, que gerencia o layout da página, recursos e a geração final do arquivo.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Etapa 2: Preencher elipse – usar set paint color
Para **preencher elipse**, primeiro chame `setPaint` com a cor de preenchimento desejada, depois invoque `fill` com uma instância de `Ellipse2D`.

`setPaint` define a cor de desenho atual usada nas operações subsequentes de preenchimento ou traço.  
`Ellipse2D` define os limites geométricos da elipse; seu construtor recebe as coordenadas X‑Y do canto superior esquerdo, além da largura e altura.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Etapa 3: Desenhar contorno da elipse e definir a espessura do traço
Após o preenchimento, você pode mudar a cor, definir um `BasicStroke` para controlar a largura da linha e desenhar o contorno da elipse.

`BasicStroke` especifica a largura da linha, padrão de traço e estilo de extremidade para desenhar contornos. Ajustando a propriedade `width` você controla o quão grosso o contorno da elipse aparecerá.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Etapa 4: Fechar e salvar o documento
Finalize a página e grave o arquivo PostScript no disco.

Chamar `document.close()` libera todos os comandos de desenho pendentes e recursos. O arquivo `.ps` resultante pode ser aberto com qualquer visualizador PostScript ou convertido para PDF.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Agora você tem um arquivo PostScript que contém duas elipses — uma preenchida com laranja e outra contornada em vermelho. Sinta‑se à vontade para experimentar diferentes coordenadas, tamanhos e cores para atender às necessidades do seu design.

## Problemas comuns e solução de problemas
- **Caminho de arquivo incorreto** – Certifique-se de que `dataDir` termina com um separador (`/` ou `\\`) adequado ao seu SO.  
- **Licença ausente** – Sem uma licença válida, a biblioteca funciona em modo de avaliação e pode adicionar marcas d'água.  
- **Cor não aplicada** – Lembre‑se de definir `document.setPaint(...)` *antes* de cada chamada `fill` ou `draw`; a configuração de cor não persiste automaticamente entre operações distintas.

## Perguntas frequentes

**Q: Posso usar Aspose.Page for Java com outras bibliotecas Java?**  
A: Sim, Aspose.Page for Java foi projetado para integrar‑se perfeitamente com outras bibliotecas Java.

**Q: Como posso obter uma licença temporária para Aspose.Page for Java?**  
A: Obtenha uma licença temporária **[da página de licença temporária da Aspose](https://purchase.aspose.com/temporary-license/)** para fins de teste.

**Q: O Aspose.Page é adequado para projetos comerciais?**  
A: Absolutamente! Visite **[a página de compra da Aspose](https://purchase.aspose.com/buy)** para explorar opções de licenciamento para uso comercial.

**Q: Onde posso buscar ajuda ou discutir dúvidas relacionadas ao Aspose.Page?**  
A: Junte‑se à comunidade no **[Fórum Aspose.Page](https://forum.aspose.com/c/page/39)** para discussões e assistência.

**Q: Existem recursos gratuitos para aprender mais sobre Aspose.Page for Java?**  
A: Utilize a **[página de teste gratuito da Aspose](https://releases.aspose.com/)** e explore exemplos na documentação.

## Conclusão
Aspose.Page for Java torna simples **definir a cor de pintura**, **preencher elipse** e **desenhar o contorno da elipse** — seja para uma forma preenchida simples ou um gráfico complexo com traço. Com os passos acima você pode rapidamente adicionar gráficos vetoriais de nível profissional a qualquer documento imprimível. Para exploração mais aprofundada — como combinar múltiplas formas, aplicar gradientes ou converter para PDF — consulte a documentação oficial **[Aspose.Page Java](https://reference.aspose.com/page/java/)**.

---

**Last Updated:** 2026-10-31  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## Tutoriais Relacionados

- [Como desenhar retângulo em Java PostScript com Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Como adicionar texto Unicode em Java PostScript com Aspose.Page](/page/java/postscript-text-manipulation/add-text-unicode/)
- [Criar gradiente radial em PostScript com Aspose.Page for Java](/page/java/postscript-gradient-addition/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}