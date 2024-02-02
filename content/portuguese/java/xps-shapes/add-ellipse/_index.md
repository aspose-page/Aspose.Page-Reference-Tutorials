---
title: Adicionar elipse de gradiente radial com Aspose.Page
linktitle: Adicionar elipse em Java XPS
second_title: API Java Aspose.Page
description: Explore o guia passo a passo sobre como adicionar uma elipse com gradiente radial em Java XPS usando Aspose.Page para Java. Aprimore a criação de documentos sem esforço.
type: docs
weight: 10
url: /pt/java/xps-shapes/add-ellipse/
---
## Introdução
Bem-vindo ao nosso guia passo a passo sobre como adicionar uma elipse em Java XPS usando Aspose.Page for Java. Aspose.Page é uma biblioteca Java poderosa que permite aos desenvolvedores trabalhar com documentos XPS sem esforço. Neste tutorial, orientaremos você no processo de criação de uma elipse com gradiente radial e salvamento como um documento XPS.
## Pré-requisitos
Antes de começarmos, certifique-se de ter os seguintes pré-requisitos em vigor:
- Java Development Kit (JDK) instalado em sua máquina.
-  Biblioteca Aspose.Page para Java baixada. Você pode conseguir isso[aqui](https://releases.aspose.com/page/java/).
- Um editor de código de sua escolha (Eclipse, IntelliJ, etc.) para escrever e executar código Java.
## Importar pacotes
Certifique-se de ter os pacotes necessários importados em seu projeto Java para usar Aspose.Page. Adicione as seguintes instruções de importação ao topo do seu arquivo Java:
```java
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsSpreadMethod;
```
## Etapa 1: configurar o diretório de documentos
Defina o caminho para o diretório do documento onde o documento XPS será salvo:
```java
String dataDir = "Your Document Directory";
```
## Etapa 2: criar documento XPS
Inicialize um novo documento XPS usando o seguinte código:
```java
XpsDocument doc = new XpsDocument();
```
## Etapa 3: Definir paradas de gradiente radial
Crie uma lista de pontos de gradiente para a elipse traçada com gradiente radial:
```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```
## Etapa 4: criar geometria de caminho
Defina uma elipse com gradiente radial usando geometria de caminho:
```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```
## Etapa 5: adicionar tela e caminho
Adicione uma nova tela ao documento e anexe o caminho com a geometria definida:
```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```
## Etapa 6: definir traço e gradiente
Configure o traçado do caminho com um pincel de gradiente radial:
```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```
## Etapa 7: definir a espessura do traço
Especifique a espessura do traço do caminho:
```java
path.setStrokeThickness(12f);
```
## Etapa 8: salve o documento
Salve o documento XPS resultante:
```java
doc.save(dataDir + "AddEllipse_out.xps");
```
Parabéns! Você adicionou com sucesso uma elipse com gradiente radial em Java XPS usando Aspose.Page para Java.
## Conclusão
Neste tutorial, exploramos as etapas para criar um documento XPS com uma elipse com gradiente radial visualmente atraente. Aspose.Page para Java simplifica a manipulação de documentos XPS, fornecendo aos desenvolvedores um poderoso conjunto de ferramentas.
## perguntas frequentes
### Posso usar Aspose.Page for Java com outras bibliotecas Java?
Sim, Aspose.Page for Java pode ser integrado perfeitamente com outras bibliotecas Java.
### O Aspose.Page é adequado para processamento de documentos em grande escala?
Absolutamente! Aspose.Page foi projetado para lidar com o processamento de documentos em grande escala com eficiência.
### Onde posso encontrar mais tutoriais e exemplos para Aspose.Page for Java?
 Visite a[Documentação Aspose.Page para Java](https://reference.aspose.com/page/java/)para tutoriais e exemplos abrangentes.
### Como posso obter uma licença temporária para Aspose.Page for Java?
 Você pode obter uma licença temporária[aqui](https://purchase.aspose.com/temporary-license/).
### Existem fóruns da comunidade para discussões do Aspose.Page?
 Sim, junte-se ao[Fórum da comunidade Aspose.Page](https://forum.aspose.com/c/page/39) para interagir com outros desenvolvedores e obter assistência.