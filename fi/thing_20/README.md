# Julkaise Aikaisin ja Usein

Julkaisu- ja asennusprosessien debuggaus j�tet��n usein projektin loppuun. Joissain projekteissa asennusty�kalut kirjoittaa asennus-insin��ri(release engineer), joka ottaa ty�n vastaan pitkin hampain. Katselmoinnit ja esitykset tehd��n k�sin tehdyiss� ymp�rist�iss�, jotta varmistutetaan kaiken toimiminen. Lopputuloksena tiimi ei saa yht��n kokemusta julkaisuprosessista tai tuotantoymp�rist�st� ennen kuin on my�h�ist� tehd� muutoksia.

Asennus/julkaisuprosessi on ensimm�inen asia, mit� asiakas n�kee ja yksinkertainen asennus/julkaisuprosessi on ensimm�inen askel luotettavaan (tai ainakin helpommpin debuggattavaan) tuotantoymp�rist��n. Julkaistu ohjelmisto on se, mit� asiakas tulee k�ytt�m��n. Kun ei varmistuta julkaisun kunnollisesta sovelluksen asennuksesta, kysyt asiakkaalta ennen kuin he p��sev�t k�ytt�m��n ohjelmistoa kunnolla.

Aloittamalla projektisi asennusprosessista annat prosessille aikaa kehitty� siirtyess�si tuotekehitys-sykliin ja mahdollisuus tehd� sovellukseen muutoksia, jotta asennus helpottuisi on helpompaa. Ajamalla ja testaamalla asennusprosessia ajoittain puhtaassa ymp�rist�ss� my�s mahdollistaa tarkastuksen, ett� et ole tehnyt oletuksia koodissa, jotka luottavat kehitys- tai testiymp�rist�ihin.

Siirt�m�ll� julkaisun viimeiseksi tarkoittaa, ett� julkaisuprosessin ymp�ri saattaa olla hankalampi ty�skennell� tehtyjen oletuksien takia. Hyv� idea ohjelmointiymp�rist�ss�, jossa sinulla on t�ysi valta ymp�rist�s� saattaakin olla paljon monimutkaisempi julkaisuprosessissa (deployment process). On parempi tiet�� kaikki kompromissit aiemmin kuin my�hemmin.

Vaikka "kyky ottaa tuotantoon" ei vaikuta tarjoavan paljoa arvoa varhaisessa vaiheessa verrattuna ajettavaan ohjelmaan kehitt�j�n kannettavalla, yksinkertainen totuus on, ett� ennen kuin ohjelma on kohdeymp�rist�ss�, niin j�ljell� on paljon ty�t� ennen kuin se tuottaa arvoa liiketoiminnalle. Jos syy julkaisuprosessin siirt�miselle on, ett� se on triviaalia, tee se silti, koska se ei maksa paljoa. Jos se on liian hankalaa tai sis�lt�� liikaa ep�varmuustekij�it�, tee mit� tekisit ohjelmiston koodille: kokeile, arvioi, refaktoroi julkaisuprosessia edetess�si.

Asennus/julkaisuprosessi on v�ltt�m�t�n asiakkaittesi tuottavuudelle tai sinun tiimillesi, sinun pit�isi testata ja refaktoroida prosessia jatkuvasti. Me testaamme ja refaktoroimme l�hdekoodia koko projektin ajan. Julkaseminen ei ansaitse v�hemp��.

Alkuper�inen kirjoittaja [Steve Berczuk](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Berczuk)