# Criando um Plugin Customizado usando o Plugman

## Passo 1) 
```
mkdir pluginDemo
```

## Passo 2)
```
cd pluginDemo
```

## Passo 3)
Verificar na linha de comando:
```
plugman create -help
```

```shel 
Create a plugin

Usage: plugman create PARAMETER... [OPTION]...

Parameters:
  --name <pluginName>           The name of the plugin
  --plugin_id <pluginID>        An ID for the plugin, ex: org.bar.foo
  --plugin_version <version>    A version for the plugin, ex: 0.0.1
```
## Passo 4)
Execute o comando dentro da pasta `pluginDemo`

```
plugman create --name CordovaCustomPlugin --plugin_id info.androidtaffarel.plugins.custom --plugin_version 1.0.0
```

Neste momento, será criada uma estrutura dentro da pasta `pluginDemo`: <br/>
![Screenshot_20221029_130200](https://user-images.githubusercontent.com/7841603/198841393-d44f5807-d96b-47d3-9610-8fe995e9d527.png)

Observe que ainda não há nada dentro da pasta `pluginDemo/CordovaCustomPlugin/src`.

Mas não se preocupe, já essa pasta será preenchida com um arquivo.

## Passo 5)
### Habilitando o plugin dentro da pasta `pluginDemo/CordovaCustomPlugin`
Execute os comandos respectivamente:
```
cd CordovaCustomPlugin && plugman platform add --platform_name android
```
## Passo 6)
Dentro da pasta `pluginDemo`, execute este comando:
```
sudo plugman createpackagejson CordovaCustomPlugin/
```
```json
name: (info.androidtaffarel.plugins.custom) 
version: (1.0.0) 
description: Plugin demonstrativo
git repository: 
author: Taffarel Xavier
license: (ISC) 
About to write to /home/acer-note/dev/pluginDemo/package.json:

{
  "name": "info.androidtaffarel.plugins.custom",
  "version": "1.0.0",
  "description": "Plugin demonstrativo",
  "cordova": {
    "id": "info.androidtaffarel.plugins.custom",
    "platforms": [
      "android"
    ]
  },
  "keywords": [
    "ecosystem:cordova",
    "cordova-android"
  ],
  "author": "Taffarel Xavier",
  "license": "ISC"
}


Is this OK? (yes) yes
```
## Passo 7
Criando um projeto `cordova`; para isso, execute o comando abaixo dentro da pasta `pluginDemo`:
```
cordova create HelloPlugin info.taffarel.helloplugin HelloPluginDemo
```
## Passo 8
Mover o projeto `CordovaCustomPlugin` para dentro da pasta `HelloPlugin`;
A estrutura será semelhante a esta:

![Screenshot_20221029_132820](https://user-images.githubusercontent.com/7841603/198842586-de786743-e2fb-4ec0-aef6-d606dea4d276.png)

## Passo 9)
Adicionar a plataforma android ao projeto `HelloPlugin`.
Para isso, execute o comando abaixo dentro da pasta `HelloPlugin`:
```
cd HelloPlugin && cordova platform add android
```

## Passo 10)
Adicionando o plugin `CordovaCustomPlugin` ao projeto `HelloPlugin`
```
cd HelloPlugin && cordova plugin add CordovaCustomPlugin
```

