# Ohjelmoi toimialueen (domain) kielellä

Kuvittele kaksi koodikantaa(codebase). Toisessa tulee vastaan:

```
if (portfolioIdsByTraderId.get(trader.getId())
  .containsKey(portfolio.getId())) {...}
```

Raaputat päätäsi miettien mitä kyseinen koodi tekee. Se vaikuttaa hakevan ID:n trade-oliolta käyttäen ID:tä assosiaatiotaulun(map) hakuun, no, nähtävästi assosiaatiotaulujen assosiaatiotaulusta ja sen jälkeen tarkastaa jos toinen ID portfolio-oliosta löytyy sisemmästä assosiaatiotaulusta. Raaputat päätäsi hieman enemmän. Etsit portfolioIdsByTraderId:n määritystä ja löydät tämän:

```
Map<int, Map<int, int>> portfolioIdsByTraderId;
```

Asteittan ymmärrät, että se saattaa liittyä traderin oikeuksiin käsitellä kyseistä portfoliota. Ja totta kai löydät saman etsintäosion(lookup fragment) - tai todennäköisesti samankaltaisen, mutta hieman erilaisen koodin osan - aina kun on väliä, saako onko traderilla oikeuksia kyseiseen portfolioon.

Toisessa koodikannassa törmäät tähän:

```
if (trader.canView(portfolio)) {...}
```

Ei pään rapsutusta. Sinun ei tarvitse tietää, miten traderi tietää. Ehkä siellä on yksi näistä assosiaatiotaulujen assosiaatiotauluista piilotettuna jonnekin sisälle. Mutta se on traderin asia, ei sinun.

Kumman koodikannan kanssa mielummin työskentelisit?

Kauan sitten meillä oli vain muutama tietotyyppi: bitit, tavut ja merkit (todellisuudessa vain tavut, mutta teeskentelimme niiden olevan kirjaimia ja välimerkkejä). Desimaalit olivat hankalia, koska 10-kantaiset numerot eivät yhteensopineet binäärin kanssa kunnolla, joten meillä oli useita erikokoisia liukulukutyyppejä. Sitten tuli taulukot ja merkkijonot (todellisuudessa vain erilaisia taulukoita). Sitten saimme pinoja, jonoja, silppuja(hash), linkitettyjä listoja ja skip listoja ja monia muita jännittäviä tietorakenteita, *joita ei ole todellisuudessa olmassa*. "Tietojenkäsittelytiede" oli todellisten ongelmien kuvaamista meidän rajoittaviin tietorakenteisiin. Todelliset gurut pystyivät jopa muistamaan miten he olivat tehneet sen.

Sitten saimme käyttäjien määrittämät tyypit! OK, tämä ei ollut uutta, mutta se muuttaa tilannetta jonkin verran. Jos toimiala sisältää konsepteja kuten treideeja ja portfoliot, voit mallintaa(model) niitä esimerkiksi tyypeillä Treidaaja ja Portfolio. Mutta tätä tärkeämpää on *niiden suhteiden* mallintaminen toimialueen termejä käyttäen.

Jos et ohjelmoi toimialueen termejä käyttäen luot äänettömän (lue:salaisen) ymmärryksen, että *tämä* int tässä tarkoittaa tapaa tunnistaa treidaaja, kun taas *tuo* int tuossa tarkoittaa tapaa tunnistaa portfolio. (Parasta välttää niiden sekoittaminen!) Ja jos esität bisneskonseptin ("Jotkut treidaajat eivät saa nähdä joitain portfolioita - se on laitonta") algoritmin pätkällä, sanotaan suhteen olemassaolo assosiaatiotaulun avaimien kesken, etkä helpota auditoinnin(audit) ja sisäisen valvonnan(compliance) henkilöiden työtä.

Seuraava ohjelmoija ei välttämättä tiedä salaisuutta, joten mikset tekisi siitä eksplisiittistä? Käyttäen avainta toiseen avaimen hakemiseen(lookup), joka tarkastaa olemassaolon ei ole kovin selkeää. Miten joku pystyy päättelemään, että siinä kohtaa bisnessääntö(business rule) eturistiriitan estämiseksi on toteutettu?

Toimialan konseptien eksplisiittiseksi tekeminen koodissasi tarkoittaa muiden ohjelmoijien pystyvän helpommin selvittämään koodin *aikomus*, kuin yrittää sovittaa algoritmi heidän ymmärrykseen toimialasta. Se tarkoittaa myös, että toimialamallin(domain model) kehittyessä - joka tapahtuu toimialan ymmärryksesi kasvaessa - olet paremmassa asemassa muuttamaan koodia. Liitettynä hyvään kapselointiin, on hyvä tidennäköisyys, että sääntö on vain yhdessä paikkaa ja voit muuttaa sitä riippuvuuksista huolimatta(you can change it without any of the dependent code being any the wiser).

Ohjelmoija, joka työskentelee koodin kanssa muutaman kuukauden päästä tulee kiittämään sinua. Ohjelmoija, joka työskentelee koodin kanssa muutaman kuukauden päästä saattaa olla sinä.

Alkuperäinen kirjoittaja [Dan North](http://programmer.97things.oreilly.com/wiki/index.php/Dan_North)