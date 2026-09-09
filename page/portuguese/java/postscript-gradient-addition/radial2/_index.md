---
date: 2026-09-09
description: Aprenda como criar gradient em Java PostScript e adicionar gradient a
  uma forma usando Aspose.Page. Siga este guia passo a passo com código e dicas.
keywords:
- how to create gradient
- add gradient to shape
- radial gradient Java
lastmod: 2026-09-09
linktitle: Java PostScript Radial Gradient com Aspose.Page
og_description: Aprenda como criar gradient em Java PostScript e adicionar gradient
  a uma forma usando Aspose.Page. Siga este guia passo a passo com código e dicas.
og_image_alt: 'Developer guide: create gradient in Java PostScript with radial fill
  using Aspose.Page'
og_title: Como criar gradient em Java PostScript com radial fill
schemas:
- author: Aspose
  dateModified: '2026-09-09'
  description: Learn how to create gradient in Java PostScript and add gradient to
    shape using Aspose.Page. Follow this step‑by‑step guide with code and tips.
  headline: How to create gradient in Java PostScript with radial fill
  type: TechArticle
- questions:
  - answer: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).
    question: Where can I find the documentation for Aspose.Page for Java?
  - answer: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).
    question: How can I download Aspose.Page for Java?
  - answer: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).
    question: Is there a free trial available?
  - answer: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for testing?
  - answer: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).
    question: Where can I get community support?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- gradient
- Aspose.Page
- Java PostScript
- radial gradient
- fill shape
title: Como criar gradient em Java PostScript com radial fill
url: /pt/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar gradiente em Java PostScript com preenchimento radial

## Introdução
Neste tutorial você aprenderá **how to create gradient** gráficos em um documento PostScript usando Java e Aspose.Page. Vamos percorrer cada passo — desde a configuração do projeto até a renderização de um círculo preenchido com um gradiente radial suave — para que você possa **add gradient to shape** objects instantaneamente e elevar a qualidade visual de suas aplicações Java.

## Respostas rápidas
- **O que este tutorial cria?** A PostScript file (`.ps`) containing a circle filled with a radial gradient.  
- **Qual biblioteca é necessária?** Aspose.Page for Java (latest version).  
- **Quanto tempo leva a implementação?** Approximately 10‑15 minutes for a working example.  
- **Preciso de uma licença?** A temporary or full license is required for production use; a free trial works for development.  
- **Posso reutilizar o código para PDF ou SVG?** Yes—Aspose.Page supports multiple output formats with minimal changes.

## Como preencher shape com gradiente no PostScript
Você pode preencher um shape com um gradiente radial no PostScript criando um `PsDocument`, definindo um `RadialGradientPaint`, aplicando-o ao shape de destino e, finalmente, salvando o documento. Esse fluxo de trabalho conciso permite produzir gráficos vetoriais com aparência profissional sem imagens raster, e o mesmo código pode ser reutilizado para saída PDF ou SVG. O processo é simples e funciona de forma consistente em todos os formatos suportados.

## O que é um gradiente radial?
Um gradiente radial transita as cores do ponto central para fora, criando uma mescla suave e circular. É ideal para realces, fundos de botões ou qualquer elemento visual que precise de um efeito de “brilho” natural. Variando as paradas de cor e o raio, você pode simular iluminação, profundidade e propriedades de material em forma vetorial pura.

## Por que usar Aspose.Page para gradientes radiais?
Aspose.Page permite gerar gráficos vetoriais independentes de dispositivo com uma única API Java. Ele suporta mais de 50 formatos de entrada e saída — incluindo PostScript, PDF e SVG — mantendo a precisão de cores e anti‑aliasing para saída de alta resolução. A biblioteca também fornece classes de gradiente fáceis de usar, tornando efeitos visuais complexos simples de implementar.

## Pré-requisitos
Antes de começarmos, certifique‑se de que você tem:

