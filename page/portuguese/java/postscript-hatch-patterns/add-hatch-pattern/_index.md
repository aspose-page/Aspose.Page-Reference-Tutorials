---
date: 2025-12-08
description: Aprenda a adicionar padrões de hachura a documentos PostScript Java usando
  Aspose.Page Java. Este guia passo a passo mostra como inserir gráficos de padrão
  de hachura de forma eficiente.
language: pt
linktitle: Add Hatch Pattern in Java PostScript
second_title: Aspose.Page Java API
title: 'Aspose.Page Java: Adicionar padrão de hachura no PostScript Java'
url: /java/postscript-hatch-patterns/add-hatch-pattern/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Padrão de Hachura em Java PostScript

## Introdução
Se você está trabalhando com **Aspose.Page Java** e precisa enriquecer sua saída PostScript com gráficos texturizados, os padrões de hachura são uma solução rápida e flexível. Neste tutorial vamos percorrer **como adicionar designs de hachura** a um documento PostScript, explicar por que eles são úteis e fornecer um exemplo de código completo e pronto‑para‑executar. Ao final, você será capaz de criar formas e textos preenchidos com hachura visualmente atraentes usando apenas algumas linhas de Java.

## Respostas Rápidas
- **Qual biblioteca eu preciso?** Aspose.Page for Java (o SDK “aspose page java”).  
- **Qual efeito visual estamos adicionando?** Padrões de hachura (por exemplo, linhas diagonais, cruzadas).  
- **Preciso de licença para executar o exemplo?** Uma avaliação gratuita funciona para desenvolvimento; uma licença é necessária para produção.  
- **Quantas linhas de código?** Cerca de 70 linhas, divididas em etapas claras.  
- **Posso usar a mesma abordagem para PDFs?** Sim—Aspose.Page suporta múltiplos formatos de saída, incluindo PDF.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

