---
date: 2025-12-30
description: Aprenda como criar documentos XPS em Java adicionando retângulos usando
  Aspose.Page. Siga este guia passo a passo para manipulação perfeita de documentos
  XPS.
linktitle: Create XPS Document Java – Add Rectangle
second_title: Aspose.Page Java API
title: Criar Documento XPS em Java – Adicionar Retângulo com Aspose.Page
url: /pt/java/xps-shapes/add-rectangle/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Criar Documento XPS Java – Adicionar Retângulo

## Introdução
Neste tutorial abrangente você **criará documentos XPS Java** e aprenderá como adicionar retângulos usando a biblioteca Aspose.Page. Seja criando relatórios, faturas ou gráficos personalizados, dominar a criação de retângulos oferece controle preciso sobre o layout XPS. Percorreremos cada passo, explicaremos o porquê de cada linha de código e mostraremos como personalizar cores e traçados para resultados profissionais.

## Respostas Rápidas
- **Qual biblioteca é recomendada?** Aspose.Page for Java  
- **Quanto tempo leva a implementação?** Cerca de 10 minutos para um retângulo básico  
- **Preciso de licença?** Uma avaliação gratuita funciona para desenvolvimento; uma licença comercial é necessária para produção  
- **Qual versão do Java é suportada?** Java 8 e posteriores  
- **Posso adicionar múltiplas formas?** Sim – repita os passos para cada forma

## Pré‑requisitos
Antes de começarmos, certifique‑se de que você tem:

- Conhecimento básico da linguagem de programação Java.  
- Biblioteca Aspose.Page instalada. Caso não tenha, você pode baixá‑la na [documentação do Aspose.Page Java](https://reference.aspose.com/page/java/).  
- Um ambiente de desenvolvimento Java funcional (IDE, JDK e Maven/Gradle, se preferir).

## Importar Pacotes
Para iniciar, importe os pacotes necessários ao seu projeto Java. Garanta que a biblioteca Aspose.Page esteja corretamente adicionada ao seu classpath. Aqui está um exemplo básico:

```java
import com.aspose.xps.XpsDocument;
import com.aspose.xps.XpsPath;
```

Agora, vamos dividir o exemplo fornecido em várias etapas para adicionar um retângulo em Java XPS.

## Etapa 1: Definir o Diretório do Documento
```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
```

Substitua `"Your Document Directory"` pelo caminho da pasta onde você deseja armazenar os arquivos XPS.

## Etapa 2: Criar um Novo Documento XPS
```java
// Create new XPS Document
XpsDocument doc = new XpsDocument();
```

Esta linha **cria** um novo documento XPS que você pode posteriormente preencher com formas, texto ou imagens.

## Etapa 3: Adicionar um Retângulo Contornado com Cor Sólida CMYK
```java
// CMYK (blue) solid color stroked rectangle in the lower left
XpsPath path = doc.addPath(doc.createPathGeometry("M 20,10 L 220,10 220,100 20,100 Z"));
path.setStroke(doc.createSolidColorBrush(
    doc.createColor(dataDir + "uswebuncoated.icc", 1.0f, 1.000f, 0.000f, 0.000f, 0.000f)));
path.setStrokeThickness(12f);
```

Esta etapa adiciona um retângulo contornado com uma cor sólida CMYK. Você pode alterar a string de geometria (`"M 20,10 L 220,10 220,100 20,100 Z"`) para modificar tamanho ou posição, e ajustar os valores de cor em `createColor` conforme seu design.

## Etapa 4: Salvar o Documento XPS Resultante
```java
// Save resultant XPS document
doc.save(dataDir + "AddRectangle_out.xps");
```

Por fim, salve o documento XPS modificado com o retângulo adicionado no diretório especificado anteriormente.

## Casos de Uso Comuns
- **Cabeçalhos de relatório** – Use retângulos como blocos de fundo para títulos.  
- **Tabelas de fatura** – Destaque células ou seções com bordas coloridas.  
- **Gráficos personalizados** – Combine múltiplos retângulos para criar formas complexas.

## Dicas de Solução de Problemas
- **Erro de arquivo não encontrado:** Verifique se `dataDir` aponta para uma pasta existente e se o perfil ICC (`uswebuncoated.icc`) está presente.  
- **Cores incorretas:** Certifique‑se de que o perfil ICC corresponde ao espaço de cor que você pretende usar (CMYK vs. RGB).  
- **Dimensões inesperadas:** Ajuste a string de geometria para refletir as coordenadas corretas.

## Conclusão
Parabéns! Você aprendeu com sucesso a **criar documentos XPS Java** e a adicionar retângulos usando Aspose.Page. Essa base permite que você construa documentos XPS mais ricos, personalize gráficos e integre formas em fluxos de trabalho maiores.

## Perguntas Frequentes
### Posso adicionar múltiplos retângulos em um único documento XPS?
Sim, você pode adicionar quantos retângulos precisar repetindo os passos descritos no tutorial.

### Como posso mudar a cor do retângulo?
Modifique os valores de cor no método `createColor` para obter a cor desejada.

### O Aspose.Page é adequado para manipulações complexas de documentos XPS?
Absolutamente! O Aspose.Page oferece um conjunto robusto de recursos para lidar com diversas tarefas em documentos XPS.

### Onde posso encontrar exemplos adicionais e suporte?
Explore o [fórum do Aspose.Page](https://forum.aspose.com/c/page/39) para mais exemplos e procure ajuda na comunidade.

### Posso experimentar o Aspose.Page antes de comprar?
Sim, você pode experimentar um [teste gratuito](https://releases.aspose.com/) para conhecer as capacidades do Aspose.Page.

## Perguntas Frequentes

**P: Essa abordagem funciona com Java 11 ou versões mais recentes?**  
R: Sim, a biblioteca Aspose.Page é compatível com Java 8 e posteriores, incluindo Java 11, 17 e versões superiores.

**P: Posso incorporar imagens dentro da área do retângulo?**  
R: Você pode adicionar um elemento `XpsImage` e posicioná‑lo sobre ou dentro do retângulo usando as mesmas coordenadas de geometria.

**P: Como definir uma cor de preenchimento em vez de apenas o traçado?**  
R: Chame `path.setFill(...)` com um pincel de cor sólida criado via `doc.createSolidColorBrush(...)`.

**P: É possível girar o retângulo?**  
R: Aplique uma matriz de transformação ao caminho usando `path.setTransform(...)` para conseguir rotação ou escala.

**P: Qual licença é necessária para uso em produção?**  
R: Uma licença comercial do Aspose.Page é necessária para implantação; o teste gratuito é limitado a avaliação e desenvolvimento.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2025-12-30  
**Testado com:** Aspose.Page for Java 24.12 (mais recente)  
**Autor:** Aspose  

---