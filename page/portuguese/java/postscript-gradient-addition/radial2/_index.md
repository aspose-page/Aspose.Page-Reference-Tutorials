---
date: 2026-02-13
description: Aprenda a preencher formas com gradiente e desenhar círculos com gradiente
  em Java PostScript usando Aspose.Page. Guia passo a passo com código e dicas.
linktitle: Java PostScript Radial Gradient with Aspose.Page
second_title: Aspose.Page Java API
title: 'Preencher Forma com Gradiente: Exemplo Radial em Java PostScript'
url: /pt/java/postscript-gradient-addition/radial2/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Preencher Forma com Gradiente: Exemplo Radial de PostScript em Java

## Introdução
Neste tutorial você aprenderá a **preencher forma com gradiente** criando um exemplo de gradiente radial para um documento PostScript usando Aspose.Page para Java. Vamos percorrer cada passo — desde a configuração do projeto até a renderização de um círculo preenchido com um gradiente radial suave — para que você possa adicionar gráficos atraentes às suas aplicações Java instantaneamente.

## Respostas Rápidas
- **O que este tutorial cria?** Um arquivo PostScript (`.ps`) contendo um círculo preenchido com um gradiente radial.  
- **Qual biblioteca é necessária?** Aspose.Page para Java (versão mais recente).  
- **Quanto tempo leva a implementação?** Aproximadamente 10‑15 minutos para um exemplo funcional.  
- **Preciso de licença?** Uma licença temporária ou completa é necessária para uso em produção; uma avaliação gratuita funciona para desenvolvimento.  
- **Posso reutilizar o código para PDF ou SVG?** Sim — Aspose.Page suporta vários formatos de saída com alterações mínimas.

## Como Preencher Forma com Gradiente em PostScript
Antes de mergulharmos no código, vamos esclarecer por que “preencher forma com gradiente” é importante. O uso de gradientes confere aos seus gráficos um aspecto profissional e tridimensional sem a necessidade de imagens rasterizadas. Com Aspose.Page você pode aplicar a mesma lógica de gradiente a qualquer forma vetorial — círculos, retângulos ou caminhos personalizados — em todos os formatos de saída suportados (PostScript, PDF, SVG).

## O que é um Gradiente Radial?
Um gradiente radial transita as cores a partir de um ponto central, criando uma mescla circular suave. É ideal para realces, fundos de botões ou qualquer elemento visual que precise de um efeito natural de “brilho”.

## Por que Usar Aspose.Page para Gradientes Radiais?
- **Renderização independente de dispositivo** – funciona da mesma forma em PostScript, PDF, SVG e outros.  
- **Integração total com Java** – sem código nativo, apenas APIs Java simples.  
- **Saída de alta qualidade** – suporta anti‑aliasing e controle de espaço de cor.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

