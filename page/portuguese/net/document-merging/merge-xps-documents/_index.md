---
date: 2026-01-15
description: Aprenda a mesclar documentos XPS usando o Aspose.Page para .NET – um
  guia passo a passo para mesclagem de documentos sem interrupções.
linktitle: Merge XPS Documents
second_title: Aspose.Page .NET API
title: Como mesclar documentos XPS com Aspose.Page para .NET
url: /pt/net/document-merging/merge-xps-documents/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Como Mesclar Documentos XPS com Aspose.Page para .NET

## Introdução

Você está procurando uma maneira confiável **de mesclar arquivos XPS** programaticamente? Neste tutorial, vamos guiá‑lo passo a passo para mesclar documentos XPS usando Aspose.Page para .NET. Seja para combinar relatórios, faturas ou quaisquer outros recursos baseados em XPS, o processo é simples e totalmente automatizado. Vamos mergulhar e ver como você pode obter um XPS mesclado e limpo com apenas algumas linhas de código C#.

## Respostas Rápidas
- **Qual biblioteca lida com a mesclagem de XPS?** Aspose.Page for .NET  
- **Quanto tempo leva a implementação?** Normalmente menos de 10 minutos  
- **Preciso de licença?** É necessária uma licença para uso em produção; uma versão de avaliação gratuita está disponível  
- **Versões .NET suportadas?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Posso mesclar arquivos XPS criptografados?** Sim – Aspose.Page pode lidar com documentos criptografados

## O que é a Mesclagem de Documentos XPS?
XPS (XML Paper Specification) é um formato de documento de layout fixo criado pela Microsoft. Mesclar arquivos XPS significa concatenar vários documentos XPS em um único arquivo contínuo, preservando o layout original, fontes e gráficos.

## Por que Usar Aspose.Page para .NET?
- **Controle total** sobre o processo de mesclagem sem precisar do Microsoft XPS Viewer  
- **Sem dependências externas** – tudo roda dentro da sua aplicação .NET  
- **Alto desempenho** – funciona de forma eficiente mesmo com documentos grandes  
- **Multiplataforma** – compatível com .NET Framework, .NET Core e .NET 5+

## Pré‑requisitos

Antes de começar, certifique‑se de que você tem:

- Um entendimento básico de C# e do ecossistema .NET.  
- **Aspose.Page for .NET** instalado – você pode baixá‑lo [aqui](https://releases.aspose.com/page/net/).  
- Um ou mais arquivos XPS que você deseja combinar.

## Importar Namespaces

No seu projeto C#, importe o namespace que fornece acesso à API XPS:

```csharp
using Aspose.Page.XPS;
```

## Etapa 1: Configurar Seu Projeto

Crie um novo projeto de console ou biblioteca C# no Visual Studio, Rider ou na sua IDE preferida. Adicione uma referência ao DLL Aspose.Page (ou instale o pacote NuGet `Aspose.Page`). Isso lhe dá acesso à classe `XpsDocument` usada posteriormente.

## Etapa 2: Inicializar Streams

Abra os arquivos XPS de origem como streams de entrada e crie um stream de saída para o documento mesclado. As instruções `using` garantem que todos os streams sejam corretamente fechados após a operação.

```csharp
// The path to the documents directory.
string dataDir = "Your Document Directory";

// Initialize XPS output stream
using (System.IO.Stream outStream = System.IO.File.Open(dataDir + "mergedXPSfiles.xps", System.IO.FileMode.OpenOrCreate, System.IO.FileAccess.Write))
// Initialize XPS input stream
using (System.IO.Stream inStream = System.IO.File.Open(dataDir + "input.xps", System.IO.FileMode.Open))
```

## Etapa 3: Carregar Documento XPS

Crie uma instância `XpsDocument` a partir do stream de entrada principal. O objeto `XpsLoadOptions` permite personalizar o comportamento de carregamento, se necessário.

```csharp
XpsDocument document = new XpsDocument(inStream, new XpsLoadOptions());
```

## Etapa 4: Criar um Array de Arquivos XPS

Prepare um array de strings que lista cada arquivo XPS que você deseja mesclar. A ordem do array determina a ordem no documento final.

```csharp
string[] filesToMerge = new string[] { dataDir + "Demo.xps", dataDir + "sample.xps" };
```

## Etapa 5: Mesclar Arquivos XPS

Chame o método `Merge`, passando o array de caminhos de arquivos e o stream de saída. Aspose.Page cuida de todo o trabalho pesado — combinando páginas, preservando recursos e gravando o arquivo XPS final.

```csharp
document.Merge(filesToMerge, outStream);
```

## Problemas Comuns & Dicas

- **Arquivo não encontrado** – Verifique novamente os caminhos em `filesToMerge`. Usar `Path.Combine` pode ajudar a evitar erros de separador de caminho.  
- **Uso de memória** – Ao mesclar um grande número de arquivos, considere processá‑los em lotes para manter o consumo de memória baixo.  
- **Documentos criptografados** – Se algum XPS de origem estiver protegido por senha, carregue‑lo com as credenciais apropriadas antes de mesclar.

## Perguntas Frequentes

**Q1: Posso mesclar arquivos XPS de tamanhos de página diferentes?**  
R: Sim. Aspose.Page normaliza automaticamente as dimensões das páginas durante a mesclagem.

**Q2: Existe um limite de quantos arquivos XPS eu posso combinar?**  
R: Não há um limite rígido, mas coleções muito grandes podem afetar o desempenho; monitore o uso de memória.

**Q3: Preciso de uma licença especial para mesclar documentos XPS criptografados?**  
R: Uma licença completa do Aspose.Page é necessária para qualquer recurso em nível de produção, incluindo o manuseio de documentos criptografados.

**Q4: Como adiciono um rodapé personalizado a cada página após a mesclagem?**  
R: Após a mesclagem, você pode reabrir o XPS resultante com `XpsDocument` e usar a API de desenho para inserir rodapés.

**Q5: O Aspose.Page suporta .NET Core?**  
R: Absolutamente. A biblioteca é compatível com .NET Core 3.1 e posteriores, bem como .NET 5/6/7.

## Conclusão

Agora você aprendeu **como mesclar documentos XPS** de forma eficiente usando Aspose.Page para .NET. Seguindo os passos acima, você pode automatizar a consolidação de documentos em qualquer aplicação .NET, economizando tempo e reduzindo o esforço manual. Explore mais a API para adicionar marcas d'água, criptografar o arquivo final ou manipular páginas individuais conforme necessário.

---

**Última atualização:** 2026-01-15  
**Testado com:** Aspose.Page for .NET (versão mais recente)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}