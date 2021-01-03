# Valitse Työkalusi Harkiten

Moderneja sovelluksia harvoin rakennetaan tyhjästä. Ne kasataan olemassaolevilla työkaluilla - komponenteista, kirjastoista ja ohjelmistokehyksistä - monista hyvistä syistä:

- Sovellukset kasvavat koossa, monimutkaisuusessa ja kehittyneisyydessä, kun aika niiden kehittämiseen vähenee. Kehittäjien aika on parempi käyttää aikaa bisnes-alueen(business-domain) koodin kirjoittamiseen kuin infrastruktuurin koodiin.

- Laajalti käytetyt komponent ja ohjelmistokehykset(framework) sisältävät todennäköisesti vähemmän vikoja kuin firman sisällä kehitetyt.

- Verkosta löytyy paljon laadukkaita ohjelmistoja ilmaiseksi, joka tarkoittaa matalampia kehityksen kustannuksia ja suurempaa todennäköisyyttä löytää kehittäjiä tarpeellisilla kiinnostuksilla ja osaamisella.

- Ohjelmistotuotanto ja ylläpito on ihmistyötä vaativaa(human-intensive work), joten ostaminen voi olla helpompaa kuin rakentaminen

Kuiteknin, oikean työkaluyhdistelmän löytäminen sovelluksellesi saattaa olla hankalaa. Päätöstä tehdessäsi kannattaa pitää mielessä muutama asia:

- Eri työkalut saattavat luottavat eri olettamuksiin niiden ympäpristösä. Esimerkiksi ympäröivä infrastruktuuri, hallintamalli(control model), data malli(data model), protokollat(communication protocols), jne. Se saattaa johtaa arkkitehtuuriseen yhteensopimattomuuteen sovelluksen ja työkalujen välillä. Yhteensopimattomuus johtaa purkkavirityksiin(hacks and workarounds), jotka tekevät koodista tarpeettoman monimutkaista.

- Eri työkaluilla on eri elinkaaret ja niistä yhden päivittäminen voi olla erittäin hankala ja aikaa vievä tehtävä, koska uusi toiminnallisuus, suunnittelumuutokset tai jopa vikojen korjaus saattaa aiheuttaa yhteensopimattomuuksia muiden työkalujen kanssa. Mitä isompi määrä työkaluja, sitä suuremmaksi ongelma voi tulla

- Jotkin työkalut vaativat paljon konfigurointia, usein se tarkoittaa yhtä tai useampaa XML-tiedostoa, jotka voivat kasvaa hallitsemattomiksi nopeastikin. Sovellus saattaa päätyä näyttämään siltä kuin se olisi kirjoitettu lähes kokonaan XML:llä ja muutamanna rivillä jotakin ohjelmointikieltä. Konfiguraation monimutkaisuus(configurational complexity) tekee sovelluksen ylläpidosta ja laajentamisesta hankalaa.

- Toimittajariippuvuus(vendor lock-in) tapahtuu, kun koodi, joka riippuu vahvasti tietyn toimittajan tuotteesta rajoittaa koodia monella saralla: ylläpidossa, suorituskyvyssä, kehityksessä, hinnassa jne.

- Jos suunnittelet ilmaisten ohjelmistojen käyttöä, saatat huomata, että se ei lopulta olekaan ilmasta. Saatat joutua ostamaan tukea (commercial support), joka ei välttämättä ole halpaa.

- Lisenssit merkitsevät, jopa ilmaisissa ohjelmistoissa. Esimerkiksi joissain yrityksissä ei ole sallittua käyttää GNU-lisensoituja ohjelmistoja (software licenced under the GNU license terms), niiden virus-maisen(viral) luonteen takia. Toisin sanoen niillä kehitetyt sovellukset tulee levittää lähdekoodin kera.

Henkilökohtainen strategiani näiden ongelmien lieventämiseksi on aloittaa pienestä, käyttäen vain välttämättömiä työkaluja. Yleensä alussa keskitytään poistamaan tarve matalan tason infrastruktuurin koodaamiselle. Esimerkiksi käyttämällä väliohjelmistoa(middleware) pistokkeiden(raw sockets) sijaan hajautetuissa sovelluksissa. Ja sitten työkaluja lisätään tarvittaessa. Minulla on myös tapana eristää ulkoiset työkalut bisnes-alueen(business domain) objekteista rajapinnoilla ja kerroksilla(layering), jotta työkalun vaihto onnistuu vähällä kivulla. Tämän lähestymistavan positiivinen sivuvaikutus on yleensä pienemmät sovellukset, jotka käyttävät vähemmän ulkoisia työkaluja kuin alunperin ennustettiin.

Alkuperäinen kirjoittaja [Giovanni Asproni](http://programmer.97things.oreilly.com/wiki/index.php/Giovanni_Asproni)