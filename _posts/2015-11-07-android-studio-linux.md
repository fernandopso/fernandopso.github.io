---
layout: post
title:  "Android Studio IDE no Elementary OS"
date:   2015-11-07 22:33:44
---

### Dependências

Requer instalação do [Java SE Development Kit][java_se].

Pode ser instalado através do site da [oracle][java_se] ou através do pacote `oracle-java8-installer`

```
sudo add-apt-repository ppa:webupd8team/java -y
sudo apt-get update
sudo apt-get install oracle-java8-installer
sudo apt-get install oracle-java8-set-default
```

Verifique

```
java -version
```

### Instalação

Baixe o [Android Studio IDE][android_studio] e no terminal navegue até o arquivo para extrair o ZIP (único formato disponível para download no site).

```
unzip android-studio-ide-{versão-do-seu-arquivo}-linux.zip
```

```
mv android-studio/ ~/
```

Execute o *bash script* para instalar

```
sh ~/android-studio/bin/studio.sh
```

### Configuração

É preciso adicionar nas variáveis de ambiente o *path*  do `android-sdk-linux` e `android-sdk-linux/tools`. Para encontrar o path do `android-sdk-linux` use o comando `find`.

```
sudo find / -name android-sdk-linux
```

Adicione no *.bashrc*

```
export ANDROID_HOME=~/android-sdk-linux
export PATH=${PATH}:~/android-sdk-linux/tools
alias android="sh ~/android-studio/bin/studio.sh"
```

Digite `android` no terminal para abrir a ide.

[java_se]: http://www.oracle.com/technetwork/pt/java/javase/downloads/index.html
[android_studio]: http://developer.android.com/sdk/index.html
