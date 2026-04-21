---
date: 2026-01-02
description: Aprenda a adicionar máscara de opacidade a documentos XPS com Aspose.Page
  Java. Guia passo a passo para criar um retângulo de máscara de opacidade e melhorar
  a qualidade visual.
linktitle: Set Opacity Mask in Java XPS
second_title: Aspose.Page Java API
title: Definir máscara de opacidade no XPS Java usando Aspose.Page Java
url: /pt/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definir Máscara de Opacidade em Java XPS usando Aspose.Page Java

## Introdução
Bem‑vindo ao nosso guia abrangente sobre máscaras de opacidade **aspose page java**. Neste tutorial você aprenderá como criar um documento XPS, adicionar uma tela (canvas) e aplicar uma máscara de opacidade a um retângulo — tudo com a poderosa API Aspose.Page Java. Ao final, você será capaz de adicionar retângulos com máscara de opacidade que dão aos seus arquivos XPS um aspecto polido e semitransparente.

## Respostas Rápidas
- **O que uma máscara de opacidade faz?** Ela define níveis de transparência variáveis para uma forma, permitindo que o conteúdo subjacente apareça.
- **Qual biblioteca é necessária?** Aspose.Page for Java (aspose page java).
- **Preciso de uma licença?** Uma licença temporária funciona para testes; uma licença completa é necessária para produção.
- **Quantas linhas de código?** Cerca de 20 linhas de Java mais algumas instruções de configuração.
- **Posso reutilizar a máscara em várias formas?** Sim, você pode atribuir o mesmo ImageBrush a vários caminhos.

## O que é uma Máscara de Opacidade em XPS?
Uma máscara de opacidade é um bitmap ou vetor que controla o alfa (transparência) de cada pixel em uma forma. Quando aplicada a um retângulo, partes do retângulo tornam‑se totalmente opacas, parcialmente transparentes ou totalmente transparentes, criando efeitos visuais sofisticados.

## Por que usar Aspose.Page Java para Máscaras de Opacidade?
- **API completa no estilo .NET em Java** – modelo de objetos intuitivo.
- **Sem dependências externas** – funciona com Java puro.
- **Renderização de alta fidelidade** – as máscaras são renderizadas exatamente como na especificação XPS.
- **Multiplataforma** – executa em Windows, Linux ou macOS sem alterações.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:
- Um entendimento básico de programação Java.  
- Biblioteca Aspose.Page for Java instalada. Você pode baixá‑la **[aqui](https://releases.aspose.com/page/java/)**.  
- Uma licença válida para Aspose.Page. Se você não tem uma, obtenha uma licença temporária **[aqui](https://purchase.aspose.com/temporary-license/)**.  
- Um ambiente de desenvolvimento capaz de compilar e executar aplicações Java (por exemplo, IntelliJ IDEA, Eclipse ou VS Code).

## Importar Pacotes
Comece importando as classes necessárias da biblioteca Aspose.Page. Isso garante que a API esteja disponível para o seu projeto.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Guia Passo a Passo

### Passo 1: Criar um Novo Documento XPS
Primeiro, instancie um novo documento XPS que conterá todos os nossos gráficos.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Passo 2: Adicionar um Canvas
Um canvas funciona como uma superfície de desenho dentro da página XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Passo 3: Adicionar um Retângulo e Aplicar um Preenchimento Sólido
Aqui criamos um caminho de retângulo e lhe damos um preenchimento sólido vermelho. Este retângulo receberá posteriormente a máscara de opacidade.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Passo 4: Adicionar Máscara de Opacidade Usando um ImageBrush
Carregamos uma imagem TIFF, definimos os retângulos de origem e destino, e configuramos o brush para modo de ladrilho (tile) para que a máscara se repita, se necessário.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Passo 5: Salvar o Documento XPS Resultante
Finalmente, persista o documento no disco. O arquivo de saída conterá o retângulo com a máscara de opacidade aplicada.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Siga estes passos cuidadosamente para incorporar a funcionalidade **add opacity mask** ao seu documento Java XPS usando Aspose.Page.

## Problemas Comuns & Solução de Problemas
- **Imagem não encontrada** – Verifique se `dataDir` aponta para a pasta correta e se `R08SY_NN.tif` existe.
- **Máscara aparece sólida** – Certifique‑se de que a imagem de origem realmente contém valores alfa variáveis; uma imagem totalmente opaca não mostrará transparência.
- **Modo de ladrilho não respeitado** – O retângulo de destino deve ser menor que o retângulo de origem para que o ladrilhamento seja perceptível.

## Perguntas Frequentes

**Q: O Aspose.Page é compatível com todos os ambientes de desenvolvimento Java?**  
A: Sim, o Aspose.Page foi projetado para funcionar perfeitamente com várias IDEs Java e ferramentas de build.

**Q: Posso usar Aspose.Page sem uma licença?**  
A: Embora você possa avaliar a biblioteca com uma licença temporária, uma licença completa é necessária para uso em produção.

**Q: Existem limitações na versão de avaliação?**  
A: A avaliação pode impor restrições de tamanho ou recursos; consulte a documentação oficial para detalhes.

**Q: Como posso obter suporte para Aspose.Page?**  
A: Visite o **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** para ajuda da comunidade ou adquira uma licença para assistência premium.

**Q: Há garantia de devolução do dinheiro para Aspose.Page?**  
A: Consulte a **[purchase page](https://purchase.aspose.com/buy)** para informações sobre políticas de reembolso.

**Última atualização:** 2026-01-02  
**Testado com:** Aspose.Page Java 24.11 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}