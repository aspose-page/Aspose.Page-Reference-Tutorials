---
date: 2025-12-28
description: Aprenda a criar documentos XPS em Java usando Aspose.Page e adicione
  imagens em mosaico sem esforço com este guia passo a passo.
linktitle: Add Tiled Image in Java XPS
second_title: Aspose.Page Java API
title: Como criar um documento XPS com uma imagem em mosaico no Java
url: /pt/java/xps-image-manipulation/add-tiled-image/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Documento XPS e Adicionar uma Imagem em Mosaico em Java

## Introdução
No desenvolvimento Java moderno, a capacidade de **criar documento XPS** programaticamente é uma habilidade valiosa, especialmente quando você precisa enriquecê‑los com gráficos como imagens em mosaico. Aspose.Page for Java torna esse processo simples, permitindo que você se concentre no design visual em vez de lidar com arquivos de baixo nível. Neste tutorial você aprenderá exatamente como criar um documento XPS, **adicionar imagem em mosaico**, e salvar o resultado, tudo com exemplos de código claros, passo a passo.

## Respostas Rápidas
- **O que o Aspose.Page faz?** Ele fornece uma API de alto nível para gerar e manipular documentos XPS em Java.  
- **Posso aplicar mosaico a uma imagem?** Sim – use `XpsImageBrush` com `XpsTileMode.Tile`.  
- **Preciso de licença?** Uma licença temporária ou comercial é necessária para uso em produção.  
- **Qual versão do Java é suportada?** Qualquer JDK 8+ é compatível.  
- **Quanto tempo leva a implementação?** Aproximadamente 10–15 minutos para um cenário básico de imagem em mosaico.

## O que é “criar documento XPS”?
Um arquivo XPS (XML Paper Specification) é um formato de documento de layout fixo semelhante ao PDF. Criar um documento XPS programaticamente permite gerar arquivos imprimíveis e independentes de dispositivo diretamente a partir do código Java.

## Por que adicionar uma imagem em mosaico?
Aplicar mosaico a uma imagem repete o gráfico em uma área definida, o que é perfeito para fundos, marcas d'água ou preenchimentos de padrão. Usando `XpsTileMode.Tile` do Aspose.Page você pode conseguir isso com apenas algumas linhas de código.

## Pré-requisitos
Antes de começar, certifique‑se de que você tem:

1. **Java Development Kit (JDK)** – JDK 8 ou mais recente instalado.  
2. **Aspose.Page for Java** – faça o download no [website](https://releases.aspose.com/page/java/).  
3. **Um diretório gravável** – onde o arquivo XPS gerado será salvo.

## Importar Pacotes
No seu projeto Java, importe as classes necessárias:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsImageBrush;
import com.aspose.xps.XpsPath;
import com.aspose.xps.XpsTileMode;
import java.awt.geom.Rectangle2D;
```

## Guia Passo a Passo

### Passo 1: Configurar Seu Projeto
Adicione os arquivos JAR do Aspose.Page ao classpath do seu projeto e verifique se as instruções de importação compilam sem erros.

### Passo 2: Criar Documento XPS
Instancie um novo objeto `XpsDocument`. Este é o contêiner principal que armazenará todas as páginas, caminhos e recursos.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

### Passo 3: Definir o Caminho da Imagem em Mosaico
Coloque a imagem que você deseja usar em mosaico (por exemplo, `R08LN_NN.jpg`) dentro do diretório referenciado por `dataDir`. A imagem será usada como padrão de pincel.

### Passo 4: Adicionar Imagem em Mosaico
Crie um caminho retangular e preencha‑o com um `XpsImageBrush`. Definindo o modo de mosaico para `Tile`, a imagem se repete ao longo do retângulo.

```java
// Tile image
// ImageBrush filled rectangle in the right top below
XpsPath path = doc.addPath(doc.createPathGeometry("M 10,160 L 228,160 228,305 10,305"));
path.setFill(doc.createImageBrush(dataDir +  "R08LN_NN.jpg",
                                new Rectangle2D.Float(0f, 0f, 128f, 96f), new Rectangle2D.Float(0f, 0f, 64f, 48f)));
((XpsImageBrush)path.getFill()).setTileMode(XpsTileMode.Tile);
path.getFill().setOpacity(0.5f);
```

### Passo 5: Salvar o Documento
Persista o arquivo XPS no disco. O arquivo de saída conterá a imagem em mosaico que você acabou de definir.

```java
// Save resultant XPS document
doc.save(dataDir + "AddTiledImage_out.xps"); 
```

Repita estas etapas sempre que precisar **adicionar imagem em mosaico** a outras páginas ou formas dentro do mesmo documento XPS.

## Problemas Comuns e Soluções
| Problema | Solução |
|----------|---------|
| Imagem não aparece | Verifique se o caminho do arquivo (`dataDir + "R08LN_NN.jpg"`) está correto e se a imagem está acessível. |
| Padrão de mosaico aparece esticado | Ajuste os valores de `Rectangle2D` de origem e destino para controlar o tamanho do mosaico. |
| Opacidade não tem efeito | Certifique‑se de que a opacidade do pincel seja definida **depois** da configuração do modo de mosaico. |

## Perguntas Frequentes

### O Aspose.Page é compatível com todas as versões do Java?
O Aspose.Page foi projetado para funcionar com várias versões do Java. Verifique a compatibilidade consultando a documentação [aqui](https://reference.aspose.com/page/java/).

### Posso usar o Aspose.Page em projetos comerciais?
Sim, o Aspose.Page oferece licenças comerciais. Adquira-as [aqui](https://purchase.aspose.com/buy).

### Existe uma versão de avaliação gratuita disponível?
Sim, explore os recursos do Aspose.Page com uma avaliação gratuita [aqui](https://releases.aspose.com/).

### Onde posso encontrar suporte da comunidade e discussões?
Participe da comunidade Aspose.Page no [forum](https://forum.aspose.com/c/page/39).

### Como posso obter uma licença temporária para o Aspose.Page?
Obtenha uma licença temporária [aqui](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2025-12-28  
**Testado com:** Aspose.Page for Java 24.12 (latest)  
**Autor:** Aspose