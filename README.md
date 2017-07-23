![logo](assets/logo_apiblueprint.png)

# API Blueprint
### Design de APIs para Humanos

[![slack](https://apiblueprint-slack.herokuapp.com/badge.svg)](https://apiblueprint-slack.herokuapp.com/)

Uma poderosa linguagem de design de APIs de alto nível para APIs web.

API Blueprint é simples e acessível para todo mundo envolvido no ciclo de vida do design de API. Sua sintaxe é concisa e expressiva.

Com API BLueprint você pode rapidamente prototipar e modelas APIs a serem criadas ou descrever as APIs de missão crítica já instaladas. De um [carro] [tesla] à maior rede de distribuição de conteúdo (CDN) no mundo.

A API Blueprint é feita para encorajar diálogo e colaboração entre os stakeholders, desenvolvedores e clientes no ponto em qualquer ponto do ciclo de vida da API. Ao mesmo tempo, as [ferramentas][] da API Bluenprint provêem o suporte para alcançar os objetivos, seja desenvolvimento da API, governança ou entrega.

![API Blueprint Lifecycle](assets/lifecycle.png)

[tesla]: https://github.com/timdorr/model-s-api/blob/master/apiary.apib
[tools]: http://apiblueprint.org/tools.html

## Open Source
API Blueprint tem seu código totalmente aberto sob a licença MIT.
Qualquer [contribuição][contribute] é altamente apreciada.
Any [contribution][contribute] is highly appreciated.

[contribute]: #contribute

## Em casa no GitHub
A linguagem API Blueprint é reconhecida pelo Github. Você pode [pesquisar por API Blueprint][search] ou usar linguagem `apib` para [syntax highlighting][gfm].

[search]: https://github.com/search?utf8=%E2%9C%93&q=language%3A%22API+Blueprint%22&type=Repositories&ref=advsearch&l=API+Blueprint&l=

[gfm]: https://help.github.com/articles/github-flavored-markdown/#syntax-highlighting

## Começando
Tudo para descrever um endpoint da sua API é escrever:

```apib
# GET /message
+ Response 200 (text/plain)

        Hello World!
```

em seus editor de texto plano favorito.

Com esse blueprint você já pode criar um [mock][], [documentação][documentation] e [testar][test] da sua API antes mesmo de começar a codificar.

Para aprender mais sobre a sintaxe API Blueprint, pule direto para o [Tutorial][tutorial] ou dê
uma olhada em alguns [exemplos][exemples].

[mock]: http://docs.apibstart.apiary.io/#reference/0/message/get?console=1
[documentation]: http://docs.apibstart.apiary.io
[test]: http://dredd.readthedocs.org/en/latest/
[tutorial]: Tutorial.md
[examples]: https://github.com/apiaryio/api-blueprint/tree/master/examples

## Media Type
O media type para API Blueprint é `text/vnd.apiblueprint`.

## Veja mais
- [Tutorial][tutorial]
- [Tutorial avançado][advanced_tutorial]
- [Exemplos][examples]
- [Wiki][wiki]
- [Glossário][glossary]
- [Especificação][specification]
- [Lista de ferramentas][tools]
- [Desenvolvedores][developers]

[advanced_tutorial]: Advanced%20Tutorial.md
[glossary]: Glossary%20of%20Terms.md
[specification]: API%20Blueprint%20Specification.md
[wiki]: https://github.com/apiaryio/api-blueprint/wiki
[developers]: https://apiblueprint.org/developers.html

## Futuro
Os planos para o API Blueprint são completamente monitarados no GitHub - veja o [Roadmap do API Blueprint][roadmap].

[roadmap]: https://github.com/apiaryio/api-blueprint/wiki/Roadmap

## Desenvolvedores
Criando ferramentas para API Blueprint é possível graças à sua interface machine-friendly provida pelo parser do API Blueprint.

Se você ficou interessados em criar ferramentas para API Blueprint, dê uma olhada em [Desenvolvendo ferramentas para API Blueprint][developers].

## Contribuir
Fique à vontade para reportar problemas ou propor novas ideias usando as Github [issues] do API Blueprint.

Nós usamos um processo de RFC para propor qualquer mudança substancial na linguagem do API Blueprint, na especificação ou no parser.

Se você vai propor alguma mudança, por favor consulte nosso [RFC process][rfc].

[issues]: https://github.com/apiaryio/api-blueprint/issues
[rfc]: https://github.com/apiaryio/api-blueprint-rfcs

## Entre em contato
- [@apiblueprint](https://twitter.com/apiblueprint)
- [Slack](https://apiblueprint-slack.herokuapp.com/)
- [Stack Overflow](http://stackoverflow.com/questions/tagged/apiblueprint)
- [GitHub Issues][issues]

## Licença
Licença MIT. Veja o arquivo da [LICENÇA](https://github.com/apiaryio/api-blueprint/blob/master/LICENSE).
