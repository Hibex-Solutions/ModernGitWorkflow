# Fluxos

Algumas pré-considerações:

- A branch principal se chama `main`
- Toda tag de versão é prefixada com `v`. Ex: `v0.1.0`

## simple-trunk-based-flow

O desenvolvimento simples baseado no tronco prevê que tudo é feito
na branch principal, e sempre que se considera algo que possa ser
liberado como uma versão (estável ou não), se cria uma tag diretamente.

```mermaid
---
config:
    theme: 'neutral'
---
gitGraph TB:
    commit
    commit tag: "v0.1.0-alpha"
    commit
    commit tag: "v0.1.0-beta"
    commit tag: "v0.1.0-rc"
    commit tag: "v0.1.0"
    commit tag: "v0.1.1"
    commit
```

## stable-release-flow

Este fluxo considera o _thunk-based_ como escolha, e quando se deseja
liberar uma versão, então criamos uma branch para estabilizá-la.
Onde testes são feitos e possíveis correções de estabilização da
versão são aplicáveis.

```mermaid
---
config:
  theme: 'neutral'
---
gitGraph LR:
    commit
    commit
    commit
    branch "release/0.1"
    commit
    commit tag: "v0.1.0-alpha"
    commit
    commit tag: "v0.1.0-beta"
    commit
    commit tag: "v0.1.0-rc"
    checkout main
    merge "release/0.1" tag: "v0.1.0"
    commit
```

## incremental-release-flow

> Este fluxo é uma extensão de `stable-release-flow`.

Considera-se que enquanto uma versão está sendo establilizada, uma
próxima versão pode ser construída em paralelo.

Ideal para times ágeis que entregam incrementos sequenciais.

```mermaid
---
config:
  theme: 'neutral'
---
gitGraph LR:
    commit
    branch "release/0.1"
    commit
    commit tag: "v0.1.0-rc"
    switch main
    commit
    commit
    branch "release/0.2"
    commit
    commit tag: "v0.2.0-alpha1"
    switch "release/0.1"
    commit tag: "v0.1.0"
    switch main
    merge "release/0.1" type: REVERSE
    switch "release/0.2"
    merge main type: HIGHLIGHT tag: "v0.2.0-alpha2"
    commit 
    commit tag: "v0.2.0"
    switch main
    merge "release/0.2" type: REVERSE
    switch main
    commit
```
```

Regras:
- Não se pode liberar uma versão final qualquer enquanto houver outra
  outra menor em aberto. Ex: Não se libera uma `release/0.2` enquanto
  uma `release/0.1` existir.
- Sempre que uma versão final é liberada as próximas versões em aberto
  devem ser atualizadas. Ex: liberando uma `release/0.1`, enquanto uma
  `release/0.2` existir, após liberação, `main` deve ser juntada a 
  `release/0.2` (_merge_). 
- As tags de versão são sempre em _commits_ da branch de _release_.
```
