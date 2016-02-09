---
layout: post
title:  "Android Studio IDE no Elementary OS"
date:   2015-11-07 22:33:44
---

## Dependências

Requer instalação do [Java SE Development Kit][java_se].

Pode ser instalado através do site da [oracle][java_se] ou através do pacote `oracle-java8-installer`

{% highlight bash %}
sudo add-apt-repository ppa:webupd8team/java -y
sudo apt-get update
sudo apt-get install oracle-java8-installer
sudo apt-get install oracle-java8-set-default
sudo apt-get install lib32z1 lib32ncurses5 lib32bz2-1.0 lib32stdc++6
{% endhighlight %}

Verifique

{% highlight bash %}
java -version
{% endhighlight %}

## Instalação

Baixe o [Android Studio IDE][android_studio] e no terminal navegue até o arquivo para extrair o ZIP (único formato disponível para download no site).

{% highlight bash %}
unzip android-studio-ide-{versão-arquivo}-linux.zip
mv android-studio/ ~/
{% endhighlight %}

Execute o *bash script* para instalar

{% highlight bash %}
sh ~/android-studio/bin/studio.sh
{% endhighlight %}

Irá instalar o SDK no diretório `~/android-sdk-linux/`, navegue até a pasta *tools* e execute:

{% highlight bash %}
android sdk
{% endhighlight %}

## Configuração

É preciso adicionar nas variáveis de ambiente o *path*  do `android-sdk-linux` e `android-sdk-linux/tools`. Adicione no *.bashrc*

{% highlight bash %}
export ANDROID_HOME=~/android-sdk-linux
export PATH=${PATH}:~/android-sdk-linux/tools
alias android_studio="sh ~/android-studio/bin/studio.sh"
{% endhighlight %}

Digite `android_studio` no terminal para abrir o Android Studio.

## Gerando APK

Instale o ADB

{% highlight bash %}
sudo apt-get install android-tools-adb
{% endhighlight %}

No projeto de permissão para o **gradlew**

{% highlight bash %}
chmod +x gradlew
{% endhighlight %}

User o *debugger* para gerar a apk

{% highlight bash %}
./gradlew assembleDebug
{% endhighlight %}

Instale usando o ADB

{% highlight bash %}
adb install -r app/build/outputs/apk/app-debug-unaligned.apk
{% endhighlight %}

[java_se]: http://www.oracle.com/technetwork/pt/java/javase/downloads/index.html
[android_studio]: http://developer.android.com/sdk/index.html
