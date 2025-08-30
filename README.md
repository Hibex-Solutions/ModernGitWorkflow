# Modern Git Workflow

> Modern Git Workflow - A Simpler Way to Release Your Software
>> Git Workflow Moderno - Uma maneira mais simples de lançar seu software.

Tenho trabalhado a um tempo com vários fluxos Git para entrega de software
dos mais variados sabores. Mas em essência, são alguma variação do famoso
[Gitflow][gitflow]. Porém o [Gitflow][gitflow] funciona bem para o cenário relatado
pelo prṕrio autor, mas existem alguns problemas para outros cenários.

Devido a esses problemas, o que tenho percebido nos projetos e equipes que
venho trabalhando, é que as equipes precisam sempre fazer algum tipo de
adaptação para usar o [Gitflow][gitflow] em seu próprio contexto. Ao final,
à pesar de dizerem estar usando o [Gitflow][gitflow], na verdade não estão.
Estão usando um fluxo personalizado baseado em [Gitflow][gitflow].

Organizações notáveis também fizeram suas próprias personalizações baseadas
no [Gitflow][gitflow]. Como [GitHub][github] com seu [GitHub flow][githubflow], e
[GitLab][gitlab] com seu [GitLab flow][gitlabflow]. Costumam dizer que se
trata de uma versão _"mais leve"_ do [Gitflow][gitflow].

O [GitLab][gitlab] chegou até a registrar os problemas do [Gitflow][gitflow]
que os levaram a criar o [GitLab flow][gitlabflow] neste artigo entitulado
["The problem with Git flow"][thegitflowproblem].

Obviamente essas organizações à pesar de resolverem o problema, puxam
bastante _a sardinha para suas brasas_. Normalmente acabam vinculando o fluxo
[Git][git] que desenvolveram com suas ferramentas de gerenciamento de problemas.

O que quero aqui é propor um fluxo que considere as vantagens do [Gitflow][gitflow],
mas também considere cenários modernos do desenvolvimento de software, e que
abstraia a parte de gestão de projeto ou problemas, sem _puxar a sardinha_
para quaisquer que sejam as ferramentas que venham a ser usadas.

> Como cenários modernos queremos citar: integração contínua, liberação
> contínua, implantação contínua, entrega contínua, _containers_ e [SemVer][semver].

Portanto, eis aqui nossos objetivos:

- Ser compatível com integração contínua
- Ser compatível com liberação contínua
- Ser compatível com implantação contínua em múltiplos ambientes
- Ser compatível com entrega contínua 
- Ser compatível com desenvolvimento de softwares em _containers_
- Ser compatível com versionamento semântico [SemVer][semver]
- Ser compatível com suporte a múltiplas versões


<!-- links -->
[git]: https://git-scm.com
[gitflow]: https://danielkummer.github.io/git-flow-cheatsheet/
[github]: https://github.com/about
[githubflow]: https://docs.github.com/en/get-started/using-github/github-flow
[gitlab]: https://about.gitlab.com
[gitlabflow]: https://about.gitlab.com/topics/version-control/what-is-gitlab-flow/
[thegitflowproblem]: https://about.gitlab.com/blog/what-is-gitlab-flow/
[semver]: https://semver.org

