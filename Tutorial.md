# Tutorial básico de API Blueprint

Seja benvindo ao Tutorial! Esse tutorial vai levá-lo pelo bsico de linguagem API Blueprint. Nós iremos criar um passo a passo para um serviço chamado Polls (Enquetes) - uma api simples que permite que clientes vejam enquetes e votem nela. Você pode dar uma olhada na [versão completa][Poll API Blueprint] da blueprint usada neste tutorial para referência.

> **Nota:** **Recursos adicionais da API Blueprint**
>
> + [Especificação da linguagem][specification]
> + [Exemplos][API Blueprint Examples]
> + [Termos do glossário][API Blueprint Glossary of Terms]
> + [Mapa da API Blueprint][map]
> + [Ferramentas para API Blueprint][Tooling Section]

## API Blueprint
O primeiro passo para criar um blueprint é especificar o nome da API e seus metadados. Esse passo parece com o seguinte:

```apib
FORMAT: 1A

# Polls

Polls is a simple API allowing consumers to view polls and vote in them.
```

## Metadados

O blueprint começa com uma seção de metadados. Nesse caso nós espeficamos que esse `FORMAT` tem o valor `À`. O palavra chave formato denota a versão da API Blueprint.

## Nome da API e descrição

O primeiro título no blueprint serve como o nome da API, que nesse caso é "Polls". Títulos começam com um ou mais "#" seguidos por um título. O nome da API aqui usa um "#" para distinguí-lo como de primeiro nível. O número de "#"que você usa determina o nível do título.

Seguindo o título vem a descrição da API. Você pode usar outros títulos para separar a descrição em partes.

Following the heading is a description of the API. You may use further headings
to break up the description section.

## Grupos de recursos

Agora é hora de começar a documentar os recursos da API. Usando a palavra chave 'Group' no início de um título, nós criamos um grupo de recursos relacionados.

```apib
# Group Questions

Resources related to questions in the API.
```

## Recurso

Dentro do grupo de recursos Questões, nós temos um recurso chamado "Coleção de Questões". Esse recurso permite que você veja a lista de questões. O título especifica a URI usada para acessar o recurso dentro de colchetes no final do título.

```apib
## Question Collection [/questions]
```

### Actions

API Blueprint permite que você especifique toda action que você crie como um recurso. Uma action é espeficada como um subtítulo dentro de um recurso com o nome da action seguido pelo método HTTP.

```apib
### List All Questions [GET]
```
Uma action deve incluir pelo menos uma resposta de um servidor que deve incluir o código de status e pode conter um corpo de resposta. Uma resposta é definida como um item da lista dentro de uma action. Listas são criadas com os itens sendo precedidos por `+`,`*`ou `-`.

Essa action retorna um status 200 com um corpo no formato JSON.

```apib
+ Response 200 (application/json)

        [
            {
                "question": "Favourite programming language?",
                "published_at": "2014-11-11T08:40:51.620Z",
                "url": "/questions/1",
                "choices": [
                    {
                        "choice": "Swift",
                        "url": "/questions/1/choices/1",
                        "votes": 2048
                    }, {
                        "choice": "Python",
                        "url": "/questions/1/choices/2",
                        "votes": 1024
                    }, {
                        "choice": "Objective-C",
                        "url": "/questions/1/choices/3",
                        "votes": 512
                    }, {
                        "choice": "Ruby",
                        "url": "/questions/1/choices/4",
                        "votes": 256
                    }
                ]
            }
        ]
```
> **Nota:** Especificar o media type depois do código de status da resposta gera 
> um `Content-type` para o cabeçalho HTTP. Você não precisa esplicitar especificamente o `Content-type` do header.

Os recursos da enquete tem uma segunda action que permite que você cria uma nova questão. Essa action inclui a descrição mostrando a estrutura que você deve enviar ao servidor para realizar essa ação.

```apib
### Create a New Question [POST]

You may create your own question using this action. It takes a JSON object
containing a question and a collection of answers in the form of choices.

+ question (string) - The question
+ choices (array[string]) - A collection of choices.
```
Essa action pega um JSON payload como parte da resposta abaixo:

```apib
+ Request (application/json)

            {
                "question": "Favourite programming language?",
                "choices": [
                    "Swift",
                    "Python",
                    "Objective-C",
                    "Ruby"
                ]
            }
```

Esse exemplo retorna um código de status `201` juntamente com os cabeçalhos HTTP e um corpo de resposta.

```apib
+ Response 201 (application/json)

    + Headers

            Location: /questions/1

    + Body

                {
                    "question": "Favourite programming language?",
                    "published_at": "2014-11-11T08:40:51.620Z",
                    "url": "/questions/1",
                    "choices": [
                        {
                            "choice": "Swift",
                            "url": "/questions/1/choices/1",
                            "votes": 0
                        }, {
                            "choice": "Python",
                            "url": "/questions/1/choices/2",
                            "votes": 0
                        }, {
                            "choice": "Objective-C",
                            "url": "/questions/1/choices/3",
                            "votes": 0
                        }, {
                            "choice": "Ruby",
                            "url": "/questions/1/choices/4",
                            "votes": 0
                        }
                    ]
                }
```

