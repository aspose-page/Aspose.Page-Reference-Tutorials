---
date: 2026-01-12
description: Aprenda como modificar documentos XPS usando o Aspose.Page para .NET
  e descubra como adicionar texto a arquivos XPS com exemplos de código simples.
linktitle: Modify XPS Document
second_title: Aspose.Page .NET API
title: Modificar documento XPS com Aspose.Page para .NET
url: /pt/net/document-creation/modify-xps-document/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Modificar Documento XPS com Aspose.Page para .NET

## Introdução

Bem‑vindo ao nosso guia passo a passo sobre **como modificar documentos xps** com Aspose.Page para .NET. Seja para inserir uma assinatura, adicionar uma marca d'água ou simplesmente colocar texto personalizado em uma página, este tutorial mostra exatamente **como adicionar texto** a um documento XPS em poucos minutos. Vamos percorrer cada linha de código, explicar por que cada passo é importante e dar dicas para evitar armadilhas comuns.

### Respostas Rápidas
- **O que este tutorial cobre?** Adicionar um texto de assinatura ("Confirmed") às páginas selecionadas de um arquivo XPS.  
- **Qual biblioteca é necessária?** Aspose.Page para .NET (versão mais recente).  
- **Preciso de licença?** Uma licença temporária funciona para testes; uma licença completa é necessária para produção.  
- **Quais versões do .NET são suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Quanto tempo leva a implementação?** Cerca de 10 minutos para uma inserção básica de assinatura.

## O que é modificar um documento XPS?

XPS (XML Paper Specification) é o formato de documento de layout fixo da Microsoft, semelhante ao PDF. Modificar um documento XPS significa alterar programaticamente seu conteúdo visual — adicionando texto, imagens ou formas — sem converter o arquivo para outro formato. Aspose.Page fornece um modelo de objetos rico que permite editar arquivos XPS diretamente a partir do seu código .NET.

## Por que usar Aspose.Page para modificar documentos XPS?

* **Controle total** – trabalhe com páginas, glifos, pincéis e transformações em nível baixo.  
* **Sem dependências externas** – biblioteca pura .NET, sem necessidade de componentes Office ou Adobe.  
* **Multiplataforma** – funciona em Windows, Linux e macOS via .NET Core.  
* **Desempenho robusto** – manipula documentos grandes de forma eficiente e suporta tipografia avançada.

## Pré-requisitos

Antes de começar, certifique‑se de que você tem o seguinte:

