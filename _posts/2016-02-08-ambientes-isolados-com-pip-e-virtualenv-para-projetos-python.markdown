---
layout: post
title:  "Ambientes isolados com Pip + Virtualenv para projetos Python"
date:   2016-02-08 17:21:59
---

Problema:

> Controle de dependências de pacotes para diferentes projetos Python.

Exemplo:

> Projeto A requer um pacote na versão 1 e o projeto B precisa do mesmo pacote na versão 2.

Solução:

> Usar o [pip][pip_path] e o [virtualenv][virtualenv_path] para criar ambientes isolados para cada projeto.

Instale o pip

{% highlight bash %}
sudo apt install python-pip
{% endhighlight %}

Instale o virtualenv como *root*

{% highlight bash %}
sudo pip install virtualenv
{% endhighlight %}

Crie um diretório para criação de ambientes

{% highlight bash %}
mkdir ~/.venvs
{% endhighlight %}

Dentro do diretório `~/.venvs`, crie um ambiente com o nome `project_name`

{% highlight bash %}
virtualenv --no-site-packages project_name
{% endhighlight %}

Ative o ambiente para instalação dos pacotes

{% highlight bash %}
source project_name/env/bin/activate
{% endhighlight %}

Use pip para instalar o pacote em uma versão especifica no ambiente ativo

{% highlight python %}
pip install 'lib_name>=1.3.0,<1.4.0'
{% endhighlight %}

Crie uma *alias* para ativar o ambiente e abrir o projeto

{% highlight bash %}
alias project_name="source ~/.venvs/project_name/bin/activate; cd ~/Projects/project_name"
{% endhighlight %}

[virtualenv_path]: https://virtualenv.readthedocs.org/en/latest/
[pip_path]: https://pip.pypa.io/en/latest/installing/
