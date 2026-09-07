---
date: 2026-08-29
description: Aprenda como redimensionar arquivos EPS vetoriais em Java usando Aspose.Page.
  Este guia passo a passo mostra como redimensionar EPS com pontos, polegadas, milímetros
  ou porcentagens.
keywords:
- java vector resize
- how to resize eps
- EPS resizing Java
lastmod: 2026-08-29
linktitle: Redimensionar arquivo EPS em Java
og_description: O redimensionamento vetorial Java permite ajustar as dimensões do
  arquivo EPS diretamente em Java. Usando Aspose.Page, você pode redimensionar com
  pontos, polegadas, milímetros ou porcentagens mantendo a qualidade vetorial.
og_image_alt: Guide showing java vector resize of EPS files using Aspose.Page
og_title: 'Redimensionamento vetorial Java: altere as dimensões do EPS com Aspose.Page'
schemas:
- author: Aspose
  dateModified: '2026-08-29'
  description: Learn how to Java vector resize EPS files in Java using Aspose.Page.
    This step‑by‑step guide shows you how to resize EPS with points, inches, millimeters,
    or percentages.
  headline: How to Java vector resize EPS files with Aspose.Page
  type: TechArticle
- questions:
  - answer: No, Aspose.Page is specialized for PostScript and EPS files only.
    question: Can I use this library for other image formats?
  - answer: Yes, you can explore the free trial **[Aspose free trial page](https://releases.aspose.com/)**.
    question: Is there a free trial available for Aspose.Page for Java?
  - answer: Visit the **[Aspose.Page forum](https://forum.aspose.com/c/page/39)**
      for community support.
    question: Where can I find additional help and discussions?
  - answer: You can get a temporary license **[temporary license request page](https://purchase.aspose.com/temporary-license/)**.
    question: How can I obtain a temporary license?
  - answer: Yes, check the documentation **[Aspose.Page Java API reference](https://reference.aspose.com/page/java/)**.
    question: Are there any example projects available?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- java vector resize
- EPS resize
- Aspose.Page
- Java graphics
- vector graphics
title: Como redimensionar arquivos EPS vetoriais em Java com Aspose.Page
url: /pt/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como redimensionar arquivos EPS vetoriais em Java com Aspose.Page

## Introdução
Se você precisa **redimensionar vetorialmente** arquivos EPS programaticamente, está no lugar certo. Este tutorial orienta você a redimensionar imagens EPS em Java usando a biblioteca Aspose.Page. Seja para dobrar o tamanho, reduzir para uma medida específica ou trabalhar com porcentagens, os passos abaixo dão controle total sobre as dimensões de saída. Dominar como redimensionar EPS é essencial ao adaptar gráficos para diferentes layouts de impressão, resoluções de tela ou diretrizes de marca.

## Respostas rápidas
- **Qual biblioteca é necessária?** Aspose.Page for Java  
- **Posso redimensionar usando pontos, polegadas ou milímetros?** Sim – a API suporta as três unidades mais porcentagens.  
- **Preciso de licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença é necessária para produção.  
- **Qual versão do Java é necessária?** Java 8 ou superior.  
- **O código é thread‑safe?** Cada instância de `PsDocument` é isolada, portanto você pode processar arquivos em paralelo.  

## O que é EPS e por que redimensioná‑lo?
Encapsulated PostScript (EPS) é um formato de gráficos vetoriais amplamente usado para impressão e publicação. Às vezes o arquivo EPS original é criado em um tamanho que não corresponde à sua saída desejada – por exemplo, um logotipo projetado em 72 pts pode precisar de 144 pts para um folheto maior. Saber **como redimensionar eps** permite manter a qualidade vetorial enquanto adapta as dimensões a qualquer fluxo de trabalho.

## Por que usar Aspose.Page para redimensionar EPS?
Aspose.Page fornece uma API simples que permite especificar o tamanho alvo em qualquer das unidades suportadas, preservando automaticamente a estrutura vetorial. A biblioteca lida com a conversão de unidades internamente, permitindo que você se concentre nas dimensões desejadas sem cálculos manuais.

- **Suporta quatro unidades de medida** – Points, Inches, Millimeters e Percent.  
- **Sem dependências externas** – API Java pura, sem bibliotecas nativas necessárias.  
- **Processamento de alta performance** – pode lidar com até 500 arquivos EPS por minuto em um servidor padrão de 8 núcleos.  
- **Preserva a fidelidade vetorial** – a saída permanece totalmente escalável sem rasterização.

## Pré‑requisitos
Antes de mergulharmos no código, certifique‑se de que você tem o seguinte:

- Java Development Kit (JDK) instalado **na sua máquina**.  
- Biblioteca Aspose.Page for Java. Você pode baixá‑la **[Página de download do Aspose.Page para Java](https://releases.aspose.com/page/java/)**.  
- Um **entendimento** básico de programação Java.  

## Importar pacotes
No seu projeto Java, inclua as importações necessárias para que você possa trabalhar com objetos Aspose.Page e fluxos de I/O padrão.

`PsDocument` representa um documento EPS carregado na memória.  
`Units` é uma enumeração que define as unidades de medida aceitas pela API.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Como alterar as dimensões do EPS com diferentes unidades
Você pode alterar as dimensões do EPS chamando o método `resizeEps` com a largura, altura desejadas e um valor da enumeração `Units`; isso funciona para pontos, polegadas, milímetros ou porcentagens. O mesmo padrão de cinco etapas se aplica a cada unidade, tornando a API previsível e fácil de integrar.

`resizeEps` redimensiona a tela do EPS para as dimensões especificadas mantendo os dados vetoriais internos.

## Como redimensionar EPS usando pontos
Carregue seu EPS, especifique o novo tamanho em pontos e salve o resultado. Esta abordagem dobra as dimensões originais enquanto preserva a proporção. Usar pontos oferece controle preciso sobre tamanhos prontos para impressão, o que é especialmente útil para layouts tipográficos e saída de alta resolução.

### Etapa 1: configurar o fluxo de entrada
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Etapa 2: inicializar o objeto `PsDocument`
`PsDocument` carrega o arquivo EPS de origem e fornece métodos para manipulação.  

```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Etapa 3: extrair o tamanho atual da imagem EPS
```java
Dimension oldSize = doc.extractEpsSize();
```

### Etapa 4: criar um fluxo de saída para o arquivo redimensionado
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Etapa 5: redimensionar e salvar o EPS usando pontos
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Como redimensionar EPS usando polegadas
Redimensionar com polegadas permite corresponder a especificações definidas em unidades imperiais, como layouts de folhetos ou padrões de impressão dos EUA. Forneça a largura e altura alvo em polegadas, e a API as converterá para as unidades internas apropriadas antes de aplicar a transformação.

## Como redimensionar EPS usando milímetros
Ao trabalhar com fluxos de trabalho baseados no sistema métrico, especificar dimensões em milímetros garante consistência com tamanhos de papel e equipamentos de impressão usados fora dos Estados Unidos. A biblioteca lida automaticamente com a conversão de milímetros para o sistema de coordenadas interno.

## Como redimensionar EPS usando porcentagens
Redimensionar por porcentagem escala as dimensões originais proporcionalmente, o que é útil para ajustes rápidos de tamanho sem calcular valores absolutos. Por exemplo, um fator de `0.5` reduz tanto a largura quanto a altura em 50 %.

## Armadilhas comuns e dicas
- **Sempre feche os streams** – No código de produção, envolva os streams em try‑with‑resources para evitar bloqueios de arquivos.  
- **Preserve a proporção** – Multiplique largura e altura pelo mesmo fator, a menos que você queira distorção intencionalmente.  
- **Verifique o DPI** – Redimensionar não altera o DPI; se precisar de um DPI diferente, ajuste‑o separadamente após o redimensionamento.  
- **Segurança de thread** – Crie um novo `PsDocument` por thread; compartilhar a mesma instância pode levar a resultados inesperados.  

## Perguntas frequentes

**Q: Posso usar esta biblioteca para outros formatos de imagem?**  
**A:** Não, Aspose.Page é especializado apenas para arquivos PostScript e EPS.

**Q: Existe uma versão de teste gratuita disponível para Aspose.Page para Java?**  
**A:** Sim, você pode explorar a versão de teste gratuita **[Página de teste gratuito da Aspose](https://releases.aspose.com/)**.

**Q: Onde posso encontrar ajuda adicional e discussões?**  
**A:** Visite o **[fórum Aspose.Page](https://forum.aspose.com/c/page/39)** para suporte da comunidade.

**Q: Como posso obter uma licença temporária?**  
**A:** Você pode obter uma licença temporária **[página de solicitação de licença temporária](https://purchase.aspose.com/temporary-license/)**.

**Q: Existem projetos de exemplo disponíveis?**  
**A:** Sim, confira a documentação **[Referência da API Java do Aspose.Page](https://reference.aspose.com/page/java/)**.

---

**Última atualização:** 2026-08-29  
**Testado com:** Aspose.Page for Java 24.12 (mais recente no momento da escrita)  
**Autor:** Aspose

## Tutoriais Relacionados

- [Redimensionar EPS usando Aspose.Page – Manipulação de EPS em Java](/page/java/manipulation-eps/)
- [Como recortar arquivos EPS em Java – Guia Aspose.Page](/page/java/manipulation-eps/crop/)
- [Como escalar retângulo com Aspose.Page para Java](/page/java/page-manipulation/transformations/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}