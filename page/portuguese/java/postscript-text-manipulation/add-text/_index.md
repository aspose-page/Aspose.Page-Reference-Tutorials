---
date: 2025-12-14
description: Aprenda como definir a cor do texto em Java usando Aspose.Page for Java,
  adicionar texto ao PostScript e aplicar contorno ao texto para um estilo de documento
  rico.
linktitle: Add Text in Java PostScript
second_title: Aspose.Page Java API
title: Definir a Cor do Texto em Java com Aspose.Page – Guia de Manipulação de Texto
url: /pt/java/postscript-text-manipulation/add-text/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definir Cor do Texto Java com Aspose.Page – Guia de Manipulação de Texto

## Introdução
Bem‑vindo ao nosso guia passo a passo sobre **definir cor do texto java** ao trabalhar com arquivos PostScript usando Aspose.Page para Java. Aspose.Page para Java é uma biblioteca poderosa que permite que desenvolvedores criem e **gerem documentos postscript**, manipulem fontes e estilizem texto com precisão. Neste tutorial você aprenderá como adicionar texto, mudar sua cor, ajustar o tamanho e até **aplicar contorno ao texto** para um visual refinado.

## Respostas Rápidas
- **Qual biblioteca me permite definir a cor do texto em Java?** Aspose.Page para Java.  
- **Posso usar fontes do sistema e fontes personalizadas?** Sim, ambas são suportadas.  
- **Como altero o tamanho do texto?** Especificando o tamanho da fonte ao criar o `Font` ou `DrFont`.  
- **É possível contornar e preencher o texto ao mesmo tempo?** Absolutamente – use `fillAndStrokeText`.  
- **Qual formato de saída este tutorial produz?** Um documento PostScript (`.ps`).

## O que é “definir cor do texto java”?
Definir a cor do texto em Java significa especificar o objeto `Color` que o motor de renderização (neste caso, Aspose.Page) usa ao desenhar caracteres em uma página. Essa operação é essencial para criar documentos visualmente distintos, especialmente ao gerar **documentos postscript** programaticamente.

## Por que usar Aspose.Page para Java?
- **Controle total** sobre a geração de PostScript sem precisar de um interpretador nativo de PostScript.  
- **Suporte a fontes do sistema e externas**, permitindo incorporar qualquer tipografia que você precisar.  
- **API simples** para preencher, contornar e **preencher e contornar texto**, oferecendo flexibilidade na estilização.  
- **Compatibilidade multiplataforma** – escreva uma vez, execute onde o Java for suportado.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

