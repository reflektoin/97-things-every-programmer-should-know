# Kommentti kommenteista

Ensimmäisellä ohjelmointikurssillani korkeakoulussa opettajani antoi kaksi BASIC ohjelmointiarkkia(coding sheet). Taululla luki tehtävä "Kirjoita ohjelma jolle syötetään 10 keilautulosta ja lasketaan niiden keskiarvo." Sitten opettaja poistui huoneesta. Miten vaikeaa se voisi olla? En muista lopullista ratkaisuani, mutta se sisälsi varmasti `FOR/NEXT` silmukan eikä se ollut yli viittätoista riviä pitkä. Ohjelmointiarkit - nuoremmille lukijoille, kyllä, meillä oli tapana kirjoittaa koodi käsin paperille ennen sen syöttämistä tietokoneelle - joihin voi kirjoittaa 70 riviä per arkki. Olen hämmentynyt, miksi opettaja antoi meille kaksi arkkia. Koska käsialani on aina ollut epäselvää, käytin toisen paperin koodin siistiksi kopiointiin, toiveenani oli saada muutama lisäpiste tyylistä.

Yllätyin saadessani tehtävän takaisin seuraavan tunnin alussa takaisin, sain välttävän arvosanan. (Se oli enne loppuajastani korkeakoulussa.) Siististi kopioidun koodini yläpuolelle oli raapustettu "Ei kommentteja?"

Ei riittänyt, että ohjelman tarkoitus oli selkeä opettajalle ja minulle. Osat tehtävän takroituksesta oli opettaa minulle, että koodin pitäisi selittää itsensä sen seuraavalle ohjelmoijalle. Sitä opetusta en ole unohtanut.

Kommentit eivät ole pahoja. Ne ovat yhtä välttämättömiä kuin ehto- ja toistorakenteet. Useimmissa moderneissa kielessä on javadocin kaltainen työkalu joka jäsentää oikeain muotoillut kommentit rakentaakseen automaattisesti API-dokumentin. Se on hyvä alku, mutta ei lainkaan riittävä. Koodin tulisi sitältää selityksiä, mitä ohjelman olisi tarkoitus tehdä. Koodaus vanhan sanonnan mukaan, "Jos se oli hankala kirjoittaa, sen tulisi olla hankala lukea," tekee karhunpalveluksen asiakkaallesi, työnantajallesi, kollegoillesi ja itsellesi tulevaisuudessa.

Toisaalta, voit kommentoida liikaakin. Varmista, että kommenttisi selkeyttävät koodiasi, eikä sumenna sitä. Ripottele relevantteja kommentteja, jotka selittävät mitä koodin pitäisi saavuttaa. Otsikko-kommenttisi tulisi antaa ohjelmoijalle riittävästi tietoa käyttääkseen koodia lukematta sitä, kun taas koodin (in-line) kommenttien tulisi auttaa seuraavaa ohjelmoijaa sen korjaamisessa tai laajentamisessa.

Yhdessä työssäni, olin eri mieltä suunnittelupäätöksestä ylempieni kanssa(those above me). Nasevana nuorena liitin koko minua opastavan suunnittelusähköpostiviestin tiedoston otsikko-lohkoon. Kävi ilmi, että kyseisen firman johtajat katselmoivat talletetut(committed) koodit. Se oli ensimmäinen törmäämiseni termiin *uraa rajoittava teko*.

by [Cal Evans](http://programmer.97things.oreilly.com/wiki/index.php/Cal_Evans)