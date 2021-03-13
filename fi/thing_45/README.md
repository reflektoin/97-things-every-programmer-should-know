# Tunne IDEsi

1980-luvulla ohjelmointiympäristömme eivät yleensä olleet muuta kuin pelkkiä tekstieditoreita... jos olimme onnekkaita. Syntaksinkorostus, jota pidämme nykyään itsestäänselvyytenä oli ylellisyys, joka ei ollut kaikkien saatavilla. Pretty printers koodin muotoiluun olivat yleensä ulkoisia työkaluja, jotka piti ajaa asettamaan välit oikein. Debuggerit olivat myös erillisiä ohjelmia, joilla askelletaan koodin läpi, mutta monin kryptisin komennoin.

1990-luvulla yritykset alkoivat huomata potentiaalisen lisätulon, jos antaisi ohjelmoijille parempie ja hyödyllisempiä työkaluja. IDE(integrated development environment) yhdisti edelliset editointiominaisuudet kääntäjän, debuggerin, pretty printerin ja muiden työkalujen kanssa. Niihin aikoihin valikot ja hiiri alkoi yleistyä, mikä tarkoitti että ohjelmoijien ei enää tarvinnut oppia kryptisiä näppäinyhdistelmiä käyttääkseen editoreitaan. He pystyivät valitsemaan komennon valikosta.

2000-luvulla IDEistä on tullut niin yleisiä, että yritykset antavat niitä ilmaiseksi toiveena kasvattaa markkinaosuutta muilla alueilla. Moderni IDE pitää sisällään suuren määrän ominaisuuksia. Suosikkini on automaattinen uudelleenmuotoilu(refactoring), erityisesti *Extract Method*, jossa voin valita ja muuttaa pätkän koodia metodiksi. Uudelleenmuotoilun työkalu poimii kaikki tarvitut parametrit, mikä tekee koodin muokkaamisesta erityisen helppoa. IDEni havaitsee jopa muut koodin pätkät, jotka voitaisiin myös korvata tällä metodilla ja se kysyy haluanko korvata ne myös.

Toinen hieno modernien IDEiden ominaisuus on valvoa yrityksen koodin tyylikäytäntöjä. Esimerkiksi Javassa jotkut ohjelmoijat ovat alkaneet määrittää kaikki parametril final:ksi (joka on mielestäni ajan tuhlausta). Kuitenkin, koska heillä on kyseinen tyylisääntö, noudattaakseni sitä minun tarvitsisi vain lisätä se IDE:heni: Saisin varoitukseni kaikista ei-final parametreistä. Tyylisääntöjä voidaan myös käyttää löytämään todennäköisiä virheitä, kuten autoboxed olioiden viittausten samankaltaisuuden vertailu(ei välttämättä oikea termi), esimerkiksi käyttäen `==` primitiivi-arvoihin, jotka autoboxataan viittaus-olioiksi(reference objects).

Valitettavasti modernit IDEt eivät vaadi meitä sijoittamaan aikaa niiden käytön opettelemiseen. Kun ensin ohjelmoin C-kielellä Unixissa, minun piti käyttää paljon aikaa opetellakseni vi-editorin toimintaa sen jyrkän oppimiskäyrän takia. Tämä alun ajankäyttö on maksanut itsensä takaisin vuosien saatossa. Kirjoitan jopa tämän artikkelin luonnosta *vi*llä. Moderneille IDEillä on erittäin asteittainen oppimiskäyrä, mikä saattaa johtaa siihen, ettemme opi siitä peruskäyttöä enempää.

Ensimmäinen vaiheeni IDEn opettelemisessa on painaa mieleen pikanäppäimet. Koska sormeni ovat näppäimistöllä koodia kirjoittaessani, pikanäppäimen *Ctrl+Shift+I* painaminen muuttujan tehdäkseni "variable inline" estää flow-tilani katkeamisen, kun taas navigoiminen valikkoon hiirelläni keskeyttää flow-tilani. Nämä keskeytykset johtavat turhiin kontekstin vaihtamisiin(context switch), heikentäen tuottavuuttani jos yritän tehdä kaiken laiskalla tavalla. Sama sääntö pätee näppäimistötaitoihin: Opettele kirjoittamaan kymmensormijärjestelmällä, et tule katumaan sen opetteluun käyttämääsi aikaa.

Viimeisenä, ohjelmoijina meillä on Unixin ajan todentamat(time proven) streaming-työkalut, jotka voivat auttaa meitä manipuloimaan koodiamme. Esimerkiksi, jos koodin katselmoinnin aikana huomasin, että ohjelmoijat olivat käyttäneet samaa nimeä usealle luokalle, voin löytää ne helposti käyttäen työkaluja *find*, *sed*, *sort*, *uniq*, ja *grep*, tähän tapaan:

```
find .
 -name "*.java" | sed 's/.*\///' | sort | uniq -c | grep -v "^ *1 " | sort -r
```

Oletamme kotiimme saapuvan putkimiehen osaavan käyttää hänen puhalluslamppuaan. Käyttäkäämme hieman aikaa oppiaksemme käyttämään IDEtämme paremmin.

Alkuperäinen kirjoittaja [Heinz Kabutz](http://programmer.97things.oreilly.com/wiki/index.php/Heinz_Kabutz)