O próximo recurso é "Questão", que representa uma questão única.

```apib
## Question [/questions/{question_id}]
```

### Modelo de URI

A URI para o recurso "Questão˜ usa uma variável expressada por [URI Template][]. Nesse caso, há um ID variável chamado `question_id`, representado no modelo da URI como `{question_id}`.

<a id="uri-parameters"></a>
### Parâmetros na URI

Parâmetros da URI devem descrever a URI usando uma lista de parâmetros. Para "Questão" isso deve ser como a seguir:

```apib
+ Parameters
    + question_id (number) - ID of the Question in the form of an integer
```

A variável `question_id` do modelo da URI é um parâmetro para toda action nesse recurso. Ele é definido usando um `número` arbitrário seguido por uma descrição para o parâmetro.

> Consulte a especificação da [Seção de parâmetros de URI][URI Parameters Section] da API Blueprint
> para mais exemplos.

### Actions

Esse recurso tem uma action para recuperar os detalhes da questão.

```apib
### View a Questions Detail [GET]

+ Response 200 (application/json)

            {
                "question": "Favourite programming language?",
                "published_at": "2014-11-11T08:40:51.620Z",
                "url": "/questions/1",
                "choices": [
                    {
                        "choice": "Swift",
                        "url": "/questions/1/choices/1",
                        "votes": 2048
                    }, {
                        "choice": "Python",
                        "url": "/questions/1/choices/2",
                        "votes": 1024
                    }, {
                        "choice": "Objective-C",
                        "url": "/questions/1/choices/3",
                        "votes": 512
                    }, {
                        "choice": "Ruby",
                        "url": "/questions/1/choices/4",
                        "votes": 256
                    }
                ]
            }
```

#### Resposta sem um corpo

Esse recurso tem uma ação de exclusão. O servidor irá retornar uma resposta 204 sem um corpo.

```apib
### Delete [DELETE]

+ Response 204
```

## Blueprint completa

Você pode achar uma [implementação](http://github.com/apiaryio/polls-api) dessa API em http://polls.apiblueprint.org/ juntamente com a [Poll API Blueprint][] completa no repositório de [Exemplos da API Blueprint][API Blueprint Examples]. Você pode tanmbém apriveitar a api [renderizada no Apiary][rendered on Apiary].

> **Nota:** Dê uma olhada nos [termos do glossário da API Blueprint][API Blueprint Glossary of Terms] se você precisar
> clarificar alguns termos usado neste documento.

> **Note:** Take a look at the [API Blueprint Glossary of Terms][] if you need
> clarification of some of the terms used though this document.

## Ferramentas para API Blueprint

Visite a [Seção de ferramentas][Tooling Section] de [apiblueprint.org][] para encontrar ferramentas para usar API Blueprints.

[GitHub Gists]:                     https://gist.github.com
[API Blueprint Glossary of Terms]:  https://github.com/apiaryio/api-blueprint/blob/master/Glossary%20of%20Terms.md
[API Blueprint Identifier]:         https://github.com/apiaryio/api-blueprint/blob/1A/API%20Blueprint%20Specification.md#Identifiers
[HTTP Request Method]:              https://github.com/for-GET/know-your-http-well/blob/master/methods.md
[status code]:                      https://github.com/for-GET/know-your-http-well/blob/master/status-codes.md
[message-headers]:                  https://github.com/for-GET/know-your-http-well/blob/master/headers.md
[payload]:                          https://github.com/apiaryio/api-blueprint/blob/master/Glossary%20of%20Terms.md#payload
[URI Template]:                     https://github.com/apiaryio/api-blueprint/blob/master/Glossary%20of%20Terms.md#uri-template
[URI Parameters Section]:           https://github.com/apiaryio/api-blueprint/blob/master/API%20Blueprint%20Specification.md#def-uriparameters-section
[Markdown pre-formatted code blocks]: http://daringfireball.net/projects/markdown/syntax#precode
[URI Parameters]: #uri-parameters
[API Blueprint Examples]: https://github.com/apiaryio/api-blueprint/tree/master/examples
[Poll API Blueprint]: https://raw.github.com/apiaryio/api-blueprint/master/examples/Polls%20API.md
[rendered on Apiary]: http://docs.pollsapi.apiary.io
[Tooling Section]: http://apiblueprint.org/tools.html
[apiblueprint.org]: http://apiblueprint.org
[specification]: https://github.com/apiaryio/api-blueprint/blob/master/API%20Blueprint%20Specification.md
[map]: https://github.com/apiaryio/api-blueprint/wiki/API-Blueprint-Map
