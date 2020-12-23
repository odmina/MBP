---
title: Istotność statystyczna - podejście 1
---

# Słowem przypomnienia

## Próba i populacja

- *Populacja* to ogół osób, do których odnosi się dana teoria (np. populacja wszystkich ludzi, populacja kobiet, populacja niemowląt).
- *Próba* to ta część populacji, którą objęliśmy badaniem

## Dobór probabilistyczny vs nieprobabilistyczny

- Proces wyłaniania próby z populacji nazywamy *doborem próby*
- *Dobór próby* może być probabilistyczny lub nieprobabilistyczny  
- Dobór propabilistyczny, czyli losowy, zakłada, że dysponujemy jakimś *operatem losowania* dla badanej populacji i z niego **losowo** wyłaniamy osoby badane
- Wszystkie metody statystyczne, jakich będziecie używać zakładają, że próba była dobrana losowo

## (Wybrane) metody probabilistyczne 
 
- Dobór prosty losowy (_simple random sampling_)
- Dobór warstwowy (_stratified sampling_)
- Dobór systematyczny (_systematic sampling_)

## (Wybrane) metody nieprobabilistyczne

- Dobór przypadkowy (_convenience sampling_)
- Dobór kwotowy (_quota sampling_)
- Kula śniegowa (_snowball sampling_)

## Ok, ale w większości badań psychologicznych mamy ochotników!

- Z oczywistych względów możemy zbadać tylko osoby, które chcą wziąć udział w naszym badaniu
- MOŻEMY SENSOWNIE KORZYSTAĆ Z WYNIKÓW TAKICH BADAŃ...
- ...przy czym zawsze musimy zadać sobie pytanie, w jaki sposób dobór próby mógł wpłynąć na wyniki

## Sampling bias

- Z *sampling bias* w doborze próby mamy do czynienia, jeżeli jacyś członkowie naszej docelowej populacji mają mniejszą/większą szansę na udział w badaniu.

# Istota istotności statycznej

## Jak myślicie, czy jeżeli między jakimiś dwoma populacjami nie ma żadnych różnic, wylosujemy próbę poprawnie, bez żadnego bias, to możemy w badaniu zaobserwować różnicę między próbami wylosowanymi z tych populacji?

## Bardzo prosty przykład na to, że nawet jeżeli w populacji nie ma różnic między grupami, możemy w badaniu taką różnicę znaleźć

Wyobraźcie sobie, że mamy populację 100 reniferów Świętego Mikołaja, w której jest 50 **miziołków** i 50 **buziołków**. Średni czas, w jakim renifery mogą dostarczyć worek prezentów z Rovaniemi i Gdańska jest taki sam, niezależnie od odmiany (miziołki / buziołki). 

------------

*UWAGA: w miejsce **miziołków** i **buziołków** możesz wstawić dowolne insteresujące Cię grupy :) w miejsce **czasu dostarczenia prezentu** możesz wstawić dowolną cechę.*



## Miziołek

![Miziołek](img/renifer1.jpg){height=350px}

<small>Autor: Are G Nilsen, Licencja: [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0), ściągnięte z [wikipedii](https://en.wikipedia.org/wiki/Reindeer#/media/File:Reinbukken_på_frisk_grønt_beite._-_panoramio.jpg)</small>

## Buziołek

![Miziołek](img/renifer2.jpg){height=350px}

<small>Autor: Ludovic Rivallain, Licencja: [CC BY-SA 3.0](https://creativecommons.org/licenses/by-sa/3.0), ściągnięte z [wikipedii](https://en.wikipedia.org/wiki/Reindeer#/media/File:Rennes_d'élevage,_mais_en_liberté,_près_de_Suomussalmi._-_panoramio.jpg)</small>

## Rozkład wyników - miziołki

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2-1.png)

## Rozkład wyników - buziolki

![plot of chunk unnamed-chunk-3](figure/unnamed-chunk-3-1.png)

## Podstawowe statystyki w obydwu grupach

- Średnia: 15.16
- Minimum: 6
- Maximum: 25

## Na ile sposobów możemy wybrać 3 z 50 miziołków / buziołków?

::: incremental

19600

:::

## Jaka będzie średnia dla 3 z 50 miziołków / buziołków?

![plot of chunk unnamed-chunk-4](figure/unnamed-chunk-4-1.png)

## Na ile sposobów możemy wybrać 5 z 50 miziołków / buziołków?

::: incremental

- Na 2118760 sposobów

:::

## Jaka będzie średnia dla 5 z 50 miziołków / buziołków?

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-5-1.png)

## Na ile sposobów możemy wybrać 7 z 50 miziołków / buziołków?

::: incremental

- Na 99884400 sposobów99884400

:::

## Jaka będzie średnia dla 7 z 50 miziołków / buziołków?

*Stworzenie 99884400 7 elementowych zbiorów wybranych z 50 elementowego zbioru miziołków i policzenie średniej dla każdego trwało tak długo, że nie chciało mi się czekać...*

