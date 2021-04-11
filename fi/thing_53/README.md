# Linkkeri(linker) Ei Ole Maaginen Ohjelma

Masentavan usein (tapahtui minulle juuri ennen t‰m‰ kirjoittamista), monien ohjelmoijien n‰kemys prosessista joka muuttaa l‰hdekoodin staattisesti linkatuksi ohjelmaksi(statically linked executable) k‰‰nnetyss‰ kieless‰ on:

1.
Muokkaa l‰hdekoodia
- K‰‰nn‰ l‰hdekoodi objektitiedostoiksi
- Jotain maagista tapahtuu
- Aja ohjelma

Vaihe 3 on, totta kai linkkaus-vaihe. Miksi sanoisin niin tyrmistytt‰v‰n asian? Olen tehnyt teknist‰ tukea vuosikymmenet ja seuraavaa asiaa kysyt‰‰n jatkuvasti:

1. Linker sanoo, ett‰ def on m‰‰ritetty useammin kuin kerran.

- Linkkeri sanoo abc on unresolved symbol.

- Miksi ohjelmani on niin iso?

Jota seuraa kysmys "Mit‰ teen nyt?" johon on yleens‰ lis‰tty mukaan sanonnat "vaikuttaa ett‰" ja "jotenkin" ja mukana on t‰ydellinen h‰mmennyksen aura. Kohdat "Vaikuttaa ett‰" ja "jotenkin" viittaavat siihen, ett‰ linkkaus-prosessin katsotaan olevan maaginen prosessi, jonka ainoastaan velhot ja noidat voivat ymm‰rt‰‰. K‰‰nt‰misen prosessi ei tuo esiin sanoma lauseita, vihjaten ohjelmoijien yleisesti tiet‰v‰n miten k‰‰nt‰j‰t toimivat, tai ainakin mit‰ ne tekee.

Linkkeri on eritt‰in tyhm‰, tavallinen ja yksinkertainen ohjelma. Kaikki mit‰ se tekee on liitt‰‰ objektitiedostojen koodi ja data-osat, yhdist‰‰ symboleiden viittaukset niiden m‰‰rityksiin, vet‰‰ ratkaisemattomat symbolit kirjastosta ja luo suoritettavan ohjelman. Siin‰ kaikki. Ei taikoja! Ei magiaa! Linkkerin kirjoittamisen pitk‰veteisyys on koostuu yleens‰ liian monimutkaisten tiedostoformaattien dekoodaamisesta ja generoinnista, mutta se ei muuta linkkereiden olennaista luonnetta.

Joten sanotaan, ett‰ linkkeri sanoo deffin olevan m‰‰ritelty useammin kuin kerran. Useat ohjelmointikielet kuten C, C++ ja D sis‰lt‰v‰t sek‰ esittelyn(declaration) ett‰ alustamisen(definition). Esittely menee normaalisti header-tiedostoon, kuten:

```
extern int iii;
```

joka generoi ulkoisen viittauksen(external reference) symboliin `iii`. Alustus sen sijaan, itse asiassa varaa muistia(set aside storage) symbolille, esiintyy toteutus-tiedostossa ja n‰ytt‰‰ t‰lt‰:

```
int iii = 3;
```

Kuinka monta alustusta voi olla jokaiselle symbolille? Kuten elokuvassa *Highlander* sanotaan, voi olla vain yksi. Joten, mit‰ jos alustus symbolille iii ilmenee useammassa kuin yhdess‰ tiedostossa?

```
// Tiedosto a.c
int iii = 3;
```

```
// Tiedosto b.c
double iii(int x) { return 3.7; }
```

Linkkeri valittaa, ett‰ `iii` on alustettu moneen kertaan. Ei ainoastaan voi olla yksi, vaan pit‰‰ olla yksi. Jos iii on vain esitelty, mutta ei alustettu, linkkeri valittaa iii:n olevan ratkaisematon(unresolved).

Selvitt‰‰ksesi ohjelman koon syyn, katso segmenttikarttatiedostoa(map file), jonka linkkerit valinnaisesti luovat. Segmenttikarttatiedosto ei ole mit‰‰n muuta kuin lista kaikista symboleista ohjelmassa, sek‰ niiden osoitteet. T‰m‰ kertoo sinulle, mit‰ moduleita on linkattu kirjastosta sek‰ moduleiden koot. Nyt voit katsoa itse mist‰ pullistuminen(bloat) aiheutuu. Usein siell‰ on moduleita, joista sinulla ei ole k‰sityst‰k‰‰n miksi ne on linkattu. Selvitt‰‰ksesi asia, poista tilap‰isesti ep‰ilytt‰v‰ moduli kirjastosta ja uudelleenlinkkaa. Generoituva undefined symbol error kertoo kuka viittaa kyseiseen moduliin.

Vaikka linkkereiden viesteist‰ ei aina heti selvi‰ viestin syy, linkkereiss‰ ei ole mit‰‰n maagista. Mekaniikka on melko suoraviivaista; yksityiskohdat joudut selvitt‰m‰‰n jokaisessa tapauksessa.

Kirjoittaja [Walter Bright](http://creativecommons.org/licenses/by/3.0/us/)