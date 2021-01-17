# Älä Jätä Huomioimatta sitä Erroria!

> *Yhtenä iltana olin kävelemässä baariin tapaamaan kavereitani. Emme olleet käyneet oluella toviin ja odotin heidän näkemistään. Kiireessä en katsonut mihin kävelin. Kompastuin jalkakäytävän reunaan ja kaaduin kasvot edellä maahan. No, sen siitä kait saa kun ei keskity tekemiseensä.*

> *Satutin jalkani, mutta minulla oli kiire tavata kaverini. Joten nousin ylös ja jatkoin matkaa. Kävellessäni kipu vain paheni. Vaikka aluksi sivuutin sen shokkina, tajusin nopeasti jonkin olevan pielessä.*

> *Mutta siitä huolimatta kiirehdin baariin. Olin tuskissani sinne saapuessani. Ilta ei ollut mahtava, koska en pystynyt keskittymään. Aamulla menin lääkärille, jossa selvisi sääriluuni murtuneen. Jos olisin lopettanut kipua tuntiessani, olisin säästynyt kävelyn aiheuttamalta vahingolta. Se oli luultavasti elämäni huonoin aamu(morning after).*

Liian moni kehittäjä kirjoittaa sellaista koodia kuin tuhoisa iltani ulkona.

*Virhe, mikä virhe? Se ei ole mitään vakavaa. Oikeasti. Voin sivuuttaa sen.* Tämä ei luotettavaa koodia(solid code) tuottava strategia. Itse asiassa se on silkkaa laiskuutta. (Vääränlaista laiskuutta.)  Riippumatta siitä, miten epätodennäköinen virhe mielestäsi on, sinun pitäisi tarkastaa ja käsitellä se. Joka kerta. Et säästä aikaa jättämällä sitä tarkastamatta: Keräät mahdollisia ongelmia tulevaisuuteen.

Raportoimme virheitä kodissamme monin tavoin:

- **Palaamis-koodeja(Return codes)** voidaan käyttää kertomaan, ettei funktio toiminut. Nämä koodit on aivan liian helppo sivuuttaa. Et näe koodissa mitään, joka korostaa ongelmaa. Todellakin, yleiseksi käytännöksi on tullut sivuuttaa jotkin standardi C-funktioiden palautusarvot. Kuinka usein tarkastat printf-komennon palautusarvon?

- **errno** on mielenkiintoinen C-kielen poikkeama, erillinen globaali muuttuja kertomaan virheestä. Se on helppo sivuuttaa, vaikea käyttää ja johtaa kaikenlaisiin ikäviin ongelmiin - esimerkiksi mitä tapahtuu usean säikeen kutsuessa samaa funktiota? Jotkut alustat eristävät sinut tältä tuskalta, toiset eivät.

- **Poikkeukset(Exception)** ovat enemmän strulturoitujen ohjelmointikielien tukema tapa ilmoittaa ja käsitellä virheitä. Etkä voi millään tavoin sivuuttaa niitä. Vai voitko? Olen nähnyt paljon tällaista koodia:

```
try {
    // ...do something...
}
catch (...)
 {} // ignore errors
```

Valopilkkuna tässä on, että se korostaa sinun tekevän jotain moraalisesti arveluttavaa.

Jos sivuutat virheen, katsot läpi sormien ja teeskentelet ettei virhettä tapahtunut, otat suuria riskejä. Aivan kuten jalkani tila paheni, koska en lopettanut kävelemistä heti, jatkaminen virheistä huolimatta voi johtaa monimutkaisiin häiriöihin. Käsittele ongelmat mahdollisimmat varhain. Pidä kirjaa(keep a short account).

Virheiden käsittelemättä jättmäminen johtaa:

- *Hauraaseen koodiin.** Koodi, joka on täynnä jännittäviä vaikeasti paikannettavia vikoja.

- **Turvattomaan koodiin.** Krakkerit käyttävät usein hyväksi huonoa virheiden käsittelyä murtautuakseen järjestelmiin.

- **Huonoon rakenteeseen.** Jos koodissasi on virheitä, jotka on jatkuvasti hankala käsitellä, sinulla saattaa olla huono rajapinta. Ilmaise se nii, että virheet ovat vähemmän tunkeilevia(intrusive) ja niiden käsittely on helpompaa.

Aivan kuten sinun täytyy tarkastaa kaikki mahdolliset virheet koodissasi, sinun tulee paljastaa mahdolliset virheet rajapinnoissasi. Älä piilota niitä, kuvitellen että palvelusi toimivat aina.

Miksi emme tarkasta virheitä? On lukuisia yleisiä tekosyitä. Mistä olet samaa mieltä? Miten vastaisit(counter) näihin?

- Virheiden käsittely sekoittaa koodin kulun, tekee siitä vaikealukuista ja vaikeamman eroittaa "normaali" ohjelman kulku.

- Se tuottaa lisätyötä ja määräaika lähestyy.

- Tiedän, että tämä funktiokutsu ei *koskaan* palauta virhettä (printf toimii aina, malloc aina palauttaa uuden muistipaikan  jos se epäonnistuu meillä on suurempia ongelmia...).

- Se on vain leikkiohjelma, meidän ei tarvitse kirjoittaa tuotanto-tason(production-worthy level) koodia.

Alkuperäinen kirjoittaja [Pete Goodliffe](http://programmer.97things.oreilly.com/wiki/index.php/Pete_Goodliffe)