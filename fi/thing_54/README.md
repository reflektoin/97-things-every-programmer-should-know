# Tilapäisten(interim) ratkaisujen pitkäikäisyys

Miksi teemme tilapäisiä ratkaisuita?

Yleensä joku välitön ongelma täytyy ratkaista. Se saattaa olla tiimin sisäinen ongelma, jokin työkalu joka täyttää aukon työkaluketjussa. Se saattaa olla ulkoinen, loppukäyttäjille näkyvä, kuten puutteellisen toiminnallisuuden toteuttava workaround.

Monista järjestelmistä ja tiimeistä löydät jotain ohjelmistoja, jotka eivät ole yhtenäisiä muun järjestelmän kanssa, mikä koetaan vedokseksi(draft), jota muutetaan tulevaisuudessa, joka ei noudata muun koodin muotoilemia standardeja ja ohjeita. Väistämättä kuulet kehittäjien valittavan näistä. Syitä niiden tekemiseen on lukuisia erilaisia, mutta avain väliaikaisten ratkaisuiden menestykseen on yksinkertainen: Se on hyödyllistä.

Väliaikaiset ratkaisut kerryttävät inertiaa (tai momentumia riippuen näkokulmastasi). Koska ne ovat olemassa ja loppuen lopuksi hyödyllisiä ja yleisesti hyväksyttyjä, ei ole välitöntä tarvetta tehdä mitään muuta. Aina sidosryhmän jäsenen päättäessä, mikä toiminto lisää eniten arvoa, on lukuisia korkeammalle sijoittuvia asioita kuin väliaikaisen ratkaisujen kunnollinen integrointi. Miksi? Koska se on siellä, se toimii ja se on hyväksytty. Ainut havaittava haitta on ettei se seuraa valittuja standardeja ja ohjeita - muutamaa nicheä lukuunottamatta tämä ei ole iso haitta.

Joten väliaikainen ratkaisu pysyy paikoillaan. Ikuisesti.

Ja väliaikaisessa ratkaisussa ilmenee ongelma, on epätodennköistä että se päivitetään yhtä laadukkaaksi kuin muu tuotantoon menevä koodi. Mitä tehdä? Nopea väliaikainen päivitys väliaikaiseen ratkaisuun yleensä riittää. Ja todennäköisesti saa hyvän vastaanoton. Sillä on samat vahvuudet kuin alkuperäisellä väliaikaisella ratkaisulla... se on vain paremmin ajan tasalla.

Onko tämä ongelma?

Vastaus riippuu projektistasi ja sinun osastasi tuotantokoodin laadussa. Kun järjestelmä sisältää liikaa tilapäisiä ratkaisuita sen entropia tai sisäinen monimutkaisuus kasvaa ja sen ylläpidettävyys vähenee. Kuitenkin tämä on luultavasti väärä asia kysyä ensimmäiseksi. Muista, että puhumme ratkaisusta. Se ei välttämättä ole mieluisin ratkaisusi - se ei todennäköisesti ole kenenkään mieluisin ratkaisu - mutta motivaatio ratkaisun muokkaamiselle on vähäinen.

Joten mitä voimme tehdä nähdessämme ongelman?

1. Vältä väliaikaisten ratkaisujen luomista alun alkaen.

- Muuta vaikutuksia/voimia, jotka vaikuttavat projektipäällikön päätökseen.

- Jätä se sellaiseksi kuin se on.

Tarkastellaan jokaista tarkemmin:

1. Välttely ei toimi useimmissa paikoissa. On ratkaistava ongelma ja standardit ovat käyneet liian rajoittaviksi. Sinun saattaa tarvita käyttää energiaa yrittää muuttaa standardeja. Kunniallinen mutta työläs tehtävä... ja muutos ei tule olemaan valmis nykyistä ongelmaasi varten.

- Voimat ovat juurtuneet projektin kulttuuriin, joka vastustaa halukasta muutosta. Se voisi olle onnistunut pienissä projekteissa - eritotetn jos kyse on vain sinusa - ja sinä voit vain korjata sotkun kysymättä etukäteen. Se voi myös onnistua jos projekti on niin sotkuinen, että se näkyvästi pysäthyy ja jonkun verran siivousta hyväksytään.

- Status quo automaattisesti pätee jos aiempi ei toimi.

Luot monia ratkaisuita, osa niistä on tilapäisiä ja suurin osa niistä tulee olemaan hyödyllisiä. Paras tapa nujertaa väliaikaiset ratkaisut on tehdä niistä tarpeettomia, tarjota hienostuneempi ja hyödyllisempi ratkaisu. Suotakoon sinulle [tyyneys](http://en.wikipedia.org/wiki/Serenity_prayer) hyväksyä asiat joita et voi muuttaa, rohkeutta muuttaa, mitkä voit, ja viisautta erottaa nämä toisistaan.

Kirjoittanut [Klaus Marquardt](http://programmer.97things.oreilly.com/wiki/index.php/Klaus_Marquardt)