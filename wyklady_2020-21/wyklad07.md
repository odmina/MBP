---
title: Próba i populacja
---

# Słowem przypomnienia

## Zmienne a przyczynowość

- Zmienna niezależna **wyjaśnia zmienność** zmiennej zależnej
- Czasem zmienna niezależna **wpływa na** zmienną zależną, ale nie zawsze

RELATYWNIE TRUDNO PRZEPROWADZIĆ BADANIE POKAZUJĄCE ZALEŻNOŚĆ PRZYCZYNOWO SKUTKOWĄ!

## Rodzaje związków między zmiennymi

- Różnice między grupami:
  + zmienna niezależna: zmienna grupująca
  + zmienna zależna: zmienna, której zmienność może być wyjaśniania przynależnością do grup różniących się poziomiem zmiennej niezależnej
  + prosty przykład: płeć a skłonność do ryzyka

------------

- Korelacja:
  + określamy współzmienność zmiennej niezależnej i zależnej, związek liniowy między nimi
  + prosty przykład: badamy, czy osoby u których obserwujemy większe natężenie cechy "męskość" są bardziej skłonne do ryzyka

## Podstawowe własności korelacji

- Siła związku między zmiennymi
- Im silniejszy związek, tym dwie zmienne są bliżej zależności **liniowej**
- Związek najczęściej wyrażony współczynnikiem korelacji

## Współczynnik korelacji 

- Technicznie kilka różnych, w praktyce podobna interpretacja
- r Pearsona, rho Spearmana, tau Kendalla
- Wartości od -1 do 1, im wyższa wartość bezwzględna, tym silniejszy związek
- Wsp. korelacji = 1 lub -1 - idealna zależność liniowa

## Korelacje dodatnie i ujemne

