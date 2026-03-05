---
date: 2025-12-28
description: Aprenda como adicionar imagens a documentos XPS em Java usando Aspose.Page.
  Este guia passo a passo mostra como inserir imagens de forma simples e aprimorar
  o processamento de documentos.
linktitle: Add Image in Java XPS
second_title: Aspose.Page Java API
title: Como adicionar imagem a documentos XPS em Java – Um guia simples com Aspose.Page
url: /pt/java/xps-image-manipulation/add-image/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Adicionar Imagem a Documentos XPS Java com Aspose.Page

Adicionar imagens a arquivos XPS é uma necessidade comum para desenvolvedores Java que necessitam de relatórios, faturas ou qualquer documento visual. Neste tutorial você descobrirá **como adicionar imagem** a um documento XPS usando a poderosa biblioteca Aspose.Page for Java. Vamos percorrer cada passo, explicar por que cada linha é importante e oferecer dicas para evitar armadilhas típicas.

## Respostas rápidas
- **Qual biblioteca é necessária?** Aspose.Page para Java
- **Posso adicionar várias imagens?** Sim – repita as etapas de adição de imagens para cada imagem
- **Formatos de imagem suportados?** TIFF, JPEG, PNG, GIF (e outros suportados pelo .NET)
- **Preciso de uma licença?** Uma avaliação gratuita funciona para avaliação; uma licença comercial é necessária para a produção
- **Tempo típico de implementação?** Cerca de 10 a 15 minutos para uma inserção básica de imagem

## Introdução
Adicionar imagens a documentos XPS é uma necessidade comum em muitas aplicações Java, desde a geração de relatórios até o processamento de documentos. Aspose.Page for Java simplifica essa tarefa, oferecendo métodos eficientes para integrar imagens aos seus arquivos XPS de forma transparente. Neste tutorial, demonstraremos como adicionar uma imagem a um documento XPS usando Aspose.Page for Java.

## Pré-requisitos
Antes de iniciar o tutorial, certifique-se de que você possui os seguintes pré-requisitos:
1. **Biblioteca Aspose.Page for Java** – Baixe e instale a biblioteca Aspose.Page for Java no [website](https://releases.aspose.com/page/java/).
2. **Java Development Environment** – Garanta que você tenha um ambiente de desenvolvimento Java configurado em sua máquina.

Agora, vamos para os próximos passos.

## Importar pacotes
Em seu projeto Java, importe os pacotes necessários do Aspose.Page for Java para acessar as classes e métodos necessários.

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
import java.awt.geom.Rectangle2D;
```

## Etapa 1: configurar o diretório de documentos
Defina o caminho para o diretório onde o documento XPS e os arquivos de imagem serão armazenados.

```java
String dataDir = "Your Document Directory";
```

## Etapa 2: Crie um novo documento XPS
Inicialize um novo documento XPS usando o trecho de código a seguir:

```java
XpsDocument doc = new XpsDocument();
```

## Etapa 3: Adicionar imagem ao documento XPS
Para adicionar uma imagem, crie um caminho no documento XPS e defina o pincel de imagem usando o arquivo de imagem fornecido e as coordenadas.

```java
XpsPath path = doc.addPath(doc.createPathGeometry("M 30,20 l 258.24,0 0,56.64 -258.24,0 Z"));
path.setRenderTransform(doc.createMatrix(0.7f, 0f, 0f, 0.7f, 0f, 20f));
path.setFill(doc.createImageBrush(dataDir + "QL_logo_color.tif", new Rectangle2D.Double(0f, 0f, 258.24f, 56.64f), new Rectangle2D.Double(50f, 20f, 193.68f, 42.48f)));
```

## Etapa 4: Salvar o documento XPS resultante
Salve o documento XPS modificado no diretório especificado.

```java
doc.save(dataDir + "AddImage_out.xps");
```

Repita estas etapas para adicionar mais imagens ou personalizar as existentes de acordo com os requisitos do seu projeto.

## Conclusão
Parabéns! Você aprendeu com sucesso **como adicionar imagem** a um documento XPS usando Aspose.Page for Java. Essa habilidade é útil para melhorar o apelo visual de suas aplicações e documentos Java.

### Perguntas frequentes
### Posso adicionar várias imagens ao mesmo documento XPS usando Aspose.Page for Java?
Sim, você pode adicionar várias imagens repetindo as etapas descritas neste tutorial para cada imagem.

### Quais formatos de imagem são suportados pelo Aspose.Page for Java?
Aspose.Page for Java suporta diversos formatos de imagem, incluindo TIFF, JPEG, PNG e GIF.

### Existe uma versão de teste do Aspose.Page para Java disponível?
Sim, você pode obter uma versão de avaliação gratuita do Aspose.Page for Java através deste [link](https://releases.aspose.com/).

### Como posso obter uma licença temporária para Aspose.Page for Java?
Você pode obter uma licença temporária neste [link](https://purchase.aspose.com/temporary-license/).

### Onde posso encontrar suporte adicional ou discutir questões relacionadas ao Aspose.Page for Java?
Visite o [fórum Aspose.Page](https://forum.aspose.com/c/page/39) para obter ajuda, compartilhar experiências e conectar-se com a comunidade Aspose.Page.

## Dicas adicionais e armadilhas comuns
- **Precisão da geometria do caminho** – Certifique-se de que a string de caminho no estilo SVG corresponde às dimensões de sua imagem; Caso contrário, a imagem pode aparecer esticada ou cortada.
- **Image Brush Scaling** – O método `createImageBrush` recebe especificados de origem e destino; ajustar esses valores permite controlar posicionamento e dimensionamento com precisão.
- **Ativação de licença** – Se você executar o código sem uma licença válida, o Aspose adicionará uma marca d'água ao arquivo XPS gerado.

---

**Última atualização:** 28/12/2025
**Testado com:** Aspose.Page para Java 23.12 (mais recente no momento da escrita)
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}