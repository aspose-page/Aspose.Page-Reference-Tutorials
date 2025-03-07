---
title: Adicionar retângulo em Java XPS
linktitle: Adicionar retângulo em Java XPS
second_title: API Java Aspose.Page
description: Aprenda como adicionar retângulos em Java XPS usando Aspose.Page. Siga nosso guia passo a passo para uma manipulação perfeita de documentos. #JavaXPS #AsposePage
weight: 11
url: /pt/java/xps-shapes/add-rectangle/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar retângulo em Java XPS

## Introdução
Bem-vindo a este guia completo sobre como adicionar retângulos em Java XPS usando Aspose.Page! Quer você seja um desenvolvedor experiente ou esteja apenas começando com Java XPS, este tutorial irá guiá-lo pelo processo com instruções passo a passo, garantindo que você obtenha um conhecimento profundo do tópico.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Conhecimento básico da linguagem de programação Java.
-  Biblioteca Aspose.Page instalada. Caso contrário, você pode baixá-lo no[Documentação Java Aspose.Page](https://reference.aspose.com/page/java/).
- Um ambiente de desenvolvimento Java funcional.
## Importar pacotes
Para começar, importe os pacotes necessários para o seu projeto Java. Certifique-se de que a biblioteca Aspose.Page foi adicionada corretamente ao seu caminho de classe. Aqui está um exemplo básico:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```
Agora, vamos dividir o exemplo fornecido em várias etapas para adicionar um retângulo em Java XPS.
## Etapa 1: definir o diretório de documentos
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
```
Substitua “Seu diretório de documentos” pelo caminho para o diretório desejado.
## Etapa 2: crie um novo documento XPS
```java
// Criar novo documento XPS
XpsDocument doc = new XpsDocument();
```
Isso inicializa um novo documento XPS.
## Etapa 3: adicionar um retângulo traçado de cor sólida CMYK
```java
// Retângulo traçado de cor sólida CMYK (azul) no canto inferior esquerdo
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```
Esta etapa adiciona um retângulo traçado com uma cor sólida CMYK.
## Etapa 4: salve o documento XPS resultante
```java
// Salve o documento XPS resultante
doc.save(dataDir + "AddRectangle_out.xps");
```
Finalmente, salve o documento XPS modificado com o retângulo adicionado.
Repita essas etapas, ajustando os parâmetros conforme necessário, para personalizar ainda mais seus retângulos.
## Conclusão
Parabéns! Você aprendeu com sucesso como adicionar retângulos em Java XPS usando Aspose.Page. Este tutorial fornece uma base sólida para seus esforços de manipulação de documentos XPS.
## Perguntas frequentes
### Posso adicionar vários retângulos em um único documento XPS?
Sim, você pode adicionar quantos retângulos forem necessários repetindo as etapas descritas no tutorial.
### Como posso mudar a cor do retângulo?
 Modifique os valores das cores no`createColor` método para obter a cor desejada.
### O Aspose.Page é adequado para lidar com manipulações complexas de documentos XPS?
Absolutamente! Aspose.Page fornece um conjunto robusto de recursos para lidar com várias tarefas de documentos XPS.
### Onde posso encontrar exemplos e suporte adicionais?
 Explore o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39)para obter mais exemplos e procurar assistência da comunidade.
### Posso experimentar o Aspose.Page antes de comprar?
 Sim, você pode explorar um[teste grátis](https://releases.aspose.com/) para experimentar os recursos do Aspose.Page.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