- Familiaridade básica com programação Java.  
- JDK 8 ou superior instalado em sua máquina.  
- Biblioteca Aspose.Page for Java (download da [Aspose.Page Java documentation](https://reference.aspose.com/page/java/)).  

## Importar pacotes
Primeiro, importe as classes que precisaremos. Elas incluem tipos gráficos padrão AWT e a API Aspose.Page.

```java
import java.awt.Color;
import java.awt.MultipleGradientPaint;
import java.awt.RadialGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Ellipse2D;
import java.awt.geom.Point2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Etapa 1: configurar diretório do documento
Defina a pasta onde o arquivo PostScript gerado será salvo. Substitua o placeholder por um caminho real no seu sistema.

```java
String dataDir = "Your Document Directory";
```

## Etapa 2: criar fluxo de saída
FileOutputStream grava bytes brutos em um arquivo, permitindo que dados binários sejam salvos. Abrir um direcionado a um arquivo `.ps` permite que Aspose.Page envie os dados PostScript gerados diretamente para o disco.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Etapa 3: criar opções de salvamento
PsSaveOptions configura como um arquivo PostScript é salvo, incluindo tamanho da página e compressão. Você pode personalizar essas configurações, mas os padrões são adequados para este exemplo.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Etapa 4: criar documento ps
PsDocument representa um documento PostScript na memória e fornece métodos para adicionar páginas e gráficos.

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Etapa 5: criar um círculo
`Ellipse2D.Float` descreve uma forma elíptica; quando largura = altura ela se torna um círculo perfeito. Este objeto servirá como a tela para o nosso preenchimento de gradiente.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Como desenhar círculo com gradiente
Para desenhar um círculo com um gradiente radial, você carrega um `RadialGradientPaint` no contexto gráfico e então preenche a elipse previamente definida. Essa única operação pinta o shape com uma transição de cores suave do centro para fora, criando um efeito visualmente atraente.

## Etapa 6: definir cores do gradiente
Prepare duas matrizes: uma para as cores que aparecerão no gradiente e outra para as posições fracionárias correspondentes (0 = centro, 1 = borda).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Etapa 7: criar AffineTransform
AffineTransform é uma matriz que pode traduzir, rotacionar, escalar ou cisalhar objetos gráficos. Aqui ela escala e traduz o gradiente para que se ajuste precisamente dentro do círculo.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Etapa 8: criar radial gradient paint
RadialGradientPaint cria um gradiente de cor radial baseado em um ponto central, raio e paradas de cor.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Etapa 9: definir pintura e preencher círculo
Aplique a pintura de gradiente ao documento e preencha o círculo previamente definido. Este é o núcleo do nosso **radial gradient example** e demonstra como **fill shape with gradient**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Etapa 10: fechar página e salvar documento
Finalize a página, escreva o conteúdo no disco e feche o fluxo. Seu arquivo PostScript está pronto para ser visualizado com qualquer visualizador PS.

```java
document.closePage();
document.save();
```

Parabéns! Você criou com sucesso um exemplo de gradiente radial em Java PostScript usando Aspose.Page. Agora você tem um padrão reutilizável para **fill shape with gradient** que pode ser adaptado a outras formas e formatos de saída.

## Problemas comuns e soluções
| Problema | Solução |
|---------|----------|
| **FileNotFoundException** ao abrir o fluxo de saída | Verifique se `dataDir` aponta para uma pasta existente e se você tem permissões de gravação. |
| Gradiente parece plano ou ausente | Certifique‑se de que a matriz `fractions` corresponde ao comprimento da matriz `colors` e que o `AffineTransform` escala corretamente. |
| Cores aparecem invertidas | Inverta a ordem das cores na matriz `colors` ou ajuste as coordenadas do ponto `focus`. |

## Perguntas frequentes

**Q: Onde posso encontrar a documentação do Aspose.Page for Java?**  
A: The full API reference is available in the [Aspose.Page Java API documentation](https://reference.aspose.com/page/java/).

**Q: Como posso baixar o Aspose.Page for Java?**  
A: Grab the latest JAR from the [releases page](https://releases.aspose.com/page/java/).

**Q: Existe uma versão de avaliação gratuita?**  
A: Yes—download a trial version from the [Aspose free trial download page](https://releases.aspose.com/).

**Q: Posso obter uma licença temporária para testes?**  
A: Absolutely, request one from the [temporary license page](https://purchase.aspose.com/temporary-license/).

**Q: Onde posso obter suporte da comunidade?**  
A: Join the discussion on the [Aspose.Page forum](https://forum.aspose.com/c/page/39).

## Conclusão
Neste guia construímos um **radial gradient example** completo para um documento PostScript usando Aspose.Page for Java. Seguindo os passos, agora você tem um padrão reutilizável para **fill shape with gradient**, que pode ser adaptado para PDF, SVG ou qualquer outro formato suportado pelo Aspose.Page. Experimente diferentes cores, raios e formas para enriquecer seus projetos gráficos Java.

---

**Last Updated:** 2026-09-09  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose

## Tutoriais Relacionados

- [Criar Gradiente PostScript em Java – Adicionar Gradiente Vertical](/page/java/postscript-gradient-addition/vertical/)
- [Criar Padrão de Textura em PostScript com Aspose.Page for Java](/page/java/postscript-texture-patterns/)
- [Tutorial de Transparência Aspose.Page – Adicionar Transparência em Java PostScript](/page/java/postscript-transparency/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}