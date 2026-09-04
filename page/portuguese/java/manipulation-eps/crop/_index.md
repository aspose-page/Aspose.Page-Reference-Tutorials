---
date: 2026-09-04
description: Aprenda a reduzir o tamanho de arquivos EPS recortando arquivos EPS em
  Java usando Aspose.Page – um guia passo a passo que mostra como recortar EPS, recortar
  imagem EPS e aparar o arquivo EPS.
keywords:
- reduce eps file size
- how to crop eps
- Aspose.Page Java
- EPS cropping Java
lastmod: 2026-09-04
linktitle: Recortar arquivo EPS em Java
og_description: Aprenda a reduzir o tamanho de arquivos EPS recortando arquivos EPS
  em Java usando Aspose.Page – um guia rápido com código e dicas.
og_image_alt: 'Guide: cropping EPS files in Java to reduce file size with Aspose.Page'
og_title: Como recortar arquivos EPS em Java para reduzir o tamanho do arquivo EPS
schemas:
- author: Aspose
  dateModified: '2026-09-04'
  description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  headline: How to crop EPS files in Java to reduce EPS file size
  type: TechArticle
- description: Learn how to reduce EPS file size by cropping EPS files in Java using
    Aspose.Page – a step‑by‑step guide that shows how to crop eps, crop eps image
    and trim eps file.
  name: How to crop EPS files in Java to reduce EPS file size
  steps:
  - name: set document directory and input stream
    text: Here we point the code to the folder that holds our source EPS file and
      open a stream for reading it.
  - name: initialize PsDocument object
    text: The `PsDocument` class represents an EPS file in memory, allowing you to
      read and modify its properties. The object gives you access to the original
      bounding box and other metadata.
  - name: extract initial bounding box
    text: Extracting the original bounding box gives you the coordinates of the current
      visible area – handy for deciding how much you need to trim.
  - name: create output stream
    text: We open a stream where the cropped EPS will be written.
  - name: define new bounding box and crop
    text: The `cropEps` method trims the document to a new bounding box and writes
      the result to an output stream. Provide the four coordinates (lower‑left x,
      lower‑left y, upper‑right x, upper‑right y) that define the area you want to
      keep. The method performs the cropping and writes the result to `output_cr
  type: HowTo
- questions:
  - answer: Yes, Aspose.Page works with Java 8 and any later version.
    question: Is Aspose.Page compatible with Java 8?
  - answer: Absolutely. A commercial license is required for production deployments.
      You can obtain one [Aspose purchase page](https://purchase.aspose.com/buy).
    question: Can I use Aspose.Page for commercial projects?
  - answer: Visit the official [Aspose.Page forum](https://forum.aspose.com/c/page/39)
      for discussions, code samples, and troubleshooting tips.
    question: Where can I find additional resources and community support?
  - answer: Yes, you can download a free trial of Aspose.Page from the releases page
      [Aspose.Page releases page](https://releases.aspose.com/).
    question: Is there a free trial available for testing?
  - answer: A temporary license can be requested from the licensing portal [temporary
      license request page](https://purchase.aspose.com/temporary-license/).
    question: How do I obtain a temporary license for short‑term evaluation?
  type: FAQPage
second_title: Aspose.Page Java API
tags:
- reduce eps file size
- Aspose.Page
- Java EPS processing
- crop EPS
title: Como recortar arquivos EPS em Java para reduzir o tamanho do arquivo EPS
url: /pt/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como recortar arquivos EPS em Java para reduzir o tamanho do arquivo EPS

## Introdução
Se você precisa **recortar EPS** programaticamente em uma aplicação Java e deseja **reduzir o tamanho do arquivo EPS**, você está no lugar certo. Neste tutorial vamos percorrer todo o processo de recorte de uma imagem EPS usando a poderosa biblioteca Aspose.Page for Java. Ao final do guia você entenderá por que o recorte de EPS é importante, verá o código exato que precisa e estará pronto para integrar a solução em seus próprios projetos.

## Respostas rápidas
- **Qual biblioteca lida com recorte de EPS em Java?** Aspose.Page for Java.  
- **Quanto tempo leva para implementar um recorte básico?** Aproximadamente 5‑10 minutos.  
- **Preciso de licença para desenvolvimento?** Um teste gratuito funciona para avaliação; uma licença comercial é necessária para produção.  
- **Quais versões do Java são suportadas?** Java 8 e superiores.  
- **Posso definir qualquer caixa delimitadora personalizada?** Sim – você fornece as coordenadas necessárias.

## O que é recorte de EPS e por que usá-lo?
**O recorte de EPS cria uma nova caixa delimitadora que define a região visível de um arquivo EPS.**  
Recortar um arquivo EPS remove espaços em branco indesejados e ajusta o gráfico à área que você realmente precisa, o que **reduz diretamente o tamanho do arquivo EPS** e melhora a consistência do layout em documentos subsequentes, como PDFs ou relatórios.

## Por que recortar arquivos EPS?
Recortar arquivos EPS permite **reduzir o tamanho do arquivo em até 30 %**, eliminar margens excessivas e padronizar gráficos para pipelines de processamento em lote. É especialmente útil quando você precisa incorporar muitos recursos EPS em um único PDF ou quando deseja acelerar a renderização em dispositivos de baixa potência.

## Pré-requisitos
Antes de mergulharmos no código, certifique‑se de que você tem:

- Biblioteca **Aspose.Page for Java** instalada – faça o download na página oficial [Aspose.Page for Java release page](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** 8 ou superior instalado na sua máquina.  
- **Uma pasta** para armazenar seu EPS de entrada (`input.eps`) e o arquivo recortado resultante (`output_crop.eps`).

## Importar pacotes
Primeiro, importe as classes Java necessárias. Este trecho permanece exatamente o mesmo do tutorial original:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

## Como recortar imagem EPS em Java
Carregue seu EPS de origem, defina uma nova caixa delimitadora e chame a API de recorte – toda a operação é concluída em cinco etapas concisas.

### Etapa 1: definir diretório do documento e fluxo de entrada
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
Aqui apontamos o código para a pasta que contém nosso arquivo EPS de origem e abrimos um fluxo para lê‑lo.

### Etapa 2: inicializar objeto PsDocument
A classe `PsDocument` representa um arquivo EPS na memória, permitindo ler e modificar suas propriedades.  
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
O objeto fornece acesso à caixa delimitadora original e a outros metadados.

### Etapa 3: extrair caixa delimitadora inicial
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
Extrair a caixa delimitadora original fornece as coordenadas da área visível atual – útil para decidir quanto você precisa aparar.

### Etapa 4: criar fluxo de saída
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
Abrimos um fluxo onde o EPS recortado será gravado.

### Etapa 5: definir nova caixa delimitadora e recortar
O método `cropEps` ajusta o documento a uma nova caixa delimitadora e grava o resultado em um fluxo de saída.  
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
Forneça as quatro coordenadas (x inferior‑esquerdo, y inferior‑esquerdo, x superior‑direito, y superior‑direito) que definem a área que você deseja manter. O método realiza o recorte e grava o resultado em `output_crop.eps`.

## Problemas comuns e soluções
- **Coordenadas incorretas:** EPS usa pontos (1/72 polegada). Se o recorte parecer errado, verifique a conversão de unidades.  
- **Erros de arquivo não encontrado:** Certifique‑se de que `dataDir` termina com o separador de caminho apropriado (`/` ou `\`).  
- **Exceções de licença:** Executar o código sem uma licença válida pode adicionar uma marca d’água ao resultado. Aplique sua licença temporária ou permanente antes do uso em produção.

## Perguntas frequentes

**Q: É o Aspose.Page compatível com Java 8?**  
A: Sim, o Aspose.Page funciona com Java 8 e qualquer versão posterior.

**Q: Posso usar o Aspose.Page em projetos comerciais?**  
A: Absolutamente. Uma licença comercial é necessária para implantações em produção. Você pode obter uma na [Aspose purchase page](https://purchase.aspose.com/buy).

**Q: Onde posso encontrar recursos adicionais e suporte da comunidade?**  
A: Visite o fórum oficial [Aspose.Page forum](https://forum.aspose.com/c/page/39) para discussões, exemplos de código e dicas de solução de problemas.

**Q: Existe um teste gratuito disponível para avaliação?**  
A: Sim, você pode baixar um teste gratuito do Aspose.Page na página de lançamentos [Aspose.Page releases page](https://releases.aspose.com/).

**Q: Como obtenho uma licença temporária para avaliação de curto prazo?**  
A: Uma licença temporária pode ser solicitada no portal de licenciamento [temporary license request page](https://purchase.aspose.com/temporary-license/).

## Conclusão
Agora você sabe **como recortar arquivos EPS** em Java usando Aspose.Page para **reduzir o tamanho do arquivo EPS**. Ao definir uma caixa delimitadora personalizada e invocar `cropEps`, você pode aparar margens indesejadas ou isolar partes específicas de um gráfico EPS com apenas algumas linhas de código. Integre este trecho ao seu pipeline de processamento de documentos para automatizar a manipulação de EPS, **recortar ativos de imagem EPS** e **aparar o conteúdo do arquivo EPS** de forma eficiente.

---

**Last Updated:** 2026-09-04  
**Tested With:** Aspose.Page for Java 24.11  
**Author:** Aspose

## Tutoriais Relacionados

- [Como redimensionar arquivos EPS em Java com Aspose.Page](/page/java/manipulation-eps/resize/)
- [Converter EPS para PNG com Aspose.Page Java (Licença Metada)](/page/java/license-management/set-metered-license/)
- [Tutorial Aspose Page Java – Adicionar Metadados XMP a Arquivos EPS](/page/java/xmp-metadata-manipulation/add-metadata/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}