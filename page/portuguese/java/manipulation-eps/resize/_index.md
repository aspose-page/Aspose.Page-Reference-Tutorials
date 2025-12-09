---
date: 2025-12-02
description: Aprenda a redimensionar arquivos EPS em Java sem esforço com o Aspose.Page.
  Este guia passo a passo mostra como redimensionar EPS usando pontos, polegadas,
  milímetros ou porcentagens.
linktitle: Resize EPS File in Java
second_title: Aspose.Page Java API
title: Como Redimensionar Arquivos EPS em Java com Aspose.Page
url: /pt/java/manipulation-eps/resize/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Redimensionar Arquivos EPS em Java com Aspose.Page

## Introdução
Se você está procurando uma maneira confiável **de redimensionar arquivos EPS** programaticamente, chegou ao lugar certo. Neste tutorial, percorreremos o redimensionamento de imagens EPS em Java usando a biblioteca Aspose.Page. Seja para dobrar o tamanho, reduzir para uma medida específica ou trabalhar com porcentagens, os passos abaixo dão total controle sobre as dimensões de saída.

## Respostas Rápidas
- **Qual biblioteca é necessária?** Aspose.Page for Java  
- **Posso redimensionar usando pontos, polegadas ou milímetros?** Sim – a API suporta as três unidades mais porcentagens.  
- **Preciso de uma licença para desenvolvimento?** Um teste gratuito funciona para testes; uma licença é necessária para produção.  
- **Qual versão do Java é necessária?** Java 8 ou superior.  
- **O código é thread‑safe?** Cada instância de `PsDocument` é isolada, portanto você pode processar arquivos em paralelo.

## Pré‑requisitos
Antes de mergulharmos no código, certifique‑se de que você tem o seguinte:

- Java Development Kit (JDK) instalado na sua máquina.  
- Biblioteca Aspose.Page for Java. Você pode baixá‑la **[aqui](https://releases.aspose.com/page/java/)**.  
- Um entendimento básico de programação Java.  

## Importar Pacotes
No seu projeto Java, inclua as importações necessárias para que você possa trabalhar com objetos Aspose.Page e fluxos de I/O padrão.

```java
import java.awt.Dimension;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.page.DimensionF;
import com.aspose.page.Units;
```

## Como Redimensionar EPS Usando Pontos
Abaixo está um exemplo completo, passo a passo, que dobra o tamanho de um arquivo EPS usando pontos como unidade de medida.

### Passo 1: Configurar o fluxo de entrada
```java
FileInputStream inputEpsStream = new FileInputStream(dataDir + "input.eps");
```

### Passo 2: Inicializar o objeto `PsDocument`
```java
PsDocument doc = new PsDocument(inputEpsStream);
```

### Passo 3: Extrair o tamanho atual da imagem EPS
```java
Dimension oldSize = doc.extractEpsSize();
```

### Passo 4: Criar um fluxo de saída para o arquivo redimensionado
```java
FileOutputStream outputEpsStream = new FileOutputStream(dataDir + "output_resize_points.eps");
```

### Passo 5: Redimensionar e salvar o EPS usando pontos
```java
doc.resizeEps(outputEpsStream, new Dimension2D.Double(oldSize.width * 2, oldSize.height * 2), Units.Points);
```

## Como Redimensionar EPS Usando Polegadas
O mesmo padrão de cinco passos se aplica; basta substituir `Units.Points` por `Units.Inches` e ajustar o fator de escala conforme necessário.

## Como Redimensionar EPS Usando Milímetros
Novamente, siga os mesmos passos, trocando a unidade para `Units.Millimeters`. Isso é útil quando você precisa de dimensões métricas para fluxos de trabalho de impressão.

## Como Redimensionar EPS Usando Porcentagens
Para escala baseada em porcentagem, mantenha a unidade como `Units.Percent`. Multiplique a largura e altura originais pela porcentagem desejada (por exemplo, `0.5` para redução de 50 %).

## Problemas Comuns & Dicas
- **Sempre feche os fluxos** – No código de produção, envolva os fluxos em try‑with‑resources para evitar bloqueios de arquivos.  
- **Preserve a proporção** – Multiplique tanto a largura quanto a altura pelo mesmo fator, a menos que você queira intencionalmente distorção.  
- **Verifique o DPI** – Redimensionar não altera o DPI; se precisar de um DPI diferente, ajuste‑o separadamente após o redimensionamento.

## Conclusão
Agora você sabe **como redimensionar arquivos EPS** em Java usando Aspose.Page, seja qual for a unidade preferida: pontos, polegadas, milímetros ou porcentagens. Essa flexibilidade permite integrar a manipulação de EPS em pipelines automatizados, utilitários de desktop ou serviços do lado do servidor.

## Perguntas Frequentes

**Q: Posso usar esta biblioteca para outros formatos de imagem?**  
A: Não, Aspose.Page é especializado apenas para arquivos PostScript e EPS.

**Q: Existe uma versão de teste gratuita disponível para Aspose.Page for Java?**  
A: Sim, você pode explorar a versão de teste gratuita **[aqui](https://releases.aspose.com/)**.

**Q: Onde posso encontrar ajuda adicional e discussões?**  
A: Visite o **[fórum Aspose.Page](https://forum.aspose.com/c/page/39)** para suporte da comunidade.

**Q: Como posso obter uma licença temporária?**  
A: Você pode obter uma licença temporária **[aqui](https://purchase.aspose.com/temporary-license/)**.

**Q: Existem projetos de exemplo disponíveis?**  
A: Sim, confira a documentação **[aqui](https://reference.aspose.com/page/java/)**.

---

**Última Atualização:** 2025-12-02  
**Testado com:** Aspose.Page for Java 24.12 (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}