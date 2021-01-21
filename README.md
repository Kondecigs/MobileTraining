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

## Interceptação
Exportar certificado do Burp.
Enviar certificado para o dispositivo:
```
adb push <arquivo> <destino>
```
## Ferramentas
### APK Extractor
```
https://play.google.com/store/apps/details?id=braveheart.apps.apkextract&hl=en_US&gl=US
```
### Apktool
https://ibotpeaches.github.io/Apktool/install/

Download Linux wrapper script (Right click, Save Link As apktool) https://raw.githubusercontent.com/iBotPeaches/Apktool/master/scripts/linux/apktool

Download apktool-2 (https://bitbucket.org/iBotPeaches/apktool/downloads/)

Renomeie o arquivo baixado para apktool.jar

Mova os arquivos (apktool.jar & apktool) para /usr/local/bin (root needed)

Permita que ambos sejam executáveis (chmod +x)

Abre outro terminal e teste o comando apktool
```
apktool -h
apktool d <aplicativo.apk>
```
### JD-GUI
https://java-decompiler.github.io

https://github.com/java-decompiler/jd-gui/releases/download/v1.6.6/jd-gui-1.6.6.jar
```
java -jar jd-gui-x.y.z.jar
```
### Bytecode Viewer
https://github.com/Konloch/bytecode-viewer/releases

https://github.com/Konloch/bytecode-viewer/releases/download/v2.9.22/Bytecode-Viewer-2.9.22.jar
```
java -jar Bytecode-Viewer-2.9.22.jar
```

### Assinatura
```
sudo apt-get install openjdk-11-jdk
keytool -genkey -v -keystore my-release-key.keystore -alias alias_name -keyalg RSA -keysize 2048 -validity 10000
jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore my-release-key.keystore my_application.apk alias_name
```
### Envio e recebimento de arquivos
```
#Enviar pro android
adb push <pathtoarquivo> <dest>
#Puxar do android
adb pull <origem> <dest>
```
Exemplos:
```
adb push Burpcerttrain /sdcard/Documents/burpcert.cer 
adb pull /storage/emulated/0/ExtractedApks/Documents_com.android.documentsui ./
```
