# Fluxos

Algumas pré-considerações:

- A branch principal se chama `main`
- Toda tag de versão é prefixada com `v`. Ex: `v0.1.0`

## Simple trunk-based flow

O desenvolvimento simples baseado no tronco prevê que tudo é feito
na branch principal, e sempre que se considera algo que possa ser
liberado como uma versão (estável ou não), se cria uma tag diretamente.

```mermaid
---
config:
    theme: 'neutral'
---
gitGraph LR:
    commit
    commit
    commit tag: "v0.1.0-alpha"
    commit
    commit 
    commit tag: "v0.1.0-beta"
    commit tag: "v0.1.0-rc"
    commit tag: "v0.1.0"
    commit tag: "v0.1.1"
    commit
    commit
```

<!-- TODO --
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
-->
