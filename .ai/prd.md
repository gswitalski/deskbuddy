# Dokument wymagań produktu (PRD) - DeskBuddy

## 1. Przegląd produktu
DeskBuddy to webowa aplikacja do zarządzania rezerwacją biurek w biurze. MVP wspiera organizację o wielkości do 200 użytkowników oraz 50 biurek. System pozwala pracownikom i administratorom na planowanie obecności, rezerwację pełnodniowych stanowisk pracy, anulowanie rezerwacji oraz przegląd historii. Panel administracyjny umożliwia zarządzanie biurkami i kontami użytkowników. Projekt jest realizowany przez jedną osobę wspieraną sztuczną inteligencją w ciągu dwóch tygodni.

## 2. Problem użytkownika
Użytkownicy biura napotykają na:
- Brak pewności co do dostępności biurek
- Konflikty wynikające z nieplanowanego zajmowania stanowisk
- Chaos w organizacji przestrzeni pracy
DeskBuddy rozwiązuje te problemy poprzez centralny system rezerwacji zapewniający przejrzyste i bezkonfliktowe zarządzanie miejscami pracy.

## 3. Wymagania funkcjonalne
1. System użytkowników
   - Rejestracja (imię, email, hasło)
   - Logowanie
   - Edycja profilu (imię, email, hasło)
   - Autoryzacja i uwierzytelnianie (dostęp do funkcji tylko dla zalogowanych)
2. Widok publiczny
   - Formularz rejestracji dla niezalogowanych
3. Kalendarz tygodniowy
   - Wyświetlenie dostępności biurek z możliwością wyboru daty przez datepicker
4. Rezerwacja biurka
   - Pełny dzień; brak rezerwacji cyklicznych
   - Wybór biurka i potwierdzenie
5. Anulowanie rezerwacji
   - Możliwość anulowania nawet w dniu rezerwacji
6. Historia rezerwacji
   - Lista rezerwacji z rozróżnieniem statusów: aktywna, anulowana
7. Panel administracyjny
   - CRUD biurek (nazwa pomieszczenia, numer)
   - Przegląd i anulowanie rezerwacji użytkowników
   - Resetowanie hasła i dezaktywacja kont
8. Continuous Integration
   - Przykładowy pipeline GitHub Actions wykonujący build i testy

## 4. Granice produktu
W MVP nie uwzględniamy:
- Interaktywnej mapy biura i wizualizacji przestrzeni
- Systemu powiadomień (email, push)
- Integracji z zewnętrznymi kalendarzami
- Single sign-on i zaawansowanych metod uwierzytelniania
- Raportów wykorzystania przestrzeni
- Aplikacji mobilnej (tylko wersja webowa)
- Rezerwacji cyklicznych

## 5. Historyjki użytkowników
- US-001: Rejestracja nowego użytkownika
  Opis: nowy użytkownik wypełnia formularz (imię, email, hasło) i tworzy konto.
  Kryteria akceptacji:
  - wszystkie pola są wymagane i walidowane (imię niepuste, email we właściwym formacie, hasło minimum 8 znaków)
  - unikalny adres email
  - po rejestracji przekierowanie do strony logowania
  - w przypadku błędnych danych wyświetla odpowiedni komunikat

- US-002: Logowanie
  Opis: użytkownik loguje się, podając email i hasło.
  Kryteria akceptacji:
  - poprawne dane umożliwiają dostęp do kalendarza
  - niepoprawne dane wyświetlają komunikat o błędzie
  - po 5 nieudanych próbach tymczasowe zablokowanie na 1 minutę (scenariusz skrajny)

- US-003: Edycja profilu
  Opis: zalogowany użytkownik aktualizuje imię, email lub hasło.
  Kryteria akceptacji:
  - pola walidowane jak podczas rejestracji
  - zmiany zapisane w bazie i natychmiast widoczne
  - w przypadku konfliktu email pojawia się komunikat

- US-004: Dostęp do formularza rejestracji dla gości
  Opis: niezalogowany gość widzi wyłącznie formularz rejestracji.
  Kryteria akceptacji:
  - brak dostępu do kalendarza i rezerwacji
  - widoczność formularza rejestracji na stronie głównej

