---
date: 2026-05-30
description: Aprenda a criar documentos XPS em Java usando Aspose.Page e adicione
  imagens em mosaico sem esforço com este guia passo a passo. Como criar arquivos
  XPS rapidamente.
keywords:
- how to create xps
- add tiled image java
- Aspose.Page XPS tutorial
linktitle: Adicionar imagem em mosaico no XPS com Java
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  headline: How to Create XPS Document with a Tiled Image in Java
  type: TechArticle
- description: Learn how to create XPS document in Java using Aspose.Page and add
    tiled image effortlessly with this step‑by‑step guide. How to create XPS files
    quickly.
  name: How to Create XPS Document with a Tiled Image in Java
  steps:
  - name: Set Up Your Project
    text: Add the Aspose.Page JAR files to your project’s classpath and verify the
      import statements compile without errors.
  - name: Create XPS Document
    text: '`XpsDocument` is the core container that holds pages, paths, and resources.
      Instantiate it with the desired page size, then you can start adding graphical
      elements.'
  - name: Define the Tiled Image Path
    text: Place the image you want to tile (e.g., `R08LN_NN.jpg`) inside the directory
      referenced by `dataDir`. The image will be used as a brush pattern.
  - name: Add Tiled Image
    text: Create a rectangular path and fill it with an `XpsImageBrush`. By setting
      the tile mode to `Tile`, the image repeats across the rectangle. Adjust the
      source and destination rectangles to control tile size and positioning.
  - name: Save the Document
    text: Persist the XPS file to disk. The output file will contain the tiled image
      you just defined and can be opened with any XPS viewer. Repeat these steps whenever
      you need to **add tiled image** to other pages or shapes within the same XPS
      document.
  type: HowTo
- questions:
  - answer: It provides a high‑level API to generate and manipulate XPS documents
      in Java.
    question: What does Aspose.Page do?
  - answer: Yes – use `XpsImageBrush` with `XpsTileMode.Tile`.
    question: Can I tile an image?
  - answer: A temporary or commercial license is required for production use.
    question: Do I need a license?
  - answer: Any JDK 8+ is compatible.
    question: What Java version is supported?
  - answer: Roughly 10–15 minutes for a basic tiled‑image scenario.
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.Page Java API
title: Como criar documento XPS com uma imagem em mosaico no Java
url: /pt/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Criar Documento XPS com uma Imagem em Mosaico em Java

## Introdução
Criar documentos XPS programaticamente é uma habilidade essencial para desenvolvedores Java que precisam de saída imprimível e independente de dispositivo. **Como criar XPS** de forma eficiente é respondido pelo Aspose.Page para Java, que abstrai os detalhes de baixo nível da XML Paper Specification e permite que você se concentre no design visual. Neste guia você verá exatamente como criar um documento XPS, adicionar uma imagem em mosaico como plano de fundo ou padrão e salvar o resultado — tudo com código conciso e pronto para produção.

## Respostas Rápidas
- **O que o Aspose.Page faz?** Ele fornece uma API de alto nível para gerar e manipular documentos XPS em Java.  
- **Posso colocar uma imagem em mosaico?** Sim – use `XpsImageBrush` com `XpsTileMode.Tile`.  
- **Preciso de uma licença?** Uma licença temporária ou comercial é necessária para uso em produção.  
- **Qual versão do Java é suportada?** Qualquer JDK 8+ é compatível.  
- **Quanto tempo leva a implementação?** Aproximadamente 10–15 minutos para um cenário básico de imagem em mosaico.

## O que é “criar documento XPS”?
`XpsDocument` é o objeto de nível superior do Aspose.Page que representa um único arquivo XPS na memória. Ele encapsula páginas, recursos e metadados, permitindo que você construa o documento programaticamente. Criar um documento XPS significa instanciar essa classe, adicionar elementos visuais e, finalmente, chamar `save` para gravar o arquivo de layout fixo no disco. Essa abordagem elimina o manuseio manual de XML e garante conformidade com a XML Paper Specification.

