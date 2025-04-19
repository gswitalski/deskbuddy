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
