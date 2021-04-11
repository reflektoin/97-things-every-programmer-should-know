# Omista (ja Uudelleenumuotoile) Koonti

Ei ole harvinaista, ett� tiimeill�, jotka ovat muuten eritt�in kurinalaisia ohjelmointik�yt�nn�ist� j�tt�� huomiotta koonti-skriptit, joko uskosta niiden merkityksett�myydest� tai pelosta, ett� ne ovat liian monimutkaisia ja niit� voi k�sitell� vain julkaisutekniikan(release engineerin) kultti. Yll�pit�m�tt�m�t koonti-skriptit duplikaatiolla ja virheill� aiheuttavat samankaltaisia ongelmia kuin huonosti muotoiltu koodi.

Yksi selitys, miksi kurinalaiset, taitavat ohjelmoijat kohtelevat koontia toissijaisena heid�n ty�h�ns� on, ett� koonti-skriptit on usein kirjoitettu eri kielell� kuin l�hdekoodi. Toinen syy on, ett� koonti ei varsinaisesti ole "koodia." N�m� oikeutukset lent�� todellisuuden kasvoihin, ett� suurin osa ohjelmoijista nauttii uusien kielten oppimisesta ja ett� koonti luo suoritettavat artefaktit kehitt�jien ja loppuk�ytt�jien testattavaksi ja ajettavaksi. Koodi on hy�dyt�nt� ilman koontia ja koonti m��ritt�� sovelluksen komponenttien arkkitehtuurin. Koonti on olennainen osa kehitys-prosessia ja p��t�kset koontiprosessista voi tehd� koodista ja koodaamisesta yksinkertaisempaa.

V��rill� idiomeilla kirjoitetut koonti-skriptit on hankalia yll�pit�� ja mik� t�rke�mp��, parantaa. On sen arvoista k�ytt�� osa ajasta ymm�rt��kseen oikea tapa tehd� muutos. Viat voivat ilmet� kun sovellus kootaan riippuvuuksien v��r�ll� versiolla tai kun koonnin-aikaiset asetukset ovat v��r�t.

Perinteisesti testaus on j�tetty "Laadunvarmistus"-tiimille. Nyt ymm�rr�mme ohjelmoitaessa testaamisen tarpeellisuuden toimittaaksemme arvoa ennustettavasti. Samaan tapaan, kehitys-tiimin tulee hallita koonti-prosessi.

Koonnin ymm�rt�minen voi yksinkertaistaa kehityksen koko elinkaarta ja v�hent�� kustannuksia. Helposti ajettava koonti sallii uuden kehitt�j�n p��st� alkuun nopeasti ja helposti. Konfiguroinnin automatisointi koonnissa voi mahdollistaa johdonmukaiset tulokset, kun monet henkil�t ty�skentelev�t projektissa, v�ltt�en "se toimii minulla"-keskusteut. Monet koonnin ty�kalut sallivat sinun luoda raportteja koodin laadusta, mahdollistaen mahdollisten ongelmien havaitsemisen aikaisin. K�ytt�m�ll� aikaa koonnin ymm�rt�miseen voit auttaa itse�si ja kaikkia tiimiss�si. Voit keskitty� ominaisuuksien ohjelmointiin, hy�dytt�en sidosryhmi�si ja tehden ty�st� nautinnollisempaa.

Opi koonti-prosessistasi riitt�v�sti ymm�rt��ksesi milloin ja miten tehd� muutoksia. Koonti-skriptit ovat koodia. Ne ovat liian t�rkeit� j�tett�v�ksi kenellek��n muulle, vaikka ainostaan siit� syyst�, ett� ohjelma ei ole valmis ennen kuin se on koottu. Ohjelmointi ei ole valmis ennen kuin toimiva sovellus on toimitettu.

Kirjoittanut [Steve Berczuk](http://programmer.97things.oreilly.com/wiki/index.php/Steve_Berczuk)