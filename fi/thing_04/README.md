# Automatisoi ohjelmointistandardisi

Olet luultavasti kokenut saman. Projektin alussa kaikilla on hyvät aikomukset. Kutsutaan niitä "uuden projektin lupauksiksi". Melko usein monet näistä lupauksista kirjoitetaan dokumentteihin. Lähdekoodia koskevat lupaukset päätyvät projektin ohjelmointistandardiin. Aloitustapaamisessa(kick-off meeting) lead developer käy läpi dokumentin ja parhaassa tapauksessa kaikki yksimielisesti yrittävät noudattaa niitä. Mutta projektin edetessä nämä hyvät aikeet hylätään, yksi kerrallaan. Kun projekti on lopulta toimitettu, lähdekoodi on yhtä sekasotkua, eikä kukaan tunnut tietävän miten näin pääsi käymään.

Missä mentiin vikaan? Luultavasti jo aloitustapaamisessa. Jotkut projektin jäsenet eivät keskittyneet. Toiset eivät ymmärtäneet sen tarkoitusta. Jotkut olivat erimieltä ja suunnittelivat jo ohjelmointistandardivastarintaa. Lopulta, jotkut ymmärsivät tarkoituksen ja hyväksyivät sen, mutta projektin paineiden kasvaessa liian korkeiksi heidän piti jättää jotain tekemättä. Asiakas, joka haluaa enemmän toiminnallisuuksia ei anna lisäpisteitä hyvin muotoillusta lähdekoodista. Lisäksi, ohjelmointistandardin noudattaminen voi olla melko tylsä tehtävä, jos sitä ei ole automatisoitu. Voit huviksesi kokeilla sisentää sotkuisen luokan käsin.

Mutta jos se on niin iso ongelma, miksi edes haluamme ohjelmointistandardin? Yksi syy lähdekoodin yhtenäiseen muotoiluun on, että kukaan ei voi "omistaa" osaa lähdekoodista vain muotoilemalla sen haluamallaan tavalla. Me saatamme haluta estää ohjelmoijia käyttämästä tiettyjä antisuunnittelumalleja(anti-pattern), välttääksemme joitain yleisiä vikoja. Kaiken kaikkiaan ohjelmointistandardin pitäisi helpottaa projektissa työskentelyä ja ylläpitää kehitysnopeus alusta loppuun. Tästä seuraa, että kaikkien pitäisi suostua ohjelmointistandardiin. Ei auta jos yksi ohjelmoija käyttää kolmea välilyöntiä sisentämiseen ja toinen neljää.

On olemassa paljon työkaluja, joilla voidaan tehdä laaturaportteja lähdekoodista, sekä dokumentoida ja ylläpitää ohjelmointistandardia. Mutta se ei ole koko ratkaisu. Sen pitäisi olla automatisoitu ja sen noudattamista pitäisi valvoa, missä se on mahdollista. Alla muutama esimerkki:

- Varmista, että lähdekoodin muotoilu on osa käännösprosessia(build process), jotta kaikki ajavat sen automaattisesti joka kerta kun he kääntävät koodin.
- Käytä staattisen analyysin työkaluja etsimään lähdekoodista haluamattomia antisuunnittelumalleja. Jos sellaisia löytyy, keskeytä kääntäminen.
- Opettele konfiguroimaan ne työkalut, jotta voit etsiä omia projektikohtaisia antisuunnittelumalleja.
- Älä mittaa ainoastaan testien kattavuutta, vaan tarkasta automaattisesti myös tulokset. Taas, keskeytä kääntäminen jos testien kattavuus on liian matala.

Kokeile tehdä tämä kaikelle, jonka koet tärkeäksi. Et pysty automatisoimaan kaikkea, josta välität. Mitä tulee asioihin, joita et voi automaattisesti merkata tai korjata. Käsittele ne ohjeina automatisoidun ohjelmointistandardin lisänä. Mutta hyväksy, ettet sinä ja kollegasi välttämättä seuraa niitä ahkerasti.

Lopuksi, ohjelmointistandardin pitäisi olla dynaaminen, eikä staattinen. Kun projekti kehittyy, projektin tarpeet muuttuvat. Ja mikä saattoi alussa vaikuttaa järkevältä, ei välttämättä ole järkevää muutamaa kuukautta myöhemmin.

Alkuperäinen kirjoittaja [Filip van Laenen](http://programmer.97things.oreilly.com/wiki/index.php/Filip_van_Laenen)