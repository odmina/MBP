# Przygotowanie danych do analizy {#lab08}

:::{.box}

**WASZE ZADANIE**

UWAGA: na zajęcia przynajmniej jedna osoba z grupy musi mieć ze sobą urządzenie z działającym RStudio (komputer z zainstalowaną wersją desktopową albo jakąś formę dostępu do interentu, gdy korzystacie z wersji chmurowej).

Na zajęciach zaczniecie tworzyć w RStudio notatnik, w którym będziecie przygotowywać dane do analizy. Dlatego każda grupa powinna mieć na zajęcia plik csv taki, jaki ściągnie po zakończeniu badani, oczywiście bez kompletu danych. Wystarczy, że będziecie mieć 2-3 ankiety, format Waszej bazy pozostanie taki sam, a kod będzie działał gdy zakończycie badanie (co z resztą jest olbrzymią przewagą kodowania nad systemem okienkowym). 

:::


:::{.box}

**LITERATURA**

Ten rozdział zawiera najbardziej podstawowe informacje o przygotowaniu danych do analizy. Jeżeli chcecie dokładnie poznać "data wrangling" w R, polecam książkę *R for Data Science* autorstwa H. Wickhama i G. Grolemunda dostępną na licencji Creative Commons Attribution-NonCommercial-NoDerivs 3.0 [tutaj](https://r4ds.had.co.nz/index.html).

Zajęcia dotyczące przygotowania danych do analizy przygotowywane są w oparciu o rozdziały 9-16.

:::

Na tych zajęciach zapoznacie się z najważniejszymi kwestiami, na które MUSICIE zwrócić uwagę przed rozpoczęciem analizy danych. Stwórzcie folder, w którym będziecie przechowywać materiały związane z projektem i umieśćcie w nim plik .csv,  na którym będziecie pracować oraz plik .Rmd z notatnikiem, który posłuży Wam do do przygotowania danych do analizy.

Gdyby ktoś miał problem z podstawami R, polecam gorąco:

- przypomnieć sobie, co robiliśmy na zajęciach w poprzednim semestrze i w razie potrzeby jeszcze raz przećwiczyć;
- skorzystać z rozdziałów 1-8 [*R for Data Science*](https://r4ds.had.co.nz/index.html).

Jeżeli ktoś ma poczucie, że sam tego nie ogarnie, zapraszam na konsultacje. Przypominam, że w tym semestrze oprócz artykułu oddajecie mi wszystkie dodatkowe pliki stworzone w Waszym projekcie, wraz z notatnikiem .Rmd. Kod, który będzie dla mnie zaskakujący, będzie znacząco różnił się od tego, co robiliśmy na zajęciach, będzie wymagał od Was wyjaśnienia (będę pytać, co robią poszczególne linijki). 

:::{.box}

**TŁUMACZENIE**

Jeżeli ktoś ma problemy z korzystaniem z materiałów dotyczących R po angielsku, nie ma problemu, książka, z której korzystamy została wydana po polsku: Wickham, H., Grolemund, G., Zatorska, J., & Grupa Wydawnicza Helion. (2020). Jezyk R: Kompletny zestaw narzedzi dla analityków danych. Wydawnictwo Helion.

Jeszcze prostszą (i darmową!) metodą jest skorzystanie z opcji automatycznego tłumaczenia w przeglądarkach Chrome i Firefox. Co prawda przekład czasem jest zadziwiający, ale być może będzie dla Was pomocą.  

:::

## Jak powinien wyglądać przygotowany do analizy zbiór {#lab08-dataset}

Przygotowany do analizy zbiór powinien mieć wszystkie poniższe właściwości:

1. Każda obserwacja powinna znajdować się w osobnym wierszu...
2. ...a każda zmienna powinna znajdować się w osobnej kolumnie. Mam nadzieję, że zaprojektowaliście swoje ankiety, by tak właśnie było, jeżeli tak nie jest - pytajcie jak sobie z tym poradzić - przypominam, że każdy nieuporządkowany zbiór jest inny, więc nie podam Wam gotowego przepisu.
3. Nazwy zmiennych powinny być pozbawione spacji i polskich znaków (osiągamy to korzystając z funkcji `rename()`, która służy do zmiany nazw zmiennych).
4. Zmienne powinny być odpowiedniego typu, tzn. tam, gdzie w analizie chcecie korzystać z danych liczbowych, zmienne powinny być liczbami, a tam, gdzie chcecie korzystać z tekstu, zmienne powinny być zmiennymi tekstowymi. Jak się dowiedzieć, jaki jest typ zmiennej i jak go zmienić? Informacje są w poświęconym im [podrozdziale](#lab08-datatypes). 
5. Powinniście wiedzieć, jakie są zakresy wartości w zmiennych liczbowych. Gdyby jakaś wartość była wartością spoza zakresu, musicie: wiedzieć ile jest takich przypadków, podjąć decyzję, co z nimi zrobić i zastosować kod, który pozwoli Wam odfiltrować lub zastąpić nieodpowiednie wartości.
6. Powinniście wiedzieć, ile macie braków danych.

Bardziej szczegółowe informacje dostępne są poniżej i w notatnikach z zajęć.

## Import i eksport danych {#lab08-import-export}

Początkiem Waszej pracy jest import zbioru i zapisanie go jako zmiennej w Waszym środowisku w R. Na tych zajęciach pracujemy z wykorzystaniem plików .csv. Pamiętajcie jednak, że R pozwala Wam na import rozmaitych typów plików, np. plików .xlsx (paczka [readxl](https://readxl.tidyverse.org)) lub plików tworzonych w pakietach statystycznych (paczka [haven](https://haven.tidyverse.org)). 

Plik .csv jest plikiem tekstowym zawierającym dane w formie tabeli. Możecie go otworzyć w dowolnym edytorze tekstu, np. w Notatniku. Kolejne kolumny tabeli oddzielane są najczęściej przecinkami, średnikami lub tabulatorami (w ostatnim przypadku możecie spotkaać się z rozszerzeniem .tsv). Gdy korzystacie z formularzy Google, możecie ściągnąć plik .csv z wynikami Waszego badania. Gdy wprowadzacie dane z wykorzystaniem arkusza kalkulacyjnego, możecie zapisać wynik Waszej pracy w formie pliku .csv korzystając z opcji Eksport w menu Plik.

### Import

By zaimportować plik o nazwie "dane.csv" możecie skorzystać z następujących funkcji z biblioteki tidyverse:

- `read_csv("dane.csv")` - gdy kolumny rozdzielone są przecinkami;
- `read_csv2("dane.csv")` - gdy kolumny rozdzielone są średnikami;
- `read_tsv("dane.csv")` - gdy kolumny rozdzielone są tabulatorami.

Funkcji do importu jest więcej, informacje znajdziecie w pomocy R oraz [na stronie tidyverse](https://readr.tidyverse.org).

### Eksport

Wyobraźcie sobie, że stworzyliście notatnik, w którym przygotowaliście zbiór do analizy. Dla przejrzystości chcecie przeprowadzić analizy w nowym notatniku. W takiej sytuacji warto zapisać Wasz gotowy do analizy, wyczyszczony zbiór w nowym pliku .csv, który będziecie mogli zaimportować. Możecie wykorzystać w tym celu funkcje analogiczne do funkcji importujących, ale zamiast read_* używacie write_*:

- `write_csv("dane_do_analizy.csv")` - kolumny rozdzielone będą przecinkami;
- `write_csv2("dane_do_analizy.csv")` - kolumny rozdzielone będą średnikami;
- `write_tsv("dane_do_analizy.csv")` - kolumny rozdzielone będą tabulatorami.

:::{.box}

*Może się Wam to wydać oczywiste, ale pamiętajcie, by zmieniony zbiór zapisać pod inną nazwą niż zbiór wyjściowy. Jeżeli wykorzystacie nazwę już istniejącego pliku, R nie poinformuje Was, że plik o takiej nazwie już istnieje, po prostu nadpisze nowy plik na starym i stary plik stracicie. Jeżeli nie będziecie mieli skąd go ściągnąć ponownie, stracicie go bezpowrotnie.*

:::

## Kilka uwag o tidyverse {#lab08-tidyverse}

Przygotowując dane do analizy będziecie korzystać z fukcji wchodzących w skład paczki (biblioteki) **tidyverse**. Kiedy programujemy, przekazujemy funkcjom argumenty. Wiele z funkcji wchodzących w skład **tidyverse** funkcji służy do dokonywania operacji na zmiennych w zbiorze. W tych funkcjach zawsze pierwszym argumentem jest nazwa zbioru. Następnie po przecinkach następują nazwy zmiennych w zbiorze albo polecenia z wykorzystaniem nazw tych zmiennych.

W skład **tidyverse** wchodzi paczka [**dplyr**](https://dplyr.tidyverse.org). Podstawą jej działania jest kilka czasowników, które pozwalają Wam wykonywać operacje na zbiorze.

- `filter()` pozwala odfiltrować dane w zbiorze na podstawie wartości zmiennych;
- `select()` pozwala wybrać ze zbioru zmienne;
- `mutate()` pozwala stworzyć nową zmienną na podstawie już istniejących zmiennych;
- `summarise()` pozwala stworzyć podsumowanie zbioru;
- `arrange()` pozwala sortować zbiór.

Jeżeli chcesz dobrze nauczyć się korzystać z tych funkcji, gorąco polecam [rozdział z R for Data Science](https://r4ds.had.co.nz/transform.html).

Poniżej kilka przypadków często spotykanych w pracy z danymi pochodzącymi z kwestionariuszy.

### Filtrowanie

Wyobraź sobie, że Twoje badanie na absolutnie fascynujący temat skierowane było tylko do osób powyżej 25 roku życia, ale link do anonimowej ankiety rozpowszechniany był bardzo szeroko, wszelkimi dostępnymi kanałami, a ankietę mógł wypełnić każdy, niezależnie od wieku (kiedy jest to dobry, a kiedy zły pomysł to odrębny temat). Masz teraz w zbiorze osoby, które nie spełniają kryterium udziału w badaniu i chcesz pozbyć się ich ze zbioru. Możesz to zrobić, korzystając z funkcji `filter()`.

Załóżmy, że zbiór przechowujesz w zmiennej `moje_dane`, a informacje o wieku znajdują się w kolumnie `wiek`. Poniższy kod stworzy zbiór, z którego usunięte zostaną obserwacje dotyczące osób młodszych niż 25 lat i zapisze go w nowej zmiennej `moje_dane_25`. By obserwacja pozostała w zbiorze muszą zostać spełnione wyszystkie warunki wymienione po przecinku. W tym przypadku zmienna `wiek` musi mieć wartość większą lub równą 25.

```
moje_dane_25 <- filter(moje_dane, wiek >= 25)
``` 

Informacje o tym, jakich operatorów możesz użyć tworząc warunki znajdziesz tu: [R for Data Science, rodz. 5. Data transformation](https://r4ds.had.co.nz/transform.html).

Kolejne warunki możesz dodać po przecinku. Gdyby w zbiorze miały zostać jedynie dane dotyczące kobiet powyżej 25 roku życia, kod mógłby wyglądać tak:

```
moje_dane_25 <- filter(moje_dane, wiek >= 25, plec == "kobieta")
```

### Tworzenie nowych zmiennych i obliczenia

Załóżmy, że chcesz odwórcić skalę w kilku pytaniach kwestionariusza. Najprościej to zrobić korzystając z funkcji `mutate()`. Jej pierwszym argumentem jest nazwa zbioru. Kolejnymi argumentami są obliczenia, które chcesz wykonać. Przed znakiem równości podajesz nazwę nowej zmiennej, a po znaku równości obliczenie, w którym wykorzystujesz zmienne już istniejące w zbiorze: 

```
moje_dane <- mutate(moje_dane,
  P2_r = 6 - P2,
  P4_r = 6 - P4,
  P6_r = 6 - P6,
  P8_r = 6 - P8
  )
``` 

:::{.box}

Uniwersalny wzór na odwracanie skali wygląda tak:

*odwrócony wynik = koniec skali + początek skali - wynik osoby badanej*

Zatem dla skali od 1 do 5 mamy:

*odwrócony wynik = 5 + 1 - wynik osoby badanej*

Prawdopodobnie będziesz odwracać wiele pytań wg tego samego wzoru. By ograniczyć ilosć tekstu, który musisz wpisać, możesz skorzystać z funkcji `across()`. Więcej informacji na jej temat znajdziesz tu: [Apply a function (or functions) across multiple columns](https://dplyr.tidyverse.org/reference/across.html).
:::

### Wybieranie kolumn

Załóżmy, że zmienne w pytaniach, które tego wymagały są już odwrócone i chcesz usunąć oryginalne zmienne i ustawić zmienne w zbiorze tak, by wyniki w kolejnych pytaniach następowały po sobie, czyli P1, P2_r, P3, P4_r itd. Możesz skorzystać z funkcji `select()`. Jak zwykle, podajesz najpierw nazwę zbioru. Potem po przecinku podajesz nazwy zmiennych, które mają zostać w zbiorze. Jeżeli chcesz usunąć jakąś zmienną, wpisujesz jej nazwę z minusem. By usunąć stare zmienne:

```
moje_dane <- select(moje_dane, -P2, -P4, -P6, -P8)
```


:::{.box}

Funkcja `select()` ma wiele słów pomocniczych, które pozwalają wykonywać najrozmaitsze manipulacje kolumnami. Informacje o nich znajdziesz tu: [Subset columns using their names and types](https://dplyr.tidyverse.org/reference/select.html)

:::

### Rura (*pipe*)

Jeżeli chcesz na zbiorze wykonać serię operacji, np. obrócić skalę i usunąć stare zmienne, możesz wykorzystać operator `%>%` zwany rurą (ang. *pipe*). "Przepycha" on wynik ostatniej operacji na zbiorze jako pierwszy argument kolejnej funkcji. Operacje obrócenia skali i wyrzucenia starych zmiennych możnaby zatem wykonać tak:

```
moje_dane <- moje_dane %>%
  mutate(
    P2_r = 6 - P2,
    P4_r = 6 - P4,
    P6_r = 6 - P6,
    P8_r = 6 - P8
  ) %>%
  select(-P2, -P4, -P6, -P8)

```

## Typy danych {#lab08-datatypes}

Typy danych w Waszym zbiorze możecie poznać korzystając funkcji `glimpse()` (w nawiasie musicie podać nazwę Waszego zbioru). Możecie spotkać się z następującymi typami danych:
  
  - `<chr>` - dane tekstowe
  - `<int>` - liczba całkowita
  - `<dbl>` - liczba rzeczywista
  - `<dt>` - data
  - `<dttm>` - data i czas
  - `<lgl>` - zmienna logiczna (może zawierać wartości `TRUE` i `FALSE`)
  - `<fct>` - faktor
  - ...i inne :)

Jak zmienić typ danych? Korzystacie z następujących funkcji:

- `as.integer()`, która zmienia typ danych na liczbę całkowitą;
- `as.character()`, która zmienia typ danych na tekstowy;
- `as.numeric()`, która zmienia typ danych na liczbę rzeczywistą.

Uwaga: jeżeli jakiejś wartości nie da się przekształcić na docelowy typ (np. tekstu "dwa" nie da się przekształcić na liczbę 2), uzyskacie brak danych. Dlatego zalecam ostrożność. 

Wyobraźmy sobie, że mamy w naszym zbiorze o nazwie `moje_dane` zmienną `dzieci` o typie  tekstowym i chcemy uzyskać zmienną `liczba_dzieci` o typie rzeczywistym. Skorzystamy z funkcji `mutate()`. 

```
moje_dane <- moje_dane %>%
  mutate(liczba_dzieci = as.numeric(dzieci))
```

Jeżeli nasza zmienna `dzieci` zawierała wartości `"syn"   "2"     "1"     "1"     "troje"`, to zmienna `liczba_dzieci` będzie zawierała wartości `NA  2  1  1 NA` (NA to brak danych).

## Wartości spoza skali i braki danych {#lab08-out-of-scale}

Może zdarzyć się, że w Waszym zbiorze pojawią się braki danych lub nieoczekiwane wartości. W ankietach papier-ołówek niewiele możecie z tym zrobić, w ankietach internetowych macie narzędzia by ograniczać występowanie takich sytuacji. Niemniej nawet w przypadku dobrze zaprojektowanej ankiety internetowej zachęcam Was (a w przypadku zadania zaliczeniowego wymagam od Was), byście weryfikowali zakres wprowadzonych wartości. Dlaczego? Np. dlatego, że czasami w pytaniu otwartym trudno ograniczyć zakres wprowadzanych wartości do sensownego przedziału i możecie dostać zaskakujący wynik, który warto znać przed przystąpieniem do analizy. 

### Braki danych

Funkcją służącą do weryfikowania, czy mamy do czynienia z brakiem danych jest funkcja `is.na()`. Jeżeli chcecie zobaczyć, czy w zmiennej `wiek` w zbiorze `moje_dane` macie jakiekolwiek braki, możecie wpisać:

```
is.na(moje_dane$wiek)
```

Funkcja `is.na()` zwraca `TRUE` jeżeli dana wartość jest brakiem danych i `FALSE` jeżeli nie jest. Robi to dla każdej pojedynczej wartości w wektorze. Jeżeli w zmiennej wiek mieliście wartości: 23, 26, 18, *NA*, 29, to po zastosowaniu is.na() otrzymacie `FALSE`, `FALSE`, `FALSE`, `TRUE`, `FALSE`. Żeby dowiedzieć się, czy macie jakiekolwiek braki, możecie użyć funkcji `any.na()`. Wtedy dostaniecie `TRUE`, jeżeli w danej zmiennej był choć jeden brak albo `FALSE`, jeżeli nie było ani jednego braku.

Jeżeli chcecie podliczyć, ile było braków możecie skorzystać z fajnej właściwości wartości logicznych. `TRUE` można traktować jak 1, a `FALSE` jako 0. Jeżeli wynik zastosowania funkcji `is.na()` zsumujecie przy użyciu funkcji `sum()`, otrzymacie liczbę braków.

```
sum(is.na(moje_dane$wiek))
```

### Podsumowania

Jest wiele sposobów, by przedstawić podsumowania zmiennych, ale zdecydowanie najprostszym jest użycie funkcji `summary()` (w nawiasie podajecie nazwę zmiennej ze zbiorem). W jej wydruku znajdziecie:

- dla zmiennych tekstowych i faktorów: informacje o częstości występowania każdej z wartości oraz informację o liczbie braków danych;
- dla zmiennych liczbowych: statystyki opisowe, czyli minima, maksima, średnią i kwartyle oraz informację o liczbie braków danych.

Dla bardziej złożonych danych warto spojrzeć na wykresy! Więcej informacji na ten temat w części poświęconej wykresom.