- US-005: Wyświetlenie kalendarza tygodniowego
  Opis: po zalogowaniu użytkownik widzi kalendarz tygodniowy z dostępnymi biurkami.
  Kryteria akceptacji:
  - kalendarz pokazuje 7 kolejnych dni i 50 biurek
  - dla każdej daty widać status dostępności biurka
  - wybór daty przez datepicker działa poprawnie

- US-006: Rezerwacja biurka
  Opis: użytkownik wybiera datę i biurko, potwierdza rezerwację na pełny dzień.
  Kryteria akceptacji:
  - rezerwacja zapisywana w systemie i odzwierciedlana w kalendarzu
  - w przypadku konfliktu (brak dostępnych biurek) wyświetla komunikat
  - 90% użytkowników kończy proces w mniej niż 30 sekund

- US-007: Anulowanie rezerwacji
  Opis: użytkownik anuluje swoją rezerwację nawet w dniu rezerwacji.
  Kryteria akceptacji:
  - status zmieniony na anulowana i widoczny w historii
  - w kalendarzu miejsce staje się dostępne
  - w przypadku braku aktywnej rezerwacji przycisk jest nieaktywny

- US-008: Podgląd historii rezerwacji użytkownika
  Opis: użytkownik przegląda listę swoich rezerwacji z podziałem na aktywne i anulowane.
  Kryteria akceptacji:
  - wyświetlane co najmniej data, biurko i status
  - możliwość filtrowania po statusie
  - dla pustej historii komunikat „Brak rezerwacji”

- US-009: Dodawanie biurka przez administratora
  Opis: administrator tworzy nowe biurko, podając nazwę pomieszczenia i numer.
  Kryteria akceptacji:
  - formularz waliduje pola jako wymagane
  - nowe biurko widoczne w kalendarzu

- US-010: Edycja biurka
  Opis: administrator edytuje dane istniejącego biurka.
  Kryteria akceptacji:
  - zmiany zapisane i natychmiast widoczne

- US-011: Usuwanie biurka
  Opis: administrator usuwa biurko.
  Kryteria akceptacji:
  - przed usunięciem ostrzeżenie o utracie danych rezerwacji
  - brak biurka w kalendarzu po usunięciu

- US-012: Zarządzanie rezerwacjami użytkowników (administrator)
  Opis: administrator przegląda rezerwacje wszystkich użytkowników i może je anulować.
  Kryteria akceptacji:
  - lista wszystkich przyszłych rezerwacji
  - możliwość anulowania wybranej rezerwacji

- US-013: Resetowanie hasła użytkownika (administrator)
  Opis: administrator resetuje hasło dowolnego użytkownika.
  Kryteria akceptacji:
  - po resecie użytkownik otrzymuje tymczasowe hasło lub link resetujący
  - nowe dane logowania działają poprawnie

- US-014: Dezaktywacja konta użytkownika (administrator)
  Opis: administrator dezaktywuje konto, blokując dostęp.
  Kryteria akceptacji:
  - dezaktywowany użytkownik nie może się zalogować
  - próba logowania wyświetla komunikat o zablokowanym koncie

- US-015: Bezpieczne przechowywanie haseł
  Opis: hasła użytkowników zapisywane są w formie zaszyfrowanej (hash).
  Kryteria akceptacji:
  - w bazie brak haseł w postaci jawnej
  - sprawdzenie poprawności hasła odbywa się przez porównanie hashy

- US-016: Autoryzacja dostępu do funkcji
  Opis: system ogranicza dostęp do funkcji w zależności od roli (użytkownik, administrator).
  Kryteria akceptacji:
  - funkcje rezerwacji i historii dostępne tylko dla zalogowanych użytkowników
  - panel administracyjny dostępny tylko dla roli administrator

## 6. Metryki sukcesu
- 90% użytkowników kończy rezerwację w mniej niż 30 sekund (monitorowanie czasu w aplikacji)
- 85% użytkowników ocenia interfejs jako intuicyjny (ankieta po wdrożeniu)
- administrator konfiguruje nowe biurko w mniej niż 2 minuty (analiza logów)
- zero konfliktów rezerwacji (testy integracyjne i monitor w produkcji) 
