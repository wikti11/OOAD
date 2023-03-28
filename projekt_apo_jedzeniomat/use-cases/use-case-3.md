Use Case 3: Zebranie informacji dotyczących sprzedaży
=====================

**Aktor podstawowy:** Analityk


Główni odbiorcy i oczekiwania względem systemu:
-----------------------------------------------

 - **Analityk:** oczekuje możliwości zebrania informacji dotyczących sprzedaży w danym okresie czasowym.
 - **Przedsiębiorstwo:** chce otrzymać informacje dotyczące realizowanych sprzedaży.

Warunki wstępne:
----------------

Automat jest włączony w zwykłym trybie użytkowania. Analityk wie, w jaki sposób otrzymać dostęp do ukrytych funkcji zawartych w trybie autoryzowanym.

Warunki końcowe:
----------------

Bezpieczny odbiór kopii danych dotyczących sprzedaży wykonany przez analityka. Automat jest pozostawiony w zwykłym trybie użytkowania.

Scenariusz główny (ścieżka podstawowa):
---------------------------------------

 1. Analityk przychodzi do automatu w celu skopiowania danych dotyczących sprzedaży w ostatnim miesiącu.
 2. Analityk wybiera tryb autoryzowany spośród opcji.
 3. System prosi o autoryzację.
 4. Analityk wprowadza hasło autoryzacji.
 5. System wyświetla dostępne opcje.
 6. Analityk wybiera opcję kopii danych sprzedaży z ostatniego miesiąca.
 7. System udostępnia dane z ostatniego miesiąca.
 8. System kopiuje dane na urządzenie analityka.
 9. Analityk potwierdza skopiowanie danych.
 10. System resetuje znacznik czasowy odbioru skopiowanych danych.
 11. Analityk wychodzi z trybu autoryzowanego.
 12. Analityk odchodzi ze skopiowanymi danymi sprzedaży z ostatniego miesiąca.

Rozszerzenia (ścieżki alternatywne):
------------------------------------

 *a. W dowolnym czasie, dotyczy sytuacji kiedy system zawiesza się:
    Aby zapewnić bezpieczną obsługę trybu autoryzowanego, niezbędne jest to, aby system powrócił do stanu obsługi zwykłego klienta.
   1. Analityk restartuje system.
   2. System uruchamia się w trybie obsługi zwykłego użytkowana.
   3. Logi dotyczące usterki są zapisywane i przesyłane do producenta.

  4a. Analityk wprowadza błędne hasło autoryzacji.

    1. System informuje analityka o wprowadzeniu błędnego hasła autoryzacji.
    2. System ponownie prosi o autoryzację.
    3. Przejście do punktu 4. scenariusza głównego.

  4b. Analityk wprowadza błędne hasło autoryzacji 3 razy pod rząd.

    1. System informuje o zbyt dużej ilości wprowadzenia błędnego hasła.
    2. System wychodzi z trybu autoryzowanego, powracając do trybu zwykłego użytkowania.

  8a. Występuje błąd podczas kopiowania danych.

    1. System informuje analityka o zaistniałym błędzie podając jego kod.
    2. Analityk potwierdza otrzymanie błędu.
    3. Przejście do punktu 5. scenariusza głównego.

  9a. Analityk nie potwierdził skopiowania danych.

    1. System zapisuje informację o braku potwierdzenia odbioru.
    2. System nie resetuje znacznika czasowego odbioru danych.
    3. Przejście do punktu 5. scenariusza głównego.

  11a. Analityk nie wyszedł z trybu autoryzowanego po skopiowaniu danych.

    1. Po 20 sekundach bezczynności system wychodzi z trybu autoryzowanego.

Wymagania specjalne:
--------------------

 - Ekran dotykowy służący do obsługi automatu.
 - Autoryzacja musi być dokonana w czasie 30 sekund.
 - Bezprzewodowy system przesyłania plików.
 - Bezczynność w trybie autoryzowanym nie powinna być dłuższa niż 20 sekund.

Wymagania technologiczne oraz ograniczenia na wprowadzane dane:
---------------------------------------------------------------

8. Dane sprzedaży z ostatniego miesiąca kopiowane są na urządzenie, które przynosi ze sobą analityk.
 
Kwestie otwarte:
----------------

- Jakie są możliwe bezprzewodowe sposoby kopiowania plików?
- Czy tylko analityk powinien posiadać dostęp do danych sprzedaży z ostatniego miesiąca?