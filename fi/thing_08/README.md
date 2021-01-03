# Partiolaissääntö

Partiolaisilla on sääntö: "Jätä aina leirintäalue siistimmäksi kuin se oli tullessasi." Jos löydät roskia, korjaa ne siitä huolimatta, kuka ne jätti. Siistit ympäristöä tietoisesti seuraavalle telttailijoille. Oikeastaan säännön alkuperäinen muoto, jonka kirjoitti Robert Stephenson Smyth Baden-Powell, partioliikkeen perustaja, oli "Yritä ja jätä tämä maailma hieman paremmaksi kuin se oli löytäessäsi."

Entä jos noudattaisimme samankaltaista sääntöä koodissamme: "Tarkasta aina, että moduuli on siistimpi kuin otit sen käsittelyyn." Alkuperäisestä kirjoittakasta riippumatta, entä jos aina, riippumatta parannuksen suuruudesta, pyrkisimme parantamaan modulia. Mikä olisi lopputulos?

Luulen, että jos me kaikki seuraisimme tuota yksinkertaista sääntöä, loppuisi järjestelmiemme periksiantamaton huonontuminen. Sen sijaan järjestelmämme parantuisivat hiljalleen niiden kehittyessä. Näkisimme myös *tiimien* välittävän koko järjestelmästä, sen sijaan että yksilöt välittäisivät vain omasta pienestä osastaan.

En usko että tämä sääntö on liikaa vaadittu. Sinun ei tarvi tehdä jokaisesta modulista täydellistä ennen kuin lisäät sen versionhallintaan. Sinun tarvitsee tehdä siitä *vain hieman parempi*, kuin se alussa oli. Tottakai, tämä tarkoittaa, että mikä tahansa koodi, minkä *lisäät* moduliin tulee olla siisti. Se myös tarkoittaa, että siistis ainakin yhden toisen asian ennen kuin lisäät muutoksen versionhallintaan. Saatat esimerkiksi parantaa yksittäisen muuttujan nimeä tai jakaa yhden pitkän funktion kahteen pienempään funktioon. Saatat katkaista kehämäisen riippuvuuden (circular dependency) tai lisätä rajapinnan irrottaaksesi toimintaperiaatteen(policy) yksityiskohdista (detail).

Suoraan sanottuna, tämä kuulostaa vain hyviltä tavoilta - kuten käsien peseminen vessassa käynnin jälkeen tai roskien laittaminen roskakoriin laittialle pudottamisen sijaan. Tosiaan koodin jättäminen sotkuiseksi pitäisi olla yhtä sosiaalisesti sopimatonta kuin *roskaaminen*. Sen pitäisi olla jotain *mitä ei yksinkertaisesti tehdä*.

Mutta sillä on myös suurempi merkitys. Omasta koodistammi välittäminen on yksi asia. Tiimin koodista välittäminen on avain toinen asia. Tiimit auttavat toisiaan ja siivovavat toistensa jälkiä. He seuraava partiolaissäntöä, koska se hyödyttää kaikkia, ei vain heitä itseään.

Alkuperäinen kirjoittaja [Uncle Bob](http://programmer.97things.oreilly.com/wiki/index.php/Uncle_Bob)