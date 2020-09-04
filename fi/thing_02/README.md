# Käytä Funktionaalisen Ohjelmoinnin Periaatteita

Valtavirta-ohjelmointiyhteisön mielenkiinto funktionaalista ohjelmointia kohtaan on herännyt uudelleen. Osasyynä on, että funktionaalisen ajatusmallin *kehkeytyvät ominaisuudet* pystyvät vastaamaan haasteisiin, joita alamme moni-ytimisyyteen siirtyminen  tuo. Vaikka se onkin tärkeä käyttökohde, se ei ole syy, miksi tämä teksti kehottaa sinua oppimaan funktionaalista ohjelmointia.

Funktionaalisen ohjelmointiajatusmallin hallinta voi parantaa huomattavasti kirjoittamasi koodin laatua eri konteksteissa. Jos ymmärrät syvästi ja käytät funktionaalista ohjelmointiajatusmallia, suunnittelusi sisältää suuremman määrän *viittausten läpikuultavuutta*.

Viittausten läpikuultavuus on erittäin mieluisa ominaisuus: Se antaa ymmärtää, että funktiot antavat saman tuloksen samoilla syötteillä. Riippumatta siitä, missä ja milloin niitä kutsutaan. Eli funktion evaluaatio riippuu vähemmän — ideaalitapauksessa ei ollenkaan — muuttuvan tilan sivuvaikutuksista.

Johtava vikojen aiheuttaja imperatiivisessa koodissa on muuttuvat muuttujat. Jokainen tätä lukeva on tutkinut, miksi jokin arvo ei ole mitä pitäisi tietyssä tilanteessa. (Visibility semantics, mikä suomeksi?) voi auttaa vähentämään näitä salakavalia vikoja, tai ainakin rajata niiden sijaintia. Mutta niiden todellinen syyllinen saattaa olla suunnitelmissa, jotka käyttävät liikaa muuttuvuutta(mutability).

Emmekä saa paljoa apua toimialalta tässä asiassa. Olio-ohjelmointia esiteltäessä huomaamatta(tacitly) kannatetaan(promote) sellaisia suunnitelmia, koska he usein näyttävät esimerkkejä melko pitkäikäisistä olioista, jotka iloisesti kutsuvat muuttaja -metodeja toisilleen, joka saattaa olla vaarallista. Kuitenkin testivetoisella suunnittelulla, erityisesti kun ["Mock Roles, not Objects"](http://www.jmock.org/oopsla2004.pdf), tarpeeton muuttuvuus voidaan suunnitella pois.

Lopputuloksena on suunnitelma, jossa on tyypillisesti paremmin määritelty vastuut. Paljon pieniä funktioita, jotka käsittelevät niille annettuja argumentteja sen sijaan, että viitattaisiin muuttuviin jäsenmuuttujiin. Näissä suunnitelmissa tulee olemaan vähemmän vikoja ja viat ovat helpommin korjattavissa, koska on helpompi paikantaa, missä kontrolloimaton arvo lisätään kuin toisessa tapauksessa, jossa joutuu päättelemään kontekstin, jossa virheellinen sijoitus tehdään. Tästä seuraa suurempi viittausten läpikuultavuus, eikä mikään muu juurruta näitä ideioita luihimme niin syvälle kuin funktionaalisen ohjelmointikielen opiskelu, jossa tämä laskennan malli on sääntö.

Tämä lähestymistapa ei tietystikään sovi kaikkii tilanteisiin. Esimerkiksi olio-pohjaisissa järjestelmissä tämä tyyli usein tuottaa parempia tuloksia toimialan mallin kehittämisessä (toisin sanoen, missä pyritään pilkkomaan bisnessääntöjen monimutkaisuus) kuin käyttöliittymän kehittämisessä.

Hallitse funktionaalinen ohjelmointiajatusmalli, jotta kykenet järkevästi käyttämään oppimaasi muilla toimialoilla. Sinun olio-järjestelmäsi (yhtenä esimerkkinä) resonoivat viittausten läpikuultavuuden hyvyyttä ja on paljon lähempänä niiden funktionaalisia vastinpareja kuin monet uskoisivatkaan. Itse asiassa jotkut väittävät, että funktionaalinen ohjelmointi ja  olio-ohjelmoinnin ovat *vain toistensa peilikuvia*, laskennan jin ja jang.

Alkuperäinen kirjoittaja [Edward Garson](http://programmer.97things.oreilly.com/wiki/index.php/Edward_Garson)