# Beware the Share

Se oli ensimmäinen projektini firmassa. Olin juuri valmistunut ja valmis todistamaan itseni, työskentelemään myöhään joka päivä käyden läpi olemassaolevaa koodia. Ensimmäistä ominaisuutta työstäessäni kiinnitin erityistä huomiota kaikkeen, minkä olin oppinut - kommentit, seuranta, jaetusta koodista kirjastojen teko, kaikki. Katselmointi, johon koin olevan täysin valmis, tuli ikävänä yllätyksenä. Uudelleenkäyttö oli paheksuttavaa!

Kuinka näin voi olla? Koko opintojen ajan uudelleenkäyttöä pidettiin laadukkaan ohjelmistotuotannon ruumiillistumana. Kaikki lukemani artikkelit, oppikirjat ja kokeneet ammattilaiset, jotka opettivat minua. Oliko se kaikki väärin?

Kävi ilmi, että minulta puuttui jotain kriittistä.

Konteksti.

Se, että kaksi erilaista järjestelmän osaa suorittivat jonkin asian samalla tavalla vaikutti vähemmän kuin olin ajatellut. Kunnes eriytin jaetun koodin kirjastoksi, nämä osat eivät olleet riippuvaisia toisistaan. Kumpikin pystyi kehittymään itsenäisesti. Kumpikin psytyi muuttamaan toimintaansa sopimaan järjestelmän muuttuvaan toimintaympäristöön. Nuo neljä riviä samankaltaista koodia syntyivät vahingossa — ajallinen poikkeama, yhteensattuma. Kunness minä tulin kuvioihin.

order of magnitudeKirjasto, jonka loin sitoi kenkien kengännauhat ristiin. Toisen toimialan vaiheita ei pysty tekemään ilman synkronisointia toisen kanssa. Itsenäisten funktioiden ylläpitokustannukset olivat olemattomat, mutta yhteinen kirjasto vaati kertaluokkaa enemmän testausta.

Samaan aikaan kun olin vähentänyt absoluuttista koodirivien määrää järjestelmässä, olin lisännyt riippuvuuksien määrää. Riippuvuuksien konteksti on tärkeä, jos ne olisivat paikallisia, se olisi ehkä oikeutettua ja tuonut lisäarvoa. Kun riippuvuuksia ei pidetä silmällä, niiden jänteet sotkevat järjestelmän suurempaa kuvaa, vaikka itse koodi näyttää kunnolliselta.

Nämä virheet ovat siitä pirullisia, että ne kuulostavat hyvältä idealta. Kun ne tehdään oikeassa kontekstissa, näm tekniikat ovat arvokkaita. Väärässä kontekstissa ne lisäävät kuluja eikä arvoa. Kun tutustun uuteen koodiin ilman kontekstia, missä osia käytetään. Olen nykyisin paljon varovaisempi, mitä kannattaa jakaa.

Varo jakamista, Tarkasta kontekstisi. Vasta sitten, etene.

Alkuperäinen kirjoittaja [Udi Dahan](http://programmer.97things.oreilly.com/wiki/index.php/Udi_Dahan)