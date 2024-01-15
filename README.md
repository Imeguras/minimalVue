# Developers environment
VS-Code
Node- v16.13.0
Ionic(installed globally)- 7.2.0
Linux-6.6.11-1-lts(Arch linux distro)
# Steps used 
1º ionic start minimalVue --type vue
	|> Blank
	|> No new Account 
2º Create Readme
3º npm install @capacitor/android
4º npx cap add android
5º npm install @capacitor-mlkit/barcode-scanning
6º npx ionic cap sync
7º 
```
<!-- To get access to the camera. -->
<uses-permission android:name="android.permission.CAMERA" />
<!-- To get access to the flashlight. -->
<uses-permission android:name="android.permission.FLASHLIGHT"/>
```