## Skupmy się na badaniu, w którym losujemy 3 miziołki i 3 buziołki

![plot of chunk unnamed-chunk-6](figure/unnamed-chunk-6-1.png)

## Jakie jest prawdopodobieństwo, że w naszym badaniu, gdzie n = 3 wystąpi średnia mniejsza od 10 albo większa od 20?

- Średnia mniejsza od 10: 0.0358673
- Średnia większa od 20: 0.0467857

## A jakie jest prawdopodobieństwo takiego scenariusza?

- Wylosowaliśmy trzy miziołki i uzyskaliśmy dla nich średnią mniejszą od 10.
- Wylosowaliśmy trzy buziołki i uzyskaliśmy dla nich średnią większą od 20.
- Pamiętamy, że grupy tak naprawdę się nie różnią i dla obydwu średnia jest równa około 15!!!!

---------

0.0016781

## A jakie jest prawdopodobieństwo takiego scenariusza?

- Wylosowaliśmy trzy miziołki i uzyskaliśmy dla nich średnią mniejszą od 13.
- Wylosowaliśmy trzy buziołki i uzyskaliśmy dla nich średnią większą od 17. 

## mean < 13 & mean > 17 

- Średnia mniejsza od 13: 0.2270918
- Średnia większa od 17: 0.2578061
- Prawdopodobieństwo, że dla miziołków średnia < 13, a dla buziołków > 17: 0.0585457

## A jakie jest prawdopodobieństwo takiego scenariusza?

- Wylosowaliśmy trzy miziołki i uzyskaliśmy dla nich średnią mniejszą od 13,5.
- Wylosowaliśmy trzy buziołki i uzyskaliśmy dla nich średnią większą od 16,5. 

## mean < 13,5 & mean > 16,5 

- Średnia mniejsza od 13,5: 0.2968367
- Średnia większa od 16,5: 0.3323469
- Prawdopodobieństwo, że dla miziołków średnia < 13,5, a dla buziołków > 16,5: 0.0986528

## Ok, a co jeżeli zbadaliśmy więcej reniferów? Np. 5?

W naszym przykładzie w rzeczywistości nie ma różnic między miziołkami i buziołkami. Czy prawdopodobieństwo, że przez przypadek zaobserwujemy różnicę na poziomie 3 punktów będzie większe czy mniejsze, kiedy zbadamy więcej reniferów (5 zamiast 3)?

--------------------

- Średnia mniejsza od 13,5: 0.2366134
- Średnia większa od 16,5: 0.2810757
- Prawdopodobieństwo, że dla miziołków średnia < 13,5, a dla buziołków > 16,5: 0.0665063

## 3 vs 5 reniferów w grupie 

|Średnie w grupach|3 renifery|5 reniferów|
|-|-|-|
|10 i 20|0.0016781|0.0001002|
|13 i 17|0.0585457|0.0326059|
|13,5 i 16,5|0.0986528|0.0665063|

## Wnioski z tej prostej symulacji

- Nawet jeżeli dwie grupy się nie różnią, możemy w badaniu uzyskać jakąś różnicę między wylosowanymi z nich próbami.
- Jesteśmy w stanie oszacować prawdopodobieństwo wystąpienia różnicy o określonej wielkości (choć w praktyce jest to nieco bardziej skomplikowane niż w podanym przykładzie).

---

- Im mniejsza różnica (słabsza zależność), tym większe prawdopodobieństwo, że ją uzyskamy w badaniu przez przypadek, nawet jeżeli w populacji nie ma różnic między grupami.
- Im więcej osób w naszej próbie, tym mniejsze prawdopodobieństwo, że przez przypadek zaobserwowaliśmy zależność, której nie ma (zalecam jednak ostrożność).

## Wartość *p*

- Wartość *p* (*p value*), z którą stykacie się analizując wyniki badań oznacza prawdopodbieństwo z jakim obserwowany w badaniu wynik mógł pojawić się przez przypadek w sytuacji, w której zaoserwowana zależność w populacji nie występuje.

# Podsumowanie

## Ważny wniosek

- Nawet jeżeli w interesującej nas populacji nie ma żadnej zależności między dwoma zmiennymi, możemy zaobserwować taką zależność nawet w doskonale zaprojektowanym badaniu.
- Dzieje się tak ze względu na to, że nie badamy całej populacji, a jedynie jej niewielką część (próbę) i możemy wystąpić sytuacja, w której zależność pojawi się przez przypadek. 
- To jak duże jest prawdopodobieństwo, że obserwowana przez nas wartość pojawiła się przez przypadek określa wartość p.

## Praktyczne pytania, które odbiorca badania powinien sobie zadać

- Jaki jest poziom istotności statystycznej uzyskanych wyników? Czy dla Ciebie, jako odbiorcy badania jest satysfakcjonujący?
 
