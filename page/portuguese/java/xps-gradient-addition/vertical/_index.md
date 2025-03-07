---
title: Adicionar gradiente vertical em Java XPS
linktitle: Adicionar gradiente vertical em Java XPS
second_title: API Java Aspose.Page
description: Aprenda como adicionar um gradiente vertical a documentos Java XPS com Aspose.Page. Aumente o apelo visual sem esforço. Guia passo a passo interno.
weight: 12
url: /pt/java/xps-gradient-addition/vertical/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar gradiente vertical em Java XPS

## Introdução
Neste tutorial, exploraremos como adicionar um gradiente vertical em Java XPS usando Aspose.Page for Java. Adicionar gradientes aos seus documentos XPS pode melhorar o apelo visual do seu conteúdo, tornando-o mais envolvente e esteticamente agradável.
## Pré-requisitos
Antes de mergulharmos no tutorial, certifique-se de ter os seguintes pré-requisitos em vigor:
- Um ambiente de desenvolvimento Java funcional.
-  Aspose.Page para biblioteca Java. Você pode baixá-lo em[aqui](https://releases.aspose.com/page/java/).
- Uma compreensão básica da programação Java.
## Importar pacotes
Comece importando os pacotes necessários para o seu projeto Java. Certifique-se de ter incluído a biblioteca Aspose.Page para Java nas dependências do seu projeto.
```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
// O caminho para o diretório de documentos.
String dataDir = "Your Document Directory";
        
// Importar Aspose.Page para Java
```
## Etapa 1: inicializar o documento
Comece inicializando o documento XPS. Isso estabelece a base para adicionar elementos como caminhos e gradientes ao seu documento.
```java
// Inicializar documento
XpsDocument doc = new XpsDocument();
```
## Etapa 2: crie um caminho com gradiente vertical
Agora, vamos criar um caminho com gradiente vertical. Isso envolve definir a geometria do caminho e especificar as paradas do gradiente.
```java
// Crie um caminho com geometria
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
// Definir paradas de gradiente vertical
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(253, 255, 12, 0), 0f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 154, 0), 0.359375f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 56, 0), 0.424805f));
stops.add(doc.createGradientStop(doc.createColor(253, 255, 229, 0), 0.879883f));
stops.add(doc.createGradientStop(doc.createColor(252, 255, 255, 234), 1f));
//Aplique o gradiente vertical ao caminho
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 110f), new Point2D.Float(10f, 200f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
```
## Etapa 3: salve o documento
Por fim, salve o documento XPS com o gradiente vertical adicionado no diretório desejado.
```java
// Salve o documento
doc.save(dataDir + "VerticalGradient.xps");
```
Parabéns! Você adicionou com sucesso um gradiente vertical ao seu documento Java XPS usando Aspose.Page.
## Conclusão
Aprimorar seus documentos XPS com gradientes pode melhorar significativamente seu apelo visual. Aspose.Page for Java simplifica esse processo, permitindo criar documentos impressionantes com facilidade.

### Perguntas frequentes
### Posso usar Aspose.Page for Java em projetos comerciais?
 Sim, Aspose.Page for Java está disponível para uso comercial. Você pode comprá-lo[aqui](https://purchase.aspose.com/buy).
### Existe uma avaliação gratuita disponível para Aspose.Page for Java?
 Sim, você pode acessar um teste gratuito[aqui](https://releases.aspose.com/).
### Onde posso encontrar a documentação do Aspose.Page for Java?
 A documentação está disponível[aqui](https://reference.aspose.com/page/java/).
### Como posso obter uma licença temporária do Aspose.Page for Java?
 Obtenha uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Necessita de ajuda ou tem dúvidas?
 Visite a comunidade Aspose.Page[fórum](https://forum.aspose.com/c/page/39).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
