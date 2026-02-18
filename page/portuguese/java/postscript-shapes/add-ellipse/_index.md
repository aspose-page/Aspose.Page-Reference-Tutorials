---
date: 2026-02-18
description: Aprenda como definir a cor da pintura e criar uma elipse PostScript em
  Java usando Aspose.Page. Este guia mostra como preencher a elipse em Java, desenhar
  o contorno da elipse e definir a espessura do traço.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Definir cor de pintura para desenhar elipse PostScript em Java
url: /pt/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Definir cor de pintura para desenhar elipse PostScript em Java

## Introdução
Se você precisar **definir cor de pintura** ao desenhar gráficos vetoriais, a biblioteca Aspose.Page for Java oferece controle total sobre cada traço e preenchimento. Neste tutorial você descobrirá como **definir cor de pintura**, **preencher elipse Java** e **desenhar contorno de elipse** usando uma abordagem simples, passo a passo. Ao final, você poderá adicionar elipses PostScript de alta qualidade a faturas, relatórios ou qualquer documento imprimível.

## Respostas Rápidas
- **Qual biblioteca é a melhor para desenhar gráficos PostScript em Java?** Aspose.Page for Java.  
- **Posso preencher uma elipse com uma cor sólida?** Sim – use `document.setPaint(Color.YOUR_COLOR)` antes de `fill`.  
- **Como desenho apenas o contorno de uma elipse?** Defina a cor de pintura e o traço, então chame `document.draw(...)`.  
- **Preciso de licença para uso em produção?** É necessária uma licença comercial; uma licença temporária está disponível para testes.  
- **Qual versão do Java é suportada?** Qualquer runtime Java 8+ funciona com a versão atual do Aspose.Page.

## O que é uma elipse PostScript?
Uma elipse PostScript é uma forma vetorial definida por um retângulo delimitador. Ao contrário de imagens raster, ela escala sem perda de qualidade, tornando‑a ideal para impressão de alta resolução e conversão para PDF.

## Por que usar Aspose.Page para criar uma elipse PostScript?
- **Controle total** sobre primitivas de desenho (linhas, curvas, elipses).  
- **Multiplataforma** – funciona no Windows, Linux e macOS.  
- **Sem dependências externas** – API Java pura, sem código nativo.  
- **Integração fácil** com aplicações Java existentes e ferramentas de build.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. Um ambiente de desenvolvimento Java funcional (JDK 8 ou posterior).  
2. A biblioteca Aspose.Page for Java adicionada ao seu projeto. Você pode baixá‑la **[aqui](https://releases.aspose.com/page/java/)**.  

## Importar Pacotes
No seu arquivo fonte Java, importe as classes necessárias para desenhar e salvar conteúdo PostScript.

```java
import java.awt.BasicStroke;
import java.awt.Color;
import java.awt.geom.Ellipse2D;
import java.io.FileOutputStream;
import com.aspose.eps.PsDocument;
import com.aspose.eps.device.PsSaveOptions;
```

## Como definir a cor de pintura para uma elipse
Definir a cor de pintura é o primeiro passo antes de qualquer operação de preenchimento ou traço. O método `setPaint` determina a cor que será usada para o próximo comando de desenho.

### Passo 1: Configurar o documento PostScript
Crie um fluxo de saída, configure o tamanho da página e instancie um `PsDocument`.

```java
// The path to the documents directory.
String dataDir = "Your Document Directory";
// Create output stream for PostScript document
FileOutputStream outPsStream = new FileOutputStream(dataDir + "AddEllipse_outPS.ps");
// Create save options with A4 size
PsSaveOptions options = new PsSaveOptions();
// Create new PS Document with the page opened
PsDocument document = new PsDocument(outPsStream, options, false);
```

### Passo 2: Como preencher a elipse – use set paint color
Para **preencher a elipse**, você deve primeiro chamar `setPaint` com a cor de preenchimento desejada, então invocar `fill` com uma instância `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Passo 3: Desenhar contorno da elipse e definir espessura do traço
Após o preenchimento, você pode mudar a cor de pintura para outra, definir um `BasicStroke` para controlar a largura da linha e desenhar o contorno da elipse.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Passo 4: Fechar e salvar o documento
Finalize a página e escreva o arquivo PostScript no disco.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Agora você tem um arquivo PostScript que contém duas elipses — uma preenchida com laranja e outra com contorno em vermelho. Sinta‑se à vontade para experimentar diferentes coordenadas, tamanhos e cores para atender às necessidades do seu design.

## Problemas comuns e solução de problemas
- **Caminho de arquivo incorreto** – Certifique‑se de que `dataDir` termina com um separador (`/` ou `\\`) apropriado para o seu SO.  
- **Licença ausente** – Sem uma licença válida, a biblioteca funciona em modo de avaliação e pode adicionar marcas d'água.  
- **Cor não aplicada** – Lembre‑se de definir `document.setPaint(...)` *antes* de cada chamada `fill` ou `draw`; a configuração de pintura não persiste automaticamente entre operações distintas.

## Perguntas Frequentes

**Q: Posso usar Aspose.Page for Java com outras bibliotecas Java?**  
A: Sim, Aspose.Page for Java foi projetado para integrar‑se perfeitamente com outras bibliotecas Java.

**Q: Como posso obter uma licença temporária para Aspose.Page for Java?**  
A: Obtenha uma licença temporária **[aqui](https://purchase.aspose.com/temporary-license/)** para fins de teste.

**Q: O Aspose.Page é adequado para projetos comerciais?**  
A: Absolutamente! Visite **[aqui](https://purchase.aspose.com/buy)** para explorar opções de licenciamento para uso comercial.

**Q: Onde posso buscar ajuda ou discutir dúvidas relacionadas ao Aspose.Page?**  
A: Junte‑se à comunidade no **[Aspose.Page Forum](https://forum.aspose.com/c/page/39)** para discussões e assistência.

**Q: Existem recursos gratuitos para aprender mais sobre Aspose.Page for Java?**  
A: Utilize o **[teste gratuito](https://releases.aspose.com/)** e explore exemplos na documentação.

## Conclusão
Aspose.Page for Java torna simples **definir cor de pintura**, **preencher elipse** e **desenhar contorno de elipse** — seja você precisar de uma forma preenchida simples ou de um gráfico complexo com traço. Com os passos acima, você pode rapidamente adicionar gráficos vetoriais de nível profissional a qualquer documento imprimível. Para uma exploração mais aprofundada — como combinar múltiplas formas, aplicar gradientes ou converter para PDF — consulte a **[documentação](https://reference.aspose.com/page/java/)** oficial.

---

**Última atualização:** 2026-02-18  
**Testado com:** Aspose.Page for Java 24.11  
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}