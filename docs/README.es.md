# Konspekt

<p align="center">
  <img width="128" height="128" src="https://raw.githubusercontent.com/lamver/konspekt-releases/master/assets/icon-256.png" alt="Logo Konspekt">
</p>

<p align="center">
  <b>Aplicación inteligente de notas para reuniones</b>
</p>

---

<p align="center">
  Graba las llamadas, las transcribe y convierte tus notas rápidas en un resumen completo.
  <br>
  Todo funciona 100% localmente. Ningún audio ni transcripción sale nunca de tu ordenador.
</p>

---

<p align="center">
  <a href="https://github.com/lamver/konspekt-releases/releases/latest">Descargar</a>
  ·
  <a href="https://github.com/lamver/konspekt-releases/blob/master/README.md">English</a>
  ·
  <a href="https://github.com/lamver/konspekt-releases/issues">Reportar problema</a>
</p>

---

## ¿Encontraste un error?

Abre un issue en este repositorio. Incluye:
1. Versión del programa desde la página Acerca de
2. Archivo de registro en: `%LOCALAPPDATA%\Konspekt\konspekt.log`

**NO** envíes audio, transcripciones ni notas de las reuniones. Nunca los necesitamos para depurar el programa.

## Verifica lo que has descargado

Konspekt graba tu micrófono, escucha el audio del sistema e intercepta
atajos de teclado. Visto desde fuera, así se comporta exactamente un
programa espía, por lo que nuestro propio «lo hemos comprobado, está
limpio» no vale nada. Compruébalo tú mismo, es un solo comando.

Cada versión publica un archivo `SHA256SUMS` junto al instalador. Compara
la línea que contiene con lo que calcula Windows:

```
certutil -hashfile konspekt-0.4.0-setup.exe SHA256
```

Si coinciden, el archivo es exactamente el que compilamos y nadie lo ha
sustituido por el camino. Si no coinciden, no lo ejecutes y avísanos.

## Por qué Windows protesta al instalar

SmartScreen muestra «Windows protegió su PC» con cualquier programa sin
certificado de firma de código. Ese certificado cuesta dinero y se emite a
una empresa, algo que un proyecto joven no suele tener. Pulsa «Más
información» y luego «Ejecutar de todas formas».

Los antivirus a veces marcan las compilaciones de PyInstaller por sí
mismas, sin importar su contenido: así se empaquetan tanto programas
honestos como maliciosos. Por eso publicamos sumas de verificación: se
pueden comprobar, las promesas no.
