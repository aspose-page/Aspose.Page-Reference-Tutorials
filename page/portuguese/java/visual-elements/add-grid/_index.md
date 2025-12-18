---
date: 2025-12-18
description: Aprenda a adicionar grade e retângulo transparente em documentos XPS
  Java com Aspose.Page. Guia passo a passo para salvar documentos XPS de forma eficiente.
linktitle: How to Add Grid using Visual Brush in Java
second_title: Aspose.Page Java API
title: Como adicionar grade usando Visual Brush no Java
url: /pt/java/visual-elements/add-grid/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Grade usando Visual Brush em Java

## Introdução
Se você está procurando **como adicionar grade** aos seus documentos XPS gerados em Java, chegou ao lugar certo. Neste tutorial vamos guiá‑lo na adição de uma grade com um Visual Brush, sobrepondo um retângulo transparente e, finalmente, **salvar documento XPS** usando a API Aspose.Page Java. Ao final, você terá um visual refinado que pode ser reutilizado em relatórios, faturas ou qualquer aplicação que trabalhe intensamente com documentos.

## Respostas Rápidas
- **O que um Visual Brush faz?** Ele pinta uma área definida com conteúdo visual reutilizável, perfeito para padrões repetidos como grades.  
- **Posso mudar a cor da grade?** Sim – modifique as configurações de brush de cor sólida.  
- **Como adiciono um retângulo transparente sobre a grade?** Use `setOpacity` em um caminho preenchido com uma cor sólida.  
- **Qual método salva o arquivo?** `doc.save(...)` grava o arquivo XPS no disco.  
- **Preciso de licença?** Uma licença temporária ou completa é necessária para uso em produção.

## O que é uma Grade de Visual Brush?
Um Visual Brush permite definir um pequeno visual (o padrão da grade) e então repeti‑lo em uma área maior. Essa abordagem é mais eficiente em memória do que desenhar cada linha individualmente e oferece repetição pixel‑perfect.

## Por que usar Aspose.Page para esta tarefa?
- **Cross‑platform** – Funciona em qualquer SO que suporte Java.  
- **High‑fidelity rendering** – Controle preciso sobre cores, opacidade e repetição.  
- **No external dependencies** – Tudo é tratado através da biblioteca Aspose.Page.

## Pré‑requisitos
Antes de começarmos, certifique‑se de que você tem:

- Conhecimento básico de programação Java.  
- Biblioteca Aspose.Page instalada – você pode baixá‑la na [Aspose.Page for Java documentation](https://reference.aspose.com/page/java/).  
- JDK 8 ou superior configurado na sua máquina de desenvolvimento.

## Importar Pacotes
Primeiro, importe as classes necessárias para que o compilador saiba onde encontrar os tipos que usaremos:

```java
import java.awt.geom.Point2D;
import java.awt.geom.Rectangle2D;
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsPathGeometry;
import com.aspose.xps.XpsTileMode;
import com.aspose.xps.XpsVisualBrush;
```

## Guia Passo a Passo

### Passo 1: Configurar Seu Projeto
Crie uma nova instância `XpsDocument` e aponte para a pasta onde deseja salvar o arquivo de saída.

```java
String dataDir = "Your Document Directory";
XpsDocument doc = new XpsDocument();
```

### Passo 2: Criar um Visual Brush de Grade Magenta
Definimos uma pequena forma magenta que será repetida na área da grade.

```java
XpsCanvas visualCanvas = doc.createCanvas();
XpsPath visualPath = visualCanvas.addPath(doc.createPathGeometry("M 0,4 L 4,4 4,0 6,0 6,4 10,4 10,6 6,6 6,10 4,10 4,6 0,6 Z"));
visualPath.setFill(doc.createSolidColorBrush(doc.createColor(1f, .61f, 0.1f, 0.61f)));
```

### Passo 3: Definir Geometria para o Brush da Grade
Configure a área retangular que receberá o visual repetido.

```java
XpsPathGeometry pathGeometry = doc.createPathGeometry();
pathGeometry.addSegment(doc.createPolyLineSegment(new Point2D.Float[] {
    new Point2D.Float(240f, 5f),
    new Point2D.Float(240f, 310f),
    new Point2D.Float(0f, 310f)
}));
pathGeometry.get(0).setStartPoint(new Point2D.Float(0f, 5f));
```

### Passo 4: Criar um Novo Canvas para o Documento
Adicione um canvas ao documento e posicione‑o onde a grade aparecerá.

```java
XpsCanvas canvas = doc.addCanvas();
canvas.setRenderTransform(doc.createMatrix(1f, 0f, 0f, 1f, 268f, 70f));
```

### Passo 5: Adicionar a Grade ao Canvas
Aplique o visual brush à geometria, habilitando a repetição.

```java
XpsPath gridPath = canvas.addPath(pathGeometry);
gridPath.setFill(doc.createVisualBrush(visualCanvas,
    new Rectangle2D.Float(0f, 0f, 10f, 10f), new Rectangle2D.Float(0f, 0f, 10f, 10f)));
((XpsVisualBrush)gridPath.getFill()).setTileMode(XpsTileMode.Tile);
```

### Passo 6: Adicionar um Retângulo Vermelho Transparente (Recurso Secundário)
Aqui demonstramos **adicionar retângulo transparente** sobre a grade para ênfase.

```java
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,10 L 228,10 228,100 10,100"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
path.setOpacity(0.7f);
```

### Passo 7: Salvar o Documento XPS Resultante
Finalmente, grave o documento no disco—este é o passo de **salvar documento XPS**.

```java
doc.save(dataDir + "AddGrid_out.xps");
```

Siga estes passos e você terá uma grade com aparência profissional e uma sobreposição transparente, tudo gerado programaticamente.

## Problemas Comuns & Dicas

- **Tamanho de tile incorreto:** Certifique‑se de que o `Rectangle2D` usado para o brush corresponda ao tamanho de repetição desejado; caso contrário o padrão pode esticar.
- **Opacidade não aplicada:** Lembre‑se de chamar `setOpacity` no caminho que deseja transparente; isso não afetará o brush em si.
- **Arquivo não salvo:** Verifique se `dataDir` aponta para uma pasta existente e se sua aplicação tem permissões de escrita.

## Perguntas Frequentes

**Q: O Aspose.Page é adequado para geração profissional de documentos?**  
A: Sim, o Aspose.Page é uma biblioteca robusta projetada para geração de XPS e PDF de alta qualidade em Java.

**Q: Posso personalizar as cores da grade usando Visual Brush?**  
A: Absolutamente! Altere os parâmetros de `createColor` na chamada `setFill` do brush para quaisquer valores RGBA que precisar.

**Q: Onde posso encontrar suporte adicional para o Aspose.Page?**  
A: Visite o [Aspose.Page forum](https://forum.aspose.com/c/page/39) para ajuda da comunidade e respostas oficiais.

**Q: Existe um teste gratuito disponível para o Aspose.Page?**  
A: Sim, você pode acessar o [free trial](https://releases.aspose.com/) para explorar todos os recursos antes de comprar.

**Q: Como posso obter uma licença temporária para testes?**  
A: Adquira uma [temporary license](https://purchase.aspose.com/temporary-license/) que funciona para desenvolvimento e avaliação.

**Última Atualização:** 2025-12-18  
**Testado com:** Aspose.Page for Java 23.12 (latest)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}