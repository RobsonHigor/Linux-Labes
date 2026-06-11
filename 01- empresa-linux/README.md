# Laboratório 01 - Empresa Linux

## Objetivo
Simular uma estrutura de empresa utilizando usuários, grupos e permissões do Linux.
## Cenário
A empresa possui três departamentos:

* RH
* Financeiro
* Suporte

Cada funcionário deve acessar apenas os arquivos do seu próprio departamento.

## Estrutura

```text
empresa
├── rh
├── financeiro
└── suporte
```

## Usuários

* Ana → RH
* Carlos → Financeiro
* Maria → Suporte
  
## Grupos

* rh
* financeiro
* suporte


## Comandos Utilizados
#### Criação de usuários

```bash
useradd -m ana
useradd -m carlos
useradd -m maria
```
#### Criação de grupos
```bash
groupadd rh
groupadd financeiro
groupadd suporte
```
#### Associação aos grupos
```bash
usermod -aG rh ana
usermod -aG financeiro carlos
usermod -aG suporte maria
```
### Configuração das pastas

```bash
chgrp rh empresa/rh
chmod 770 empresa/rh

chgrp financeiro empresa/financeiro
chmod 770 empresa/financeiro

chgrp suporte empresa/suporte
chmod 770 empresa/suporte
```

## Testes Realizados

* Ana conseguiu acessar a pasta RH.
* Carlos não conseguiu acessar a pasta RH.
* Maria não conseguiu acessar a pasta Financeiro.
* Cada usuário permaneceu isolado em seu departamento.

## Aprendizados

* Diferença entre usuário e grupo.
* Como associar usuários a grupos.
* Como utilizar `chgrp` para alterar o grupo de uma pasta.
* Como utilizar `chmod 770` para restringir acessos.
* Como o Linux decide permissões utilizando dono, grupo e outros.

## Conclusão

O laboratório demonstrou como implementar controle de acesso baseado em grupos, uma prática comum em servidores Linux corporativos.
