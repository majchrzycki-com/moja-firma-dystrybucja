# moja-firma-dystrybucja

**Agent zamówień B2B dla polskiej firmy: dystrybucja i hurt B2B.** Czyta zamówienie klienta z PDF, dopasowuje pozycje do kartoteki, sprawdza stany, liczy wartość według umowy i limit kredytowy, a na końcu oddaje szkic zamówienia z listą wyjątków do decyzji.

Pakiet branżowy paczki [moja-firma](https://github.com/majchrzycki-com/moja-firma). Procedura w formacie [Agent Skills](https://agentskills.io/specification) (`SKILL.md`) działa w Claude, ChatGPT i Codex, Microsoft 365 Copilot, Gemini oraz OpenClaw.

## Czego agent nie zrobi

Nie zgodzi się na rabat spoza umowy, dłuższy termin płatności ani wydanie towaru klientowi ponad limit. Pierwsze dwie decyzje należą do dyrektora sprzedaży, trzecia do finansów. Agent pokazuje, ile każde odstępstwo kosztuje w złotych i kto ma się pod nim podpisać, żeby ta rozmowa zajęła minutę, a nie pół dnia.

Ślepa automatyzacja szkodzi tu w jednym konkretnym miejscu: przy dopasowaniu po opisie. W kartotece są dwa grzejniki C22 o wysokości 600 mm, jeden o długości 1000, drugi 800. Agent, który dopasuje linię 4 do złego indeksu, pokaże pełną dostępność i ukryje brak dwunastu sztuk, a klient dowie się o nim od kierowcy. Dlatego instrukcja każe porównywać wymiary, a nie tylko pierwsze słowa opisu.

Warunek brzegowy jest prosty. Jeśli ten sam produkt ma u Was trzy indeksy, a rabaty żyją w mailach handlowców, agent policzy wszystko na złych danych, tyle że szybciej niż ludzie. Najpierw jedna kartoteka i spisane warunki klientów, potem agent.

## Wypróbuj na danych ćwiczeniowych

W katalogu [`dane-cwiczeniowe/`](dane-cwiczeniowe/) są fikcyjne dane firmy: `kartoteka.csv`, `kartoteka.xlsx`, `klienci-warunki.csv`, `klienci-warunki.xlsx`, `stany.csv`, `stany.xlsx`, `zamowienie.pdf`. Pliki XLSX i CSV mają tę samą treść.

1. Zainstaluj procedurę `zamowienie-b2b` (niżej).
2. Dodaj pliki ćwiczeniowe do wiedzy agenta albo załącz je do rozmowy.
3. Napisz:

```text
Nowe zamówienie od klienta. Przeprowadź analizę według instrukcji projektu, licząc kodem na plikach z wiedzy. Na końcu przygotuj plik XLSX ze szkicem zamówienia i listą wyjątków.
```

4. Porównaj odpowiedź z [WYNIK-KONTROLNY.md](WYNIK-KONTROLNY.md). Jest tam też „krok z rzeczywistością”: jedna zmiana w danych i wynik, który agent powinien po niej pokazać.

## Instalacja

### Claude Code

```text
/plugin marketplace add majchrzycki-com/moja-firma
/plugin install moja-firma-dystrybucja@moja-firma
```

### Pozostałe narzędzia

```bash
node scripts/build.mjs
```

Skrypt tworzy `dist/skills/` dla Claude, Codex, OpenClaw i Copilot Cowork oraz `dist/instrukcje/` z tekstem do wklejenia w agencie Microsoft 365 Copilot, Gemie albo projekcie ChatGPT. Szczegóły instalacji w każdym narzędziu: [README rdzenia moja-firma](https://github.com/majchrzycki-com/moja-firma#instalacja).

## Ten sam agent krok po kroku

- [Agent zamówień B2B w Claude](https://majchrzycki.com/blog/agent-zamowien-b2b-w-claude-krok-po-kroku?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=zamowienie-b2b)
- [Agent zamówień B2B w Microsoft 365 Copilot](https://majchrzycki.com/blog/agent-zamowien-b2b-w-microsoft-365-copilot-krok-po-kroku?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=zamowienie-b2b)
- [Agent zamówień B2B w ChatGPT](https://majchrzycki.com/blog/agent-zamowien-b2b-w-chatgpt-krok-po-kroku?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=zamowienie-b2b)
- [Agent zamówień B2B w Gemini](https://majchrzycki.com/blog/agent-zamowien-b2b-w-gemini-krok-po-kroku?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=zamowienie-b2b)

Gdzie ten agent mieści się w całej firmie i jakich jeszcze agentów potrzebuje dystrybucja i hurt B2B: [darmowy poradnik branżowy](https://majchrzycki.com/transformacja-agenci-ai/dystrybucja-hurt-b2b?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=zamowienie-b2b#pobierz).

## Na własnych danych

Zacznij od procedury `kontrola-danych` z rdzenia moja-firma na eksporcie z Waszego programu. Jeśli kolumny nazywają się inaczej, agent pokaże przypisanie i poprosi o potwierdzenie. Pierwszy tydzień puść agenta obok normalnej pracy jednej osoby i porównuj wyniki.

Procedura nie jest poradą prawną, podatkową ani handlową. Wynik sprawdza osoba, która za niego odpowiada.

## Licencja

[MIT](LICENSE), dla procedur, skryptów i danych ćwiczeniowych.

Autor: [Krzysztof Majchrzycki](https://majchrzycki.com/o-mnie?utm_source=github&utm_medium=referral&utm_campaign=moja-firma&utm_content=zamowienie-b2b), wdrożenia AI w polskich firmach.

---

**English:** moja-firma-dystrybucja is an industry pack of the open [moja-firma](https://github.com/majchrzycki-com/moja-firma) Agent Skills for Polish SMBs. It contains one `SKILL.md` procedure (in Polish), fictional practice data and expected results. MIT licence.
