---
layout: post
title:  "Ambientes isolados com Pip + Virtualenv para projetos Python"
date:   2016-02-08 17:21:59
---

Problema:
> Controle de dependências de pacotes para diferentes projetos Python.

Exemplo:
> Projeto A precisa de um pacote na versão 1 e o projeto B precisa do mesmo pacote na versão 2.

Solução:
> Usar o [pip][pip_path] e o [virtualenv][virtualenv_path] para criar ambientes isolados para cada projeto.

Instale o pip

```
sudo apt-get install python-setuptools python-dev build-essential
sudo easy_install pip
```

Instale o virtualenv como *root*

```
$ sudo pip install virtualenv
```

Crie um diretório para criação de ambientes

```
mkdir ~/.venvs
```

Dentro do diretório `~/.venvs`, crie um ambiente com o nome `project_name`

```
virtualenv --no-site-packages project_name
```

Ative o ambiente para instalação dos pacotes

```
$ source project_name/env/bin/activate
```

Use pip para instalar o pacote em uma versão especifica no ambiente ativo

```
pip install 'lib_name>=1.3.0,<1.4.0'
```

Crie uma *alias* para ativar o ambiente e abrir o projeto

```
alias project_name="source ~/.venvs/project_name/bin/activate; cd ~/Projets/project_name"
```

[virtualenv_path]: https://virtualenv.readthedocs.org/en/latest/
[pip_path]: https://pip.pypa.io/en/latest/installing/
