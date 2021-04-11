# Yksi Binääri

Olen nähnyt useita projekteja, joissa koonti(build) uudelleenkirjoittaa jonkun koodin osan generoidakseen erikois-binäärin jokaseen kohdeympäristöön. Tämä monimutkaistaa asioita tarpeettomasti ja tuo riskin, että tiimilla ei ole johdonmukaisia versioita jokaisesta asennuksesta. Vähimmillään se sisältää monien lähes identtisten kopioiden koonnin ohjelmistosta, joista jokainen täytyy ottaa käyttöön oikeassa paikassa. Se tarkoittaa tarpeettoman monta liikkuvaa asiaa, mikä tarkoittaa enemmän mahdollisuuksia tehdä virheitä.

Työskentelin kerran tiimissä, missä jokainen muutos piti kirjata sisään (check in) täyttä koontia varten, joten testaajat joutuivat odottamaan aina, kun pieni muutos tehtiin (mainitsinko, että koonti myös kesti erittäin pitkään?). Työskentelin myös tiimissä, jossa järjestelmänvalvojat vaativat järjestelmän koontia alusta lähtien tuotantoon siirtoa varten (meidän skriptiämme käyttäen), mikä tarkoitti, ettei meillä ollut todisteitä, että versio tuotannossa oli sama, joka oli testattu. Ja niin edelleen.

Sääntö oli yksinkertainen: *Kokoa yksi binääri, jonka voit tunnistaa ja kuljettaa jokaisen julkaisuputken vaiheen läpi.* Pidä ympäristökohtaiset yksityiskohdat muuttujassa. Tämä tarkoittaa esimerkiksi niiden pitämistä komponenttikontissa(component container), tietyssä tiedostossa tai polussa.

Jos tiimilläri on koodin sekoittamis-koonti tai säilyttää kaikki kohteiden asetukset koodissa, se viittaa siihen, ettei kukaan ole ajatellut suunnittelua riittävästä, eriyttääkseen sovelluksen ytimen ominaisuudet alusta-kohtaisista ominaisuuksista. Tai asiat voisivat olla huonommin: tiimi tietää, mitä tehdä mutta ei priorisoi muutoksen tekemistä.

Tottakai poikkeuksiakin on: Saatat koota kohteille, joiden resurssirajoitukset vaihtelevat suuresti, mutta se ei päde suurimpaan osaan meistä, ketkä kirjoittavat "tietokannasta näytölle ja takaisin" -tyylisiä ohjelmia. Tai sitten, saatat elää perintösovelluksen kanssa, jonka sotkuja on liian vaikea korjata tällä hetkellä. Sellaisissa tapauksissa sinun on edetttävä asteittain - mutta aloitettava mahdollisimman nopeasti.

Ja vielä yksi asia. Pidä versioita myös ympäristön tiedoista. Ei ole mitään ikävempää kuin rikkoa ympäristön asetukset ja olla kykenemätön selvittämään, mitä tapahtui. Ympäristön tiedost pitäisi versioda koodista erikseen, koska ne muuttuvat eri tahtiin ja eri syistä. Jotkut tiimit käyttävät tähän hajautetttua versionhallintaan (kuten bazaar ja git, koska ne helpottavat tuotantoympäristöön tehtyjen muutosten -  mikä väistämättä tapahtuu - siirtämistä takaisin repositorioon.

Kirjoittanut [Steve Freeman](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Freeman)