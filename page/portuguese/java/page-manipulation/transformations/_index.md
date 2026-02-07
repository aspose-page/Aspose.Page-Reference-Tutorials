---
date: 2026-02-07
description: Aprenda como dimensionar retângulos com Aspose.Page para Java, como transladar
  formas e aplicar transformações afins para criar documentos PostScript.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Como escalar um retângulo com Aspose.Page para Java
url: /pt/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como dimensionar retângulo com Aspose.Page para Java

## Introdução
Bem‑vindo a um guia abrangente sobre como utilizar os recursos poderosos do **Aspose.Page for Java** para executar uma variedade de transformações de página. Neste tutorial você aprenderá **como dimensionar retângulo**, traduzir formas, girar objetos e **aplicar transformações afins** ao criar um **documento PostScript**. Esses recursos permitem que você construa aplicações Java ricas e intensivas em gráficos sem lidar com código de renderização de baixo nível.

## Respostas rápidas
- **Como dimensiono um retângulo em Java com Aspose.Page?** Use o método `document.scale()` antes de desenhar a forma.  
- **Posso mover (traduzir) uma forma sem afetar outros gráficos?** Sim—salve o estado gráfico, chame `document.translate(x, y)`, desenhe e, em seguida, restaure o estado.  
- **Qual classe cria um arquivo PostScript?** `PsDocument` juntamente com `PsSaveOptions`.  
- **Preciso de licença para uso em produção?** É necessária uma licença válida do Aspose.Page para implantações comerciais.  
- **Qual versão do Java é suportada?** Aspose.Page funciona com Java 8 ou superior.

## Pré‑requisitos
Antes de mergulharmos no guia passo a passo, certifique-se de que você possui os seguintes pré‑requisitos:

- Conhecimento básico de programação Java.  
- Biblioteca Aspose.Page for Java instalada. Você pode baixá‑la na [documentação do Aspose.Page for Java](https://reference.aspose.com/page/java/).  
- Um Ambiente de Desenvolvimento Integrado (IDE) Java configurado em sua máquina.

## Importar pacotes
Em seu projeto Java, importe os pacotes necessários para utilizar o Aspose.Page for Java:

```java
import java.awt.Color;
import java.awt.Shape;
import java.awt.geom.AffineTransform;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## O que é “como dimensionar retângulo” no Aspose.Page?
Dimensionar um retângulo altera seu tamanho ao longo dos eixos X e Y, preservando sua forma. O Aspose.Page expõe o método `scale(float sx, float sy)`, que aplica uma **transformação afim** ao estado gráfico atual. Essa é a técnica central por trás da palavra‑chave **como dimensionar retângulo**.

## Como traduzir forma com Aspose.Page
A tradução move uma forma para uma nova localização sem alterar suas dimensões. Essa é a essência de **como traduzir forma**. Ao salvar o estado gráfico, aplicar `translate(dx, dy)`, desenhar e, então, restaurar o estado, você mantém os demais objetos inalterados.

## Exemplo 1: Sem transformações
O primeiro exemplo desenha um retângulo simples sem nenhuma transformação aplicada. Ele serve como referência para comparação com os exemplos posteriores.

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

## Exemplo 2: Tradução
Aqui demonstramos **como traduzir forma** movendo o contexto gráfico 250 unidades para a direita antes de desenhar um segundo retângulo.

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

## Exemplo 3: Dimensionamento
Este exemplo responde à pergunta principal **como dimensionar retângulo**. Reduzimos o retângulo para 50 % de sua largura original e 75 % de sua altura.

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

## Como girar forma Java (rotate shape java)
A rotação é outra operação afim comum. Embora os trechos de código para rotação sejam omitidos por brevidade, o padrão é idêntico: salve o estado gráfico, chame `document.rotate(angle)`, desenhe a forma e, então, restaure. Isso demonstra **rotate shape java** e **como girar retângulo** na prática.

## Por que isso importa – Benefícios no mundo real
- **Saída independente de dispositivo** – Escreva uma vez e gere PostScript ou XPS sem ajustes específicos de plataforma.  
- **Controle granular** – Combine tradução, dimensionamento, cisalhamento e rotação para atender a requisitos de layout exatos.  
- **Desempenho otimizado** – API de baixo overhead ideal para processamento em lote de documentos de grande escala.  

## Casos de uso comuns
- Geração de faturas imprimíveis – por exemplo, uma solução **printable invoice java** que posiciona logotipos e códigos de barras com precisão.  
- Criação de diagramas técnicos onde dimensionamento e posicionamento precisos são necessários.  
- Automação da produção de relatórios multipágina em formato PostScript.

## Problemas comuns e soluções
- **Transformação não sendo redefinida** – Sempre emparelhe `document.writeGraphicsSave()` com `document.writeGraphicsRestore()` para evitar efeitos indesejados de herança.  
- **Cores inesperadas** – Certifique‑se de definir a tinta após cada transformação; o estado gráfico não mantém as configurações de cor anteriores após uma restauração.  
- **Tamanho de arquivo muito grande** – Use `PsSaveOptions` para habilitar compressão ou reduzir a resolução da imagem ao incorporar gráficos rasterizados.

## Perguntas Frequentes
### Posso usar Aspose.Page for Java para outros formatos de documento?
O Aspose.Page foca principalmente na manipulação de páginas para os formatos PostScript e XPS.

### Onde posso encontrar mais exemplos e documentação para Aspose.Page for Java?
Visite a [documentação do Aspose.Page for Java](https://reference.aspose.com/page/java/) para informações completas.

### Existe uma versão de avaliação gratuita do Aspose.Page for Java?
Sim, você pode acessar uma avaliação gratuita [aqui](https://releases.aspose.com/).

### Como obtenho uma licença temporária para Aspose.Page for Java?
Obtenha uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Onde posso buscar suporte da comunidade ou fazer perguntas sobre Aspose.Page for Java?
Visite o [fórum do Aspose.Page for Java](https://forum.aspose.com/c/page/39) para discussões da comunidade.

## Perguntas Frequentes

**Q: Qual a diferença entre `translate` e `scale`?**  
A: `translate` move a origem do sistema de coordenadas, enquanto `scale` altera o tamanho dos objetos desenhados ao longo dos eixos X e/ou Y.

**Q: Posso combinar múltiplas transformações em um único estado gráfico?**  
A: Sim—chamando `translate`, `scale`, `rotate` ou `shear` sequencialmente antes de desenhar, você cria uma transformação afim combinada.

**Q: Como redefino as transformações após desenhar uma forma?**  
A: Use `document.writeGraphicsRestore()` para retornar ao estado gráfico previamente salvo.

**Q: É possível girar um retângulo ao redor de seu centro?**  
A: Absolutamente. Traduza o retângulo para a origem, aplique `rotate(angle)`, então traduza‑o de volta antes de desenhar.

**Q: O Aspose.Page suporta anti‑aliasing para gráficos mais suaves?**  
A: Sim—defina as opções de renderização apropriadas em `PsSaveOptions` para habilitar anti‑aliasing.

---

**Última atualização:** 2026-02-07  
**Testado com:** Aspose.Page for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}