- Conhecimento básico de programação Java.  
- Biblioteca Aspose.Page para Java instalada. Você pode baixá‑la na [página de download do Aspose.Page para Java](https://releases.aspose.com/page/java/).  
- Fontes necessárias disponíveis na pasta especificada. Detalhes adicionais estão na [documentação do Aspose.Page para Java](https://reference.aspose.com/page/java/).

## Importar Pacotes
No seu projeto Java, importe os pacotes necessários para Aspose.Page para Java:

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

## Etapa 1: Configurar o Documento
Primeiro, criamos um novo **documento PostScript** e configuramos as opções de saída.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
String FONTS_FOLDER = dataDir + "necessary_fonts/";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddText_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
options.setAdditionalFontsFolders(new String[] { FONTS_FOLDER });
// A text to write to PS file
String str = "ABCDEFGHIJKLMNO";
int fontSize = 48;
// Create new 1-paged PS Document
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Como Definir Cor do Texto Java Usando Fonte do Sistema
Agora demonstramos **definir cor do texto java** com uma fonte fornecida pelo sistema.

```java
// Using system font for filling text
Font font = new Font("Times New Roman", Font.BOLD, fontSize);
// Fill text with default or already defined color (black)
document.fillText(str, font, 50, 100);
// Fill text with blue color
document.fillText(str, font, 50, 150, Color.BLUE);
```

> **Dica:** O método `fillText` usa automaticamente a cor atual se você não passar um argumento `Color`, que por padrão é preto.

## Usando Fonte Personalizada e Alterando o Tamanho do Texto
Você também pode **alterar o tamanho do texto** e usar uma fonte personalizada armazenada na sua pasta de fontes.

```java
// Using custom font for filling text
DrFont drFont = ExternalFontCache.fetchDrFont("Palatino Linotype", fontSize, Font.PLAIN);
// Fill text with default or already defined color (black)
document.fillText(str, drFont, 50, 200);
// Fill text with blue color
document.fillText(str, drFont, 50, 250, Color.BLUE);
```

## Contornando (Stroke) Texto – Aplicar Contorno ao Texto
Contornar o texto lhe dá uma borda nítida. Aqui nós **aplicamos contorno ao texto** usando um `BasicStroke`.

```java
// Using system font for outlining text
document.outlineText(str, font, 50, 300);
// Outline text with blue‑violet colored 2‑points width pen
Stroke stroke = new BasicStroke(2);
Color strokeColor = new Color(138, 43, 226); // blue‑violet
document.outlineText(str, font, 50, 350, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, font, 50, 400, Color.YELLOW, strokeColor, stroke);
```

## Contornando Texto com Fonte Personalizada
A mesma técnica funciona com fontes personalizadas.

```java
// Using custom font for outlining text
document.outlineText(str, drFont, 50, 450);
// Outline text with blue‑violet colored 2‑points width pen
document.outlineText(str, drFont, 50, 500, strokeColor, stroke);
// Fill text with orange color and stroke with blue colored 2‑points width pen
document.fillAndStrokeText(str, drFont, 50, 550, Color.ORANGE, Color.BLUE, stroke);
```

## Etapa 6: Salvar o Documento
Por fim, feche a página e grave o arquivo no disco.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

## Problemas Comuns & Soluções
| Problema | Solução |
|----------|---------|
| **Fonte não encontrada** | Certifique‑se de que o arquivo de fonte está colocado em `necessary_fonts` e que o caminho da pasta foi adicionado corretamente via `options.setAdditionalFontsFolders`. |
| **Cor não aplicada** | Verifique se está chamando a sobrecarga de `fillText` ou `outlineText` que inclui um argumento `Color`. |
| **Contorno muito fino** | Aumente a largura do `BasicStroke` (por exemplo, `new BasicStroke(3)`). |
| **Documento não abre** | Confirme que o arquivo `.ps` gerado foi salvo com a extensão correta e que seu visualizador suporta PostScript. |

## Perguntas Frequentes

**P:** Posso usar minhas próprias fontes personalizadas com Aspose.Page para Java?  
**R:** Sim, você pode usar fontes personalizadas especificando o nome da fonte e o tamanho na classe `DrFont`.

**P:** Como posso mudar a cor do texto?  
**R:** Você pode definir a cor desejada usando a classe `Color` ao preencher ou contornar o texto.

**P:** É possível adicionar várias páginas a um documento PostScript?  
**R:** Absolutamente! Você pode criar múltiplas páginas repetindo as etapas de criação e salvamento do documento.

**P:** Qual é a finalidade da classe `ExternalFontCache`?  
**R:** `ExternalFontCache` é usada para buscar fontes personalizadas, garantindo que estejam disponíveis para a manipulação de texto.

**P:** Posso aplicar diferentes contornos ao texto contornado?  
**R:** Sim, você pode personalizar a largura e a cor do contorno usando a classe `Stroke` e a classe `Color`, respectivamente.

## Conclusão
Parabéns! Agora você sabe como **definir cor do texto java**, mudar tamanhos de fonte, **aplicar contorno ao texto** e **criar arquivos de documento postscript** usando Aspose.Page para Java. Experimente diferentes fontes, cores e estilos de contorno para produzir saídas PostScript com aparência profissional.

---

**Última atualização:** 2025-12-14  
**Testado com:** Aspose.Page para Java 23.12 (mais recente)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}