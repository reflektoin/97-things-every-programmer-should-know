# Paranna koodia poistamalla sitä

*Vähemmän* on enemmän. Se on aika kulunut sanonta, mutta joskus se todella pitää paikkansa.

Yksi parannuksista, joita olen tehnyt koodikantaamme lähiviikkojen aikana on ollut osien poistaminen siitä. Olemme kirjoittaneet ohjelmistoa seuraten XPn oppeja, sen lisäksi YAGNIa(You Aren't gonna Need it, suom. et tule tarvitsemaan sitä). Ihmisluonto on mitä se on ja lopulta ne jäävät noudattamatta muutamissa paikoissa.

Huomasin, että tuotteella kesti liian pitkään suorittaa tiettyjä tehtäviä - yksinkertaisia tehtäviä, joiden olisi pitänyt tapahtua lähes silmänräpäyksessä. Tämä johtua liiallisista ominaisuuksista(overimplemented); se oli koristeltu kelloin ja pillein, jotka eivät ollee tarpeellisia, mutta jotka tekohetkellä vaikuttivat hyviltä ideioilta.

Joten yksinkertaistin koodia, paransin tuotteen suorituskykyä ja vähensin globaalin koodin entropiaa yksinkertaisesti poistamalla haittaavia ominaisuuksia koodikannasta. Hyödyllisesti yksikkötestini kertoivat, etten ollut rikkonut mitään operaation aikana.

Yksinkertainen ja erittäin miellyttävä kokemus.

Joten miksi tarpeeton koodi edes päätyi sinne? Miksi yksi ohjelmoija koki tarpeen kirjoittaa ylimääräistä koodia ja miten se pääsi katselmoinnin tai pariohjelmoinnin läpi? Lähes varmasti jotenkin näin:

- Se oli hauska ekstra-asia ja ohjelmoija halusi kirjoittaa sen. *(Vinkki: Kirjoita koodia, koska se lisää arvoia, älä viihdearvon takia.)*
- Joku ajatteli, että sitä saatetaan tarvita tulevaisuudessa, joten se olisi parasta koodata nyt. *(Vinkki: Se ei ole YAGNIa. Jos et tarvitse sitä nyt, älä kirjoita sitä nyt.)*
- Se ei olle kovin iso "ekstra"m joten se oli helpompi toteuttaa kuin varmistaa asiakkaalta tarvitaanko sitä varmasti. *(Vinkki: Aina kestää pidempään kirjoittaa ja ylläpitää koodia. Ja asiakas on itse asiassa melko lähestyttävä. Pieni määrä ylimääräistä koodia kasvaa ajan myötä isoksi osaksi koodia, jota täytyy ylläpitää.)*
- Ohjelmoija keksi ylimääräisen vaatimuksen, jota ei oltu dokumentoitu tai sitä ei oltu perusteltu keskusteluissa. Vaatimus oli itse asiassa väärä. *(Vinkki: Ohjelmoijat eivät määritä vaatimuksia, vaan asiakas tekee sen.)*

Minkä parissa sinä työskentelet tällä hetkellä? Tarvitaanko sitä kaikkea?

Alkuperäinen kirjoittaja [Pete Goodliffe](http://programmer.97things.oreilly.com/wiki/index.php/Pete_Goodliffe)