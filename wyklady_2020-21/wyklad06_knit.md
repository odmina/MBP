---
Title: Korelacja vs przyczynowość
---

# Słowem przypomnienia

## Kontekst

![](img/nauka_kontekst_diagram.png)

## Etapy

![](img/science_proces.png)

## Operacjonalizacja

Definiowanie zmiennej przez pryzmat obiektywnych, empirycznych wskaźników.

## Zmienne

Jakakolwiek własność lub cecha, która przyjmuje różne wartości u różnych ludzi, w różnych sytuacjach etc.

- *Zmienne niezależne* to te, którymi badacz manipuluje lub które kontroluje w swoim badaniu.
- *Zmienne zależne* to te, w przypadku których weryfikujemy **czy ich poziom zmienia się, jeżeli zmienia się poziom zmiennej niezależnej**. 

## Zmienne a przyczynowość

- Zmienna niezależna **wyjaśnia zmienność** zmiennej zależnej
- Czasem zmienna niezależna **wpływa na** zmienną zależną, ale nie zawsze

# Podstawowe rodzaje zależności statystycznych

## Podstawowe rodzaje zależności statystycznych

- Różnice pomiędzy grupami
- Korelacje

## Różnice pomiędzy grupami - przykładowe hipotezy

- Kobiety są bardziej rozmowne niż mężczyźni
- Ludzie rozmawiający przez telefon w czasie jazdy samochodem gorzej prowadzą samochód niż ludzie nie rozmawiający przez telefon
- Ludzie z kultury amerykańskiej są bardziej indywidualistyczni niż ludzie z kultury polskiej

## Jak porównujemy grupy

- Miary tendencji centralnej: średnia, mediana, moda
- Miary zmienności, rozproszenia wyników wokół średniej: odchylenie standardowe, wariancja



## Czy mężczyźni są wyżsi niż kobiety?

## Rozkład wzrostu w próbie

![plot of chunk w06-height1](figure/w06-height1-1.png)

## Rozkład wzrostu w zależności od płci

![plot of chunk w06-height2](figure/w06-height2-1.png)

## Czy mężczyźni są wyżsi niż kobiety?

![plot of chunk w06-height3](figure/w06-height3-1.png)

## Czy mężczyźni są wyżsi niż kobiety?

![plot of chunk w06-height4](figure/w06-height4-1.png)

## Wykres ramka-wąsy (Tukey)

- *Box-and-whiskers plot*
- W środku mediana
- Ramka od Q1 do Q3
- Wąsy od min do max **bez obserwacji odstających**

## Czy mężczyźni są ciężsi niż kobiety?

![plot of chunk w06-weight1](figure/w06-weight1-1.png)

## Korelacja

- Siła związku między zmiennymi
- Im silniejszy związek, tym dwie zmienne są bliżej zależności **liniowej**
- Związek najczęściej wyrażony współczynnikiem korelacji

## Współczynnik korelacji

- Technicznie kilka różnych, w praktyce podobna interpretacja
- r Pearsona, rho Spearmana, tau Kendalla
- Wartości od -1 do 1, im wyższa wartość bezwzględna, tym silniejszy związek
- Wsp. korelacji = 1 lub -1 - idealna zależność liniowa

## Korelacje dodatnie i ujemne

- Dodatni/pozytywny związek, r > 0: wyższe wartości A wiążą się z wyższymi B
- Ujemny/negatywny związek, r < 0: wyższe wartości A wiążą się z niższymi B

## Waga wiąże się ze wzrostem? (N=100)

![plot of chunk w06-cor1](figure/w06-cor1-1.png)

## Waga wiąże się ze wzrostem? (N=100)


```
## `geom_smooth()` using method = 'loess' and formula 'y ~ x'
```

![plot of chunk w06-cor2](figure/w06-cor2-1.png)

## Waga a wzrost (N=10000)

![plot of chunk w06-cor3](figure/w06-cor3-1.png)

## Waga a wzrost (N=10000)


```
## `geom_smooth()` using method = 'gam' and formula 'y ~ s(x, bs = "cs")'
```

![plot of chunk w06-cor4](figure/w06-cor4-1.png)

## Waga, wzrost a płeć?

![plot of chunk w06-cor5](figure/w06-cor5-1.png)

## Inne przykłady

---
![plot of chunk w06-cor6](figure/w06-cor6-1.png)

---

![plot of chunk w06-cor7](figure/w06-cor7-1.png)

---

![plot of chunk w06-cor8](figure/w06-cor8-1.png)

---

![plot of chunk w06-cor9](figure/w06-cor9-1.png)

---

![plot of chunk w06-cor10](figure/w06-cor10-1.png)

---

![plot of chunk w06-cor11](figure/w06-cor11-1.png)

---

![plot of chunk w06-cor12](figure/w06-cor12-1.png)

# Czy z tą korelacją to zawsze taka prosta sprawa?

## Zagadka (kwartet Anscombe'a)

---

![plot of chunk w06-anscombe1](figure/w06-anscombe1-1.png)

---

![plot of chunk w06-anscombe2](figure/w06-anscombe2-1.png)

---

![plot of chunk w06-anscombe3](figure/w06-anscombe3-1.png)

---

![plot of chunk w06-anscombe4](figure/w06-anscombe4-1.png)

## r = ?

## r = 0.816 dla WSZYSTKICH zbiorów

## Jak to jest możliwe?

- Współczynnik korelacji jest czuły na związki **liniowe**
- Zaburzenie liniowości powoduje "dziwne" efekty
- Czy można powiedzieć że we wszystkich 4 przypadkach związek jest taki sam?

