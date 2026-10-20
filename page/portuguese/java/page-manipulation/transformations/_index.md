---
date: 2026-10-20
description: Aprenda como escalar um retângulo com Aspose.Page for Java, como traduzir
  formas e aplicar affine transform para criar documentos PostScript.
keywords:
- how to scale rectangle
- how to translate shape
- save postscript file
- apply affine transform
- java graphics scaling
lastmod: 2026-10-20
linktitle: Transformações na manipulação de páginas Java
og_description: Aprenda como escalar um retângulo, traduzir formas e aplicar affine
  transform usando Aspose.Page for Java para gerar arquivos PostScript de forma eficiente.
og_image_alt: Screenshot of Java code scaling a rectangle with Aspose.Page
og_title: Como escalar um retângulo com Aspise.Page for Java – guia passo a passo
schemas:
- author: Aspose
  dateModified: '2026-10-20'
  description: Learn how to scale rectangle with Aspose.Page for Java, how to translate
    shape, and apply affine transform to create PostScript documents.
  headline: How to Scale Rectangle with Aspose.Page for Java
  type: TechArticle
- questions:
  - answer: '`translate` moves the origin of the coordinate system, while `scale`
      changes the size of drawn objects along the X and/or Y axes.'
    question: What is the difference between `translate` and `scale`?
  - answer: Yes—by calling `translate`, `scale`, `rotate`, or `shear` sequentially
      before drawing, you create a combined affine transformation.
    question: Can I combine multiple transformations in a single graphics state?
  - answer: Use `writeGraphicsRestore()` to revert to the previously saved graphics
      state.
    question: How do I reset transformations after drawing a shape?
  - answer: Absolutely. Translate the rectangle to the origin, apply `rotate(angle)`,
      then translate it back before drawing.
    question: Is it possible to rotate a rectangle around its center?
  - answer: Yes—set the appropriate rendering options in `PsSaveOptions` to enable
      anti‑aliasing.
    question: Does Aspose.Page support anti‑aliasing for smoother graphics?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- Aspose.Page
- Java graphics
- PostScript generation
- affine transformation
- rectangle scaling
title: Como escalar um retângulo com Aspose.Page for Java
url: /pt/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como dimensionar retângulo com Aspose.Page para Java

## Introdução
Neste guia você descobrirá **how to scale rectangle** objetos usando Aspose.Page para Java, além de aprender como traduzir posições de formas, girar gráficos e aplicar operações de transformação afim para produzir saída PostScript de alta qualidade. Essas técnicas permitem criar gráficos sofisticados e independentes de dispositivo sem escrever código de renderização de baixo nível, tornando suas aplicações Java mais poderosas e fáceis de manter.

## Respostas rápidas
`scale(sx, sy)` escala o contexto gráfico pelos fatores horizontal e vertical fornecidos.  

- **Como dimensiono um retângulo em Java com Aspose.Page?** Chame o método `scale(sx, sy)` no contexto gráfico antes de desenhar o retângulo.  
- **Posso mover (traduzir) uma forma sem afetar outros gráficos?** Sim—envolva a tradução entre chamadas `writeGraphicsSave()` e `writeGraphicsRestore()`.  
- **Qual classe cria um arquivo PostScript?** Use `PsDocument` junto com `PsSaveOptions`.  
- **Preciso de uma licença para uso em produção?** Uma licença válida do Aspose.Page é necessária para implantações comerciais.  
- **Qual versão do Java é suportada?** Aspose.Page funciona com Java 8 e posteriores.

## Pré-requisitos
Antes de começar, verifique se você tem:

