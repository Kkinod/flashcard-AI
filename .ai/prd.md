# Dokument wymagań produktu (PRD) - Fiszki Edukacyjne

## 1. Przegląd produktu

Fiszki Edukacyjne to aplikacja webowa umożliwiająca tworzenie, zarządzanie i powtarzanie fiszek edukacyjnych. Aplikacja oferuje dwie główne metody tworzenia fiszek:

- Generowanie fiszek przez AI na podstawie wprowadzonego tekstu (kopiuj-wklej).
- Manualne tworzenie fiszek przy użyciu prostego formularza.

Dodatkowo system zapewnia intuicyjny interfejs do przeglądania, recenzji (zaakceptuj, edytuj, odrzuć) oraz zarządzania fiszkami, a także integrację z gotowym, open-source algorytmem powtórek (spaced repetition). Użytkownicy mają również możliwość zarządzania swoim kontem (edycja hasła oraz usunięcie konta).

## 2. Problem użytkownika

Manualne tworzenie wysokiej jakości fiszek edukacyjnych jest czasochłonne i często zniechęca użytkowników do korzystania z efektywnych metod nauki, takich jak spaced repetition. Użytkownicy potrzebują rozwiązania, które automatycznie generuje fiszki w oparciu o dostarczony tekst, jednocześnie umożliwiając łatwą edycję i zarządzanie nimi, aby usprawnić proces nauki i poprawić wyniki edukacyjne.

## 3. Wymagania funkcjonalne

1. Generowanie fiszek przez AI:

   - Umożliwienie wprowadzenia tekstu (kopiuj-wklej) o długości od 1000 do 10000 znaków.
   - Automatyczna walidacja wprowadzonego tekstu na poziomie frontendu, backendu.
   - AI generuje kandydatów na fiszki zawierających pola "przód" (maks. 200 znaków) i "tył" (maks. 500 znaków).
   - Prezentacja kandydatów do recenzji z wyświetleniem metadanych (data, nazwa użytkownika) oraz zapisem logów procesu generowania w dedykowanej tabeli.

2. Recenzja kandydatów na fiszki:

   - Użytkownik przegląda listę wygenerowanych kandydatów i ma możliwość:
     - Akceptacji fiszki (zapis do bazy danych),
     - Edycji fiszki,
     - Odrzucenia fiszki.
   - Możliwość wykonania bulk akcji (zbiorczego zaakceptowania, edycji lub odrzucenia fiszek).

3. Manualne tworzenie fiszek:

   - Udostępnienie prostego formularza do ręcznego tworzenia fiszek (przód i tył).
   - Walidacja pól "przód" (maks. 200 znaków) oraz "tył" (maks. 500 znaków).
   - Ręczne tworzenie fiszek i wyświetlanie w ramach widoku listy "Moje fiszki".

4. Zarządzanie fiszkami:

   - Przeglądanie, edycja i usuwanie zaakceptowanych fiszek.
   - Lista fiszek jest paginowana (10 fiszek na stronę).
   - Wyświetlanie komunikatu o pustej liście w przypadku braku fiszek.

5. Zarządzanie kontem użytkownika:

   - System prostych kont użytkowników umożliwiający rejestrację/logowanie i przechowywanie fiszek.
   - Funkcjonalność edycji hasła oraz usunięcia konta użytkownika.

6. Integracja z systemem powtórek:

   - Integracja zaakceptowanych fiszek z gotowym, open-source algorytmem spaced repetition.

7. Statystyki generowania fiszek:

   - Zbieranie informacji o liczbie generowanych fiszek przez AI oraz ich liczbie akceptowanych.

8. Wymagania prawne i ograniczenia:
   - Dane osobowe użytkowników i fiszek przechowywane zgodnie z RODO.
   - Prawo do wglądu i usunięcia danych (konto wraz z fiszkami) na wniosek użytkownika.

## 4. Granice produktu

- Nie jest przewidziane wdrożenie własnego, zaawansowanego algorytmu powtórek (np. SuperMemo, Anki); wykorzystana będzie jedynie gotowa biblioteka open-source.
- Brak wsparcia dla importu wielu formatów (PDF, DOCX, itp.).
- Nie przewiduje się współdzielenia zestawów fiszek między użytkownikami.
- Wykluczona jest integracja z innymi platformami edukacyjnymi.
- Aplikacja mobilna nie jest częścią MVP (na początek tylko wersja webowa).

## 5. Historyjki użytkowników

### US-001: Uwierzytelnianie użytkownika

- Tytuł: Rejestracja i logowanie użytkownika
- Opis: Jako nowy użytkownik chcę mieć możliwość rejestracji i logowania się do systemu, aby bezpiecznie przechowywać oraz zarządzać moimi fiszkami.
- Kryteria akceptacji:
  1. Formularz rejestracji z walidacją danych (np. email, hasło).
  2. Mechanizm logowania z weryfikacją tożsamości.
  3. Bezpieczne przechowywanie haseł (np. przez hash i salt).

### US-002: Generowanie fiszek przez AI

- Tytuł: Automatyczne generowanie fiszek przy użyciu AI
- Opis: Jako użytkownik chcę móc wprowadzić tekst (1000–10000 znaków), aby system za pomocą AI wygenerował kandydatów na fiszki z polami "przód" i "tył".
- Kryteria akceptacji:
  1. Pole do wprowadzenia tekstu odpowiadające wymaganej długości.
  2. Automatyczna walidacja długości tekstu.
  3. Generacja kandydatów na fiszki z poprawnymi limitami znaków (przód max 200, tył max 500).
  4. Wyświetlenie metadanych dla każdej kandydatury (data, nazwa użytkownika).

