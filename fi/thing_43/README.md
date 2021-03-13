# Hallitse Komentorivity�kalujen k�ytt�

Nyky��n monet ohjelmistokehityksen ty�kalut on paketoitu integroituihin kehitysymp�rist�ihin(engl. IDE). Microsoftin Visual Studio ja avoimen l�hdekoodin Eclipse ovat kaksi suosittua esimerkkia, vaikkakin on monia muitakin. IDEiss� on paljon hyvi� asioita. Niit� ei ole ainoastaan helppo k�ytt��, ne my�s v�hent�v�t ohjelmoijan tarvetta ajatella monia koonnin prosessin vaiheita.

Helppok�ytt�isyydell� on kuitenkin haittapuolensa. Tyypillisesti ty�kalun ollessa helppok�ytt�inen se johtuua siit�, ett� ty�kalu tekee p��t�ksi� puolestasi ja tekee paljon asioita automaattisesti taustalla. Siten, jos IDE on ainut k�ytt�m�si ohjelmointiymp�rist�, ei saata ymm�rt�� koskaan t�ysin, mit� ty�kalusi varsinaisesti tekev�t. Painat nappia, jotain taikoja tapahtuu ja suoritettava tiedosto ilmestyy projektihakemistoosi.

Ty�skentelem�ll� komentorivin koontity�kaluilla, opit paljon enemm�n mit� tekev�t kun projektiasi kootaan. Omien make-tiedostojen kirjoittaminen auttaa sinua ymm�rt�m��n kaikki vaiheet(k�nt�minen, assembling, linkitys, jne.), joista suoritettavan tiedostona koonti koostuu. Kokeilemalla monia komentorivity�kalujen mahdollisuuksia saat arvokkaita oppimiskokemuksia. Aloittaaksesi komentorivien koontity�kalujen kanssa, voit k�ytt�� avoimen l�hdekoodin komentorivity�kaluja kuten GCC tai voit k�ytt�� patentoidun(proprietary) IDEn mukana tulleita ty�kaluja. Kuitenkin, hyvin suunniteltu IDE on vain graafinen julkisivu(frontend) joukolla komentorivity�kaluja.

Koontiprosessin paremman ymm�rryksen lis�ksi jotkut asiat saa tehty� paljon helpommin tai tehokkaammin komentorivity�kaluilla kuin IDEll�. Esimerkiksi etsi ja korvaa toiminnallisuudet *grep*- ja *sed*-ty�kaluilla ovat usein tehokkaampia kuin IDEn tarjoamat vastineet. Komentorivity�kalut luonnostaan tukevat skriptien tekemist�, joka sallii teht�vien, kuten p�ivitt�isten koontien ajoittamisen, useiden versioiden luonnin projektista, sek� testijoukon suorittamisen. IDEss� t�m�n tyylinen automatisointi saattaa olla hankalampaa (ellei mahdotonta) tehd�, koska koonti-asetukset yleens� m��ritet��n GUIn dialogilaatikoilla ja koontiprosessi k�ynnistet��n hiiren klikkauksella. Jos et koskaan astu IDEn ulkopuolelle, et saata huomata, ett� t�m�n kaltaiset automatisoidut teht�v�t ovat mahdollisia.

Mutta odota. Eik� IDEn tarkoitus ole helpottaa kehitt�mist� ja parantaa ohjelmoijan tuottavuutta? Kyll� on. Esitetty ehdotus ei ole IDEn k�yt�n lopettaminen. Ehdotus on, ett sinun pit�isi "katsoa pellin alle" ja ymm�rt�� mit� IDE tekee puolestasi. Paras tapa sen ymm�rt�miseen on oppia k�ytt�m��n komentorivity�kaluja. Sitten kun palaat k�ytt�m��t IDEt�si, ymm�rr�t paremmin mit� se tekee sinulle ja kuinka voit hallita koontiprosessia. Toisaalta, kun kerran opit k�ytt�m��n komentorivity�kaluja ja koet niiden tehokkuuden ja joustavuuden, saatat mielty� enemm�n niihin kuin IDE:hen.

Alkuper�inen kirjoittaja [Carroll Robinson](http://programmer.97things.oreilly.com/wiki/index.php/Carroll_Robinson)