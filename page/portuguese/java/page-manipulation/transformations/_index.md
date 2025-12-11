---
date: 2025-12-07
description: Aprenda a dimensionar retângulos, transladar formas e aplicar transformações
  afins em Java usando Aspose.Page para criar documentos PostScript.
linktitle: Transformations in Java Page Manipulation
second_title: Aspose.Page Java API
title: Como escalar retângulo e aplicar transformações com Aspose.Page
url: /pt/java/page-manipulation/transformations/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como dimensionar retângulo e aplicar transformações com Aspose.Page

## Introdução
Bem-vindo a um guia abrangente sobre a utilização dos recursos poderosos do **Aspose.Page for Java** para realizar uma variedade de transformações de página. Neste tutorial, você aprenderá **how to scale rectangle**, traduzir formas, girar objetos e **apply affine transform** técnicas ao criar um **PostScript document**. Essas capacidades permitem que você construa aplicações Java ricas e intensivas em gráficos sem lidar com código de renderização de baixo nível.

## Respostas rápidas
- **Como escalo um retângulo em Java com Aspose.Page?** Use o método `document.scale()` antes de desenhar a forma.  
- **Posso mover (traduzir) uma forma sem afetar outros gráficos?** Sim—salve o estado gráfico, chame `document.translate(x, y)`, desenhe e, em seguida, restaure o estado.  
- **Qual classe cria um arquivo PostScript?** `PsDocument` junto com `PsSaveOptions`.  
- **Preciso de uma licença para uso em produção?** Uma licença válida do Aspose.Page é necessária para implantações comerciais.  
- **Qual versão do Java é suportada?** Aspose.Page funciona com Java 8 e posteriores.

## Pré-requisitos
Antes de mergulharmos no guia passo a passo, certifique-se de que você tem os seguintes pré-requisitos configurados:

- Conhecimento básico de programação Java.  
- Biblioteca Aspose.Page for Java instalada. Você pode baixá‑la na [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- Um Ambiente de Desenvolvimento Integrado (IDE) Java configurado em sua máquina.

## Importar Pacotes
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

## O que é “how to scale rectangle” no Aspose.Page?
Dimensionar um retângulo altera seu tamanho ao longo dos eixos X e Y enquanto preserva sua forma. Aspose.Page expõe o método `scale(float sx, float sy)`, que aplica um **affine transform** ao estado gráfico atual. Esta é a técnica central por trás da palavra‑chave **how to scale rectangle**.

## Como transladar forma com Aspose.Page
A translação move uma forma para uma nova localização sem alterar suas dimensões. Esta é a essência de **how to translate shape**. Ao salvar o estado gráfico, aplicar `translate(dx, dy)`, desenhar e, em seguida, restaurar o estado, você mantém os outros objetos inalterados.

## Exemplo 1: Sem transformações
O primeiro exemplo desenha um retângulo simples sem nenhuma transformação aplicada. Isso serve como base para comparação com os exemplos posteriores.

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

## Exemplo 2: Translação
Aqui demonstramos **how to translate shape** movendo o contexto gráfico 250 unidades para a direita antes de desenhar um segundo retângulo.

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
Este exemplo responde à pergunta principal **how to scale rectangle**. Reduzimos o retângulo para 50 % de sua largura original e 75 % de sua altura.

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
A rotação é outra operação affine comum. Embora os trechos de código para rotação sejam omitidos por brevidade, o padrão é idêntico: salve o estado gráfico, chame `document.rotate(angle)`, desenhe a forma e, em seguida, restaure. Isso demonstra **rotate shape java** e **how to rotate rectangle** na prática.

## Por que usar Aspose.Page para essas transformações?
- **Independente de dispositivo**: Escreva uma vez, gere PostScript ou XPS sem código específico de plataforma.  
- **Controle fino**: Acesso direto ao estado gráfico permite combinar translação, dimensionamento, cisalhamento e rotação.  
- **Desempenho**: API de baixa sobrecarga adequada para processamento em lote de documentos grandes.  

## Casos de uso comuns
- Geração de faturas imprimíveis com códigos de barras dinâmicos e logotipos.  
- Criação de diagramas técnicos onde dimensionamento e posicionamento precisos são necessários.  
- Automatização da produção de relatórios de várias páginas em formato PostScript.  

## Conclusão
Neste tutorial, exploramos várias transformações na Manipulação de Páginas Java usando Aspose.Page for Java, focando em **how to scale rectangle**, **how to translate shape** e outras operações affine. Seguindo estes exemplos, você pode aprimorar suas aplicações Java com capacidades avançadas de manipulação de páginas e **create PostScript document** que atendem aos padrões profissionais de publicação.

## FAQ's
### Posso usar Aspose.Page for Java para outros formatos de documento?
Aspose.Page foca principalmente na manipulação de páginas para os formatos PostScript e XPS.

### Onde posso encontrar mais exemplos e documentação para Aspose.Page for Java?
Visite a [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) para informações abrangentes.

### Existe uma versão de avaliação gratuita disponível para Aspose.Page for Java?
Sim, você pode acessar uma avaliação gratuita [aqui](https://releases.aspose.com/).

### Como posso obter uma licença temporária para Aspose.Page for Java?
Obtenha uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Onde posso buscar suporte da comunidade ou fazer perguntas sobre Aspose.Page for Java?
Visite o [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) para discussões da comunidade.

## Perguntas Frequentes

**Q: Qual é a diferença entre `translate` e `scale`?**  
A: `translate` move a origem do sistema de coordenadas, enquanto `scale` altera o tamanho dos objetos desenhados ao longo dos eixos X e/ou Y.

**Q: Posso combinar múltiplas transformações em um único estado gráfico?**  
A: Sim—chamando `translate`, `scale`, `rotate` ou `shear` sequencialmente antes de desenhar, você cria uma transformação affine combinada.

**Q: Como redefino as transformações após desenhar uma forma?**  
A: Use `document.writeGraphicsRestore()` para reverter ao estado gráfico previamente salvo.

**Q: É possível girar um retângulo ao redor de seu centro?**  
A: Absolutamente. Translade o retângulo para a origem, aplique `rotate(angle)`, então translade de volta antes de desenhar.

**Q: O Aspose.Page suporta anti‑aliasing para gráficos mais suaves?**  
A: Sim—defina as opções de renderização apropriadas em `PsSaveOptions` para habilitar o anti‑aliasing.

---

**Última atualização:** 2025-12-07  
**Testado com:** Aspose.Page for Java 24.12  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}