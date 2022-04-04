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
2. ...a każda zmienna powinna znajdować się w osobnej kolumnie. Mam nadzieję, że zaprojektowaliście swoje ankiety, by tak właśnie było, jeżeli tak nie jest - pytajcie jak sobie z tym poradzić.
3. Nazwy zmiennych powinny być pozbawione spacji i polskich znaków (osiągamy to korzystając z funkcji `rename()`, która służy do zmiany nazw zmiennych)
4. Zmienne powinny być odpowiedniego typu, tzn. tam, gdzie w analizie chcecie korzystać z danych liczbowych, zmienne powinny być liczbami, a tam, gdzie chcecie korzystać z tekstu, zmienne powinny być zmiennymi tekstowymi. Jak się dowiedzieć, jaki jest typ zmiennej i jak go zmienić? Informacje są w odpowiednim podrozdziale. 
5. Powinniście wiedzieć, jakie są zakresy wartości w zmiennych liczbowych. Gdyby jakaś wartość była wartością spoza zakresu, musicie: wiedzieć ile jest takich przypadków, podjąć decyzję, co z nimi zrobić i zastosować kod, który pozwoli Wam odfiltrować lub zastąpić nieodpowiednie wartości.
6. Powinniście wiedzieć, ile macie braków danych.

Bardziej szczegółowe informacje dostępne są poniżej i w notatnikach z zajęć.

## Typy danych {#lab08-datatypes}

Typy danych w Waszym zbiorze możecie poznać korzystając funkcji `glimpse()` (w nawiasie musicie podać nazwę Waszego zbioru). Możecie spotkać się z następującymi typami danych:
  
  - <chr> - dane tekstowe
  - <int> - liczba całkowita
  - <dbl> - liczba rzeczywista
  - <dt> - data
  - <dttm> - data i czas
  - <lgl> - zmienna logiczna (może zawierać wartości `TRUE` i `FALSE`)
  - <fct> - faktor
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


