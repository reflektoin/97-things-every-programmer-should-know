# Tunne IDEsi

1980-luvulla ohjelmointiymp�rist�mme eiv�t yleens� olleet muuta kuin pelkki� tekstieditoreita... jos olimme onnekkaita. Syntaksinkorostus, jota pid�mme nyky��n itsest��nselvyyten� oli ylellisyys, joka ei ollut kaikkien saatavilla. Pretty printers koodin muotoiluun olivat yleens� ulkoisia ty�kaluja, jotka piti ajaa asettamaan v�lit oikein. Debuggerit olivat my�s erillisi� ohjelmia, joilla askelletaan koodin l�pi, mutta monin kryptisin komennoin.

1990-luvulla yritykset alkoivat huomata potentiaalisen lis�tulon, jos antaisi ohjelmoijille parempie ja hy�dyllisempi� ty�kaluja. IDE(integrated development environment) yhdisti edelliset editointiominaisuudet k��nt�j�n, debuggerin, pretty printerin ja muiden ty�kalujen kanssa. Niihin aikoihin valikot ja hiiri alkoi yleisty�, mik� tarkoitti ett� ohjelmoijien ei en�� tarvinnut oppia kryptisi� n�pp�inyhdistelmi� k�ytt��kseen editoreitaan. He pystyiv�t valitsemaan komennon valikosta.

2000-luvulla IDEist� on tullut niin yleisi�, ett� yritykset antavat niit� ilmaiseksi toiveena kasvattaa markkinaosuutta muilla alueilla. Moderni IDE pit�� sis�ll��n suuren m��r�n ominaisuuksia. Suosikkini on automaattinen uudelleenmuotoilu(refactoring), erityisesti *Extract Method*, jossa voin valita ja muuttaa p�tk�n koodia metodiksi. Uudelleenmuotoilun ty�kalu poimii kaikki tarvitut parametrit, mik� tekee koodin muokkaamisesta erityisen helppoa. IDEni havaitsee jopa muut koodin p�tk�t, jotka voitaisiin my�s korvata t�ll� metodilla ja se kysyy haluanko korvata ne my�s.

Toinen hieno modernien IDEiden ominaisuus on valvoa yrityksen koodin tyylik�yt�nt�j�. Esimerkiksi Javassa jotkut ohjelmoijat ovat alkaneet m��ritt�� kaikki parametril final:ksi (joka on mielest�ni ajan tuhlausta). Kuitenkin, koska heill� on kyseinen tyylis��nt�, noudattaakseni sit� minun tarvitsisi vain lis�t� se IDE:heni: Saisin varoitukseni kaikista ei-final parametreist�. Tyylis��nt�j� voidaan my�s k�ytt�� l�yt�m��n todenn�k�isi� virheit�, kuten autoboxed olioiden viittausten samankaltaisuuden vertailu(ei v�ltt�m�tt� oikea termi), esimerkiksi k�ytt�en `==` primitiivi-arvoihin, jotka autoboxataan viittaus-olioiksi(reference objects).

Valitettavasti modernit IDEt eiv�t vaadi meit� sijoittamaan aikaa niiden k�yt�n opettelemiseen. Kun ensin ohjelmoin C-kielell� Unixissa, minun piti k�ytt�� paljon aikaa opetellakseni vi-editorin toimintaa sen jyrk�n oppimisk�yr�n takia. T�m� alun ajank�ytt� on maksanut itsens� takaisin vuosien saatossa. Kirjoitan jopa t�m�n artikkelin luonnosta *vi*ll�. Moderneille IDEill� on eritt�in asteittainen oppimisk�yr�, mik� saattaa johtaa siihen, ettemme opi siit� perusk�ytt�� enemp��.

Ensimm�inen vaiheeni IDEn opettelemisessa on painaa mieleen pikan�pp�imet. Koska sormeni ovat n�pp�imist�ll� koodia kirjoittaessani, pikan�pp�imen *Ctrl+Shift+I* painaminen muuttujan tehd�kseni "variable inline" est�� flow-tilani katkeamisen, kun taas navigoiminen valikkoon hiirell�ni keskeytt�� flow-tilani. N�m� keskeytykset johtavat turhiin kontekstin vaihtamisiin(context switch), heikent�en tuottavuuttani jos yrit�n tehd� kaiken laiskalla tavalla. Sama s��nt� p�tee n�pp�imist�taitoihin: Opettele kirjoittamaan kymmensormij�rjestelm�ll�, et tule katumaan sen opetteluun k�ytt�m��si aikaa.

Viimeisen�, ohjelmoijina meill� on Unixin ajan todentamat(time proven) streaming-ty�kalut, jotka voivat auttaa meit� manipuloimaan koodiamme. Esimerkiksi, jos koodin katselmoinnin aikana huomasin, ett� ohjelmoijat olivat k�ytt�neet samaa nime� usealle luokalle, voin l�yt�� ne helposti k�ytt�en ty�kaluja *find*, *sed*, *sort*, *uniq*, ja *grep*, t�h�n tapaan:

```
find .
 -name "*.java" | sed 's/.*\///' | sort | uniq -c | grep -v "^ *1 " | sort -r
```

Oletamme kotiimme saapuvan putkimiehen osaavan k�ytt�� h�nen puhalluslamppuaan. K�ytt�k��mme hieman aikaa oppiaksemme k�ytt�m��n IDEt�mme paremmin.

Alkuper�inen kirjoittaja [Heinz Kabutz](http://programmer.97things.oreilly.com/wiki/index.php/Heinz_Kabutz)