## Inne dziwolągi (zaburzenie liniowości)

![r to zero!](img/w02_0_corr.png)

## Inne dziwolągi (zaburzenie liniowości)

![tu też r zero!](img/w02_0_corr_2.png)

# Korelacja, obserwowany związek a przyczynowość

## Podstawowe pytanie

- Czy jeśli a koreluje z b to a **spowodowało** b?
- Być może tak...
- ...albo nie!!!!!!!!!!
- Tylko na podstawie faktu, że a koreluje z b nie możemy wyciągnąć wniosków przyczynowo-skutkowych

## Jakie są możliwości? (przykłady z wikipedia.org)

## A powoduje B

- Wiek koreluje ze wzrostem u dzieci
- Dziecko rośnie ponieważ się starzeje, a nie na odwrót

## B powoduje A

- Im szybciej kręcą się wiatraki, tym wiatr wieje szybciej...
- Więc wiatraki powodują wiatr
- ...
- ...mamy dobre argumenty, żeby sądzić, że jest dokładnie na odwrót

## B powoduje A

- Ludzie w średniowieczu wierzyli, że posiadanie wszy jest gwarancją życia w dobrym zdrowiu
- Obserwacja: bardzo rzadko można zaobserwować wszy na chorym człowieku
- ???
- Wszy okazują się być bardzo wrażliwe na temperaturę. Przy najmniejszym stanie podgorączkowym uciekają

---

- Spanie w butach jest silnie skorelowane z bólem głowy po przebudzeniu
- ?

## Trzeci czynnik C powoduje A i B

- Pijaństwo powoduje spanie w butach
- Pijaństwo powoduje ból głowy po przebudzeniu

## Trzeci czynnik C powoduje A i B

- Spożycie lodów jest silnie dodatnio skorelowane z liczbą zgonów w wyniku utonięcia
- ?
- Wzrost temperatury powoduje wzrost spożycia lodów. Wzrost temperatury powoduje, że więcej ludzi się kąpie i, w konsekwencji, więcej jest utonięć

## A powoduje B a B powoduje A (zależności cykliczne, sprzężenia zwrotne)

- Rowerzyści mają niższe BMI niż ludzie nie jeżdżący na rowerze
- Czy jazda na rowerze obniża BMI?
- Czy niskie BMI sprzyja jeżdżeniu na rowerze?

## Dodatnie i ujemne sprzężenia zwrotne (_feedback loops_)

- Dodatnie sprzężenie zwrotne:
    - wzrost A powoduje wzrost B
    - wzrost B powoduje wzrost A
    - wzrost A powoduje wzrost B
    - itd.
    - obie zmienne wzrastają

## Dodatnie i ujemne sprzężenia zwrotne (_feedback loops_)

- Ujemne sprzężenie zwrotne:
    - spadek A powoduje spadek B
    - spadek B powoduje spadek A
    - spadek A powoduje spadek B
    - itd.
    - obie zmienne maleją
    
## Sprzężenia zwrotne

- Depresja i ból
- Fear avoidance model of chronic pain
- Nieśmiałość i lęk

# Kilka przykładów tego, że korelacja i przyczynowość nie idą w parze

---

- Wynik ostatniego domowego meczu Washington Redskins przed wyborami prezydenckimi w USA był wprost skorelowany z wynikiem wyborów (od 1936 do 2000)
- Od 200 lat przywódcy Rosji/Związku Radzieckiego są na zmianę łysiejący i "włochaci"

--- 

![Przywódcy Zwiazku Radzieckiego/Rosji](img/w02_russia.png)

---

![Hm...](img/w02_spurious/chart-1.png)

<small>Wykres pochodzi z [http://tylervigen.com/spurious-correlations](http://tylervigen.com/spurious-correlations),  
[creative commons license](https://creativecommons.org/licenses/by/4.0/)</small>

---

![Hm...](img/w02_spurious/chart-2.png)

<small>Wykres pochodzi z [http://tylervigen.com/spurious-correlations](http://tylervigen.com/spurious-correlations),  
[creative commons license](https://creativecommons.org/licenses/by/4.0/)</small>

---

![Hm...](img/w02_spurious/chart-3.png)

<small>Wykres pochodzi z [http://tylervigen.com/spurious-correlations](http://tylervigen.com/spurious-correlations),  
[creative commons license](https://creativecommons.org/licenses/by/4.0/)</small>

---

![Hm...](img/w02_spurious/chart-4.png)

<small>Wykres pochodzi z [http://tylervigen.com/spurious-correlations](http://tylervigen.com/spurious-correlations),  
[creative commons license](https://creativecommons.org/licenses/by/4.0/)</small>

---

![Hm...](img/w02_spurious/chart-5.png)

<small>Wykres pochodzi z [http://tylervigen.com/spurious-correlations](http://tylervigen.com/spurious-correlations),  
[creative commons license](https://creativecommons.org/licenses/by/4.0/)</small>

---

![Hm...](img/w02_spurious/chart-6.png)

<small>Wykres pochodzi z [http://tylervigen.com/spurious-correlations](http://tylervigen.com/spurious-correlations),  
[creative commons license](https://creativecommons.org/licenses/by/4.0/)</small>

---

![Hm...](img/w02_spurious/chart-7.png)

<small>Wykres pochodzi z [http://tylervigen.com/spurious-correlations](http://tylervigen.com/spurious-correlations),  
[creative commons license](https://creativecommons.org/licenses/by/4.0/)</small>

---

## DLACZEGO?

- Bo tak wyszło
- Nigdy nie mamy pewności, czy wykryta korelacja nie jest przypadkowa

# Podsumowanie

## Literatura

<small>
