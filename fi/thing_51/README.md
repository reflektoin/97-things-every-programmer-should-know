# Opi Sanomaan "Hei Maailma"

Paul Leellä, käyttäjätunnus leep, yleisemmin tunnetaan nimellä Hoppy, on maine paikallisena asiantuntijana ohjelmointiasioissa. Tarvitsin apua. Kävelin Hoppyn pöydälle ja kysyin, voisiko hän katsoa hieman koodia puolestani?

Tottakai, sanoi Hoppy, ota tuoli. Varoin kaatamasta pyramidiksi pinottuja tyhjiä kolatölkkejä hänen takanaan.

Mitä koodia?

Tiedostossa olevaa funktiota, sanoin.

Joten katsotaan tätä funktiota. Hoppy siirsi sivuun K&R:n kirjan ja liu'utti näppäimistönsä eteeni.

Missä IDE on? Nähtävästi Hoppy ei käyttänyt IDE:tä, ainostaan editoria, jota en osannut käyttää. Hän nappasi näppäimistön takaisin. Muutamaa näppäimen painalluksen jälkeen meillä oli tiedosto auki - se oli melko iso tiedosto - ja me katsoimme funktiota - se oli melko iso funktio. Hän hyppi alaspäin, konditionaalin kohdalle, josta halusin kysyä.

Mitä tämä lause tekee jos `x` on negatiivinen? Kysyin häneltä. Kaiketi se on väärin.

Olin koko aamun yrittänyt löytää tapaa pakottaa `x`:n negatiiviseksi, mutta iso funktio isossa tiedostossa oli osa isoa projektia ja uudelleenkääntämis-sykli ja *sitten* kokeilujeni uudelleen ajaminen alkoi uuvuttaa minua. Eikö asiantuntija kuten Hoppy voisi vain kertoa minulle vastauksen?

Hoppy myönsi, ettei hän ollut varma. Yllätyksekseni hän ei kurottanut K&R:ään. Sen sijaan hän kopioi koodilohkon uuteen editoriin, sisensi sen uudelleen ja kääri sen funktioon. Hetkeä myöhemmin hän oli koodannut main-funktion, joka looppasi ikuisesti, kehottaen käyttäjää syöttämään arvoja, välittäen ne funktiolle ja tulostaen lopputuloksen. Hän tallensi bufferin uuteen tiedostoon, tryit.c. Olisin voinut tehdä kaiken tämä itsekin, vaikkakaan en ehkä yhtä nopeasti. Mutta hänen seuraava vaiheesnsa oli mahtavan yksinkertainen ja sillä hetkellä minulle melko tuntematon tapa toimia:

```
$ cc tryit.c && ./a.out
```

Katso! Hänen varsinainen ohjelmansa, luotu vain muutama minuutti aiemmin, oli ajokunnossa. Kokeilimme muutamilla arvoilla ja vahvistimme epäilykseni (joten olin ollut oikeassa jostakin!) ja sitten hän tarkisti asian siihen liittyvästä K&R:n kappaleesta. Kiitin Hoppya ja poistuin, taas varoen, etten häirinnyt hänen kolapyramidiaan.

Takaisin omalla pöydälläni, suljin IDEni. Olin niin tottunut työskentelemään isossa projektissa ison tuotteen sisällä, että aloin ajatella että niin minun pitäisi työskennellä. Tietokone voi tehdä myös pieniä tehtäviä. Avastin tekstinkäsittelyohjelman ja aloitin kirjoittamaan.


```
#include <stdio.h>

int main()
{
    printf("Hello, World\n");
    return 0;
}
```

Kirjoittanut [Thomas Guest](http://programmer.97things.oreilly.com/wiki/index.php/Thomas_Guest)