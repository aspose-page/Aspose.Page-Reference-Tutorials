---
title: Adicionar gradiente horizontal em Java PostScript
linktitle: Adicionar gradiente horizontal em Java PostScript
second_title: API Java Aspose.Page
description: Aprenda como adicionar um gradiente horizontal em Java PostScript com Aspose.Page para Java. Crie documentos visualmente impressionantes sem esforço.
weight: 11
url: /pt/java/postscript-gradient-addition/horizontal/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar gradiente horizontal em Java PostScript

## Introdução
Bem-vindo a este tutorial abrangente sobre como adicionar um gradiente horizontal em Java PostScript usando Aspose.Page para Java. Aspose.Page é uma biblioteca Java poderosa que permite aos desenvolvedores trabalhar com PostScript e outros formatos de documentos. Neste tutorial, orientaremos você no processo de criação de um documento PostScript com gradiente horizontal usando exemplos passo a passo.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
- Java Development Kit (JDK) instalado em sua máquina.
- Aspose.Page para biblioteca Java. Você pode baixá-lo no[Documentação Java Aspose.Page](https://reference.aspose.com/page/java/).
## Importar pacotes
Comece importando os pacotes necessários em seu projeto Java. Esses pacotes são cruciais para trabalhar com Aspose.Page.
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.LinearGradientPaint;
import java.awt.MultipleGradientPaint;
import java.awt.geom.AffineTransform;
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;

```
## Etapa 1: crie um retângulo
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Crie fluxo de saída para documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "HorizontalGradient_outPS.ps");
// Crie opções de salvamento com tamanho A4
PsSaveOptions options = new PsSaveOptions();
// Crie um novo documento PS com a página aberta
PsDocument document = new PsDocument(outPsStream, options, false);
//Crie um retângulo
Rectangle2D.Float rectangle = new Rectangle2D.Float(200, 100, 200, 100);
```
## Etapa 2: criar tinta gradiente linear horizontal
```java
// Crie tinta gradiente linear horizontal. Os componentes de escala na transformação devem ser iguais à largura e à altura do retângulo.
// Os componentes de tradução são deslocamentos do retângulo.
LinearGradientPaint paint = new LinearGradientPaint(new Point2D.Float(0, 0), new Point2D.Float(200, 100),
        new float[]{0, 1}, new Color[]{new Color(0, 0, 0, 150), new Color(40, 128, 70, 50)},
        MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        new AffineTransform(200, 0, 0, 100, 200, 100));
// Definir pintura
document.setPaint(paint);
```
## Etapa 3: preencha o retângulo
```java
// Preencha o retângulo
document.fill(rectangle);
```
## Passo 4: Preencha um Texto com o Gradiente
```java
// Preencha um texto com o gradiente
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 300, paint, Color.BLACK, new BasicStroke(2));
```
## Etapa 5: traçar um texto com o gradiente
```java
// Traçar um texto com o gradiente
document.outlineText("ABC", font, 200, 400, paint, new BasicStroke(5));
```
## Conclusão
Parabéns! Você adicionou com sucesso um gradiente horizontal em Java PostScript usando Aspose.Page para Java. Este tutorial forneceu um guia passo a passo detalhado para ajudá-lo a criar documentos PostScript visualmente atraentes.
## perguntas frequentes
### Posso usar Aspose.Page for Java em projetos comerciais?
Sim, Aspose.Page for Java pode ser usado em projetos comerciais. Para detalhes de licenciamento, visite[Aspose.Compra](https://purchase.aspose.com/buy).
### Existe um teste gratuito disponível?
 Sim, você pode acessar uma avaliação gratuita do Aspose.Page for Java[aqui](https://releases.aspose.com/).
### Onde posso encontrar documentação e suporte adicionais?
 Visite a[Documentação Java Aspose.Page](https://reference.aspose.com/page/java/) para recursos abrangentes. Para suporte da comunidade, verifique o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39).
### Como posso obter uma licença temporária?
 Você pode obter uma licença temporária em[Aspose.Compra](https://purchase.aspose.com/temporary-license/).
### Quais são os requisitos de sistema para Aspose.Page para Java?
 Consulte o[documentação](https://reference.aspose.com/page/java/) para requisitos detalhados do sistema.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
