# Tiedä Rajasi

> *"Henkilön täytyy tietää rajansa."
- Dirty Harry*

Resurssisi ovat rajatut. Sinulla on tietty määrä aikaa ja rahaa tehdä työsi, sisältäen tarvitsemasi ajan ja rahan tietojesi, taitojesi ja työkalujesi kunnossapitämiseen. Voit tehdä töitä tietyn verran, tietyllä nopeudella ja älykkyydellä tietyn aikaa. Työkalusi ovat vain tietyn tehokkaita. Kohdekoneesi(target machines) ovat vain tietyn tehokkaita. Sinun täytyy kunnioittaa resurssiesi rajoitteita.

Kuinka kunnioitat/otat ne rajat huomioon? Tunne itsesi, tunne väkesi, tunne budjettisi ja tunne juttusi. Erityisesti, ohjelmistoinsinöörinä, tiedä tietorakenteidesi ja algoritmiesi tila- ja aikakompleksisuus(space and time complexity), ja järjestelmiesi arkkitehtuuri ja suorityskykypiirteet(characteristics). Työsi on luoda optimaalinen liitto ohjelmiston ja järjestelmien välillä.

Tila- ja aikakompleksisuus annetaan funktiona *O(f(n))*, jossa n:n ollessa syötteen koko on asymptoottinen tila tai aika vaaditaan kun n kasvaa äärettömään(which for n equal the size of the input is the asymptotic space or time required as n grows to infinity). Tärkeitä kompleksisuusluokkia funktiolle *f(n)* on muun muassa *ln(n)*, *n*, *n ln(n)*, *n<sup>e</sup>*, and *e<sup>n</sup>*. Funktioiden piirtäminen näyttää, kun *n* kasvaa *O(ln(n))* on pienempi kuin *O(n)* ja *O(n ln(n))*, mitkä ovat pienempiä(ever so much smaller) kuin *O(n<sup>e</sup>)* ja *O(e<sup>n</sup>)*. Kuten Sean Parent asian esittää, saavutettavalla n kaikille kompleksisuusluokille amount to near-constant, near-linear, or near-infinite.

![](http://programmer.97things.oreilly.com/wiki/images/c/c0/Clearly.jpeg)


|              | access time      |   capacity |
|--------------|-----------------:| ----------:|
| register     |  < 1 ns          |        64b |
| cache line   |                  |        64B |
| L1 cache     |  1 ns            | 64 KB      |
| L2 cache     |  4 ns            | 8 MB       |
| RAM          | 20 ns            | 32 GB      |
| disk         | 10 ms            | 10 TB      |
| LAN          | 20 ms            | > 1 PB     |
| internet     | 100 ms           | > 1 ZB     |

Kompleksisuusanalyysi tehdään abstraktin koneen mukaan, mutta ohjelmisto ajetaan oikealla koneella. Modernit tietokonejärjestelmät(computer systems) on organisoitu fyysisten ja virtuaalikoneiden hierarkiaksi, sisältäen language runtimes, käyttöjärjestelmät, suorittimet, välimuistit, RAMit, levymuistin, ja verkot. Ensimmäinen taulukko näyttää RAMin ja levytilan rajat tyypiliselle palvelimelle.

Huomaa, että kapasiteetti ja nopeus vaihtelevat useita suuruusluokkia. Välimuistia ja lookaheadia(suomeksi*) käytetään järjestelmän jokaisella tasolla piilottaakseen tämän vaihtelun, mutta ne toimivat vain kun saanti(access) on ennustettavissa. Kun asia ei löydy välimuistista, järjestelmä hidastuu(thrashing). Esimerkiksi levyn satunnaisesti koko levyn tavujen tarkastelu kestäisi 32 vuotta. Jopa RAMin kaikkien tavujen satunnainen tutkiminen voisi kestää 11 minuuttia. Hajasaanti(random access) ei ole ennustettavissa. Mikä on? Se riippuu järjestelmästä, mutta äskettäin haetun uudelleenhaku(re-accessing recently used items) ja esineiden(item) haku (access) sarjassa(sequentially) ovat yleensä hyviä tapoja(are usually a win).

Algoritmit ja tietorakenteet hyödyntävät eriäviä määriä välimuistia. Esimerkiksi:
- Lineaarinen haku hyödyntää lookaheadia(suomeksi...), mutta vaatii *O(n)* vertailua.

- Järjestetyn taulukon(sorted array) binäärihaku vaatii vain *O(log(n))* vertailua.

- van Emde Boas puun haku on *O(log(n))* ja eikä käytä välimuistia(is cache-oblivious).

|Elements | Search time (ns)|       |         |
|:--------|-----------:|-----------:|--------:|
|         | **linear** | **binary** |	**vEB** |
| 8       | 50         | 90         | 40      |
| 64      | 180        | 150        | 70      |
| 512     | 1200       | 230        | 100     |
| 4096    | 17000      | 320        | 160     |


Miten valita? Viimeisessä analyysissä, mittaamalla. Toinen taulu näyttää vaaditun ajan hakea 64-bittisiä kokonaislukuja taulukosta näillä kolmella tavalla. Minun koneellani:
- Lineaarinen haku on kilpailukykyinen pienillä taulukoille, mutta häviää eksponentiaalisesti isoilla taulukoilla.
- van Emde Boas voittaa hands down, kiitos sen ennustettavan pääsymallin(access pattern).

> *"You pays your money and you takes your choice."

 — [Punch](http://www.nytimes.com/1988/02/28/magazine/on-language-you-pays-yer-money.html?pagewanted=all)*

Alkuperäinen kirjoittaja [Greg Colvin](http://programmer.97things.oreilly.com/wiki/index.php/Greg_Colvin)