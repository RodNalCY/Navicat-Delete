# Navicat-Delete
Para utilizar Navicat en su versión gratuita de manera permanente debe seguir los siguientes pasos:
### Paso 1
- Abrir la consola de `Ejecutar (Windows + R)`
- Ingrese el comando `regedit`
### Paso 2
- Ubicar el Directorio : `HKEY_CURRENT_USER`
- Ubique el siguiente direcotrio : `HKEY_CURRENT_USER\Software\PremiumSoft\`
### Paso 3
- Eliminar los archivos dentro del Direcotrio `..\PremiumSoft\*`

Ojo: Esta opcion solo habilita la versión gratuita de 15 dias.
Si los pasos no funcionan existe un codigo en .bat en este repositorio 
y ejecutelo para hacer el mismo procedimento.
```js
// Copie en bloc de texto y guarde en un tipo de archivo con extension (name_file.bat)
@echo off

echo Delete HKEY_CURRENT_USER\Software\PremiumSoft\NavicatPremium\Registration[version and language]
for /f %%i in ('"REG QUERY "HKEY_CURRENT_USER\Software\PremiumSoft\NavicatPremium" /s | findstr /L Registration"') do (
    reg delete %%i /va /f
)
echo.

echo Delete Info folder under HKEY_CURRENT_USER\Software\Classes\CLSID
for /f %%i in ('"REG QUERY "HKEY_CURRENT_USER\Software\Classes\CLSID" /s | findstr /E Info"') do (
    reg delete %%i /va /f
)
echo.

echo Finish

pause
```
# Navicat-Delete 2.0
- Desinstalar "Navicat"
- Eliminar los archivos de "HKEY_CURRENT_USER\Software\PremiumSoft\"
- Realizar Copia y descargar la carpeta "CLSID" en la ruta "HKEY_CURRENT_USER\Software\Classes\CLSID" ... (1)
- Eliminar los archivos del "CLSID" y deja solo la carpeta
- Instalar "Navicat"
- Realizar Copia y descargar la carpeta "CLSID" con los nuevos "COMS" cifrados ... (2)
- Abrir la segunda copia e identificar las "codificación" de los COMS
- IDENTIFICAR Y ELIMINAR LOS COMS CIFRADOS de la Carpeta "CLSID" del archivo (2) al archivo (1)
- Subir la carpeta de "CLSID" editado.
- Puede ser que debas instalar y desintalar Navicat

# Por ejemplo es mi caso de esta manera los tengo los COMS del el CLSID
Windows Registry Editor Version 5.00

Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\SOFTWARE\Classes\CLSID]

[HKEY_CURRENT_USER\SOFTWARE\Classes\CLSID\{274357B9-1BCB-A2CB-D720-BD78657755BD}]

[HKEY_CURRENT_USER\SOFTWARE\Classes\CLSID\{274357B9-1BCB-A2CB-D720-BD78657755BD}\DefaultIcon]

[HKEY_CURRENT_USER\SOFTWARE\Classes\CLSID\{274357B9-1BCB-A2CB-D720-BD78657755BD}\ShellFolder]
////////////////////////////////////SOLO//ESTO//CAMBIO//DINAMICAMENTE////////////////////////////////
[HKEY_CURRENT_USER\SOFTWARE\Classes\CLSID\{38142727-3008-9161-1521-349515000000}]

[HKEY_CURRENT_USER\SOFTWARE\Classes\CLSID\{38142727-3008-9161-1521-349515000000}\LocalServer32]
@="\"C:\\Program Files\\Adobe\\Acrobat DC\\Acrobat\\ADNotificationManager.exe\" -ToastActivated"
/////////////////////////////////////////////////////////////////////////////////////////////////////
[HKEY_CURRENT_USER\SOFTWARE\Classes\CLSID\{F5F8BF08-353D-841E-453C-AA5D61059E74}]

[HKEY_CURRENT_USER\SOFTWARE\Classes\CLSID\{F5F8BF08-353D-841E-453C-AA5D61059E74}\Info]
"274357B91BCBA2CBD720BD78824CB729"="9B71D77E7A4AD82041CF145D665B551E"

