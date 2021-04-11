# Tiedä Seuraava Committisi

Koputin kolmea ohjelmoijaa olkapäälle ja kysyin mitä he tekivät. "Refaktoroin näitä metodeja," vastasi ensimmäinen. "Lisään joitain parametreja tähän web actioniin," toinen vastasi. Kolmas vastasi, "työstän tätä user storya."

Saattaa vaikuttaa siltä, että kaksi ensimmäistä olivat syventyneet työnsä yksityiskohtiin ja vain kolmas näki isomman kuvan, ja että viimeinen keskittyy oikeaan asiaan. Mutta kun kysyin, milloin ja mitä he commitoisivat, kuva muuttui dramaattisesti. Kahdella ensimmäisellä oli melko selvä, mitä tiedostoja he muokkaavat ja että he olisivat valmiit noin tunnin sisällä. Kolmas vastai "No, ehkä olen valmis muutamassa päivässä. Lisään luultavasti muutaman luokan ja saatan muuttaa noita palveluita jollain tavalla."

Kahdeltä ensimmäiseltä ei puuttunut kokonaistavoitteen näkemystä(lack a vision of the overall goal). He valitsivat tehtäviä, joiden he uskoivat johtavan tuottavaan suuntaan ja he voisivat saada valmiiksi parissa tunnissa. Saatuaan tehtävät valmiiksi, he ottaisivat työkseen uuden ominaisuuden tai refaktoroinnin. Kaikella kirjoitetulla koodilla on selkeä merkitys ja rajattu saavutettava tavoite mielessä.

Kolmas ohjelmoija ei onnistunut hajoittamaan(decompose) ongelmaa osiin ja työsti jokaista osaa samanaikaisesti. Hänellä ei ollut ideaa, mitä se vaatisi, käytännössä spekulatiivista koodausta, toivoen saapuvansa johonkin commitoimis-kelpoiseen tilaan. Mitä todennäköisimmin pitkän session alussa kirjoitettu koodi sopii huonostiratkaisuun johon lopussa päädyttiin.

Mitä kaksi ensimmäistä ohjelmoijaa tekisivät jos heidän tehtävänsä vaatisi yli kaksi tuntia aikaa? Tajuttuaan, että he ottivat liian ison palan, he todennäköisesti heittäisivät muutoksensa pois, määrittäisivät pienempiä tehtäviä ja aloittaisivat alusta. Työstä olisi puuttunut fokus ja olisi johtanut spekulatiisisen koodin lisäämiseen repositorioon. Sen sijaan, muutokse heitettäisiin pois, mutta oivallukset säilytettäisiin.

Kolmas ohjelmoija saattaisi jatkaa arvuuttelua ja epätoivoisesti yrittäisi parsia kasaan muutoksistaan jotain jonka voisi commitoida. Kuitenkaan, et voi tekemiäsi muutoksiasi pois - se olisi tuhlattua työtä, eikö? Valitettavasti koodin pois heittämättä jättäminen johtaa hieman kummalliseen koodiin, josta puuttuu selkeä tarkoitus repositorioon mennessään.

Jossain vaiheessa jopa committeihin keskittyvät ohjelmoijatkaan eivät löydä mitään hyödyllistä, minkä voisi saada valmiiksi kahdessa tunnissa. Sitten he menevät suoraan spekulatiiviseen moodiin, leikkivät koodilla ja tottakai joskus heittävät muutokset pois saatuaan ovivalluksen, joka johdattaa heidän takaisin oikealle polulle. Jopa näillä tavoitteettomilla hakkerointisessioilla on tarkoitus: oppia jotain koodista jotta voi määrittää tehtävän joka olisi rakentava askel

Tiedä seuraava committisi. Jos et saa sitä valmiiksi, heitä muutokset pois, ja määritä tehtävä, johon uskot saaduilla oivalluksillasi. Tee spekulatiivisia kokeiluja tarvitessasi, mutta älä ajaudu spekulatiiviseen moodiin huomaamattasi. Älä commitoi arvuuttelujasi repositorioon.

Kirjoittaja [Dan Bergh Johnsson](http://programmer.97things.oreilly.com/wiki/index.php/Dan_Bergh_Johnsson)