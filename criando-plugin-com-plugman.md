# Criando um Plugin Customizado usando o Plugman

## Passo 1) 
`mkdir pluginDemo`

## Passo 2)
cd pluginDemo

## Passo 3)
Verificar na linha de comando:
`plugman create -help`

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

`plugman create --name CordovaCustomPlugin --plugin_id info.androidtaffarel.plugins.custom --plugin_version 1.0.0`

Neste momento, será criada uma estrutura dentro da pasta pluginDemo
