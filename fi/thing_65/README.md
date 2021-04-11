# K�yt� Mielummin Sovellusalueen Tyyppej� Kuin Alkeistyyppej� (Tai k�yt� Sovellusalueen Tyyppeja Alkeistyyppien sijaan)

23. syyskuuta 1999 menetettiin maalla tapahtuneen ohjelmistovian takia 327,6 miljoonan dollarin Mars Climate Orbiter sen asettuessa Marsin kiertoradalle. Vikaa my�hemmin kutsuttiin *metriseksi mokaksi*(metric mix-up). Maa-aseman ohjelmisto toimi paunoissa avaruusaluksen odottaessa newtoneita, mik� johti maa-aseman 4,45-kertaiseen aliarviointiin avaruusaluksen tarvitsemasta ty�nt�voimasta.

T�m� on yksi useista ohjelmistovirheist�, joka olisi voitu v�ltt�� k�ytt�m�ll� vahvempia ja enemm�n sovellusalueen tyyppej�. Se on my�s syy monille Ada-kielen ominaisuuksille, jonka p��suunnittelutavoitteet on toteuttaa turvallisuuden kannalta kriittisi� sulautettuja ohjelmistoja. Adassa on vahva ja staattinen tyypitys sek� alkeistyypeille ett� k�ytt�j�n m��ritt�mille tyypeille:

```
type Velocity_In_Knots is new Float range 0.0 .. 500.00;

type Distance_In_Nautical_Miles is new Float range 0.0 .. 3000.00;

Velocity: Velocity_In_Knots;

Distance: Distance_In_Nautical_Miles;

Some_Number: Float;

Some_Number:= Distance + Velocity; -- Will be caught by the compiler as a type error.
```

V�hemm�n vaativilla sovellusalueilla ty�skentelev�t kehitt�j�t voivat my�s hy�ty� sovellusalue-kohtaisesta tyypityksest, jossa he normaalisti k�ytt�isiv�t kielen ja sen kirjastojen tarjoamia alkeistyyppej�, kuten merkkijonoja ja liukulukuja. Javassa, C++:ssa, Pythonissa ja muissa moderneissa kieliss� abstrakti tietotyyppi tunnetaan luokkana. K�ytt�en luokkia, kuten `Velocity_In_Knots` ja `Distance_In_Nautical_Miles` parantaa koodin laatua:

1. Koodista tulee luettavampaa sen esitt�ess� asiat sovellusalueen k�sittein, ei vain liukulukuina ja merkkijonoina.

- Koodista tulee testattavampaa, kun koodi kapseloi testattavan toiminnan.

- Koodi helpottaa uudelleenk�ytt�� sovellusten ja j�rjestelmien v�lill�.

T�m� tapa toimii sek� staattisen ett� dynaamisen tyypityksen kielill�. Ainoana erona staattisen tyypityksen kielet saavat hieman apua k��nt�j�lt�, kun dynaamisten kielten k�ytt�j�t todenn�k�isesti luottavat yksikk�testeihins�. Tarkastamistapa on eri, mutta perustelu ja tyyli eiv�t ole.

Opetus on aloittaa tutkimaan sovellusalue-kohtaisia tyyppej� parantaaksemme ohjelmistojen laatua.

Kirjoittanut [Einar Landre](http://programmer.97things.oreilly.com/wiki/index.php/Einar_Landre)