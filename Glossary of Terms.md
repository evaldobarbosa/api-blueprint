# Glossário da API Blueprint

Uma breve lista de termos usandos no contexto da [API Blueprint](http://apiblueprint.org).

## Glossário

<a name="def-action"></a>
### Action
Uma **transação HTTP** (uma transação requisição-resposta).

Actions são especificados por um [método de requisição HTTP](#def-method) dentro de um [recurso](#def-resource).

<a name="def-api"></a>
### API
Uma **HTTP Application programming interface** deve consultar uma descrição de API. Veja [**API Blueprint**](#def-api-blueprint).

<a name="def-api-blueprint"></a>
### API Blueprint
A **linguagem API Blueprint**. Um formato para descrever API em um arquivo de API blueprint.

<a name="def-asset"></a>
### Asset
**Dado Atômico**. Na maioria das vezes descreve uma representação de recurso na forma de corpo de mensagem ou seu esquema de validação.

<a name="def-attribute"></a>
### Atributo
Baseado no contexto, atributo (ou propriedade) da estrutura de um corpo de mensagem, ou atributo de um recurso ou um atributo de entrada de uma transição (input) – [Action](#def-action).

<a name="def-blueprint"></a>
### Blueprint
Uma **descrição de API**. Um **arquivo de blueprint** (ou conjunto de arquivos) que descrevem uma API usando a linguagem API Blueprint.

<a name="def-data-structure"></a>
### Estrutura de dados
Uma organização de dados particular, ou uma descrição disso. Em API Blueprint, estruturas de dados e seus [Atributos](#def-attribute) são descritos usando sintaxe Markdown para Notação de objetos – [MSON][].

<a name="def-entity"></a>
### Entitidade
[**Entidade**](http://www.w3.org/Protocols/rfc2616/rfc2616-sec7.html) sendo transferida em um [payload](#def-payload).

<a name="def-header"></a>
### Header (Cabeçalho)
Um [**cabealho de mensagem**](#def-message-header).

<a name="def-method"></a>
### Método
Um [**Método de requisição HTTP**](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol#Request_methods).

<a name="def-message"></a>
### Mensagem
Uma **mensagem de transação HTTP**.

<a name="def-message-body"></a>
### Corpo da mensagem
Um [**asset**](#def-asset) representando [**um corpo de mensagem de transação HTTP**](http://en.wikipedia.org/wiki/HTTP_body_data).

<a name="def-message-header"></a>
### Cabeçalho de mensagem
Um [**asset**](#def-asset) representando [**um cabeçalho de mensagem de transação HTTP**](http://en.wikipedia.org/wiki/List_of_HTTP_header_fields).

<a name="def-parameter"></a>
### Parâmetro
Uma **variável** de [**modelo de URI**](#def-uri-template).

<a name="def-payload"></a>
### Payload
Uma **mensagem de transação HTTP** incluindo dua **discussão** e qualquer [**assets**](#def-asset) adicional como entidade-corpo de esquema de validação.


Um payload pode ter um **identificador** – uma string para o payload da [requisição](#def-request)
ou um [código de status HTTP](http://en.wikipedia.org/wiki/List_of_HTTP_status_codes) para um
payload de [response](#def-response).

<a name="def-property"></a>
### Propriedade
Um campo [entitidade](#def-entity) (atributo).

<a name="def-request"></a>
### Requisição
Um [**payload**](#def-payload) contento uma [requisição HTTP](http://www.w3.org/TR/di-gloss/#def-http-request) específica.

<a name="def-response"></a>
### Resposta
Um [**payload**](#def-payload) contento uma [resposta HTTP](http://www.w3.org/TR/di-gloss/#def-http-response) específica.

<a name="def-resource"></a>
### Recurso
Um [**recurso**](http://www.w3.org/TR/di-gloss/#def-resource) de API especificado por uma *URI*. Isso também pode consultar um [**conjunto de recursos**](#def-resource) combinando com um [**modelo de URI**](#def-uri-template).

<a name="def-resource-model"></a>
### Modelo de recurso
Uma [**manifestação de um recurso**](http://www.w3.org/TR/di-gloss/#def-resource-manifestation) em forma de um [payload](#def-payload). Um modelo de recurso é um exemplo que representa esse recurso. Pode ser referenciado no lugar de um [payload](#def-payload).

<a name="def-resource-set"></a>
### Conjunto de recursos
Um conjunto de [**recursos**](http://www.w3.org/TR/di-gloss/#def-resource) de uma API. Essa *URI* combina com um  [**modelo de URI**](#def-uri-template) específico.

<a name="def-trait"></a>
### Trait
Uma qualidade ou característica de uma SEÇÃO de uma API Blueprint.

<a name="def-schema"></a>
### Esquema
Um **esquema de validação** em forma de um [**asset**](#def-asset) usado para validar (ou descrever) um [**corpo de mensagem**](#def-message-body).

<a name="def-uri-template"></a>
### Modelo de URI
Uma sequência compacta de caracteres para descrever o alcance de uma **URI (Unified Resource Idenfifiers)** por uma expansão de **variável**, veja [**RFC 6570**](http://tools.ietf.org/html/rfc6570).

## Referências adicionais

+ [HTTP/1.1 Terminology](http://www.w3.org/Protocols/rfc2616/rfc2616-sec1.html#sec1.3)
+ [W3C Glossary of Terms for Device Independence](http://www.w3.org/TR/di-gloss)
+ [Know your HTTP well](https://github.com/for-GET/know-your-http-well)
+ [Markdown Syntax for Object Notation][MSON]



[MSON]: https://github.com/apiaryio/mson