## Por que adicionar uma imagem em mosaico?
O mosaico repete um gráfico em uma área definida, o que é ideal para planos de fundo, marcas d'água ou preenchimentos de padrão. Usando `XpsTileMode.Tile` a imagem repete automaticamente sem duplicação manual, economizando tempo de desenvolvimento e garantindo renderização consistente em qualquer dispositivo. Imagens em mosaico também mantêm o tamanho do arquivo baixo porque o mesmo recurso bitmap é reutilizado em vez de ser incorporado várias vezes.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – JDK 8 ou mais recente instalado.  
2. **Aspose.Page for Java** – faça o download no [website](https://releases.aspose.com/page/java/).  
3. **Um diretório gravável** – onde o arquivo XPS gerado será salvo.

## Importar Pacotes
No seu projeto Java, importe as classes necessárias:

`XpsDocument` é o objeto principal que representa um arquivo XPS.  
`XpsImageBrush` pinta formas usando uma fonte de imagem.  
`XpsTileMode` especifica como uma imagem é mosaico.  
`Rectangle2D` descreve uma região retangular para posicionamento.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Guia Passo a Passo

### Etapa 1: Configurar Seu Projeto
Adicione os arquivos JAR do Aspose.Page ao classpath do seu projeto e verifique se as instruções de importação compilam sem erros.

### Etapa 2: Criar Documento XPS
`XpsDocument` é o contêiner central que contém páginas, caminhos e recursos. Instancie‑o com o tamanho de página desejado e então você pode começar a adicionar elementos gráficos.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Etapa 3: Definir o Caminho da Imagem em Mosaico
Coloque a imagem que você deseja mosaicar (por exemplo, `R08LN_NN.jpg`) dentro do diretório referenciado por `dataDir`. A imagem será usada como padrão de pincel.

### Etapa 4: Adicionar Imagem em Mosaico
Crie um caminho retangular e preencha‑o com um `XpsImageBrush`. Definindo o modo de mosaico para `Tile`, a imagem repete‑se ao longo do retângulo. Ajuste os retângulos de origem e destino para controlar o tamanho e o posicionamento das telhas.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Etapa 5: Salvar o Documento
Persista o arquivo XPS no disco. O arquivo de saída conterá a imagem em mosaico que você acabou de definir e pode ser aberto com qualquer visualizador XPS.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Repita estas etapas sempre que precisar **adicionar imagem em mosaico** a outras páginas ou formas dentro do mesmo documento XPS.

## Problemas Comuns e Soluções
| Problema | Solução |
|----------|----------|
| Imagem não aparece | Verifique se o caminho do arquivo (`dataDir + "R08LN_NN.jpg"`) está correto e se a imagem está acessível. |
| Padrão de mosaico aparece esticado | Ajuste os valores de `Rectangle2D` de origem e destino para controlar o tamanho da telha. |
| Opacidade não tem efeito | Certifique‑se de que a opacidade do pincel está definida **depois** da configuração do modo de mosaico. |

## Perguntas Frequentes

**Q:** O Aspose.Page é compatível com todas as versões do Java?  
**A:** O Aspose.Page suporta Java 8 até Java 21; você pode encontrar a matriz completa de compatibilidade [aqui](https://reference.aspose.com/page/java/).

**Q:** Posso usar o Aspose.Page em projetos comerciais?  
**A:** Sim, uma licença comercial é necessária para uso em produção. Opções de compra estão listadas [aqui](https://purchase.aspose.com/buy).

**Q:** Existe uma versão de avaliação gratuita disponível?  
**A:** Uma avaliação totalmente funcional pode ser baixada na página de lançamentos da Aspose [aqui](https://releases.aspose.com/).

**Q:** Onde posso obter suporte da comunidade?  
**A:** Participe do fórum da comunidade Aspose.Page em [forum](https://forum.aspose.com/c/page/39) para fazer perguntas e compartilhar exemplos.

**Q:** Como obtenho uma licença temporária para avaliação?  
**A:** Licenças temporárias são fornecidas mediante solicitação via portal da Aspose [aqui](https://purchase.aspose.com/temporary-license/).

## Conclusão
Agora você tem um fluxo de trabalho completo e pronto para produção **como criar XPS** com imagens em mosaico usando Aspose.Page para Java. Ao aproveitar `XpsImageBrush` e `XpsTileMode.Tile`, você pode gerar gráficos ricos e repetíveis sem inflar o tamanho do arquivo. Experimente diferentes tamanhos de telha, níveis de opacidade e formas para construir layouts de documentos sofisticados. No próximo passo, explore a adição de formas vetoriais ou sobreposições de texto para aprimorar ainda mais seus arquivos XPS.

---

**Última atualização:** 2026-05-30  
**Testado com:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Tutoriais Relacionados

- [Como Adicionar Imagem a Documentos XPS Java – Um Guia Simples com Aspose.Page](/page/java/xps-image-manipulation/add-image/)
- [Aspose.Page Java - Adicionar Páginas ao Tutorial XPS](/page/java/xps-page-manipulation/add-page/)
- [Converter XPS para PDF em Java usando Aspose.Page Java](/page/java/file-merging/xps-to-pdf/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}