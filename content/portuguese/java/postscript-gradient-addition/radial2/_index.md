---
title: Gradiente radial PostScript Java com Aspose.Page
linktitle: Gradiente radial PostScript Java com Aspose.Page
second_title: API Java Aspose.Page
description: Explore o guia passo a passo para adicionar Gradiente Radial em Java PostScript usando Aspose.Page para obter gráficos impressionantes em seus aplicativos Java.
type: docs
weight: 13
url: /pt/java/postscript-gradient-addition/radial2/
---
## Introdução
Bem-vindo ao nosso guia passo a passo sobre como adicionar Radial Gradient 2 em Java PostScript usando Aspose.Page para Java. Este tutorial orientará você no processo de criação de um documento PostScript com um lindo gradiente radial, aprimorando seus aplicativos Java com gráficos visualmente atraentes.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento prático de programação Java.
- Instalado o Java Development Kit (JDK) em sua máquina.
-  Biblioteca Aspose.Page para Java, que você pode baixar do[Documentação Java Aspose.Page](https://reference.aspose.com/page/java/).
## Importar pacotes
No seu projeto Java, importe os pacotes necessários para Aspose.Page:
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
## Etapa 1: configurar o diretório de documentos
Defina o caminho para o diretório do seu documento:
```java
String dataDir = "Your Document Directory";
```
## Etapa 2: criar fluxo de saída
Crie um fluxo de saída para o documento PostScript:
```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```
## Etapa 3: criar opções para salvar
Crie opções de salvamento com tamanho A4:
```java
PsSaveOptions options = new PsSaveOptions();
```
## Etapa 4: criar documento PS
Crie um novo documento PS com a página aberta:
```java
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Etapa 5: crie um círculo
Defina um círculo usando a classe Ellipse2D.Float:
```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```
## Etapa 6: definir cores gradientes
Crie matrizes de cores e frações para o gradiente radial:
```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```
## Etapa 7: Criar AffineTransform
Crie um AffineTransform para o gradiente radial:
```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```
## Etapa 8: criar tinta gradiente radial
Crie um RadialGradientPaint com os parâmetros especificados:
```java
RadialGradientPaint paint = new RadialGradientPaint(new Point2D.Float(64, 64), 68, new Point2D.Float(24, 24),
        fractions, colors, MultipleGradientPaint.CycleMethod.NO_CYCLE, MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```
## Etapa 9: definir círculo de pintura e preenchimento
Defina a tinta e preencha o círculo com o gradiente radial:
```java
document.setPaint(paint);
document.fill(circle);
```
## Etapa 10: feche a página e salve o documento
Feche a página atual e salve o documento:
```java
document.closePage();
document.save();
```
Parabéns! Você adicionou com sucesso Radial Gradient 2 em Java PostScript usando Aspose.Page para Java.
## Conclusão
Neste tutorial, exploramos como aprimorar seus aplicativos Java com gradientes radiais em documentos PostScript. Aspose.Page for Java fornece um poderoso conjunto de ferramentas para criar gráficos impressionantes, permitindo que você leve seus projetos Java para o próximo nível.
## Perguntas frequentes
### P: Onde posso encontrar a documentação do Aspose.Page for Java?
 R: A documentação está disponível[aqui](https://reference.aspose.com/page/java/).
### P: Como posso baixar Aspose.Page para Java?
 R: Você pode baixá-lo no[página de lançamentos](https://releases.aspose.com/page/java/).
### P: Existe uma avaliação gratuita disponível?
 R: Sim, você pode acessar o teste gratuito[aqui](https://releases.aspose.com/).
### P: Posso obter uma licença temporária do Aspose.Page for Java?
 R: Sim, você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### P: Onde posso buscar apoio da comunidade e participar de discussões?
 R: Visite o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39).