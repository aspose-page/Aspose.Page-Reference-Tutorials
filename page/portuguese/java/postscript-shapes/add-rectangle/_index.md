---
date: 2025-12-11
description: Aprenda a desenhar formas retangulares em Java PostScript usando Aspose.Page.
  Este guia passo a passo mostra como definir a pintura, definir a cor do retângulo
  em Java e criar gráficos vibrantes.
linktitle: Add Rectangle in Java PostScript
second_title: Aspose.Page Java API
title: Como desenhar retângulo em Java PostScript com Aspose.Page
url: /pt/java/postscript-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como desenhar retângulo em Java PostScript com Aspose.Page

## Introdução
Se você precisa **como desenhar retângulo** formas dentro de um arquivo Java PostScript, você chegou ao lugar certo. Neste tutorial vamos percorrer o uso do Aspose.Page para Java para adicionar retângulos coloridos, controlar seu preenchimento e contorno, e salvar o resultado como um documento PostScript. Você verá exatamente **como definir paint**, como definir a geometria do retângulo, e por que essa abordagem é ideal para gerar gráficos imprimíveis programaticamente.

## Respostas rápidas
- **Qual biblioteca é necessária?** Aspose.Page for Java  
- **Posso mudar as cores do retângulo?** Sim – use `setPaint` com qualquer `java.awt.Color`  
- **Preciso de licença para desenvolvimento?** Uma versão de avaliação gratuita funciona para testes; uma licença é necessária para produção  
- **Qual tamanho de página é usado no exemplo?** A4 (padrão `PsSaveOptions`)  
- **O código é compatível com Java 8+?** Absolutamente – ele usa classes padrão do AWT  

## Pré-requisitos
- Compreensão básica de programação Java.  
- Biblioteca Aspose.Page para Java instalada. Caso não esteja, faça o download a partir da [documentação do Aspose.Page para Java](https://reference.aspose.com/page/java/).  
- Um ambiente de desenvolvimento Java configurado na sua máquina.

## Importar pacotes
No seu projeto Java, comece importando os pacotes necessários:

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Como desenhar retângulo em Java PostScript
Abaixo está o fluxo de trabalho completo dividido em etapas claras. Cada etapa inclui uma breve explicação seguida pelo bloco de código original (inalterado).

### Etapa 1: Definir paint para preenchimento do retângulo  
**Como definir paint** – escolhemos uma cor de preenchimento laranja para o primeiro retângulo.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddRectangle_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
// Set paint for filling rectangle
document.setPaint(Color.ORANGE);        
// Fill the first rectangle
document.fill(new Rectangle2D.Float(250, 100, 150, 100));
```

### Etapa 2: Definir paint para contorno do retângulo  
**Definir cor do retângulo java** – agora alteramos o paint para vermelho e definimos a largura do traço.

```java
// Set paint for stroking rectangle
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second rectangle
document.draw(new Rectangle2D.Float(250, 300, 150, 100));
```

### Etapa 3: Fechar a página atual e salvar o documento  
Após desenhar, fechamos a página e persistimos o arquivo.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Por que usar Aspose.Page para gráficos de retângulo?
- **Multiplataforma**: Gera PostScript padrão que funciona em qualquer impressora.  
- **Controle granular**: Você pode definir cores de preenchimento, cores de contorno e larguras de linha de forma independente.  
- **Sem dependências externas**: Usa apenas as classes de geometria AWT incorporadas.  

## Problemas comuns e dicas
- **Erros de caminho de arquivo** – certifique-se de que `dataDir` termina com um separador de arquivos (`/` ou `\\`).  
- **Exceções de licença** – a versão de avaliação adiciona uma marca d'água; obtenha uma licença completa para uso em produção.  
- **Visibilidade de cor** – algumas impressoras podem interpretar certos valores RGB de forma diferente; teste primeiro com um retângulo preto simples.

## Conclusão
Neste guia demonstramos **como desenhar retângulo** em um documento Java PostScript, abordamos **como definir paint** e mostramos como **definir cor do retângulo java** usando Aspose.Page. Sinta-se à vontade para experimentar diferentes formas, cores e estilos de linha para criar gráficos imprimíveis ricos para relatórios, faturas ou impressões personalizadas.

## Perguntas Frequentes

### Posso usar Aspose.Page para Java com outras linguagens de programação?
O Aspose.Page suporta principalmente Java, mas bibliotecas semelhantes estão disponíveis para outras linguagens.

### Existe uma versão de avaliação do Aspose.Page para Java disponível?
Sim, você pode explorar os recursos do Aspose.Page para Java com a [versão de avaliação gratuita](https://releases.aspose.com/).

### Onde posso encontrar ajuda adicional e discussões?
Visite o [fórum do Aspose.Page](https://forum.aspose.com/c/page/39) para interagir com a comunidade e obter assistência.

### Como posso obter uma licença temporária para Aspose.Page para Java?
Obtenha uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

### Onde posso comprar uma versão licenciada do Aspose.Page para Java?
Compre uma versão licenciada [aqui](https://purchase.aspose.com/buy).

**Perguntas e Respostas Adicionais**

**Q:** *Posso mudar o tamanho do retângulo dinamicamente?*  
**A:** Sim – basta modificar os parâmetros `Rectangle2D.Float(x, y, width, height)` antes de chamar `fill` ou `draw`.

**Q:** *É possível adicionar texto dentro do retângulo?*  
**A:** Absolutamente. Após desenhar o retângulo, use `document.drawString(...)` com a fonte e posição desejadas.

**Q:** *O Aspose.Page suporta outras formas como círculos ou polígonos?*  
**A:** Sim, a API fornece métodos como `drawEllipse` e `drawPolygon` para uma variedade de gráficos vetoriais.

---

**Última atualização:** 2025-12-11  
**Testado com:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}