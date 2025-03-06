---
title: Manipulação de texto Java Aspose.Page
linktitle: Adicionar texto em Java PostScript
second_title: API Java Aspose.Page
description: Explore o poder do Aspose.Page para Java em nosso tutorial sobre como adicionar texto a documentos PostScript. Aprenda a usar fontes do sistema e personalizadas com facilidade.
weight: 10
url: /pt/java/postscript-text-manipulation/add-text/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Manipulação de texto Java Aspose.Page

## Introdução
Bem-vindo ao nosso guia passo a passo sobre como adicionar texto em Java PostScript usando Aspose.Page for Java. Aspose.Page for Java é uma biblioteca poderosa que permite aos desenvolvedores manipular documentos PostScript com facilidade. Neste tutorial, orientaremos você no processo de adição de texto, uso de fontes personalizadas e do sistema, delineamento de texto e incorporação de traços para um resultado visualmente atraente.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos:
- Conhecimento básico de programação Java.
-  Biblioteca Aspose.Page para Java instalada. Você pode baixá-lo no[Página de download do Aspose.Page para Java](https://releases.aspose.com/page/java/).
-  Fontes necessárias disponíveis na pasta especificada. Você pode encontrar informações adicionais no[Documentação Aspose.Page para Java](https://reference.aspose.com/page/java/).
## Importar pacotes
Em seu projeto Java, importe os pacotes necessários para Aspose.Page for Java:
```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.Font;
import java.awt.Stroke;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
import com.aspose.page.ExternalFontCache;
import com.aspose.page.font.DrFont;
```
## Etapa 1: configurar o documento
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Crie fluxo de saída para documento PostScript
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Crie opções de salvamento com tamanho A4
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// Um texto para escrever no arquivo PS
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Crie um novo documento PS de 1 página
PsDocument document = new PsDocument(outPsStream, options, false);
```
## Etapa 2: usando a fonte do sistema para preencher o texto
```java
// Usando fonte do sistema para preencher texto
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Preencha o texto com a cor padrão ou já definida (preto)
document.fillText(str, font, 50, 100);
// Preencha o texto com a cor azul
document.fillText(str, font, 50, 150, Color.BLUE);
```
## Etapa 3: usando fonte personalizada para preencher texto
```java
// Usando fonte personalizada para preencher texto
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Preencha o texto com a cor padrão ou já definida (preto)
document.fillText(str, drFont, 50, 200);
// Preencha o texto com a cor azul
document.fillText(str, drFont, 50, 250, Color.BLUE);
```
## Etapa 4: delineando o texto com a fonte do sistema
```java
// Usando fonte do sistema para delinear texto
document.outlineText(str, font, 50, 300);
// Contorne o texto com caneta azul-violeta de 2 pontos de largura
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Preencha o texto com a cor laranja e traço com caneta azul de 2 pontos de largura
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```
## Etapa 5: delineando o texto com fonte personalizada
```java
// Usando fonte personalizada para delinear o texto
document.outlineText(str, drFont, 50, 450);
// Contorne o texto com caneta azul-violeta de 2 pontos de largura
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Preencha o texto com a cor laranja e traço com caneta azul de 2 pontos de largura
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```
## Etapa 6: salve o documento
```java
// Fechar página atual
document.closePage();
// Salve o documento
document.save();
```
## Conclusão
Parabéns! Você aprendeu com sucesso como adicionar texto em Java PostScript usando Aspose.Page for Java. Experimente diferentes fontes, cores e opções de contorno para aprimorar ainda mais seu documento.
## perguntas frequentes
### Posso usar minhas próprias fontes personalizadas com Aspose.Page for Java?
 Sim, você pode usar fontes personalizadas especificando o nome e o tamanho da fonte no campo`DrFont` aula.
### Como posso mudar a cor do texto?
 Você pode definir a cor desejada usando o`Color` aula ao preencher ou delinear o texto.
### É possível adicionar várias páginas a um documento PostScript?
Absolutamente! Você pode criar várias páginas repetindo as etapas de criação e salvamento do documento.
###  Qual é o propósito do`ExternalFontCache` class?
`ExternalFontCache` é usado para buscar fontes personalizadas, garantindo que estejam disponíveis para manipulação de texto.
### Posso aplicar traços diferentes ao texto delineado?
 Sim, você pode personalizar a largura e a cor do traço usando o`Stroke` classe e`Color` classe, respectivamente.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