- **Aspose.Page para .NET** – Instale o pacote NuGet ou faça o download da biblioteca a partir da documentação oficial **[aqui](https://reference.aspose.com/page/net/)**.  
- **Arquivo XPS de entrada** – Obtenha um documento XPS de exemplo (por exemplo, `input1.xps`) a partir da **[página de releases da Aspose](https://releases.aspose.com/page/net/)**.  
- **Diretório de trabalho** – Crie uma pasta na sua máquina para armazenar os arquivos de entrada e saída e anote seu caminho completo; você atribuirá esse caminho à variável `dir` no código.  
- **Ambiente de desenvolvimento** – Visual Studio 2019/2022, .NET Framework 4.7.2 ou posterior, ou qualquer projeto .NET Core/5/6.

Agora que tudo está configurado, vamos mergulhar no código.

## Importar Namespaces

No seu projeto .NET, comece importando os namespaces necessários para Aspose.Page:

```csharp
using Aspose.Page.XPS;
using Aspose.Page.XPS.XpsModel;
using System.Drawing;
using System.IO;
```

## Etapa 1: Abrir Fluxo do Documento XPS

Abriremos o arquivo XPS de origem como um fluxo e criaremos um objeto `XpsDocument` que representa todo o documento.

```csharp
// ExStart:3
// The path to the documents directory.
string dir = "Your Document Directory";
// Open a stream of XPS file
using (FileStream xpsStream = File.Open(dir + "input1.xps", FileMode.Open, FileAccess.Read))
{
    // Create PS document from stream
    XpsDocument document = new XpsDocument(xpsStream, new XpsLoadOptions());
    // Continue to the next step...
}
// ExEnd:3
```

*Dica:* Envolva o fluxo em um bloco `using` para garantir que o manipulador de arquivo seja liberado automaticamente.

## Etapa 2: Criar Texto da Assinatura

Em seguida, criamos um pincel de cor sólida que será usado para pintar os glifos da assinatura.

```csharp
// ExStart:4
// Create fill of the signature text
XpsSolidColorBrush textFill = document.CreateSolidColorBrush(Color.BlueViolet);
// Continue to the next step...
// ExEnd:4
```

Você pode mudar `Color.BlueViolet` para qualquer `System.Drawing.Color` que corresponda à sua identidade visual.

## Etapa 3: Definir Páginas e Adicionar Assinatura

Especificaremos quais páginas devem receber a assinatura e então adicionaremos os glifos a cada página.

```csharp
// ExStart:5
// Define pages where signature will be set
int[] pageNumbers = new int[] {1, 2, 3};

// For every defined page set signature "Confirmed" at coordinates x=650 and y=950
for (int i = 0; i < pageNumbers.Length; i++)
{
    // Define active page
    document.SelectActivePage(pageNumbers[i]);

    // Create glyphs object
    XpsGlyphs glyphs = document.AddGlyphs("Arial", 24, FontStyle.Bold, 650, 900, "Confirmed");

    // Define fill for glyphs
    glyphs.Fill = textFill;
}
// Continue to the next step...
// ExEnd:5
```

*Por que essas coordenadas?* Os valores de X e Y são medidos em pontos (1/72 polegada). Ajuste‑os para posicionar o texto exatamente onde precisar no layout da sua página.

## Etapa 4: Salvar Alterações no Documento XPS

Finalmente, gravamos o documento modificado de volta ao disco.

```csharp
// ExStart:6
// Save changed XPS document
document.Save(dir + "input1_out.xps");
// ExEnd:6
```

O novo arquivo `input1_out.xps` agora contém a assinatura “Confirmed” nas páginas 1‑3.

## Problemas Comuns e Soluções

| Problema | Causa | Solução |
|----------|-------|----------|
| **Assinatura não visível** | Coordenadas erradas ou página não selecionada | Verifique se `SelectActivePage` é chamado para cada página e ajuste os valores de X/Y. |
| **Exceção em `AddGlyphs`** | Fonte não instalada no servidor | Garanta que a fonte especificada (por exemplo, Arial) esteja disponível, ou incorpore uma fonte personalizada usando `document.AddFont`. |
| **Arquivo de saída corrompido** | Fluxo não fechado corretamente | Use instruções `using` para todos os fluxos e chame `document.Dispose()` se necessário. |
| **Desaceleração de desempenho em arquivos grandes** | Carregamento de todo o documento na memória | Processar páginas em lotes ou usar `XpsLoadOptions` com opções de streaming (se disponível em versões mais recentes). |

## Perguntas Frequentes

**Q: O Aspose.Page é compatível com os frameworks .NET mais recentes?**  
A: Sim, o Aspose.Page é atualizado regularmente para suportar .NET Framework 4.5+, .NET Core 3.1+, .NET 5 e .NET 6.

**Q: Posso personalizar a fonte e o estilo do texto adicionado?**  
A: Absolutamente. Altere os parâmetros de `AddGlyphs` (nome da fonte, tamanho, `FontStyle`) conforme o seu design.

**Q: Existem limites de tamanho para arquivos XPS?**  
A: O Aspose.Page pode lidar com documentos grandes, mas o consumo de memória cresce com o tamanho do arquivo. Para arquivos muito grandes, considere processar as páginas individualmente.

**Q: Como obtenho uma licença temporária para o Aspose.Page?**  
A: Você pode adquirir uma licença temporária **[aqui](https://purchase.aspose.com/temporary-license/)**.

**Q: Onde posso buscar ajuda ou conectar‑me com a comunidade Aspose?**  
A: Visite o **[fórum Aspose.Page](https://forum.aspose.com/c/page/39)** para fazer perguntas e compartilhar experiências.

## Conclusão

Neste tutorial demonstramos como **modificar documentos xps** adicionando texto de assinatura personalizado usando Aspose.Page para .NET. Agora você tem uma base sólida para inserir qualquer texto, marca d'água ou anotação em páginas específicas de um arquivo XPS. Experimente diferentes fontes, cores e posições para atender aos requisitos de identidade da sua aplicação e explore a API mais ampla do Aspose.Page para recursos avançados de gráficos e layout.

---

**Última atualização:** 2026-01-12  
**Testado com:** Aspose.Page 24.11 para .NET (mais recente no momento da escrita)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}