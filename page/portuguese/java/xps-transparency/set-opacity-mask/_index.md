---
date: 2026-04-30
description: Aprenda a criar documentos XPS em Java e adicionar uma máscara de opacidade
  usando Aspose.Page Java. Guia passo a passo com exemplos de código.
keywords:
- create xps document java
- opacity mask java
- aspose.page java
linktitle: Definir máscara de opacidade no Java XPS
second_title: Aspose.Page Java API
title: Criar documento XPS em Java – Definir máscara de opacidade com Aspose.Page
url: /pt/java/xps-transparency/set-opacity-mask/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definir Máscara de Opacidade em Java XPS usando Aspose.Page Java

## Introdução
Neste tutorial você **criará XPS document Java** arquivos e aprenderá como aplicar uma máscara de opacidade que confere aos seus gráficos um aspecto polido e semi‑transparente. Percorreremos todo o processo — desde a inicialização de um documento XPS, adição de uma tela (canvas), desenho de um retângulo, até a anexação de uma máscara de opacidade baseada em imagem — usando a intuitiva API Aspose.Page Java. Ao final, você será capaz de gerar arquivos XPS profissionais programaticamente e reutilizar a máscara em qualquer forma que precisar.

## Respostas Rápidas
- **O que faz uma máscara de opacidade?** Ela define níveis variáveis de transparência para uma forma, permitindo que o conteúdo subjacente apareça.  
- **Qual biblioteca é necessária?** Aspose.Page for Java (aspose page java).  
- **Preciso de uma licença?** Uma licença temporária funciona para testes; uma licença completa é necessária para produção.  
- **Quantas linhas de código?** Cerca de 20 linhas de Java mais algumas instruções de configuração.  
- **Posso reutilizar a máscara em várias formas?** Sim, você pode atribuir o mesmo `ImageBrush` a vários caminhos.

## O que é uma Máscara de Opacidade em XPS?
Uma máscara de opacidade é um bitmap ou vetor que controla o alfa (transparência) de cada pixel em uma forma. Quando aplicada a um retângulo, partes do retângulo tornam‑se totalmente opacas, parcialmente transparentes ou totalmente transparentes, criando efeitos visuais sofisticados sem camadas de desenho adicionais.

## Por que usar Aspose.Page Java para **create XPS document java**?
- **Pure Java API** – Sem dependências nativas, portanto o mesmo código roda no Windows, Linux ou macOS.  
- **Full XPS spec compliance** – Máscaras são renderizadas exatamente como definido pelo padrão XPS.  
- **Object‑oriented design** – Similar ao .NET, facilitando a adoção se você já usou Aspose em outras linguagens.  
- **High performance** – Otimizado para documentos grandes e processamento em lote.

## Casos de Uso Comuns
- **Watermarking** – Aplique um logotipo semi‑transparente em todas as páginas.  
- **Dynamic theming** – Altere o estilo visual dos elementos de UI em relatórios gerados.  
- **Print‑ready previews** – Mostre como um design ficará com opacidade variável antes de enviá‑lo para a impressora.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:
- Um entendimento básico de programação Java.  
- Biblioteca Aspose.Page for Java instalada. Você pode baixá‑la **[here](https://releases.aspose.com/page/java/)**.  
- Uma licença válida para Aspose.Page. Se você não tem uma, obtenha uma licença temporária **[here](https://purchase.aspose.com/temporary-license/)**.  
- Um ambiente de desenvolvimento capaz de compilar e executar aplicações Java (por exemplo, IntelliJ IDEA, Eclipse ou VS Code).

## Importar Pacotes
Comece importando as classes necessárias da biblioteca Aspose.Page. Isso garante que a API esteja disponível para seu projeto.

```java
import com.aspose.xps.XpsCanvas;
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Guia Passo a Passo

### Etapa 1: Criar um Novo Documento XPS
Primeiro, instancie um novo documento XPS que conterá todos os nossos gráficos.

```java
// Create a new XPS document
XpsDocument doc = new XpsDocument();
```

### Etapa 2: Adicionar um Canvas
Um canvas funciona como uma superfície de desenho dentro da página XPS.

```java
// New canvas
XpsCanvas canvas = doc.addCanvas();
```

### Etapa 3: Adicionar um Retângulo e Aplicar um Preenchimento Sólido
Aqui criamos um caminho de retângulo e lhe damos um preenchimento sólido vermelho. Este retângulo receberá posteriormente a máscara de opacidade.

```java
// Rectangle in the middle left with opacity masked by ImageBrush
XpsPath path = canvas.addPath(doc.createPathGeometry("M 10,180 L 228,180 228,285 10,285"));
path.setFill(doc.createSolidColorBrush(doc.createColor(1.0f, 0.0f, 0.0f)));
```

### Etapa 4: Adicionar Máscara de Opacidade Usando um ImageBrush
Carregamos uma imagem TIFF, definimos retângulos de origem e destino, e configuramos o brush para modo de ladrilho (tile) para que a máscara se repita se necessário.

```java
path.setOpacityMask(doc.createImageBrush(dataDir +  "R08SY_NN.tif", 
                    new Rectangle2D.Float(0f, 0f, 128f, 192f), new Rectangle2D.Float(0f, 0f, 64f, 96f)));
((XpsImageBrush)path.getOpacityMask()).setTileMode(XpsTileMode.Tile);
```

### Etapa 5: Salvar o Documento XPS Resultante
Finalmente, persista o documento no disco. O arquivo de saída conterá o retângulo com a máscara de opacidade aplicada.

```java
// Save resultant XPS document
doc.save(dataDir + "OpacityMask_out.xps"); 
```

Siga estas etapas cuidadosamente para incorporar a funcionalidade de **add opacity mask** ao seu documento Java XPS usando Aspose.Page.

## Problemas Comuns & Solução de Problemas
- **Image not found** – Verifique se `dataDir` aponta para a pasta correta e se `R08SY_NN.tif` existe.  
- **Mask appears solid** – Certifique‑se de que a imagem de origem realmente contém valores alfa variáveis; uma imagem totalmente opaca não mostrará transparência.  
- **Tile mode not respected** – O retângulo de destino deve ser menor que o retângulo de origem para que o ladrilhamento seja perceptível.

## Perguntas Frequentes

**Q: O Aspose.Page é compatível com todos os ambientes de desenvolvimento Java?**  
A: Sim, o Aspose.Page foi projetado para funcionar perfeitamente com várias IDEs Java e ferramentas de construção.

**Q: Posso usar o Aspose.Page sem uma licença?**  
A: Embora você possa avaliar a biblioteca com uma licença temporária, uma licença completa é necessária para uso em produção.

**Q: Existem limitações na versão de avaliação?**  
A: A versão de avaliação pode impor restrições de tamanho ou recursos; consulte a documentação oficial para detalhes.

**Q: Como posso obter suporte para o Aspose.Page?**  
A: Visite o **[Aspose.Page forum](https://forum.aspose.com/c/page/39)** para ajuda da comunidade ou adquira uma licença para assistência premium.

**Q: Existe garantia de devolução de dinheiro para o Aspose.Page?**  
A: Consulte a **[purchase page](https://purchase.aspose.com/buy)** para informações sobre políticas de reembolso.

---

**Última Atualização:** 2026-04-30  
**Testado com:** Aspose.Page Java 24.11 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}