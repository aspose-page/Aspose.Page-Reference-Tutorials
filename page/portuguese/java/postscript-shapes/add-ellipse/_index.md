---
date: 2025-12-11
description: Aprenda a criar elipses em PostScript usando Java com Aspose.Page. Este
  guia passo a passo mostra como preencher a elipse com cor e desenhar a elipse usando
  Java.
linktitle: Add Ellipse in Java PostScript
second_title: Aspose.Page Java API
title: Como criar elipse PostScript em Java com Aspose.Page
url: /pt/java/postscript-shapes/add-ellipse/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como criar elipse PostScript em Java com Aspose.Page

## Introdução
Criar uma **elipse PostScript** programaticamente oferece controle detalhado sobre gráficos vetoriais em relatórios, faturas ou qualquer documento imprimível. Neste tutorial você aprenderá a **criar elipses PostScript** usando a biblioteca Aspose.Page para Java, preencher uma elipse com cor e desenhar o contorno de uma elipse. Ao final, você estará pronto para incorporar gráficos personalizados diretamente na saída PostScript.

## Respostas rápidas
- **Qual biblioteca é a melhor para desenhar gráficos PostScript em Java?** Aspose.Page para Java.  
- **Posso preencher uma elipse com uma cor sólida?** Sim – use `document.setPaint(Color.SUA_COR)` antes de `fill`.  
- **Como desenho apenas o contorno de uma elipse?** Defina a pintura e o traço, então chame `document.draw(...)`.  
- **Preciso de licença para uso em produção?** Uma licença comercial é necessária; uma licença temporária está disponível para testes.  
- **Qual versão do Java é suportada?** Qualquer runtime Java 8+ funciona com a versão atual do Aspose.Page.

## O que é uma elipse PostScript?
Uma elipse PostScript é uma forma vetorial definida por um retângulo delimitador. Ao contrário de imagens raster, ela escala sem perda de qualidade, tornando‑a ideal para impressão de alta resolução e conversão para PDF.

## Por que usar Aspose.Page para criar uma elipse PostScript?
- **Controle total** sobre primitivas de desenho (linhas, curvas, elipses).  
- **Multiplataforma** – funciona no Windows, Linux e macOS.  
- **Sem dependências externas** – API pura em Java, sem código nativo.  
- **Integração fácil** com aplicações Java existentes e ferramentas de build.

## Pré‑requisitos
Antes de começar, certifique‑se de que você tem:

1. Um ambiente de desenvolvimento Java funcional (JDK 8 ou superior).  
2. A biblioteca Aspose.Page para Java adicionada ao seu projeto. Você pode baixá‑la **[aqui](https://releases.aspose.com/page/java/)**.  

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

## Guia passo a passo

### Etapa 1: Configurar o documento PostScript
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

### Etapa 2: Preencher a elipse com cor
Defina a pintura para a cor de preenchimento desejada e chame `fill` com uma instância `Ellipse2D`.

```java
// Set paint for filling ellipse
document.setPaint(Color.ORANGE);
// Fill the first ellipse
document.fill(new Ellipse2D.Float(250, 100, 150, 100));
```

### Etapa 3: Contornar a elipse com traço
Altere a pintura para a cor do traço, defina um `BasicStroke` para a espessura da linha e desenhe o contorno da elipse.

```java
// Set paint for stroking ellipse
document.setPaint(Color.RED);
// Set stroke
document.setStroke(new BasicStroke(3));
// Stroke (outline) the second ellipse
document.draw(new Ellipse2D.Float(250, 300, 150, 100));
```

### Etapa 4: Fechar e salvar o documento
Finalize a página e grave o arquivo PostScript no disco.

```java
// Close current page
document.closePage();
// Save the document
document.save();
```

Agora você tem um arquivo PostScript que contém duas elipses — uma preenchida com laranja e outra contornada em vermelho. Sinta‑se à vontade para experimentar diferentes coordenadas, tamanhos e cores para atender às necessidades do seu design.

## Armadilhas comuns e solução de problemas
- **Caminho de arquivo incorreto** – Certifique‑se de que `dataDir` termina com um separador (`/` ou `\\`) adequado ao seu SO.  
- **Licença ausente** – Sem uma licença válida, a biblioteca funciona em modo de avaliação e pode adicionar marcas d’água.  
- **Cor não aplicada** – Lembre‑se de definir `document.setPaint(...)` *antes* de cada chamada `fill` ou `draw`; a configuração de pintura não persiste entre operações separadas automaticamente.

## Perguntas Frequentes

**P: Posso usar Aspose.Page para Java com outras bibliotecas Java?**  
R: Sim, Aspose.Page para Java foi projetado para integrar‑se perfeitamente com outras bibliotecas Java.

**P: Como obtenho uma licença temporária para Aspose.Page para Java?**  
R: Obtenha uma licença temporária **[aqui](https://purchase.aspose.com/temporary-license/)** para fins de teste.

**P: O Aspose.Page é adequado para projetos comerciais?**  
R: Absolutamente! Visite **[aqui](https://purchase.aspose.com/buy)** para explorar opções de licenciamento para uso comercial.

**P: Onde posso buscar ajuda ou discutir dúvidas relacionadas ao Aspose.Page?**  
R: Junte‑se à comunidade no **[Fórum Aspose.Page](https://forum.aspose.com/c/page/39)** para discussões e assistência.

**P: Existem recursos gratuitos para aprender mais sobre Aspose.Page para Java?**  
R: Utilize o **[teste gratuito](https://releases.aspose.com/)** e explore exemplos na documentação.

## Conclusão
Aspose.Page para Java facilita a **criação de elipses PostScript**, seja você precisar de uma forma simples preenchida ou de um contorno complexo. Com os passos acima, você pode rapidamente adicionar gráficos vetoriais de nível profissional a qualquer documento imprimível. Para exploração mais aprofundada — como combinar múltiplas formas, aplicar gradientes ou converter para PDF — consulte a **[documentação oficial](https://reference.aspose.com/page/java/)**.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Última atualização:** 2025-12-11  
**Testado com:** Aspose.Page para Java 24.11  
**Autor:** Aspose