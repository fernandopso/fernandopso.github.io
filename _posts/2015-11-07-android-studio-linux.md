---
layout: post
title:  "Android Studo no Linux"
date:   2015-11-07 22:33:44
---

Faça o download do [Android Studio IDE][android_studio], no terminal navegue até o arquivo para extrair o ZIP (único formato disponível para download no site)

```
$ unzip android-studio-ide-{versão-do-seu-arquivo}-linux.zip
```

```
$ mv android-studio/ ~/
```

Configuração
=====

Adicione no arquivo *.bashrc* as variaveis de ambiente necessária

```
$ export ANDROID_HOME=/home/fernando/android-sdk-linux
```

```
$ export PATH=${PATH}:~/android-sdk-linux/tools
```

Alias para iniciar o Android Studio digitando android no terminal

```
$ alias android="sudo sh ~/android-studio/bin/studio.sh"
```

Para encontrar um diretorio o comando `find` é uma mão na roda!

```
$ sudo find / -name android-sdk-linux
```

Para abrir o Android Studio basta digitar `android` no terminal.

[java]: http://www.java.com/en/download/linux_manual.jsp
[java_se]: http://www.oracle.com/technetwork/pt/java/javase/downloads/index.html
[android_studio]: http://developer.android.com/sdk/index.html
