---
title: Definir máscara de opacidade em Java XPS
linktitle: Definir máscara de opacidade em Java XPS
second_title: API Java Aspose.Page
description: Descubra o poder de definir máscaras de opacidade em Java XPS com Aspose.Page. Siga nosso guia passo a passo para obter uma experiência documental visualmente aprimorada.
weight: 11
url: /pt/java/xps-transparency/set-opacity-mask/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definir máscara de opacidade em Java XPS

## Introdução
Bem-vindo ao nosso guia completo sobre como definir máscaras de opacidade em Java XPS usando Aspose.Page. Neste tutorial, orientaremos você no processo de criação de um documento XPS, adição de uma tela e aplicação de uma máscara de opacidade a um retângulo usando os recursos poderosos do Aspose.Page para Java.
## Pré-requisitos
Antes de mergulhar neste tutorial, certifique-se de ter o seguinte:
- Uma compreensão básica da programação Java.
-  Biblioteca Aspose.Page para Java instalada. Você pode baixá-lo[aqui](https://releases.aspose.com/page/java/).
-  Uma licença válida para Aspose.Page. Se você não tiver uma, poderá obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
- Um ambiente de desenvolvimento configurado para executar aplicativos Java.
## Importar pacotes
Comece importando os pacotes necessários para o seu projeto Java. Certifique-se de ter a biblioteca Aspose.Page devidamente integrada. Abaixo está um trecho para orientá-lo:
```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```
Agora, vamos dividir o código de exemplo em várias etapas:
## Etapa 1: crie um novo documento XPS
```java
// Crie um novo documento XPS
XpsDocument doc = new XpsDocument();
```
## Etapa 2: adicionar uma tela
```java
// Nova tela
XpsCanvas canvas = doc.addCanvas();
```
## Etapa 3: adicione um retângulo com máscara de opacidade
```java
// Retângulo no meio à esquerda com opacidade mascarada pelo ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```
## Etapa 4: definir máscara de opacidade com ImageBrush
```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```
## Etapa 5: salve o documento XPS resultante
```java
// Salve o documento XPS resultante
doc.save(dataDir + "OpacityMask_out.xps"); 
```
Siga estas etapas cuidadosamente para incorporar máscaras de opacidade em seu documento Java XPS usando Aspose.Page.
## Conclusão
Parabéns! Você aprendeu com sucesso como definir máscaras de opacidade em Java XPS com Aspose.Page. Este recurso adiciona uma camada de riqueza visual aos seus documentos, tornando-os mais envolventes e dinâmicos.
## Perguntas frequentes
### O Aspose.Page é compatível com todos os ambientes de desenvolvimento Java?
Sim, Aspose.Page foi projetado para funcionar perfeitamente com vários ambientes de desenvolvimento Java.
### Posso usar Aspose.Page sem licença?
Embora você possa usar o Aspose.Page sem licença, é recomendável obter uma para obter toda a gama de recursos e suporte.
### Há alguma limitação na versão de teste?
A versão de teste pode ter algumas limitações de recursos. É aconselhável verificar a documentação para obter detalhes.
### Como posso obter suporte para Aspose.Page?
 Você pode visitar o[Fórum Aspose.Page](https://forum.aspose.com/c/page/39) para suporte da comunidade ou adquira uma licença para assistência premium.
### Existe uma garantia de devolução do dinheiro para Aspose.Page?
 Consulte o[página de compra](https://purchase.aspose.com/buy) para obter informações sobre políticas de reembolso.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
