---
date: 2026-03-13
description: Aprenda como adicionar gradiente a documentos XPS em Java usando Aspose.Page
  e como personalizar as paradas de gradiente para efeitos horizontais impressionantes.
linktitle: Add Horizontal Gradient in Java XPS
second_title: Aspose.Page Java API
title: Como adicionar gradiente – Gradiente horizontal no Java XPS
url: /pt/java/xps-gradient-addition/horizontal/
weight: 11
---

Autor:"

Make sure to keep code block placeholders unchanged.

Also keep URLs unchanged.

Now produce final content with same shortcodes and structure.

Let's write.

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Gradiente – Gradiente Horizontal em Java XPS

## Introdução
Bem‑vindo a este guia passo a passo sobre **como adicionar gradiente** a um documento XPS usando Java. Neste tutorial você aprenderá a adicionar um gradiente horizontal, por que ele é importante para o acabamento visual e como **personalizar as paradas de gradiente** para controle preciso de cores. Aspose.Page para Java torna o trabalho com documentos XPS (XML Paper Specification) simples, permitindo que você se concentre no design em vez de no manuseio de arquivos de baixo nível.

## Respostas Rápidas
- **Qual biblioteca é necessária?** Aspose.Page para Java  
- **Qual versão do Java funciona?** Qualquer runtime Java 8+  
- **Preciso de licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção  
- **Posso mudar a direção do gradiente?** Sim – basta modificar os pontos inicial/final do pincel linear  
- **É possível adicionar múltiplos gradientes?** Absolutamente – repita as etapas de criação de caminho com pincéis diferentes  

## O que é um Gradiente Horizontal em XPS?
Um gradiente horizontal é uma transição suave de cores da esquerda para a direita em uma forma. No XPS ele é representado por um pincel de gradiente linear que interpola entre **paradas de gradiente** definidas. Esse efeito visual é comumente usado em banners, botões e preenchimentos de fundo.

