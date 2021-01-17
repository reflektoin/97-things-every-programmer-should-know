# Älä söpöile testidatalla

> *Alkoi olla myöhä. Olin laittamassa paikanpitäjädataa testatakseni sivun asettelua(layout).*

> *Käytin käyttäjiän The Clashin jäseniä. Yrityksien nimet? Sex Pistolssin kappaleiden nimet ovat sopivia. Sitten tarvitsin pörssikoodien(ticker) symboleita - vain joitain nelikirjaimisia sanoja isoilla kirjaimilla.*

> *Käytin **niitä** nelikirjaimisia sanoja.*

> *Se tuntui harmittomalta. Vain jotain itseni viihdyttämiseksi, ja ehkä muut kehittäjät lisäisivät oikean tiedonlähteen seuraavana päivänä.

> *Seuraavana aamuna projektin vetäjä otti kuvakaappauksia esitystään varten.**

Ohjelmoinnin historia on pullollaan tällaisia tarinoita. Asioita, joita kehittäjät ja suunnittelijat tekivät, "joita kukaan ei koskaan näkisi", jotka kuitenkin tulivat yllättäen näkyviin.

Vuodon tyyppi saattaa vaihdella, mutta sen tapahtuessa se voi aiheuttaa suurta vahinkoa henkilölle, tiimille tai yritykselle. Esimerkkejä ovat muun muassa:

- Status-palaverin aikana asiakas klikkaa painiketta, jota ei ole vielä toteutettu. Heille sanotaan: "Älä klikkaa sitä uudelleen. Senkin ääliö."

- Legacy-järjestelmän ylläpitäjää on pyydetty lisäänään virhedialogi ja hän päättää käyttää tulosteena olemassaolevaa kulissien takana olevaa loggausta sen luomiseen. Käyttäjät saavat yllättäen viestejä kuten "Pyhä tietokanta commit virhe, Batman!" jonkin mennessä hajalle.

- Jollain menee testi- ja tuotantoympäristöt ja syöttää jotain "hauskaa" tietoa. Asiakkaat huomaavat 1 milj. dollarin "Bill Gatesin muotoisen hierontavälineen" myyntitapahtuman verkkokaupassaan.

Omiakseni vanhan sanonnan "vale voi matkustaa puoli maapalloa totuuden vasta laittaessa kenkiä jalkaan", nykypäivänä Duggata, twiitata ja flibflarbata enenn kuin kukaan kehittäjän aikavyöhykkeellä on tekemässä asialle mitään.

Lähdekoodisikin saattaa joutua tarkkailun alaiseksi. Vuonna 2004, kun Windows 2000 lähdekoodin sisältämä tervapallo(tarball) löysi tiensä tiedostojenjako-verkkoihin, jotkut iloisesti etsivät sieltä kirosanoja, loukkauksia ja [ja muuta hauskaa sisältöä](http://www.kuro5hin.org/story/2004/2/15/71552/7795). (Kommenttia `// TERRIBLE HORRIBLE NO GOOD VERY BAD HACK`, myönnän, käytän joskus itsekin!)

Yhteenvetona, kirjoittaessasi mitään tekstiä koodiisi - oli se sitten kommentteja, loggausta, dialogeja tai testidataa - aina kysy itseltäsi miltä se näyttäisi tullessaan julkiseksi.

Se säästää monia punastuneita kasvoja.

Alkuperäinen kirjoittaja [Rod Begbie](http://programmer.97things.oreilly.com/wiki/index.php/Rod_Begbie)