![](https://upload.wikimedia.org/wikipedia/commons/8/83/Pearson_Correlation_Coefficient_and_associated_scatterplots.png)

<small>[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0) [wikipedia.org](https://en.wikipedia.org/wiki/Correlation_and_dependence#/media/File:Pearson_Correlation_Coefficient_and_associated_scatterplots.png)</small>

## Możliwe wyjaśnienia obserwowanego związku A z B

- A powoduje B lub B powoduje A
- A lub B powoduje całą->kaskadę->różnych->zmian, na końcu której jest druga badana zmienna
- Trzeci czynnik (grupa czynników) powoduje, że pojawia się związek A i B
- Dodatnie i ujemne sprzężenia zwrotne (zależności cykliczne)
- Związek może być PRZYPADKOWY

-----

![](img/mozarella.png)

<small>Wykres pochodzi z [http://tylervigen.com/spurious-correlations](http://tylervigen.com/spurious-correlations)</small>

# Próba vs populacja

## Populacja i próba

- *Populacja* - ogół osób, do których odnosi się dana teoria psychologiczna (np. populacja wszystkich ludzi, populacja kobiet, populacja niemowląt)
- Najczęściej nie możemy zbadać całej populacji ze względów praktycznych
- Badamy tylko określoną cześć populacji - *próbę*
- Jest wiele różnych metod *doboru próby*

## Metody doboru próby

- Probabilistyczne
    - Dobór prosty losowy (_simple random sampling_)
    - Dobór warstwowy (_stratified sampling_)
    - Dobór systematyczny (_systematic sampling_)

---------

- Nieprobabilistyczne
    - Dobór przypadkowy (_convenience sampling_)
    - Dobór kwotowy (_quota sampling_)
    - Kula śniegowa (_snowball sampling_)

-----------

ISTNIEJE JESZCZE WIELE INNYCH METOD DOBORU PRÓBY

## Dobór prosty, losowy

- Każda osoba z populacji ma równą szansę dostania się do próby
- Potrzebny **operat losowania**

## Dobór prosty, losowy

![](img/w02_simple_random.png)

<small>Obrazek pochodzi z artykułu Seemy Singh pt. [Sampling Techniques](https://towardsdatascience.com/sampling-techniques-a4e34111d808)</small>

## Dobór warstwowy

- Dobór pod względem jakiejś ważnej charakterystyki
- Najpierw trzeba wyłonić ważne charakterystyki, co bywa trudne
- W obrębie warstw stosujemy dobór prosty losowy

## Dobór warstwowy

![](img/w02_stratified.png)

<small>Obrazek pochodzi z artykułu Seemy Singh pt. [Sampling Techniques](https://towardsdatascience.com/sampling-techniques-a4e34111d808)</small>

## Dobór systematyczny

- Jeśli dysponujemy populacją uszeregowaną, możemy wybrać co n-tą osobę z szeregu
- Często w badaniach medycznych (np. _co trzecia osoba rejestrująca się do onkologa w WCO_)
- Metoda dobra jeśli tylko lista nie zawiera w sobie ukrytego porządku

## Dobór systematyczny

![Dobór systematyczny](img/w02_systematic.png)

<small>Obrazek pochodzi z artykułu Seemy Singh pt. [Sampling Techniques](https://towardsdatascience.com/sampling-techniques-a4e34111d808)</small>

## Dobór przypadkowy

- Kto się nawinie
- Najczęstszy przypadek w badaniach psychologicznych
- Może nie stanowić problemu, może stanowić ogromny problem

## Dobór kwotowy

- Zakładamy liczebności osób o zadanych cechach obecne w populacji
- Rekrutujemy badanych aż osiągniemy te liczebności

## Kula śniegowa

- Rekrutujemy badanego, po czym każemy mu przyprowadzić ludzi podobnych do niego
- Zupełnie niepoprawne metodologicznie, ale czasem jest to jedyna opcja, jeśli badamy bardzo specyficzne populacje/bardzo rzadkie cechy

## Kula śniegowa

![](img/w02_snowball.png)

<small>Obrazek pochodzi z artykułu Seemy Singh pt. [Sampling Techniques](https://towardsdatascience.com/sampling-techniques-a4e34111d808)</small>

## Próba a populacja

- Skąd wiemy, że zależność wykryta w próbie jest obecna w populacji? Nawet jeśli mamy najlepszy, najbardziej reprezentatywny dobór próby.
- Nie wiemy
- Możemy przypuszczać z określonym *prawdopodobieństwem*
- Do określenia tego prawdopodobieństwa potrzebujemy testów statystycznych

# Bias w doborze próby

## Sampling bias

- Z *sampling bias* w doborze próby mamy do czynienia, jeżeli jacyś członkowie naszej docelowej populacji mają mniejszą/większą szansę na udział w badaniu.

## Self selection bias

- Błąd, z którym mamy do czynienia, kiedy osoby zmotywowane do udziału w badaniu / zgadzające się na udział różnią się istotnie od interesującej nas populacji w sposób, który może wpłynąć na wyniki badania. 
- Przykład: badamy związek stereotypów dotyczących ról płciowych z jakąkolwiek zmienną zależną. Jest wysoce prawdopodobne, że w przypadku, w którym w badaniu będą brać udział ochotnicy, w naszej próbie znajdą się osoby o skrajnych poglądach na ten temat, co może prowadzić do zniekształcenia wyników.

## Dobób badanych z jakiejś konkretnej lokalizacji 

- Błąd wynikający z tego, że z zasady osoby w jakiejś konkretnej lokalizacji (cała klasa, cała szkoła, przechodnie w jakimś konkretnym miejscu) mogą różnić się od interesującej nas populacji.
- Np. badanie w którym zmienną zależną jest poziom agresji przeprowadzone w jednej, konkretnej szkole.

## Healthy participant bias

- Ma szczególne znaczenie w badaniach związanych ze zdrowiem i badaniach epidemiologicznych.
- Osoby, które decydują się na udział w badaniu zwykle są nieco zdrowsze od tych, które na udział się nie decydują.
- Jak myślicie, jak ma się to do badań longitudinalnych i attrition?

## Berkson's fallacy

- Sytuacja, w której obserwujemy związek między dwoma zmiennymi tylko i wyłącznie ze względu na chcarakterystykę próby.
- Np. jeżeli prowadzimy badanie w szpitalu, mamy dużą szansę odkrycia, że istnieje korelacja między wystąpieniem dwóch konkretnych chorób, głównie dlatego, że nasi badani z jakiegoś powodu musieli trafić do szpitala...
- Inny przykład: związek talentu z atrakcyjnością wśród celebrytów.

## Exclusion bias

- Ma miejsce, kiedy jakaś grupa potencjalnych uczestników badania w ogóle nie ma szansy wziąć udziału w badaniu...
- ...bo np. nie korzysta z Internetu.

## Najważniejsze pytanie

CZY NASZA PRÓBA NIE RÓŻNI SIĘ PRZYPADKIEM OD INTERESUJĄCEJ NAS POPULACJI? CZY MOŻEMY UOGÓLNIAĆ NASZ WYNIK?

# Podsumowanie

## Praktyczne pytania, które odbiorca badania powinien sobie zadać

- Czy dobór próby w badaniu miał charakter probablilistyczny czy autorzy zbadali jakąś próbę, którą akurat "mieli pod ręką"?
- Czy zbadane osoby mogą się różnić od interesującej nas populacji? Pod względem jakich zmiennych?
- Czy w/w zmienne mogą mieć wpływ na wyniki badania? 
- Czy autorzy starali się w jakikolwiek sposób kotrolować zmienne, które mogły zakłócić wyniki badania?


