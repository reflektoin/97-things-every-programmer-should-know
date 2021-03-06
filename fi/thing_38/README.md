# Kuinka K�ytt�� Virheenseurantaohjelmaa

Kutsut niit� sitten *bugeiksi*, *vioiksi*, tai jopa *suunnittelun sivuvaikutukseksi*, et p��se niist� eroon. Hyv�n bugiraportin tekeminen ja niist� asioiden etsiminen ovat avaintaitoja projektin pit�misess� liikkeess�.

Hyv� bugiraportti tarvitsee kolme asiaa:

- Miten toistaa bugi, mahdollisimman tarkasti, ja kuinka usein t�m� aiheuttaa bugin ilmenemisen.
- Mit� olisi pit�nyt tapahtua, ainakin sinun mielest�si.
- Mit� oikeasti tapahtui, tai ainakin kaikki tieto, mit� sin� ollet tallentanut.

Bugiraportin tiedon m��r� ja laatu kertoo yht� paljon itse raportoijasta kuin itse bugista. Vihaiset, lyhyet bugit ("T�m� funktio on syv�lt�!") kertoo kehitt�jille, ett� sinulla oli huono p�iv�, mutta ei pajona muuta. Bugi ja laaja konteksti tekee helpommaksi sen toistamisen ja ansaitsee kaikkien kunioituksen, vaikka se pys�ytt�isi julkaisun.

Bugit ovat kuin keskustelu, kaikki historia kaikkien n�ht�vill�(with all the history right there in front of everyone). �l� syyt� muita tai kiell� bugin olemassaoloa. Pyyd� sen sijaan lis�� tietoa tai mieti, mit� sinulta olisi voinut j��d� huomaamatta.

Bugin statuksen muuttaminen *Avoimesta* *Suljetuksi* on julkinen kannanotto mit� ajattelet bugista. Ajan k�ytt�minen selostamiseen, miksi bugi pit�isi sulkea tulee s��st�m��n monia tunteja my�hemmin kun p��t�s pit�� oikeuttaa turhautuneille managereille ja asiakkaille. Bugin prioriteetin muuttaminen on samankaltainen julkinen kannanotto ja vain koska se on triviaalia sinulle, ei tarkoita, ettei se est�isi jotakuta muuta k�ytt�m�st� tuotetta.

�l� ylikuormita(overload) bugin kentti� omiin tarkoituksiisi. Lis��m�ll� "ELINT�RKE�:" bugin otsikkokentt��n saattaa helpottaa sinua j�rjestelem��n tulokset jossain raportissa, mutta lopulta muut kopioivat ja kirjoittavat sen v��rin, tai heid�n tarvitseee poistaa se jostain raportista. K�yt� sen sijaan uutta arvoa tai kentt�� ja dokumentoi miten kentt�� pit�isi k�ytt��, jotta muiden ei tarvitse toistaa itse��n.

Varmista, ett� kaikki tiet�v�t miten l�yt�� bugit, joita tiimin on tarkoitus t�ll� hetkell� korjata. T�m�n saa yleens� tehty� julkisell� kyselyll�, jolla on itsest��nselv� nimi. Varmista ett� kaikki k�ytt�v�t samaa kysely�, �l�k� muuta t�t� kysely� ilman tiimin tiedottamista, ett� muutat kaikkien teht�vi�.

Lopuksi, muista, ett� bugi ei ole standardoitu ty�m��r�n yksikk� sen enemp�� kuin yksi rivi koodia on tarkka vaivann��n m��r�.

Alkuper�inen kirjoittaja [Matt Doar](http://programmer.97things.oreilly.com/wiki/index.php/Matt_Doar)