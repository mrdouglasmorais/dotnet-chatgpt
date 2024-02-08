# ChatGPT + .NET

[![Lint Code Base](https://github.com/marcominerva/ChatGptNet/actions/workflows/linter.yml/badge.svg)](https://github.com/marcominerva/ChatGptNet/actions/workflows/linter.yml)
[![CodeQL](https://github.com/marcominerva/ChatGptNet/actions/workflows/codeql.yml/badge.svg)](https://github.com/marcominerva/ChatGptNet/actions/workflows/codeql.yml)
[![NuGet](https://img.shields.io/nuget/v/ChatGptNet.svg?style=flat-square)](https://www.nuget.org/packages/ChatGptNet)
[![Nuget](https://img.shields.io/nuget/dt/ChatGptNet)](https://www.nuget.org/packages/ChatGptNet)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://github.com/marcominerva/ChatGptNet/blob/master/LICENSE)

Uma biblioteca de integração do ChatGPT para .NET, com suporte para OpenAI e Azure OpenAI Service.

## Instalação

A biblioteca está disponível no [NuGet](https://www.nuget.org/packages/ChatGptNet). Basta pesquisar por *ChatGptNet* no **Package Manager GUI** ou executar o seguinte comando no **.NET CLI**:

```shell
dotnet adicionar o pacote ChatGptNet
```

## Configuração

Registre o serviço do ChatGPT no início da aplicação:

```csharp
builder.Services.AddChatGpt(options =>
{
    // OpenAI.
    //options.UseOpenAI(apiKey: "", organization: "");

    // Azure OpenAI Service.
    //options.UseAzure(resourceName: "", apiKey: "", authenticationType: AzureAuthenticationType.ApiKey);

    options.DefaultModel = "my-model";
    options.DefaultEmbeddingModel = "text-embedding-ada-002";
    options.MessageLimit = 16;  // Default: 10
    options.MessageExpiration = TimeSpan.FromMinutes(5);    // Default: 1 hour
    options.DefaultParameters = new ChatGptParameters
    {
        MaxTokens = 800,
        Temperature = 0.7
    };
});
```

**ChatGptNet** suporta tanto OpenAI quanto Azure OpenAI Service, então é necessário configurar as configurações corretas com base no provedor escolhido:

#### OpenAI (UseOpenAI)

- _ApiKey_: Está disponível na página [Configurações do usuário](https://platform.openai.com/account/api-keys) da conta OpenAI (obrigatório).
- _Organization_: para usuários que pertencem a várias organizações, você também pode especificar qual organização está sendo usada. O uso dessas solicitações de API será contabilizado na cota de assinatura da organização especificada (opcional).

##### Azure OpenAI Service (UseAzure)

- _ResourceName_: o nome do seu Recurso Azure OpenAI (obrigatório).
- _ApiKey_: o Azure OpenAI fornece dois métodos de autenticação. Você pode usar chaves de API ou Token de Diretório Ativo da Azure (obrigatório).
- _ApiVersion_: a versão da API a ser usada (opcional). Valores permitidos:
  - 2023-03-15-preview
  - 2023-05-15
  - 2023-06-01-preview
  - 2023-07-01-preview
  - 2023-08-01-preview
  - 2023-09-01-preview
  - 2023-12-01-preview (padrão)
- _AuthenticationType_: especifica se a chave é uma chave de API real ou um [token de Diretório Ativo da Azure](https://learn.microsoft.com/azure/cognitive-services/openai/how-to/managed-identity) (opcional, padrão: "ApiKey").

#### Por Douglas Morais