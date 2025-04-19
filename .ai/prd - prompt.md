Jesteś doświadczonym menedżerem produktu, którego zadaniem jest stworzenie kompleksowego dokumentu wymagań produktu (PRD) w oparciu o poniższe opisy:


# DeskBuddy - Koncepcja MVP

## 1. Główny problem

DeskBuddy rozwiązuje problem efektywnego zarządzania miejscami pracy w biurze poprzez system rezerwacji biurek. Umożliwia pracownikom zaplanowanie obecności w biurze i zapewnienie sobie dostępnego miejsca pracy, eliminując chaos i konflikty związane z nieplanowanym zajmowaniem przestrzeni.

## 2. Najmniejszy zestaw funkcjonalności

- **Rezerwacja biurka**: Możliwość wyboru i rezerwacji konkretnego biurka na określony dzień
- **Odwoływanie rezerwacji**: Użytkownicy mogą anulować swoje rezerwacje
- **Kalendarz rezerwacji**: Widok tygodniowy dostępności biurek
- **Panel administracyjny**: Zarządzanie biurkami (dodawanie, edycja, usuwanie)
- **Zarządzanie rezerwacjami**: Admin może odwoływać rezerwacje użytkowników
- **System użytkowników**: Rejestracja, logowanie i podstawowe zarządzanie kontem
- **Historia rezerwacji**: Podgląd przeszłych i przyszłych rezerwacji użytkownika
- **Widok publiczny**: Ograniczony dostęp dla niezalogowanych gości (tylko rejestracja użytkownika)

## 3. Co NIE wchodzi w zakres MVP

- Interaktywna mapa biura lub wizualizacja przestrzeni
- System powiadomień (email, push)
- Integracja z zewnętrznymi kalendarzami
- Single sign-on lub zaawansowane metody uwierzytelniania
- Raporty wykorzystania przestrzeni biurowej
- Aplikacja mobilna (tylko wersja webowa)

## 4. Kryteria sukcesu

- 90% użytkowników może samodzielnie dokonać rezerwacji biurka w czasie poniżej 30 sekund
- 85% użytkowników ocenia interfejs jako intuicyjny (w ankiecie po wdrożeniu)
- Administrator może skonfigurować nowe biurko w systemie w czasie poniżej 2 minut
- Zero konfliktów rezerwacji (to samo biurko, ten sam czas)

</project_description>

<project_details>
<conversation_summary>
<decisions>
1. Organizacja 200 osób, 50 biurek.  
3. Rezerwacje pełnodniowe.  
4. Role: użytkownik i administrator.  
5. Widok publiczny: tylko formularz rejestracji.  
6. Brak rezerwacji cyklicznych.  
7. Brak wymagań wydajnościowych.  
8. Brak dodatkowych wskaźników sukcesu.  
9. Zespół: jedna osoba wspierana AI, czas realizacji MVP – 2 tygodnie.  
10. Atrybuty biurka: nazwa pomieszczenia i numer biurka.  
11. Formularz rejestracji: imię, email, hasło (bez potwierdzenia).  
12. Użytkownik może edytować profil.  
13. Ekran główny zalogowanego: kalendarz tygodniowy.  
14. Wybór daty: datepicker.  
15. Anulowanie rezerwacji możliwe nawet w dniu rezerwacji.  
16. Historia rezerwacji z rozróżnieniem statusów (aktywna, anulowana).  
17. Panel administracyjny: CRUD biurek pojedynczo; reset hasła i dezaktywacja kont; interfejs wyłącznie w języku polskim; przykładowy job GitHub Actions (build + testy).
</decisions>

<matched_recommendations>
1. Opracowanie modelu danych `Desk` z atrybutami: nazwa pomieszczenia, numer biurka.  
2. Specyfikacja formularza rejestracji (pola: imię, email, hasło) i reguły walidacji.  
3. Makieta UI ekranu głównego z kalendarzem tygodniowym oraz przyciskami rezerwacji/anulowania.  
4. Definicja komponentu datepicker do wyboru daty rezerwacji.  
5. Określenie polityki anulowania rezerwacji w kryteriach akceptacji.  
6. Rozbudowa modelu `Reservation` o pole `status` i endpointy do przeglądu historii.  
7. Projekt panelu admina z funkcjami CRUD dla biurek oraz zarządzania kontami (reset hasła, dezaktywacja).  
8. Przygotowanie przykładowego pipeline GitHub Actions wykonującego build i uruchamiającego testy.
</matched_recommendations>

<prd_planning_summary>
a. Główne wymagania funkcjonalne produktu  
 - Rejestracja użytkownika (imię, email, hasło) bez potwierdzenia.  
 - Logowanie i edycja profilu przez użytkownika.  
 - Widok publiczny: formularz rejestracji.  
 - Ekran główny zalogowanego: kalendarz tygodniowy z funkcją rezerwacji biurka (pełny dzień) za pomocą datepickera.  
 - Anulowanie rezerwacji nawet w dniu rezerwacji.  
 - Historia rezerwacji z rozróżnieniem statusów (aktywna, anulowana).  
 - Panel administracyjny: CRUD biurek (nazwa pomieszczenia, numer), reset hasła, dezaktywacja kont.  
 - Panel administracyjny: przegląd i możliwoś anulowania pojedynczych rezerwacji dowolnego użytkownika.
 - Interfejs wyłącznie w języku polskim.  
 - Przykładowy CI: GitHub Actions (build + testy).  

