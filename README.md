# Treinamento Mobile
Repositório de suporte para treinamento de terceiros.

## Setup de ambiente
Faça Download das ferramentas do Android SDK
```
$sudo apt install android-sdk
$sudo apt install android-tools-adb
```
Também é preciso o emulador Genymotion:
```
https://www.genymotion.com/download/
```
Conexão com dispositivo:
```
$adb tcpip 5555
$adb connect <IPdoDispositivo>:5555
```
Testando se funcionou:
```
$adb devices
$adb shell
```

## Prática DIVA
Download do APK:
```
http://www.payatu.com/wp-content/uploads/2016/01/diva-beta.tar.gz
$tar -xcvf diva-beta.tar.gz
```
Instalação do APK:
```
adb install diva-beta.apk
```
