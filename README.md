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
