---
title: Adicionar imagem lado a lado em Java XPS
linktitle: Adicionar imagem lado a lado em Java XPS
second_title: API Java Aspose.Page
description: Explore a manipulação perfeita de documentos Java XPS com Aspose.Page. Aprenda a adicionar imagens lado a lado sem esforço usando este guia passo a passo.
weight: 11
url: /pt/java/xps-image-manipulation/add-tiled-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar imagem lado a lado em Java XPS

## Introdução
No mundo dinâmico do desenvolvimento Java, a necessidade de manipulação e criação eficiente de documentos é cada vez maior. Aspose.Page for Java surge como uma ferramenta poderosa, fornecendo aos desenvolvedores a capacidade de trabalhar com documentos XPS perfeitamente. Este tutorial se concentra em uma tarefa específica – adicionar uma imagem lado a lado a um documento Java XPS.
## Pré-requisitos
Antes de mergulhar no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
1. Java Development Kit (JDK): Certifique-se de ter o JDK instalado em seu sistema.
2.  Aspose.Page para Java: Baixe e instale Aspose.Page para Java do[local na rede Internet](https://releases.aspose.com/page/java/).
3. Seu diretório de documentos: Escolha ou crie um diretório onde deseja salvar seu documento XPS.
## Importar pacotes
Em seu projeto Java, importe os pacotes necessários para utilizar as funcionalidades do Aspose.Page:
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Agora, vamos dividir o processo de adição de uma imagem lado a lado a um documento Java XPS em etapas claras e gerenciáveis.
## Etapa 1: configure seu projeto
Comece configurando seu projeto Java, garantindo que Aspose.Page for Java esteja devidamente integrado.
## Etapa 2: criar documento XPS
Inicialize um novo documento XPS usando o seguinte código:
```java
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
// Criar novo documento XPS
XpsDocument doc = new XpsDocument();
```
## Etapa 3: definir o caminho da imagem lado a lado
Especifique o caminho para a imagem lado a lado que deseja adicionar ao documento XPS.
## Etapa 4: adicionar imagem lado a lado
Utilize o snippet de código abaixo para adicionar uma imagem lado a lado ao documento XPS:
```java
// Imagem lado a lado
// Retângulo preenchido com ImageBrush no canto superior direito abaixo
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```
## Etapa 5: salve o documento
Por fim, salve o documento XPS resultante usando o código abaixo:
```java
// Salve o documento XPS resultante
doc.save(dataDir + "AddTiledImage_out.xps"); 
```
Repita essas etapas para incorporar facilmente uma imagem lado a lado em seu documento Java XPS usando Aspose.Page.
## Conclusão
Aspose.Page for Java agiliza o processo de trabalho com documentos XPS, oferecendo aos desenvolvedores uma solução eficiente para manipulação de documentos. Seguindo este guia passo a passo, você pode adicionar facilmente uma imagem lado a lado ao seu documento Java XPS.

## Perguntas frequentes
### O Aspose.Page é compatível com todas as versões Java?
 Aspose.Page foi projetado para funcionar com várias versões Java. Garanta a compatibilidade verificando a documentação[aqui](https://reference.aspose.com/page/java/).
### Posso usar Aspose.Page para projetos comerciais?
Sim, Aspose.Page oferece licenças comerciais. Compre-os[aqui](https://purchase.aspose.com/buy).
### Existe um teste gratuito disponível?
 Sim, explore os recursos do Aspose.Page com uma avaliação gratuita[aqui](https://releases.aspose.com/).
### Onde posso encontrar suporte e discussões da comunidade?
 Envolva-se com a comunidade Aspose.Page no[fórum](https://forum.aspose.com/c/page/39).
### Como posso obter uma licença temporária para Aspose.Page?
 Adquira uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
