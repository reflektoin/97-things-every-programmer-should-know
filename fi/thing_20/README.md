# Julkaise Aikaisin ja Usein

Julkaisu- ja asennusprosessien debuggaus jätetään usein projektin loppuun. Joissain projekteissa asennustyökalut kirjoittaa asennus-insinööri(release engineer), joka ottaa työn vastaan pitkin hampain. Katselmoinnit ja esitykset tehdään käsin tehdyissä ympäristöissä, jotta varmistutetaan kaiken toimiminen. Lopputuloksena tiimi ei saa yhtään kokemusta julkaisuprosessista tai tuotantoympäristöstä ennen kuin on myöhäistä tehdä muutoksia.

Asennus/julkaisuprosessi on ensimmäinen asia, mitä asiakas näkee ja yksinkertainen asennus/julkaisuprosessi on ensimmäinen askel luotettavaan (tai ainakin helpommpin debuggattavaan) tuotantoympäristöön. Julkaistu ohjelmisto on se, mitä asiakas tulee käyttämään. Kun ei varmistuta julkaisun kunnollisesta sovelluksen asennuksesta, kysyt asiakkaalta ennen kuin he pääsevät käyttämään ohjelmistoa kunnolla.

Aloittamalla projektisi asennusprosessista annat prosessille aikaa kehittyä siirtyessäsi tuotekehitys-sykliin ja mahdollisuus tehdä sovellukseen muutoksia, jotta asennus helpottuisi on helpompaa. Ajamalla ja testaamalla asennusprosessia ajoittain puhtaassa ympäristössä myös mahdollistaa tarkastuksen, että et ole tehnyt oletuksia koodissa, jotka luottavat kehitys- tai testiympäristöihin.

Siirtämällä julkaisun viimeiseksi tarkoittaa, että julkaisuprosessin ympäri saattaa olla hankalampi työskennellä tehtyjen oletuksien takia. Hyvä idea ohjelmointiympäristössä, jossa sinulla on täysi valta ympäristösä saattaakin olla paljon monimutkaisempi julkaisuprosessissa (deployment process). On parempi tietää kaikki kompromissit aiemmin kuin myöhemmin.

Vaikka "kyky ottaa tuotantoon" ei vaikuta tarjoavan paljoa arvoa varhaisessa vaiheessa verrattuna ajettavaan ohjelmaan kehittäjän kannettavalla, yksinkertainen totuus on, että ennen kuin ohjelma on kohdeympäristössä, niin jäljellä on paljon työtä ennen kuin se tuottaa arvoa liiketoiminnalle. Jos syy julkaisuprosessin siirtämiselle on, että se on triviaalia, tee se silti, koska se ei maksa paljoa. Jos se on liian hankalaa tai sisältää liikaa epävarmuustekijöitä, tee mitä tekisit ohjelmiston koodille: kokeile, arvioi, refaktoroi julkaisuprosessia edetessäsi.

Asennus/julkaisuprosessi on välttämätön asiakkaittesi tuottavuudelle tai sinun tiimillesi, sinun pitäisi testata ja refaktoroida prosessia jatkuvasti. Me testaamme ja refaktoroimme lähdekoodia koko projektin ajan. Julkaseminen ei ansaitse vähempää.

Alkuperäinen kirjoittaja [Steve Berczuk](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Berczuk)