### US-003: Ręczne tworzenie fiszek

- Tytuł: Manualne tworzenie fiszek
- Opis: Jako użytkownik chcę mieć możliwość ręcznego tworzenia fiszek za pomocą prostego formularza, aby dodać fiszki, które nie zostały wygenerowane przez AI.
- Kryteria akceptacji:
  1. Formularz umożliwiający wprowadzenie pól "przód" i "tył" z walidacją długości.
  2. Poprawne zapisanie fiszki do bazy danych po walidacji.

### US-004: Recenzja kandydatów na fiszki

- Tytuł: Przegląd i edycja kandydatów na fiszki wygenerowanych przez AI
- Opis: Jako użytkownik chcę przeglądać kandydatów na fiszki wygenerowanych przez AI oraz mieć możliwość ich zaakceptowania, edycji lub odrzucenia, zarówno indywidualnie, jak i zbiorczo.
- Kryteria akceptacji:
  1. Lista kandydatów wyświetlana w przejrzystym interfejsie.
  2. Możliwość akceptacji, edycji lub odrzucenia każdej fiszki.
  3. Funkcjonalność bulk actions umożliwiająca zbiorcze operacje.
  4. Zapis do bazy danych wyłącznie zaakceptowanych fiszek.

### US-005: Zarządzanie fiszkami

- Tytuł: Przegląd, edycja i usuwanie zaakceptowanych fiszek
- Opis: Jako użytkownik chcę mieć możliwość przeglądania, edytowania oraz usuwania już zapisanych fiszek w celu utrzymania porządku i aktualności mojej bazy fiszek.
- Kryteria akceptacji:
  1. Lista ("Moje fiszki") zapisanych fiszek wyświetlana z paginacją (10 fiszek na stronę), w widoku listy znajduje się również przycisk dodania nowej fiszki.
  2. Naciśniecie przycisku dodania nowej fiszki otwiera formularz z polami "Przód" i "Tył".
  3. Opcje edycji i usuwania fiszek dostępne w interfejsie.
  4. Wyświetlenie komunikatu o pustej liście w przypadku braku fiszek.
  5. Przy każej fiszce na liście (w widoku "Moje fiszki") widoczna jest opcja usunięcia.
  6. Po wybraniu usuwania użytkownik musi potwierdzić operację, zanim fiszka zostanie trwale usunięta.
  7. Fiszki zostają trwale usunięte z bazy danych po potwierdzeniu operacji usuwania.

### US-006: Zarządzanie kontem użytkownika

- Tytuł: Edycja hasła i usunięcie konta
- Opis: Jako użytkownik chcę mieć możliwość zmiany swojego hasła oraz usunięcia konta, aby zarządzać bezpieczeństwem dostępu do moich danych.
- Kryteria akceptacji:
  1. Funkcjonalność umożliwiająca zmianę hasła po poprawnej weryfikacji.
  2. Opcja usunięcia konta z potwierdzeniem operacji.

### US-007: Sesja nauki z systemem powtórek

- Tytuł: Sesja nauki z algorytmem spaced repetition
- Opis: Jako zalogowany użytkownik chcę, aby zaakceptowane fiszki były dostępne w widoku "Sesja nauki" opartym na zewnętrznym algorytmie, aby móc efektywnie się uczyć (spaced repetition).
- Kryteria akceptacji:
  1. W widoku "Sesja nauki" algorytm przygotowuje dla mnie sesję nauki fiszek
  2. Na start wyświetlany jest przód fiszki, poprzez interakcję użytkownik wyświetla jej tył.
  3. Użytkownik ocenia zgodnie z oczekiwaniami algorytmu na ile przyswoił fiszkę.
  4. Następnie algorytm pokazuje kolejną fiszkę w ramach sesji nauki.

### US-008: Bezpieczny dostęp i autoryzacja

- Tytuł: Bezpieczny dostęp i autoryzacja
- Opis: Jako zalogowany użytkownik chcę mieć pewność, że moje fiszki nie są dostępne dla innych użytkowników, aby zachować prywatność i bezpieczeństwo.
- Kryteria akceptacji:
  1. Tylko zalogowany użytkownik może wyświetlać, edytować i usuwać swoje fiszki.
  2. Nie ma dostepu do fiszek innych użytkowników ani możliwości współdzielenie ich.

## 6. Metryki sukcesu

1. Co najmniej 75% fiszek wygenerowanych przez AI musi być zaakceptowanych przez użytkownika.
2. Użytkownicy powinni tworzyć przynajmniej 75% fiszek z wykorzystaniem generacji AI.
3. System walidacji powinien skutecznie zapobiegać przekraczaniu limitów znaków (przód max 200, tył max 500, tekst wejściowy 1000–10000 znaków).
4. Interfejs recenzji kandydatów powinien umożliwiać łatwe i intuicyjne akceptowanie, edycję lub odrzucanie fiszek (w tym bulk actions).
5. Integracja z algorytmem spaced repetition powinna poprawić efektywność nauki, co można mierzyć poprzez feedback użytkowników oraz analizę logów systemowych.