b. Kluczowe historie użytkownika i ścieżki korzystania  
 - Jako nowy użytkownik chcę w prosty sposób się zarejestrować, by uzyskać dostęp do rezerwacji.  
 - Jako zalogowany użytkownik chcę zobaczyć tydzień w kalendarzu i wybrać datę przez datepicker, by zarezerwować biurko.  
 - Jako użytkownik chcę móc anulować rezerwację nawet w dniu, by zwolnić biurko.  
 - Jako użytkownik chcę zobaczyć historię moich rezerwacji (aktywne i anulowane).  
 - Jako administrator chcę dodawać/edytować/usunąć biurko pojedynczo, by zarządzać zasobami.  
 - Jako administrator chcę resetować hasło i dezaktywować konto użytkownika, by zarządzać uprawnieniami.  
 - Jako administrator chcę przeglądać i anulować rezerwacje dowolnego użytkownika

c. Ważne kryteria sukcesu i sposoby ich mierzenia  
 - 90% użytkowników dokonuje rezerwacji w <30 s (monitorowanie czasu w aplikacji).  
 - 85% użytkowników ocenia interfejs jako intuicyjny (ankieta po wdrożeniu).  
 - Administrator konfiguruje nowe biurko w <2 min (logi operacji).  
 - Zero konfliktów rezerwacji (testy integracyjne + monitor konfliktów w produkcji).  

d. Nierozwiązane kwestie lub obszary wymagające dalszego wyjaśnienia  
 - Brak nierozwiązanych kwestii – wszystkie kluczowe pytania zostały wyjaśnione i podjęto decyzje.
</prd_planning_summary>

<unresolved_issues>
Brak nierozwiązanych kwestii.
</unresolved_issues>
</conversation_summary>

</project_details>

Wykonaj następujące kroki, aby stworzyć kompleksowy i dobrze zorganizowany dokument:

1. Podziel PRD na następujące sekcje:
   a. Przegląd projektu
   b. Problem użytkownika
   c. Wymagania funkcjonalne
   d. Granice projektu
   e. Historie użytkownika
   f. Metryki sukcesu

2. W każdej sekcji należy podać szczegółowe i istotne informacje w oparciu o opis projektu i odpowiedzi na pytania wyjaśniające. Upewnij się, że:
   - Używasz jasnego i zwięzłego języka
   - W razie potrzeby podajesz konkretne szczegóły i dane
   - Zachowujesz spójność w całym dokumencie
   - Odnosisz się do wszystkich punktów wymienionych w każdej sekcji

3. Podczas tworzenia historyjek użytkownika i kryteriów akceptacji
   - Wymień WSZYSTKIE niezbędne historyjki użytkownika, w tym scenariusze podstawowe, alternatywne i skrajne.
   - Przypisz unikalny identyfikator wymagań (np. US-001) do każdej historyjki użytkownika w celu bezpośredniej identyfikowalności.
   - Uwzględnij co najmniej jedną historię użytkownika specjalnie dla bezpiecznego dostępu lub uwierzytelniania, jeśli aplikacja wymaga identyfikacji użytkownika lub ograniczeń dostępu.
   - Upewnij się, że żadna potencjalna interakcja użytkownika nie została pominięta.
   - Upewnij się, że każda historia użytkownika jest testowalna.

Użyj następującej struktury dla każdej historii użytkownika:
- ID
- Tytuł
- Opis
- Kryteria akceptacji

4. Po ukończeniu PRD przejrzyj go pod kątem tej listy kontrolnej:
   - Czy każdą historię użytkownika można przetestować?
   - Czy kryteria akceptacji są jasne i konkretne?
   - Czy mamy wystarczająco dużo historyjek użytkownika, aby zbudować w pełni funkcjonalną aplikację?
   - Czy uwzględniliśmy wymagania dotyczące uwierzytelniania i autoryzacji (jeśli dotyczy)?

5. Formatowanie PRD:
   - Zachowaj spójne formatowanie i numerację.
   - Nie używaj pogrubionego formatowania w markdown ( ** ).
   - Wymień WSZYSTKIE historyjki użytkownika.
   - Sformatuj PRD w poprawnym markdown.

Przygotuj PRD z następującą strukturą:

```markdown
# Dokument wymagań produktu (PRD) - {{app-name}}
## 1. Przegląd produktu
## 2. Problem użytkownika
## 3. Wymagania funkcjonalne
## 4. Granice produktu
## 5. Historyjki użytkowników
## 6. Metryki sukcesu
```

Pamiętaj, aby wypełnić każdą sekcję szczegółowymi, istotnymi informacjami w oparciu o opis projektu i nasze pytania wyjaśniające. Upewnij się, że PRD jest wyczerpujący, jasny i zawiera wszystkie istotne informacje potrzebne do dalszej pracy nad produktem.

Ostateczny wynik powinien składać się wyłącznie z PRD zgodnego ze wskazanym formatem w markdown, który zapiszesz w pliku .ai/prd.md