- Um sólido domínio da sintaxe central do Java e dos conceitos orientados a objetos.  
- A biblioteca Aspose.Page para Java instalada. Você pode baixá‑la na [documentação do Aspose.Page para Java](https://reference.aspose.com/page/java/).  
- Um IDE Java (IntelliJ IDEA, Eclipse ou VS Code) configurado com os arquivos JAR da biblioteca no classpath.

## Importar pacotes
`PsDocument` é a classe principal usada para criar um documento PostScript, e `PsSaveOptions` configura como o documento é salvo.  

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## O que é “how to scale rectangle” no Aspose.Page?
O método `scale(float sx, float sy)` aplica uma transformação de escala afim ao estado gráfico atual, redimensionando desenhos subsequentes pelos fatores `sx` (horizontal) e `sy` (vertical). Esta é a operação central por trás da palavra‑chave **how to scale rectangle**. Ao aplicar essa transformação antes de desenhar, quaisquer formas subsequentes, como retângulos, serão renderizadas com as novas dimensões preservando suas proporções.

## Como traduzir forma com Aspose.Page
`writeGraphicsSave()` salva o estado gráfico atual e `writeGraphicsRestore()` o restaura, garantindo que as transformações afetem apenas a forma pretendida. A tradução reposiciona a origem do sistema de coordenadas sem alterar as dimensões do objeto. Ao envolver `translate(dx, dy)` com `writeGraphicsSave()` / `writeGraphicsRestore()`, você assegura que somente a forma desejada se mova enquanto os demais gráficos permanecem inalterados, proporcionando controle preciso sobre elementos individuais.

## Exemplo 1: sem transformações
O primeiro exemplo desenha um retângulo sem nenhuma transformação, estabelecendo uma linha de base para comparação visual com os exemplos posteriores.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "Tranformations_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Create a rectangle
Shape shape = new Rectangle2D.Float(0, 0, 150, 100);
// Set paint in graphics state on the upper level
document.setPaint(Color.ORANGE);
// Fill the first rectangle without any transformations.
document.fill(shape);
// Close current page
document.closePage();
// Save the document
document.save();
```

## Exemplo 2: translação
Neste exemplo movemos o contexto gráfico 250 unidades para a direita antes de desenhar um segundo retângulo, ilustrando **how to translate shape**.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Displace current graphics state 250 to the right
document.translate(250, 0);
// Set paint in the current graphics state
document.setPaint(Color.BLUE);
// Fill the second rectangle with translation transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Exemplo 3: dimensionamento
Aqui respondemos à pergunta principal **how to scale rectangle**. O retângulo é reduzido para 50 % da largura original e 75 % da altura original usando a chamada `scale(0.5f, 0.75f)`.

```java
// Save graphics state to return back after transformation
document.writeGraphicsSave();
// Scale current graphics state on 0.5 in X axis and 0.75f in Y axis
document.scale(0.5f, 0.75f);
// Set paint in the current graphics state
document.setPaint(Color.RED);
// Fill the third rectangle with scale transformation
document.fill(shape);
// Restore graphics state to the previous (upper) level
document.writeGraphicsRestore();
```

## Como girar forma java (rotate shape java)
`rotate(angle)` gira o sistema de coordenadas pelo ângulo especificado em graus. Carregue seu `PsDocument`, chame `rotate(angle)` no estado gráfico, desenhe a forma e então restaure o estado anterior. Esse padrão implementa **rotate shape java** e **how to rotate rectangle** em um bloco reutilizável, permitindo girar gráficos em torno de qualquer ponto que você escolher.

## Por que isso importa – benefícios reais
- **Saída independente de dispositivo** – Aspose.Page pode gerar arquivos PostScript e XPS que são renderizados de forma idêntica em qualquer impressora ou visualizador, eliminando ajustes específicos de plataforma.  
- **Controle granular** – Combine translação, dimensionamento, cisalhamento e rotação para atender a especificações de layout exatas; a API suporta mais de 20 combinações de transformação por página.  
- **Processamento orientado ao desempenho** – A biblioteca processa documentos com uso de memória abaixo de 10 MB para relatórios típicos de 100 páginas, tornando trabalhos em lote rápidos e escaláveis.

## Casos de uso comuns
- **Faturas imprimíveis** – Posicione logotipos, códigos de barras e tabelas com precisão usando dimensionamento e translação para atender às diretrizes de identidade visual corporativa.  
- **Diagramas técnicos** – Gere esquemas onde cada componente deve ser redimensionado e posicionado proporcionalmente.  
- **Relatórios automatizados de múltiplas páginas** – Crie relatórios PostScript que exigem dimensionamento consistente entre páginas, como especificações de engenharia.

## Problemas comuns e soluções
- **Transformação não sendo redefinida** – Sempre emparelhe `writeGraphicsSave()` com `writeGraphicsRestore()`; caso contrário, desenhos subsequentes herdarão transformações indesejadas.  
- **Cores inesperadas** – Defina a cor (paint) após cada transformação porque o estado gráfico não preserva informações de cor após uma restauração.  
- **Tamanho de arquivo muito grande** – Ative compressão em `PsSaveOptions` e limite a resolução de imagens raster incorporadas para manter o arquivo final abaixo de 5 MB para documentos típicos de 50 páginas.

## Perguntas Frequentes

### Posso usar Aspose.Page para Java em outros formatos de documento?
Aspose.Page foca principalmente na manipulação de páginas para formatos PostScript e XPS, mas também oferece capacidades limitadas de exportação para PDF.

### Onde posso encontrar mais exemplos e documentação para Aspose.Page para Java?
Visite a [documentação do Aspose.Page para Java](https://reference.aspose.com/page/java/) para guias abrangentes, referências de API e projetos de exemplo.

### Existe um teste gratuito disponível para Aspose.Page para Java?
Sim, você pode acessar um teste gratuito na página de **download de teste gratuito da Aspose**: [Aspose free trial download](https://releases.aspose.com/).

### Como posso obter uma licença temporária para Aspose.Page para Java?
Obtenha uma licença temporária através da **página de solicitação de licença temporária**: [temporary license request page](https://purchase.aspose.com/temporary-license/).

### Onde posso buscar suporte da comunidade ou fazer perguntas sobre Aspose.Page para Java?
Visite o [fórum Aspose.Page para Java](https://forum.aspose.com/c/page/39) para discussões da comunidade, trechos de código e dicas de solução de problemas.

## Perguntas frequentes

**Q: Qual a diferença entre `translate` e `scale`?**  
A: `translate` move a origem do sistema de coordenadas, enquanto `scale` altera o tamanho dos objetos desenhados ao longo dos eixos X e/ou Y.

**Q: Posso combinar múltiplas transformações em um único estado gráfico?**  
A: Sim—chamando `translate`, `scale`, `rotate` ou `shear` sequencialmente antes de desenhar, você cria uma transformação afim combinada.

**Q: Como redefino as transformações após desenhar uma forma?**  
A: Use `writeGraphicsRestore()` para reverter ao estado gráfico previamente salvo.

**Q: É possível girar um retângulo ao redor de seu centro?**  
A: Absolutamente. Traduza o retângulo para a origem, aplique `rotate(angle)`, então traduza de volta antes de desenhar.

**Q: O Aspose.Page suporta anti‑aliasing para gráficos mais suaves?**  
A: Sim—defina as opções de renderização apropriadas em `PsSaveOptions` para habilitar anti‑aliasing.

---

**Última atualização:** 2026-10-20  
**Testado com:** Aspose.Page para Java 24.12  
**Autor:** Aspose

## Tutoriais Relacionados

- [Como desenhar retângulo em Java PostScript com Aspose.Page](/page/java/postscript-shapes/add-rectangle/)
- [Criar gradiente radial em PostScript com Aspose.Page para Java](/page/java/postscript-gradient-addition/)
- [Manipulação de página PostScript](/page/java/postscript-page-manipulation/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}