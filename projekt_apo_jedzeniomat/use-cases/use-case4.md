Use Case 4: Wezwanie ekipy serwisowej po wykryciu usterki
=========================================================

**Aktor podstawowy:** Czas

Główni odbiorcy i oczekiwania względem systemu:
-----------------------------------------------

 Usługa oferująca ekipy serwisowe: Przestrzeganie protokołu komunikacji
 Właściciel automatu: Automat pedejmie najlepszą decyzję w zależności od sytuacji

Warunki wstępne:
----------------

 Wykrto usterkę w automacie

Warunki końcowe:
----------------

 Ekipa serwisowa została pomyślnie wezwana

Scenariusz główny (ścieżka podstawowa):
---------------------------------------

 1. Automat analizuje rodzaj usterki
 2. Automat przechodzi w tryb awaryjny
 3. Automat kontaktuje się z usługą oferującą ekipy serwisowe.
 4. Automat przekazuje usłudze potrzebne informacje o usterce
 5. Usługa akceptuje prośbę o wysłanie ekipy serwisowej
 6. Usługa przekazuje informacje o prognozowanym czasie przybycia
 7. Automat wyświetla informację o czasie przybycia ekipy
 8. Automat pozostaje w trybie awaryjnym i czeka na ekipę awaryjną

Rozszerzenia (ścieżki alternatywne):
------------------------------------

2a. Usterka zagraża życiu potencjalnym klientom
1. Automat wyłącza się zamiast przechodzić w tryb awaryjny

3a. Nie można skontaktować się z usługą
1. Automat cyklicznie ponawia próbę kontaktu z usługą

4a. Występuje błąd w komunikacji z usługą
1. Automat cyklicznie ponawia próbę komunikacji z usługą

5a. Usługa odmawia prośbę o wezwanie ekipy serwisowej
1. Automat cyklicznie ponawia prośbę o wysłanie ekipy

7a. Usługa nie przekazuje informacji o czasie
1. Automat wyświetla komunikat o niekreślonym czasie przybycia ekipy

Wymagania specjalne:
--------------------

 Automat musi mieć możliwość wejścia w tryb awaryjny
 Automat musi mieć możliwość mierzenia czasu

Wymagania technologiczne oraz ograniczenia na wprowadzane dane:
---------------------------------------------------------------

 4a. Protokół komunikacji z usługą musi byc szyfrowany

Kwestie otwarte:
----------------

 Jak pokazać zewnętrznie, że automat wszedł w tryb awaryjny? ( czerwone światła? )
