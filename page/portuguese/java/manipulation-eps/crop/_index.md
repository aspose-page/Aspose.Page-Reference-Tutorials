---
date: 2025-11-30
description: Aprenda a recortar arquivos EPS em Java com Aspose.Page – um tutorial
  claro, passo a passo, sobre como recortar EPS usando a biblioteca Aspose.Page.
linktitle: Crop EPS File in Java
second_title: Aspose.Page Java API
title: Como recortar arquivos EPS em Java – Guia Aspose.Page
url: /pt/java/manipulation-eps/crop/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Recortar Arquivos EPS em Java – Guia Passo a Passo com Aspose.Page

## Introdução
Se você precisa **como recortar eps** arquivos programaticamente em uma aplicação Java, está no lugar certo. Neste tutorial vamos percorrer todo o processo de recorte de uma imagem EPS usando a poderosa biblioteca Aspose.Page for Java. Ao final do guia você entenderá por que recortar EPS é importante, verá o código exato que precisa e estará pronto para integrar a solução em seus próprios projetos.

## Respostas Rápidas
- **Qual biblioteca manipula o recorte de EPS em Java?** Aspose.Page for Java.  
- **Quanto tempo leva para implementar um recorte básico?** Aproximadamente 5‑10 minutos.  
- **Preciso de licença para desenvolvimento?** Uma avaliação gratuita funciona para testes; uma licença comercial é necessária para produção.  
- **Quais versões do Java são suportadas?** Java 8 e superiores.  
- **Posso definir qualquer caixa delimitadora personalizada?** Sim – você fornece as coordenadas que precisar.

## O que é Recorte de EPS e Por que Usá‑lo?
Encapsulated PostScript (EPS) é um formato gráfico que armazena imagens vetoriais junto com uma caixa delimitadora que define a área visível. Recortar um arquivo EPS significa criar uma nova caixa delimitadora de modo que apenas a região desejada seja mantida. Isso é útil quando você quer remover margens brancas, extrair um logotipo ou ajustar o gráfico a um layout mais compacto sem recriar o arquivo original.

## Pré‑requisitos
Antes de mergulharmos no código, certifique‑se de que você tem:

- Biblioteca **Aspose.Page for Java** instalada – faça o download na página oficial [aqui](https://releases.aspose.com/page/java/).  
- **Java Development Kit (JDK)** 8 ou superior instalado na sua máquina.  
- **Uma pasta** para armazenar seu EPS de entrada (`input.eps`) e o arquivo recortado resultante (`output_crop.eps`).

## Importar Pacotes
Primeiro, importe as classes Java necessárias. Este trecho permanece exatamente igual ao tutorial original:

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
```

### Etapa 1: Definir Diretório do Documento e Stream de Entrada
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create an input stream for EPS file
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
Aqui apontamos o código para a pasta que contém nosso arquivo EPS fonte e abrimos um stream para leitura.

### Etapa 2: Inicializar o Objeto PsDocument
```java
// Initialize PsDocument object with input stream
PsDocument doc = new PsDocument(inputEpsStream);
```
A classe `PsDocument` representa o documento EPS na memória, permitindo consultar e manipular suas propriedades.

### Etapa 3: Extrair a Caixa Delimitadora Inicial
```java
// Get initial bounding box of EPS image
int[] initialBoundingBox = doc.extractEpsBoundingBox();
```
Extrair a caixa delimitadora original fornece as coordenadas da área visível atual – útil para decidir quanto você precisa cortar.

### Etapa 4: Criar Stream de Saída
```java
// Create output stream for PostScript document
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_crop.eps");
```
Abrimos um stream onde o EPS recortado será gravado.

### Etapa 5: Definir Nova Caixa Delimitadora e Recortar
```java
// Create new bounding box
float[] newBoundingBox = new float[] { 260, 300, 480, 432 };
// Crop EPS image and save to the output stream
doc.cropEps(outputEpsStream, newBoundingBox);
```
Forneça as quatro coordenadas (x inferior‑esquerdo, y inferior‑esquerdo, x superior‑direito, y superior‑direito) que definem a área que você deseja manter. O método `cropEps` realiza o recorte e grava o resultado em `output_crop.eps`.

## Problemas Comuns e Soluções
- **Coordenadas incorretas:** EPS usa pontos (1/72 polegada). Se o recorte ficar errado, verifique a conversão de unidades.  
- **Erros de arquivo não encontrado:** Certifique‑se de que `dataDir` termina com o separador de caminho adequado (`/` ou `\`).  
- **Exceções de licença:** Executar o código sem uma licença válida pode adicionar uma marca d’água ao output. Aplique sua licença temporária ou permanente antes do uso em produção.

## Perguntas Frequentes

**P: O Aspose.Page é compatível com Java 8?**  
R: Sim, o Aspose.Page funciona com Java 8 e qualquer versão posterior.

**P: Posso usar o Aspose.Page em projetos comerciais?**  
R: Absolutamente. Uma licença comercial é necessária para implantações em produção. Você pode obter uma [aqui](https://purchase.aspose.com/buy).

**P: Onde encontro recursos adicionais e suporte da comunidade?**  
R: Visite o fórum oficial do [Aspose.Page](https://forum.aspose.com/c/page/39) para discussões, exemplos de código e dicas de solução de problemas.

**P: Existe uma avaliação gratuita disponível para testes?**  
R: Sim, você pode baixar uma avaliação gratuita do Aspose.Page na página de releases [aqui](https://releases.aspose.com/).

**P: Como obtenho uma licença temporária para avaliação de curto prazo?**  
R: Uma licença temporária pode ser solicitada no portal de licenciamento [aqui](https://purchase.aspose.com/temporary-license/).

## Conclusão
Agora você sabe **como recortar eps** arquivos em Java usando o Aspose.Page. Definindo uma caixa delimitadora personalizada e invocando `cropEps`, você pode eliminar margens indesejadas ou isolar partes específicas de um gráfico EPS com apenas algumas linhas de código. Integre este trecho ao seu pipeline maior de processamento de documentos para automatizar a manipulação de EPS e manter seus ativos visuais organizados.

---

**Última atualização:** 2025-11-30  
**Testado com:** Aspose.Page for Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}