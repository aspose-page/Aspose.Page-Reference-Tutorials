---
title: Redimensione arquivos EPS em Java com Aspose.Page
linktitle: Redimensionar arquivo EPS em Java
second_title: API Java Aspose.Page
description: Aprenda como redimensionar arquivos EPS em Java sem esforço com Aspose.Page for Java. Siga nosso guia completo para obter instruções passo a passo.
type: docs
weight: 11
url: /pt/java/manipulation-eps/resize/
---
## Introdução
Bem-vindo ao nosso guia passo a passo sobre como redimensionar arquivos EPS em Java usando a poderosa biblioteca Aspose.Page. Se você já precisou ajustar as dimensões de suas imagens EPS de maneira programática, você está no lugar certo. Neste tutorial, exploraremos várias opções de redimensionamento, incluindo pontos, polegadas, milímetros e porcentagens, proporcionando a flexibilidade necessária para seus requisitos específicos.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter o seguinte:
- Java Development Kit (JDK) instalado em sua máquina.
-  Aspose.Page para biblioteca Java. Você pode baixá-lo[aqui](https://releases.aspose.com/page/java/).
- Uma compreensão básica da programação Java.
## Importar pacotes
Em seu projeto Java, certifique-se de ter as importações necessárias para usar as funcionalidades do Aspose.Page. Aqui está um exemplo:
```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;

```
Agora, vamos dividir o tutorial em várias etapas para cada opção de redimensionamento:
## Redimensionar EPS usando pontos
### Etapa 1: configurar o fluxo de entrada
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```
### Etapa 2: inicializar o objeto PsDocument
```java
PsDocument doc = new PsDocument(inputEpsStream);
```
### Etapa 3: extraia o tamanho atual da imagem EPS
```java
Dimension oldSize = doc.extractEpsSize();
```
### Etapa 4: crie um fluxo de saída
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```
### Passo 5: Redimensione e salve em pontos
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```
## Redimensionar EPS usando polegadas
Siga etapas semelhantes ao Exemplo 1, substituindo “Pontos” por “Polegadas” e ajustando o novo tamanho de acordo.
## Redimensionar EPS usando milímetros
Siga etapas semelhantes ao Exemplo 1, substituindo “Pontos” por “Milímetros” e ajustando o novo tamanho de acordo.
## Redimensionar EPS usando porcentagens
Siga etapas semelhantes ao Exemplo 1, substituindo “Pontos” por “Porcentagens” e ajustando o novo tamanho de acordo.
## Conclusão
Parabéns! Você aprendeu com sucesso como redimensionar arquivos EPS em Java usando Aspose.Page. Este guia oferece opções versáteis, garantindo que você possa adaptar o processo de redimensionamento para atender às suas necessidades específicas.

## Perguntas frequentes
### Posso usar esta biblioteca para outros formatos de imagem?
Não, o Aspose.Page foi projetado especificamente para lidar com arquivos PostScript e EPS.
### Existe uma avaliação gratuita disponível para Aspose.Page for Java?
Sim, você pode explorar a avaliação gratuita[aqui](https://releases.aspose.com/).
### Onde posso encontrar ajuda e discussões adicionais?
 Visite a[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para apoio comunitário.
### Como posso obter uma licença temporária?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Existem exemplos de projetos disponíveis?
 Sim, verifique a documentação[aqui](https://reference.aspose.com/page/java/).