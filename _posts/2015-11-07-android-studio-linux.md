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

```
sudo apt-get install lib32z1 lib32ncurses5 lib32bz2-1.0 lib32stdc++6
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

Irá instalar o SDK no diretório `~/android-sdk-linux/`, navegue até a pasta *tools* e execute:

```
android sdk
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

Digite `android` no terminal para abrir o Android Studio para um Hello World.

### Gerando APK

Instale o ADB

```
sudo apt-get install android-tools-adb
```

No projeto de permissão para o **gradlew**

```
chmod +x gradlew
```

User o *debugger* para gerar a apk


```
./gradlew assembleDebug

```

Instale usando o ADB

```
adb install -r app/build/outputs/apk/app-debug-unaligned.apk
```

[java_se]: http://www.oracle.com/technetwork/pt/java/javase/downloads/index.html
[android_studio]: http://developer.android.com/sdk/index.html
