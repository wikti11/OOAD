Use Case 2: Przygotowanie do pracy
=====================

**Aktor podstawowy: Pracownik obsługi**


Główni odbiorcy i oczekiwania względem systemu:
-----------------------------------------------

 - Właściciel automatu: Chce, aby cała gotówka z automatu, w kwocie zgodnej z wynikami sprzedaży (weryfikowanymi przez analityka), została odebrana i dostarczona w bezpieczne miejsce. Chce, aby automat był w pełni zaopatrzony, czysty i zabezpieczony przed kradzieżą.

 - Pracownik obsługi: Chce łatwo uzyskać dostęp do wnętrza automatu. Chce wygodnie go wyczyścić i uzupełnić asortyment. Chce włożyć do automatu wszystkie produkty, które do niego przyniósł. 

 - Zaopatrzenie automatu (magazyn): Chce wydać pracownikowi obsługi odpowiednią liczbę produktów.

Warunki wstępne:
----------------

Pracownik obsługi ma dostęp do klucza, kodu, lub breloka zbliżeniowego do drzwiczek automatu. Pracownik obsługi ma dostęp do klucza do skrytki z gotówką.

Warunki końcowe:
----------------

Automat ma zapisaną liczbę produktów na każdej pozycji. Drzwiczki automatu są bezpiecznie zamknięte.

Scenariusz główny (ścieżka podstawowa):
---------------------------------------

 1. Pracownik obsługi przychodzi do automatu z produktami do uzupełnienia i środkami czyszczącymi.
 2. Pracownik obsługi otwiera drzwiczki automatu kluczem do drzwiczek.
 3. Pracownik obsługi, w razie potrzeby, czyści wnętrze automatu.
 4. Pracownik obsługi wkłada przyniesione produkty w odpowiednie nisze w automacie.
 5. Pracownik obsługi uruchamia procedurę aktualizacji liczby produktów.
 6. Pracownik obsługi podaje liczbę produktów na każdej pozycji.
 7. System aktualizuje swój stan wiedzy o liczbie produktów na każdej pozycji.
 8. Pracownik obsługi otwiera skrytkę z gotówką kluczem do skrytki.
 9. Pracownik obsługi zabiera gotówkę ze skrytki.
 10. Pracownik obsługi zamyka skrytkę z gotówką.
 11. Pracownik obsługi zamyka drzwiczki automatu, które zatrzaskują się automatycznie.
 12. Pracownik obsługi czyści zewnętrze automatu.

Rozszerzenia (ścieżki alternatywne):
------------------------------------

 2a. Otwarcie drzwiczek automatu bez użycia klucza, za pomocą kodu

   1. Pracownik obsługi wpisuje kod na otwarcie drzwiczek automatu.
   2. System sprawdza poprawność kodu.
   3. System otwiera drzwiczki automatu.
   4. przejście do kroku 3. scenariusza głównego
   
     2a. Podanie nieprawidłowego kodu

       1. System wyświetla informację, że podano błędny kod.
       2. System blokuje opcję wpisywania kodu na 8 sekund.
       3. przejście do kroku 2. scenariusza głównego

 2b. Otwarcie drzwiczek automatu bez użycia klucza, za pomocą breloka zbliżeniowego

   1. Pracownik obsługi zbliża brelok do czytnika zbliżeniowego.
   2. System otwiera drzwiczki automatu.
   3. przejście do kroku 3. scenariusza głównego

 3-10. Przypomnienie o długim czasie otwarcia drzwiczek automatu

   1. Minęło 5 minut od otwarcia drzwiczek automatu.
   2. System wyświetla informację, że drzwiczki są otwarte.
   3. System wydaje dźwięk, który ma przypomnieć pracownikowi obsługi o zatrzaśnięciu drzwiczek.
   4. powrót do scenariusza głównego

 6a. Pominięcie podania liczby niektórych produktów

   1. Minęła 1 minuta od ostatniego podania liczby produktów na pozycji, a są jeszcze pozycje, dla ktorych nie podano liczby produktów.
   2. System aktualizuje liczbę produktów na pozycjach, dla których została ona podana, a nie zmienia liczby produktów na pozostałych pozycjach.
   3. przejście do kroku 8. scenariusza głównego

 6b. Wpisanie większej niż maksymalna liczby produktów na pozycji

   1. System wyświetla informację o błędzie, z prośbą o wpisanie prawidłowej liczby.
   4. powrót do kroku 6. scenariusza głównego

Wymagania specjalne:
--------------------

 - W trakcie procedury aktualizacji liczby produktów, zamiast wpisywać liczbę produktów na danej pozycji, można wybrać opcję "maksymalna liczba produktów".

 - Czytnik zbliżeniowy jest dyskretnie wyróżniony, aby był wygodny w użyciu przez obsługę, a nie przykuwał uwagi klientów.

 - Automat posiada wyświetlacz, mogący pokazać co najmniej 50 znaków.

 - Kod na otwarcie drzwiczek automatu powinien być długi, żeby nie został przypadkowo wpisany przez klienta.

Wymagania technologiczne oraz ograniczenia na wprowadzane dane:
---------------------------------------------------------------

 6 . Liczby są wprowadzane za pomocą (fizycznej lub ekranowej) klawiatury numerycznej.

 11 . Drzwiczki automatu są wyposażone w zamek zatrzaskowy wielopunktowy z wkładką jednostronną.

 2a . System ma możliwość sterowania zamkiem drzwiczek automatu.

 2b . Automat jest wyposażony w czytnik zbliżeniowy RFID.

 3-10 . System ma możliwość wydawania dźwięków.

Kwestie otwarte:
----------------

 - Czy skrytka z gotówką zatrzaskuje się automatycznie, czy żeby ją zamknąć trzeba użyć klucza?

 - Czy wyświetlaczem powinna być matryca punktowa, czy monitor LCD?