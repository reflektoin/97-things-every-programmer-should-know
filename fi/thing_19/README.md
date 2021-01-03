# Mukavuus ei kuulu "uus"iin
# Convenience Is not an -ility

On sanottu paljon APIen suunnittelun tärkeydestä ja haasteista. Se on vaikea saada oikein ensimmäisellä kerralla ja se on vielä vaikeampaa muuttaa myöhemmin. Hieman kuin lasten kasvatus. Kokeneimmat kehittäjät ovat oppineet, että hyvä API noudattaa johdonmukaista abstraktiotasoa, ilmaisee johdonmukaisuutta ja symmetriaa, sekä muodostaa sanaston ilmaisuvoimaiselle kielelle. Valitettavasti näiden ohjeiden tietäminen ei välttämättä muunnu kunnolliseksi toiminnaksi. Karkkien syöminen on pahaksi sinulle.

Saarnaamisen sijaan haluan valita tietyn APIn suunnittelemisen "strategian, johon olen useasti törmännyt: mukavuuden perustelu(argument of convenience). Se normaalisti alkaa yhdellä seuraavista "oivalluksista:"

- En halua muiden luokkie tekevän kahta erillistä kutsua tehdäkseen tämän yhden asian.
- Miksi minun pitäisi tehdä toinen metodi, jos se on lähse sama kuin tämä? Lisään vain yksinkertaisen valintalauseen(switch).
- Katsos, se on erittäin helppoa: Jos toinen merkkijono-parametri päättyy ".txt", metodi automaattisesti olettaa ensimmäisen parametrin olevan tiedostonimi, joten en tarvitse kahta metodia.

Vaikka aie on hyvä, tuollaisilla perusteluilla on taipumus vähentää APIa käyttävän koodin luettavuutta. Esimerkiksi metodikutsu

```
parser.processNodes(text, false);
```

on käytännössä merkityksetön ilman tietoa toteutuksesta, tai vähintään ilman dokumentaation lukemista. Tämä metodi todennäköisesti suunniteltiin toteuttajan mukavuutta ajatellen kutsujan sijaan - "En halua kutsujan tarvitsevan tehdä kahta erillistä kutsut" käännettynä "En halunnut koodata kahta erillistä metodia." Mukavuudessa ei ole pohjimmiltaan mitään väärää jos se vähentää ikävyyttä, kömpelyyttä tai kiusallisuutta. Mutta tarkemmin ajatellen vastalääke noihin oireisiin on tehokkuus, yhdenmukaisuus ja eleganssi, ei välttämättä mukavuus. APIen pitäisi piilottaa takana oleva monimutkaisuus, joten voimme realistisesti olettaa APIn suunnittelun vaativan jonkin verran vaivannäköä. Yksi iso metodi voi olla mukavampi kirjoittaa kuin joukko tarkkaan mietittyjä operaatioita, mutta kumpaa olisi helpompi käyttää?

Metafora APIsta kielenä voi auttaa meitä parempiin suunnittelupäätöksiin näissä tilanteissa. APIn pitäisi tarjoita ilmaiseva kieli, joka seuraavalle tasolle riittävän sanaston kysyä ja vastata hyödyllisiin kysymyksiin. Tämä ei merkitse,että sen pitäisi tarjota yksi metodi, tai verbi jokaiselle kysyttävälle kysymykselle. Laaja sanasto sallii meidän ilmaista hienovaraisia merkityksiä. Esimerkiksi sanomme mielummin aja(run) kuin kävele(walk), vaikka molemmat olisivat käytännössä sama operaatio, vain toteutettuna eri nopeuksilla. Johdonmukainen ja hyvin ajateltu API-sanasto tekee seuraavalla tasolla olevasta koodista ilmaisevan ja helposti ymmärrettävän. Vielä tärkeämpää, yhteensopva(composable) sanasto sallii muiden ohjelmian käyttää APIa tavoin, joita et osannut odottaa - erittäin mukavaa APIn käyttäjille! Seuraavalla kerralla kun käy kiusaus niputtaa yhteen muutama asia yhteen API-metodiin, muista ettei suomen kielessä ole yhtä sanaa teolle "SiivoaHuoneesiOleHiljaaJaTeeKotitehtäväsi", vaikka sellainen olisikin näppärä niin useasti pyydetylle toiminnalle.

Alkuperäinen kirjoittaja [Gregor Hohpe](http://programmer.97things.oreilly.com/wiki/index.php/Gregor_Hohpe)