- Familiaridade básica com programação Java.  
- JDK 8 ou superior instalado em sua máquina.  
- Biblioteca Aspose.Page para Java (download na [documentação do Aspose.Page Java](https://reference.aspose.com/page/java/)).  

## Importar Pacotes
Primeiro, importe as classes que usaremos. Elas incluem tipos gráficos padrão do AWT e a API Aspose.Page.

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

## Etapa 1: Configurar Diretório do Documento
Defina a pasta onde o arquivo PostScript gerado será salvo. Substitua o placeholder por um caminho real no seu sistema.

```java
String dataDir = "Your Document Directory";
```

## Etapa 2: Criar Fluxo de Saída
Abra um `FileOutputStream` que aponta para o arquivo `.ps` de destino. Esse fluxo alimenta os dados binários gerados pelo Aspose.Page.

```java
FileOutputStream outPsStream = new FileOutputStream(dataDir + "RadialGradient2_outPS.ps");
```

## Etapa 3: Criar Opções de Salvamento
Instancie `PsSaveOptions`. Você pode personalizar tamanho de página, compressão, etc., mas os padrões são suficientes para este exemplo.

```java
PsSaveOptions options = new PsSaveOptions();
```

## Etapa 4: Criar Documento PS
Crie o objeto `PsDocument`, passando o fluxo de saída e as opções de salvamento. O parâmetro `false` indica ao Aspose.Page que não abra uma página automaticamente (faremos isso manualmente).

```java
PsDocument document = new PsDocument(outPsStream, options, false);
```

## Etapa 5: Criar um Círculo
Desenharemos um círculo usando `Ellipse2D.Float`. Os parâmetros são `(x, y, width, height)`. Definir `width = height` cria um círculo perfeito.

```java
Ellipse2D.Float circle = new Ellipse2D.Float(200, 100, 200, 200);
```

## Como Desenhar Círculo com Gradiente
Agora que temos uma forma, o próximo passo é **desenhar círculo com gradiente**. Ao aplicar um `RadialGradientPaint` ao círculo, a operação de preenchimento usará automaticamente o gradiente que definimos.

## Etapa 6: Definir Cores do Gradiente
Prepare dois arrays: um para as cores que aparecerão no gradiente e outro para as posições fracionárias correspondentes (0 = centro, 1 = borda).

```java
Color[] colors = { Color.WHITE, Color.WHITE, Color.BLUE };
float[] fractions = { 0.0f, 0.2f, 1.0f };
```

## Etapa 7: Criar AffineTransform
O `AffineTransform` escala e translada o gradiente para caber no nosso círculo. A matriz `(scaleX, 0, 0, scaleY, translateX, translateY)` realiza essa tarefa.

```java
AffineTransform transform = new AffineTransform(200, 0, 0, 200, 200, 100);
```

## Etapa 8: Criar RadialGradientPaint
Agora construímos o objeto `RadialGradientPaint`. Ele recebe o ponto central, raio, ponto focal, frações de cor, array de cores, método de ciclo, espaço de cor e a transformação que acabamos de definir.

```java
RadialGradientPaint paint = new RadialGradientPaint(
        new Point2D.Float(64, 64),   // gradient center
        68,                          // radius
        new Point2D.Float(24, 24),   // focus point
        fractions,
        colors,
        MultipleGradientPaint.CycleMethod.NO_CYCLE,
        MultipleGradientPaint.ColorSpaceType.SRGB,
        transform);
```

## Etapa 9: Definir Pintura e Preencher Círculo
Aplique a pintura de gradiente ao documento e preencha o círculo definido anteriormente. Este é o núcleo do nosso **exemplo de gradiente radial** e demonstra como **preencher forma com gradiente**.

```java
document.setPaint(paint);
document.fill(circle);
```

## Etapa 10: Fechar Página e Salvar Documento
Finalize a página, escreva o conteúdo no disco e feche o fluxo. Seu arquivo PostScript está pronto para ser visualizado em qualquer visualizador PS.

```java
document.closePage();
document.save();
```

Parabéns! Você criou com sucesso um exemplo de gradiente radial em Java PostScript usando Aspose.Page. Agora você tem um padrão reutilizável para **preencher forma com gradiente** que pode ser adaptado a outras formas e formatos de saída.

## Problemas Comuns e Soluções
| Problema | Solução |
|----------|---------|
| **FileNotFoundException** ao abrir o fluxo de saída | Verifique se `dataDir` aponta para uma pasta existente e se você tem permissão de gravação. |
| O gradiente parece plano ou ausente | Certifique‑se de que o array `fractions` corresponde ao tamanho do array `colors` e que o `AffineTransform` está escalando corretamente. |
| As cores aparecem invertidas | Inverta a ordem das cores no array `colors` ou ajuste as coordenadas do ponto `focus`. |

## Perguntas Frequentes

**P: Onde posso encontrar a documentação do Aspose.Page para Java?**  
R: A referência completa da API está disponível [aqui](https://reference.aspose.com/page/java/).

**P: Como faço o download do Aspose.Page para Java?**  
R: Baixe o JAR mais recente na [página de lançamentos](https://releases.aspose.com/page/java/).

**P: Existe uma versão de avaliação gratuita?**  
R: Sim — faça o download da versão de avaliação [aqui](https://releases.aspose.com/).

**P: Posso obter uma licença temporária para testes?**  
R: Absolutamente, solicite uma na [página de licença temporária](https://purchase.aspose.com/temporary-license/).

**P: Onde posso obter suporte da comunidade?**  
R: Participe da discussão no [fórum do Aspose.Page](https://forum.aspose.com/c/page/39).

## Conclusão
Neste guia construímos um **exemplo completo de gradiente radial** para um documento PostScript usando Aspose.Page para Java. Seguindo os passos, você agora possui um padrão reutilizável para **preencher forma com gradiente**, que pode ser adaptado para PDF, SVG ou qualquer outro formato suportado pelo Aspose.Page. Experimente diferentes cores, raios e formas para enriquecer seus projetos gráficos Java.

---

**Última atualização:** 2026-02-13  
**Testado com:** Aspose.Page para Java 24.11 (última versão na data de escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}