- **Ambiente de Desenvolvimento Java** – JDK 8 ou superior e uma IDE de sua escolha.  
- **Biblioteca Aspose.Page for Java** – Baixe o JAR mais recente no site oficial [here](https://releases.aspose.com/page/java/).  
- **Permissão de escrita** em uma pasta onde o arquivo PostScript gerado será salvo.

## Importar Pacotes
Primeiro, traga as classes necessárias para o seu projeto. Essas importações dão acesso a primitivas de desenho, manipulação de cores e à API Aspose.Page.

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

## Etapa 1: Configurar Parâmetros Iniciais
Crie o fluxo de saída, configure o tamanho da página (A4) e defina algumas variáveis de layout que serão reutilizadas ao desenhar cada quadrado preenchido com hachura.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddHatchPattern_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
int x0 = 20;
int y0 = 100;
int squareSide = 32;
int width = 500;
int sumX = 0;
```

## Etapa 2: Salvar o Estado Gráfico e Translacionar
Salvar o estado gráfico permite que retornemos ao sistema de coordenadas original mais tarde, enquanto `translate` move a origem para um ponto de partida conveniente.

```java
document.writeGraphicsSave();
document.translate(x0, y0);
```

## Etapa 3: Criar Quadrado para Cada Padrão
Defina um retângulo reutilizável que representará cada célula preenchida com hachura.

```java
Rectangle2D.Float square = new Rectangle2D.Float(0, 0, squareSide, squareSide);
```

## Etapa 4: Configurar a Caneta para o Contorno do Quadrado do Padrão
Um `BasicStroke` de 2 pontos fornece um contorno nítido ao redor de cada quadrado.

```java
BasicStroke stroke = new BasicStroke(2);
```

## Etapa 5: Iterar pelos Padrões de Hachura
Percorra cada valor no enum `HatchStyle`, preencha cada quadrado com a textura correspondente e, em seguida, desenhe seu contorno. Esta é a parte central da funcionalidade de **adição de padrão de hachura**.

```java
HatchStyle[] hatchStyles = HatchStyle.values();
for (int i = 0; i < hatchStyles.length; i++) {
    // ... (continue with the provided code)
}
```

## Etapa 6: Restaurar o Estado Gráfico
Retorne ao sistema de coordenadas original após terminar de desenhar a grade de quadrados.

```java
document.writeGraphicsRestore();
```

## Etapa 7: Preencher Texto com Padrão de Hachura
Aqui demonstramos como pintar texto usando uma textura de hachura. O exemplo preenche a palavra “ABC” com um padrão diagonal‑cruzado.

```java
TexturePaint paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.DiagonalCross, Color.RED, Color.YELLOW);
Font font = new Font("Arial", Font.BOLD, 96);
document.fillAndStrokeText("ABC", font, 200, 320, paint, Color.BLACK, stroke);
```

## Etapa 8: Contornar Texto com Padrão de Hachura
Agora contornamos o mesmo texto, mas desta vez usando um estilo de hachura de 70 % e um traço mais grosso.

```java
paint = HatchPaintLibrary.getHatchTexturePaint(HatchStyle.Percent70, Color.BLUE, Color.WHITE);
document.outlineText("ABC", font, 200, 420, paint, new BasicStroke(5));
```

## Etapa 9: Fechar e Salvar o Documento
Finalize a página, grave o arquivo no disco e libere os recursos.

```java
document.closePage();
document.save();
```

Siga estas etapas e você terá um arquivo PostScript que demonstra um conjunto completo de padrões de hachura aplicados tanto a formas quanto a texto—tudo impulsionado por **aspose page java**.

## Por que Usar Padrões de Hachura com Aspose.Page Java?
- **Distinção visual** – Preenchimentos de hachura funcionam mesmo quando as impressoras são limitadas a saída monocromática.  
- **Desempenho** – Texturas são geradas sob demanda, evitando arquivos de imagem grandes.  
- **Suporte multiplataforma** – O mesmo código pode gerar PDF, EPS ou SVG com alterações mínimas.

## Armadilhas Comuns e Dicas
- **Erros de caminho de arquivo** – Certifique‑se de que `dataDir` termina com o separador de arquivos apropriado (`/` ou `\`).  
- **Cores não suportadas** – Alguns interpretadores PostScript mais antigos podem não lidar com certos espaços de cor; use RGB básico para máxima compatibilidade.  
- **Avisos de licença** – Executar o exemplo sem uma licença válida inserirá uma marca d’água na saída.

## Conclusão
Incorporar padrões de hachura pode melhorar drasticamente a legibilidade e a estética de desenhos técnicos, mapas ou quaisquer gráficos gerados por Java. Com **Aspose.Page Java**, você obtém uma API concisa que abstrai os comandos de baixo nível do PostScript, permitindo que você se concentre no design em vez das particularidades do formato de arquivo.

## Perguntas Frequentes

**Q: Posso usar Aspose.Page Java com outros frameworks Java?**  
A: Sim, a biblioteca é independente de framework e funciona com Spring, Jakarta EE, Android (limitado) e Java SE puro.

**Q: Existe uma versão de avaliação disponível para Aspose.Page Java?**  
A: Absolutamente. Baixe uma avaliação gratuita de 30 dias [here](https://releases.aspose.com/).

**Q: Como obtenho uma licença temporária para desenvolvimento?**  
A: Solicite uma licença temporária [here](https://purchase.aspose.com/temporary-license/). Ela remove as marcas d’água de avaliação.

**Q: Onde posso encontrar mais tutoriais e suporte da comunidade?**  
A: Visite o fórum oficial [Aspose.Page for Java forum](https://forum.aspose.com/c/page/39) para exemplos adicionais e perguntas‑respostas.

**Q: Existe documentação completa para todas as classes e métodos?**  
A: Sim, a referência completa da API está disponível [here](https://reference.aspose.com/page/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última Atualização:** 2025-12-08  
**Testado com:** Aspose.Page for Java 24.12 (mais recente no momento da escrita)  
**Autor:** Aspose