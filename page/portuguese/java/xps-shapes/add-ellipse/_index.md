---
date: 2026-04-24
description: Aprenda como criar um documento XPS em Java com uma elipse de gradiente
  radial. Este guia passo a passo mostra como definir a espessura do traço e especificar
  a geometria do caminho usando o Aspose.Page.
keywords:
- create xps document java
- set stroke thickness
- define path geometry
linktitle: Adicionar Elipse no Java XPS
second_title: Aspose.Page Java API
title: Criar documento XPS em Java – Adicionar elipse com gradiente radial
url: /pt/java/xps-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adicionar Elipse com Gradiente Radial usando Aspose.Page

## Introdução
Neste tutorial, você aprenderá como **create XPS document Java** com uma bela elipse contornada por um gradiente radial usando Aspose.Page para Java. Aspose.Page é uma biblioteca robusta que abstrai os detalhes de baixo nível do XPS, permitindo que você se concentre no design em vez das intricacias do formato de arquivo. Ao final deste guia, você terá um arquivo XPS pronto para uso que pode ser incorporado em relatórios, faturas ou qualquer fluxo de trabalho de geração de documentos.

## Respostas Rápidas
- **O que este código produz?** Um arquivo XPS de página única contendo uma elipse contornada com um gradiente radial multicolorido.  
- **Qual API principal é usada?** `Aspose.Page` for Java (`XpsDocument`, `XpsCanvas`, `XpsPath`, etc.).  
- **Preciso de uma licença para executar o exemplo?** Uma licença temporária funciona para avaliação; uma licença completa é necessária para produção.  
- **Quais são as propriedades principais que definimos?** Pincel de contorno (gradiente radial), método de espalhamento, paradas de gradiente e espessura do contorno.  
- **Posso mudar o tamanho da elipse?** Sim – modifique a string de geometria do caminho ou as coordenadas do pincel de gradiente.

## O que é “create XPS document Java”?
Criar um documento XPS em Java significa gerar programaticamente um arquivo XML Paper Specification (XPS) — um formato de documento de layout fixo semelhante ao PDF — diretamente a partir de código Java. Aspose.Page fornece um modelo de objeto de alto nível (`XpsDocument`, `XpsCanvas`, etc.) que abstrai a marcação XML, tornando o processo tão simples quanto trabalhar com objetos Java padrão.

## Por que usar uma elipse com gradiente radial?
Um gradiente radial confere uma sensação tridimensional, perfeito para destaques visuais, logotipos ou elementos decorativos em relatórios. Comparado a um contorno de cor sólida, o gradiente adiciona profundidade sem aumentar significativamente o tamanho do arquivo, e o formato XPS preserva a qualidade vetorial para qualquer escala.

## Pré-requisitos
Antes de começarmos, certifique‑se de que você tem os seguintes pré‑requisitos:
- Java Development Kit (JDK) instalado na sua máquina.
- Biblioteca Aspose.Page for Java baixada. Você pode obtê‑la [aqui](https://releases.aspose.com/page/java/).
- Um editor de código de sua escolha (Eclipse, IntelliJ, etc.) para escrever e executar código Java.

## Importar Pacotes
Certifique‑se de que os pacotes necessários estejam importados em seu projeto Java para usar Aspose.Page. Adicione as seguintes instruções de importação ao topo do seu arquivo Java:

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

## Etapa 1: Configurar Diretório do Documento
Defina o caminho para o diretório onde o documento XPS será salvo:

```java
String dataDir = "Your Document Directory";
```

## Etapa 2: Criar Documento XPS
Inicialize um novo documento XPS usando o código a seguir:

```java
XpsDocument doc = new XpsDocument();
```

## Etapa 3: Definir Paradas do Gradiente Radial
Crie uma lista de paradas de gradiente para a elipse contornada por gradiente radial:

```java
List<XpsGradientStop> stops = new LinkedList<>();
stops.add(doc.createGradientStop(doc.createColor(0, 0, 255), 0f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), .25f));
stops.add(doc.createGradientStop(doc.createColor(0, 255, 0), .5f));
stops.add(doc.createGradientStop(doc.createColor(255, 255, 0), .75f));
stops.add(doc.createGradientStop(doc.createColor(255, 0, 0), 1f));
```

## Etapa 4: Criar Geometria do Caminho
Defina uma elipse contornada por gradiente radial usando geometria de caminho:

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry("M 20,250 A 100,50 0 1 1 220,250 100,50 0 1 1 20,250");
```

## Etapa 5: Adicionar Canvas e Caminho
Adicione um novo canvas ao documento e anexe o caminho com a geometria definida:

```java
XpsCanvas canvas = doc.addCanvas();
XpsPath path = canvas.addPath(pathGeometry);
```

## Etapa 6: Definir Contorno e Gradiente
Configure o contorno do caminho com um pincel de gradiente radial:

```java
path.setStroke(doc.createRadialGradientBrush(new Point2D.Float(575f, 125f), new Point2D.Float(575f, 100f), 75f, 50f));
((XpsGradientBrush)path.getStroke()).setSpreadMethod(XpsSpreadMethod.Reflect);
((XpsGradientBrush)path.getStroke()).getGradientStops().addAll(stops);
stops.clear();
```

## Etapa 7: Definir Espessura do Contorno
Especifique a **set stroke thickness** do caminho:

```java
path.setStrokeThickness(12f);
```

## Etapa 8: Salvar o Documento
Salve o documento XPS resultante:

```java
doc.save(dataDir + "AddEllipse_out.xps");
```

Parabéns! Você adicionou com sucesso uma elipse contornada com gradiente radial enquanto **create XPS document Java** com Aspose.Page.

## Problemas Comuns e Soluções
| Problema | Por que acontece | Correção |
|----------|------------------|----------|
| **A elipse parece plana** | Usando `XpsSpreadMethod.Pad` em vez de `Reflect` | Altere o método de espalhamento para `XpsSpreadMethod.Reflect` como mostrado na Etapa 6. |
| **Nenhum arquivo de saída** | `dataDir` aponta para uma pasta inexistente | Certifique‑se de que o diretório exista ou use um caminho absoluto. |
| **Cores do gradiente parecem incorretas** | Ordem incorreta das paradas de gradiente | Verifique se os valores `offset` (0 → 1) aumentam monotonamente. |
| **Erros de compilação** | JARs do Aspose.Page ausentes no classpath | Adicione `aspose-page-xx.jar` às dependências do seu projeto. |

## Perguntas Frequentes

**Q: Posso usar Aspose.Page for Java com outras bibliotecas Java?**  
A: Sim, Aspose.Page for Java pode ser integrado com outras bibliotecas Java sem problemas.

**Q: Aspose.Page é adequado para processamento de documentos em grande escala?**  
A: Absolutamente! Aspose.Page foi projetado para lidar com processamento de documentos em grande escala de forma eficiente.

**Q: Onde posso encontrar mais tutoriais e exemplos para Aspose.Page for Java?**  
A: Visite a [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/) para tutoriais e exemplos abrangentes.

**Q: Como posso obter uma licença temporária para Aspose.Page for Java?**  
A: Você pode obter uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

**Q: Existem fóruns da comunidade para discussões sobre Aspose.Page?**  
A: Sim, participe do [Aspose.Page community forum](https://forum.aspose.com/c/page/39) para interagir com outros desenvolvedores e obter assistência.

---

**Last Updated:** 2026-04-24  
**Tested With:** Aspose.Page for Java 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}