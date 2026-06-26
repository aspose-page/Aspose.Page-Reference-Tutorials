---
date: 2026-02-07
description: Aprenda a redimensionar arquivos EPS em Java e alterar as dimensões do
  EPS usando Aspose.Page. Este guia passo a passo mostra como redimensionar EPS em
  pontos, polegadas, milímetros ou porcentagens.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Como redimensionar arquivos EPS em Java com Aspose.Page
url: /pt/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Redimensionar Arquivos EPS em Java com Aspose.Page

## Introduction
Se você está procurando uma maneira confiável **de redimensionar arquivos EPS** programaticamente, chegou ao lugar certo. Neste tutorial, vamos percorrer o redimensionamento de imagens EPS em Java usando a biblioteca Aspose.Page. Seja para dobrar o tamanho, reduzir para uma medida específica ou trabalhar com percentuais, os passos abaixo dão controle total sobre as dimensões de saída. Entender **como redimensionar eps** é essencial quando você precisa adaptar gráficos para diferentes layouts de impressão ou resoluções de tela.

## Quick Answers
- **Qual biblioteca é necessária?** Aspose.Page for Java  
- **Posso redimensionar usando pontos, polegadas ou milímetros?** Sim – a API suporta as três unidades mais percentuais.  
- **Preciso de licença para desenvolvimento?** Uma avaliação gratuita funciona para testes; uma licença é necessária para produção.  
- **Qual versão do Java é necessária?** Java 8 ou superior.  
- **O código é thread‑safe?** Cada instância de `PsDocument` é isolada, então você pode processar arquivos em paralelo.  

## What is EPS and Why Resize It?
Encapsulated PostScript (EPS) é um formato popular de gráficos vetoriais usado em publicação e impressão. Às vezes o arquivo EPS original é criado em um tamanho que não corresponde à sua saída alvo – por exemplo, um logotipo projetado em 72 pts pode precisar ser 144 pts para uma brochura maior. Saber **como redimensionar eps** permite que você mantenha a qualidade vetorial enquanto adapta as dimensões a qualquer fluxo de trabalho.

## Why Use Aspose.Page for Resizing EPS?
- **Controle total sobre unidades** – pontos, polegadas, milímetros ou percentuais.  
- **Sem dependências externas** – API Java pura, sem bibliotecas nativas.  
- **Alto desempenho** – adequado para processamento em lote em servidores.  
- **Preserva a fidelidade vetorial** – a saída permanece escalável sem rasterização.

## Prerequisites
Antes de mergulharmos no código, certifique-se de que você tem o seguinte:

- Java Development Kit (JDK) instalado na sua máquina.  
- Biblioteca Aspose.Page for Java. Você pode baixá‑la **[aqui](https://releases.aspose.com/page/java/)**.  
- Um entendimento básico de programação Java.  

## Import Packages
Em seu projeto Java, inclua os imports necessários para que você possa trabalhar com objetos Aspose.Page e fluxos de I/O padrão.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## How to Change EPS Dimensions with Different Units
A biblioteca permite que você **mude as dimensões eps** simplesmente selecionando o enum `Units` apropriado. Abaixo percorreremos o mesmo padrão de cinco passos para pontos, polegadas, milímetros e percentuais. A única coisa que muda é a unidade que você passa para `resizeEps`.

## How to Resize EPS Using Points
Abaixo está um exemplo completo, passo a passo, que dobra o tamanho de um arquivo EPS usando pontos como unidade de medida.

### Step 1: Set up the input stream
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Step 2: Initialize the `PsDocument` object
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Step 3: Extract the current size of the EPS image
```java
Dimension oldSize = doc.extractEpsSize();
```

### Step 4: Create an output stream for the resized file
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Step 5: Resize and save the EPS using points
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## How to Resize EPS Using Inches
O mesmo padrão de cinco passos se aplica; basta substituir `Units.Points` por `Units.Inches` e ajustar o fator de escala para o valor de polegadas desejado.

## How to Resize EPS Using Millimeters
Novamente, siga os mesmos passos, trocando a unidade para `Units.Millimeters`. Isso é útil quando você precisa de dimensões métricas para fluxos de trabalho de impressão.

## How to Resize EPS Using Percentages
Para escala baseada em percentuais, mantenha a unidade como `Units.Percent`. Multiplique a largura e altura originais pelo percentual desejado (por exemplo, `0.5` para uma redução de 50 %).

## Common Pitfalls & Tips
- **Sempre feche os streams** – No código de produção, envolva os streams em try‑with‑resources para evitar bloqueios de arquivos.  
- **Preserve a proporção** – Multiplique largura e altura pelo mesmo fator, a menos que você queira distorção intencionalmente.  
- **Verifique o DPI** – Redimensionar não altera o DPI; se precisar de um DPI diferente, ajuste-o separadamente após o redimensionamento.  
- **Segurança de thread** – Crie um novo `PsDocument` por thread; compartilhar a mesma instância pode levar a resultados inesperados.  

## Frequently Asked Questions

**Q: Posso usar esta biblioteca para outros formatos de imagem?**  
A: Não, Aspose.Page é especializado apenas para arquivos PostScript e EPS.

**Q: Existe uma avaliação gratuita disponível para Aspose.Page for Java?**  
A: Sim, você pode explorar a avaliação gratuita **[aqui](https://releases.aspose.com/)**.

**Q: Onde posso encontrar ajuda adicional e discussões?**  
A: Visite o **[fórum Aspose.Page](https://forum.aspose.com/c/page/39)** para suporte da comunidade.

**Q: Como posso obter uma licença temporária?**  
A: Você pode obter uma licença temporária **[aqui](https://purchase.aspose.com/temporary-license/)**.

**Q: Existem projetos de exemplo disponíveis?**  
A: Sim, confira a documentação **[aqui](https://reference.aspose.com/page/java/)**.

---

**Última atualização:** 2026-02-07  
**Testado com:** Aspose.Page for Java 24.12 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}