## Por que Usar Aspose.Page para Java?
- **Suporte total a XPS** – crie, edite e renderize sem ferramentas de terceiros.  
- **API simples** – objetos de alto nível como `XpsDocument`, `XpsPath` e `XpsGradientBrush` ocultam a complexidade XML.  
- **Desempenho** – otimizado para documentos grandes e processamento em lote.  

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. **Ambiente de Desenvolvimento Java** – Instale o JDK mais recente em [java.com](https://www.java.com).  
2. **Biblioteca Aspose.Page para Java** – Baixe o JAR na [documentação Aspose.Page para Java](https://reference.aspose.com/page/java/).  

## Importar Pacotes
Comece importando as classes necessárias. Essas importações dão acesso à criação de documentos, manipulação de gradientes e geometria básica.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsGradientBrush;
import com.aspose.xps.XpsGradientStop;
import com.aspose.xps.XpsPath;
import java.awt.geom.Point2D;
import java.util.LinkedList;
import java.util.List;
```

## Etapa 1: Inicializar o Documento XPS
Crie uma nova instância de `XpsDocument` e aponte para a pasta onde deseja salvar o resultado.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
//Initialize document
XpsDocument doc = new XpsDocument();
```

## Etapa 2: Criar Gradiente Horizontal
Defina uma lista de **paradas de gradiente** que controlam a cor e a posição de cada ponto de transição. O exemplo abaixo cria um gradiente vibrante semelhante a um arco‑íris.

```java
// Horizontal gradient
List<XpsGradientStop> stops = new LinkedList<XpsGradientStop>();
stops.add(doc.createGradientStop(doc.createColor(255, 244, 253, 225), 0.0673828f));
stops.add(doc.createGradientStop(doc.createColor(255, 251, 240, 23), 0.314453f));
stops.add(doc.createGradientStop(doc.createColor(255, 252, 209, 0), 0.482422f));
stops.add(doc.createGradientStop(doc.createColor(255, 241, 254, 161), 0.634766f));
stops.add(doc.createGradientStop(doc.createColor(255, 53, 253, 255), 0.915039f));
stops.add(doc.createGradientStop(doc.createColor(255, 12, 91, 248), 1f));
```

### Como personalizar as paradas de gradiente
- **Cor** – Use `doc.createColor(alpha, red, green, blue)` para definir qualquer valor ARGB.  
- **Posição** – O segundo argumento (`float` entre `0` e `1`) define onde a parada aparece ao longo da linha do gradiente. Ajuste esses valores para deslocar as cores para a esquerda ou direita.

## Etapa 3: Adicionar Caminho com Gradiente
Crie um caminho retangular, aplique uma transformação se necessário e preencha‑o com o pincel de gradiente linear. O pincel usa dois pontos (`(10,0)` a `(228,0)`) para produzir um efeito horizontal. Como as coordenadas Y são idênticas, esse pincel funciona como um **pincel de gradiente horizontal**.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path = doc.addPath(doc.createPathGeometry("M 10,210 L 228,210 228,300 10,300"));
path.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 20f, 70f));
path.setFill(doc.createLinearGradientBrush(new Point2D.Float(10f, 0f), new Point2D.Float(228f, 0f)));
((XpsGradientBrush)path.getFill()).getGradientStops().addAll(stops);
stops.clear();
```

**Dica profissional:** Reutilizar a mesma lista `stops` para múltiplos caminhos pode melhorar o desempenho, mas lembre‑se de chamar `clear()` antes de adicionar novas paradas.

## Etapa 4: Salvar o Documento
Persista o arquivo XPS no disco. Agora você pode abri‑lo com qualquer visualizador XPS para ver o gradiente horizontal em ação.

```java
doc.save(dataDir + "HorizontalGradient.xps");
```

## Como Aplicar Múltiplos Gradientes
Se quiser **aplicar múltiplos gradientes** dentro do mesmo documento XPS, basta repetir as etapas “Criar Gradiente Horizontal” e “Adicionar Caminho com Gradiente” para cada nova forma. Use uma nova lista de objetos `XpsGradientStop` (ou limpe a lista existente) e atribua um novo `LinearGradientBrush` com seus próprios pontos inicial/final. Essa abordagem permite sobrepor gradientes, criar fundos complexos ou destacar diferentes elementos de UI em uma única página.

## Por que Isso Importa – Benefícios do Pincel de Gradiente Horizontal
- **Profundidade visual:** Um pincel de gradiente horizontal adiciona uma sensação sutil tridimensional sem imagens extras.  
- **Eficiência de tamanho de arquivo:** Gradientes são armazenados como definições vetoriais, mantendo o arquivo XPS leve.  
- **Escalabilidade:** Como o gradiente é baseado em vetor, ele escala perfeitamente em telas de alta resolução.  

## Problemas Comuns & Soluções
| Problema | Razão | Correção |
|----------|-------|----------|
| O gradiente aparece sólido | Nenhuma parada de gradiente adicionada ou pincel não definido | Certifique‑se de que `path.setFill(...)` usa um `LinearGradientBrush` e que as paradas são adicionadas via `getGradientStops().addAll(stops)`. |
| Cores parecem apagadas | Valor alfa incorreto (primeiro parâmetro) | Use `255` para cores totalmente opacas, a menos que transparência seja desejada. |
| Tamanho do caminho está incorreto | Valores da matriz de transformação errados | Ajuste os parâmetros da matriz (`scaleX, skewY, skewX, scaleY, translateX, translateY`). |

## Perguntas Frequentes

**P: Posso aplicar múltiplos gradientes em um único documento XPS?**  
R: Sim, você pode adicionar múltiplos caminhos, cada um com seu próprio pincel de gradiente, para criar designs em camadas complexas.

**P: O Aspose.Page é compatível com as versões mais recentes do Java?**  
R: Aspose.Page para Java é atualizado regularmente e funciona com Java 8 e versões posteriores.

**P: Existem outros tipos de gradiente disponíveis no Aspose.Page?**  
R: Além dos gradientes lineares, o Aspose.Page também suporta gradientes radiais para transições circulares de cor.

**P: Posso personalizar as cores e posições das paradas de gradiente?**  
R: Absolutamente! Você tem controle total sobre a cor ARGB de cada parada e sua posição relativa (intervalo 0‑1).

**P: Existe um fórum da comunidade para o Aspose.Page onde eu possa buscar ajuda?**  
R: Sim, você pode visitar o [forum Aspose.Page](https://forum.aspose.com/c/page/39) para se conectar com a comunidade e obter assistência.

---

**Última Atualização:** 2026-03-13  
**Testado com:** Aspose.Page para Java 24.11  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}