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

## Qué necesitas

Windows 10 u 11, de 64 bits.

|            | Mínimo    | Cómodo    |
| ---------- | --------- | --------- |
| Procesador | 2 núcleos | 4 núcleos |
| Memoria    | 4 GB      | 8 GB      |
| Disco      | 3 GB      | 10 GB     |

Todo se calcula en el procesador, no hace falta tarjeta gráfica.

El espacio en disco se va en el programa (unos 250 MB), los modelos de
reconocimiento de voz (unos 560 MB, se descargan al primer inicio) y el
modelo que escribe las notas (1,8 GB, se descarga la primera vez que
pides notas; los más potentes ocupan 2,5 y 5 GB). Las grabaciones
ocupan unos 230 MB por hora.

## Licencia

Las primeras 10 reuniones funcionan por completo. Después puedes seguir
viendo, buscando y copiando todo; para grabar reuniones nuevas hace falta
una licencia: [aisearch.ru/pricing/license/konspekt](https://aisearch.ru/pricing/license/konspekt). La clave
se pega en Ajustes → Licencia y se comprueba en tu ordenador, sin
internet.

## ¿Encontraste un error?

Abre un issue en este repositorio. Incluye:
1. Versión del programa desde la página Acerca de
2. Archivo de registro en: `%APPDATA%\Konspekt\konspekt.log`

**NO** envíes audio, transcripciones ni notas de las reuniones. Nunca los necesitamos para depurar el programa.

## Verifica lo que has descargado

Konspekt graba tu micrófono, escucha el audio del sistema e intercepta
atajos de teclado. Visto desde fuera, así se comporta exactamente un
programa espía, por lo que nuestro propio «lo hemos comprobado, está
limpio» no vale nada. Compruébalo tú mismo, son dos comandos.

Cada versión publica un archivo `SHA256SUMS` junto al instalador. Compara
la línea que contiene con lo que calcula Windows:

```
certutil -hashfile konspekt-0.9.0-setup.exe SHA256
```

Si coinciden, el archivo es exactamente el que compilamos y nadie lo ha
sustituido por el camino. Si no coinciden, no lo ejecutes y avísanos.

Cada instalador se analiza con VirusTotal durante la compilación, con unos
setenta motores antivirus, y el enlace al informe está en la descripción de
la versión. El análisis se ejecuta en el servidor de compilación antes de
publicar, así que no hay ningún paso donde alguien pueda saltárselo en
silencio.

También puedes comprobar que el archivo lo compilamos nosotros, desde
nuestro código fuente, y no otra persona:

```
gh attestation verify konspekt-0.9.0-setup.exe --repo lamver/konspekt
```

El comando nombra `lamver/konspekt`, el repositorio del código donde se
ejecuta la compilación, no este donde se publican las versiones. No es una
errata: la firma registra dónde se compiló el archivo.

## Por qué Windows protesta al instalar

SmartScreen muestra «Windows protegió su PC» con cualquier programa sin
certificado de firma de código. Ese certificado cuesta dinero y se emite a
una empresa, algo que un proyecto joven no suele tener. Pulsa «Más
información» y luego «Ejecutar de todas formas».

Los antivirus a veces marcan las compilaciones de PyInstaller por sí
mismas, sin importar su contenido: así se empaquetan tanto programas
honestos como maliciosos. Por eso publicamos sumas de verificación, el
informe de VirusTotal y la firma de compilación: se pueden comprobar, las
promesas no.

Si el programa queda bloqueado del todo y no arranca (Defender indica el
error 225), el archivo está intacto, simplemente se le niega el permiso de
ejecución. Comprueba primero la suma, y solo si coincide: «Protección
antivirus y contra amenazas» → «Historial de protección» → busca Konspekt →
«Acciones» → «Permitir en el dispositivo».
