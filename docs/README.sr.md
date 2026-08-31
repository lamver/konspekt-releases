# Konspekt

<p align="center">
  <img width="128" height="128" src="https://raw.githubusercontent.com/lamver/konspekt-releases/master/assets/icon-256.png" alt="Konspekt logo">
</p>

<p align="center">
  <b>Pametna aplikacija za bilješke na sastancima</b>
</p>

---

<p align="center">
  Snima pozive, transkribuje ih i pretvara vaše kratke bilješke u čitljiv sažetak.
  <br>
  Sve funkcionalnosti rade isključivo lokalno na vašem računaru. Zvuk i transkripti nikada ne napuštaju vaš uređaj.
</p>

---

<p align="center">
  <a href="https://github.com/lamver/konspekt-releases/releases/latest">Preuzimanje</a>
  ·
  <a href="https://github.com/lamver/konspekt-releases/blob/master/README.md">English</a>
  ·
  <a href="https://github.com/lamver/konspekt-releases/issues">Prijavi problem</a>
</p>

---

## Našao si grešku?

Otvori issue u ovom repozitorijumu. Priloži:
1. Verziju programa sa stranice O programu
2. Datoteka loga na putanji: `%LOCALAPPDATA%\Konspekt\konspekt.log`

**NE** šalji audio zapise, transkripte ili bilješke sa sastanaka. Nikada nam ne trebaju za otklanjanje grešaka.

## Proveri šta si preuzeo

Konspekt snima tvoj mikrofon, sluša zvuk sistema i presreće prečice na
tastaturi. Spolja gledano, tako se ponaša špijunski program, pa naše
sopstveno „proverili smo, čisto je" ne vredi ništa. Proveri sam, jedna je
komanda.

Uz svaki instalater objavljujemo i `SHA256SUMS`. Uporedi liniju iz njega sa
onim što izračuna Windows:

```
certutil -hashfile konspekt-0.4.0-setup.exe SHA256
```

Ako se poklapa, datoteka je tačno ona koju smo napravili i niko je nije
zamenio usput. Ako se ne poklapa, nemoj je pokretati i javi nam.

## Zašto se Windows buni pri instalaciji

SmartScreen prikazuje „Windows je zaštitio vaš računar" za svaki program
bez sertifikata za potpisivanje koda. Takav sertifikat košta i izdaje se
firmi, što mlad projekat obično nema. Klikni „Više informacija", pa
„Svejedno pokreni".

Antivirusi ponekad prijavljuju PyInstaller izdanja sama po sebi, bez obzira
na sadržaj: tako se pakuju i pošteni i zlonamerni programi. Upravo zato
objavljujemo kontrolne sume: one se mogu proveriti, obećanja ne mogu.
