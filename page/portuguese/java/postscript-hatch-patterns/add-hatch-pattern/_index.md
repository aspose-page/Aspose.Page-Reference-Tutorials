---
title: Adicionar padrão de hachura em Java PostScript
linktitle: Adicionar padrão de hachura em Java PostScript
second_title: API Java Aspose.Page
description: Aprenda como adicionar padrões de hachura cativantes a documentos Java PostScript usando Aspose.Page. Eleve seu conteúdo visual sem esforço.
weight: 10
url: /pt/java/postscript-hatch-patterns/add-hatch-pattern/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar padrão de hachura em Java PostScript

## Introdução
No mundo da programação Java, aprimorar elementos visuais é um requisito comum para desenvolvedores. Um aprimoramento visual intrigante é a adição de padrões de hachura aos documentos PostScript. Este tutorial irá guiá-lo através do processo de adição de padrões de hachura usando Aspose.Page para Java.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter a seguinte configuração:
- Ambiente de desenvolvimento Java: certifique-se de ter um ambiente de desenvolvimento Java pronto.
-  Biblioteca Aspose.Page para Java: Baixe e instale a biblioteca Aspose.Page para Java. Você pode encontrar os arquivos necessários[aqui](https://releases.aspose.com/page/java/).
## Importar pacotes
Para começar, importe os pacotes necessários para o seu projeto Java. Use o seguinte trecho de código:
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
## Etapa 1: configurar os parâmetros iniciais
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie fluxo de saída para documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Crie opções de salvamento com tamanho A4
PsSaveOptions options = new PsSaveOptions();
// Crie um novo documento PS com a página aberta
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```
## Etapa 2: salvar o estado dos gráficos e traduzir
```java
document.writeGraphicsSave();
document.translate(x0, y0);
```
## Etapa 3: crie um quadrado para cada padrão
```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```
## Etapa 4: configurar a caneta para contorno quadrado padrão
```java
BasicStroke stroke = new BasicStroke(2);
```
## Etapa 5: iterar por meio de padrões de hachura
```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue com o código fornecido)
}
```
## Etapa 6: restaurar o estado dos gráficos
```java
document.writeGraphicsRestore();
```
## Etapa 7: preencher o texto com padrão de hachura
```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```
## Etapa 8: delinear o texto com padrão de hachura
```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```
## Etapa 9: feche e salve o documento
```java
document.closePage();
document.save();
```
Siga estas etapas e você adicionará padrões de hachura ao seu documento Java PostScript usando Aspose.Page.
## Conclusão
A incorporação de elementos visuais, como padrões de hachura, pode aumentar significativamente o apelo de seus aplicativos Java. Aspose.Page for Java torna esse processo perfeito, permitindo criar documentos PostScript visualmente impressionantes sem esforço.
## Perguntas frequentes
### Posso usar Aspose.Page for Java com outras estruturas Java?
Sim, Aspose.Page for Java foi projetado para integração perfeita com várias estruturas Java.
### Há uma versão de teste disponível para Aspose.Page for Java?
 Sim, você pode acessar o teste gratuito[aqui](https://releases.aspose.com/).
### Como posso obter uma licença temporária para Aspose.Page for Java?
 Você pode adquirir uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Onde posso encontrar mais tutoriais e suporte para Aspose.Page for Java?
 Explore o[Fórum Aspose.Page para Java](https://forum.aspose.com/c/page/39) para tutoriais e suporte da comunidade.
### Existe um recurso de documentação abrangente para Aspose.Page for Java?
 Sim, consulte a documentação[aqui](https://reference.aspose.com/page/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
