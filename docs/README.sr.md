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

## Šta vam treba

Windows 10 ili 11, 64-bitni.

|          | Minimum  | Udobno   |
| -------- | -------- | -------- |
| Procesor | 2 jezgra | 4 jezgra |
| Memorija | 4 GB     | 8 GB     |
| Disk     | 1 GB     | 4 GB     |

Sve se računa na procesoru, grafička kartica nije potrebna.
Prepoznavanje govora stiže sa viškom: i na jednom jezgru prepisuje pet
puta brže nego što ljudi govore.

Prostor na disku uglavnom odlazi na modele, koji se preuzimaju pri prvom
pokretanju: 214 MB za prepoznavanje govora i još oko 1,8 GB ako želite
sažetke koje piše ugrađeni jezički model.

## Našao si grešku?

Otvori issue u ovom repozitorijumu. Priloži:
1. Verziju programa sa stranice O programu
2. Datoteka loga na putanji: `%APPDATA%\Konspekt\konspekt.log`

**NE** šalji audio zapise, transkripte ili bilješke sa sastanaka. Nikada nam ne trebaju za otklanjanje grešaka.

## Proveri šta si preuzeo

Konspekt snima tvoj mikrofon, sluša zvuk sistema i presreće prečice na
tastaturi. Spolja gledano, tako se ponaša špijunski program, pa naše
sopstveno „proverili smo, čisto je" ne vredi ništa. Proveri sam, dve su
komande.

Uz svaki instalater objavljujemo i `SHA256SUMS`. Uporedi liniju iz njega sa
onim što izračuna Windows:

```
certutil -hashfile konspekt-0.9.0-setup.exe SHA256
```

Ako se poklapa, datoteka je tačno ona koju smo napravili i niko je nije
zamenio usput. Ako se ne poklapa, nemoj je pokretati i javi nam.

Svaki instalater se tokom pravljenja proverava na VirusTotal-u, sa oko
sedamdeset antivirusnih motora, a link ka izveštaju stoji u opisu izdanja.
Provera se izvršava na serveru za pravljenje pre objave, pa ne postoji korak
u kome bi neko mogao tiho da je preskoči.

Možeš proveriti i da smo datoteku napravili mi, iz našeg izvornog koda, a ne
neko drugi:

```
gh attestation verify konspekt-0.9.0-setup.exe --repo lamver/konspekt
```

U komandi stoji `lamver/konspekt`, repozitorijum sa kodom gde se pravljenje
izvršava, a ne ovaj gde se izdanja objavljuju. Nije greška: potpis beleži
gde je datoteka napravljena.

## Zašto se Windows buni pri instalaciji

SmartScreen prikazuje „Windows je zaštitio vaš računar" za svaki program
bez sertifikata za potpisivanje koda. Takav sertifikat košta i izdaje se
firmi, što mlad projekat obično nema. Klikni „Više informacija", pa
„Svejedno pokreni".

Antivirusi ponekad prijavljuju PyInstaller izdanja sama po sebi, bez obzira
na sadržaj: tako se pakuju i pošteni i zlonamerni programi. Upravo zato
objavljujemo kontrolne sume, VirusTotal izveštaj i potpis o poreklu: oni se
mogu proveriti, obećanja ne mogu.

Ako je program potpuno blokiran i ne pokreće se (Defender javlja grešku
225), datoteka je čitava, samo joj se uskraćuje pravo da se pokrene. Prvo
proveri kontrolnu sumu, i samo ako se poklapa: „Zaštita od virusa i pretnji"
→ „Istorija zaštite" → pronađi Konspekt → „Radnje" → „Dozvoli na uređaju".
