# Wynik kontrolny: agent zamówień b2b

Liczby poniżej policzono niezależnie z plików w katalogu `dane-cwiczeniowe/`. Jeśli agent oddaje inne wartości, procedura nie działa poprawnie w Waszym narzędziu.

## Sprawdź wynik na danych kontrolnych

Porównaj odpowiedź z tabelami poniżej. Liczby policzyliśmy niezależnie z tych samych plików.

| Lp. | Indeks | Ilość | Cena kat. | Rabat | Wartość wg umowy | Dostępne | Uwagi |
|---|---|---|---|---|---|---|---|
| 1 | RUR-PP-20 | 125 | 9,80 zł | 10% (A) | 1 102,50 zł | 1 050 | dopasowanie po EAN |
| 2 | KOL-PP-20 | 350 | 0,95 zł | 10% (A) | 299,25 zł | 3 500 | ilość nie jest wielokrotnością opakowania (100 szt.) |
| 3 | ZAW-KUL-12N | 40 | 19,40 zł | 8% (B) | 713,92 zł | 65 | ZAW-KUL-12 wycofany, zamiennik droższy o 0,50 zł; potwierdzić z klientem |
| 4 | GRZ-22-600 | 20 | 412,00 zł | 5% (C) | 7 828,00 zł | 8 | brakuje 12 szt.; 24 szt. w drodze na 12.05.2026 |
| 5 | ZAW-TER-15 | 20 | 32,00 zł | 8% (B) | 588,80 zł | 260 | |
| 6 | GLW-TER | 20 | 38,50 zł | 8% (B) | 708,40 zł | 230 | |
| 7 | IZO-22 | 200 | 2,10 zł | 10% (A) | 378,00 zł | 800 | dopasowanie po EAN |
| 8 | PMP-25-60 | 2 | 689,00 zł | 5% (C) | 1 309,10 zł | 8 | |

| Pozycja | Wartość |
|---|---|
| Wartość katalogowa | 13 781,50 zł |
| Wartość według umowy (A 10%, B 8%, C 5%) | 12 927,97 zł |
| Wartość przy żądanym rabacie 12% na całość | 12 127,72 zł |
| Różnica do decyzji | 800,25 zł |
| Termin płatności | żądany 45 dni, umowny 30 dni |
| Limit kredytowy | 60 000,00 zł |
| Saldo należności | 48 200,00 zł, w tym 6 100,00 zł przeterminowane (18 dni) |
| Saldo po zamówieniu | 61 127,97 zł, przekroczenie limitu o 1 127,97 zł |

Na liście wyjątków powinno się znaleźć sześć spraw: opakowanie w linii 2 i zamiennik w linii 3 (opiekun klienta z klientem), brak grzejników przy żądaniu jednorazowej dostawy na 06.05 (opiekun z klientem: dostawa częściowa albo późniejszy termin), rabat 12% i termin 45 dni (dyrektor sprzedaży) oraz przekroczenie limitu przy przeterminowanym saldzie (finanse). Jeśli linia 4 ma dostępne 20 sztuk, agent dopasował grzejnik 600 × 800. Jeśli wartość wynosi 12 127,72 zł, agent uwierzył klientowi zamiast umowie.

## Krok z rzeczywistością

Następnego dnia klient wpłaca zaległe 6 100 zł. Otwórz `klienci-warunki.xlsx` i w wierszu K-0107 zmień: `saldo_naleznosci_pln` na 42100, `w_tym_przeterminowane_pln` na 0, `najstarsza_zaleglosc_dni` na 0. Usuń stary plik z wiedzy projektu, dodaj nowy i zadaj w nowej rozmowie to samo pytanie.

Agent powinien teraz pokazać saldo po zamówieniu **55 027,97 zł** i wolny limit **4 972,03 zł**, a wyjątek kredytowy powinien zniknąć z listy. Wartość zamówienia się nie zmienia: nadal 12 927,97 zł według umowy i 800,25 zł różnicy przy żądanym rabacie. Zostaje pięć wyjątków: opakowanie, zamiennik, grzejniki, rabat i termin.

Wpłata zdjęła jedną decyzję z biurka finansów, ale nie zdjęła żadnej z biurka dyrektora sprzedaży. Jeśli agent po tej zmianie uzna całe zamówienie za „czyste”, nie trzyma się instrukcji.
