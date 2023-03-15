Use Case 1:  Zakup produktu
=====================

**Aktor podstawowy:** Klient


Główni odbiorcy i oczekiwania względem systemu:
-----------------------------------------------

 - Klient: otrzymuje wybrane, nieuszkodzone towary po uiszczeniu odpowiedniej opłaty.

 - System Autoryzacji Płatości: jest gotowa do otrzymywania zapytań o możliwość dokonania transakcji i realizuje je poprawnie.

 - Pracownik obsługi: jest gotowy do ewentualnego przygotowania oraz podania ciepłych produktów.

Warunki wstępne:
----------------

 Automat jest gotowy do pracy.

Warunki końcowe:
----------------

Klient otrzymał zakupione produkty.

Scenariusz główny (ścieżka podstawowa):
---------------------------------------

 1. Klient przychodzi do automatu celem zakupu produktu.
 2. Klient używa interfejsu automatu do wybrania produktu.
 3. System wyświetla cenę produktu.
 4. Klient wybiera płatność gotówką.
 5. Klient wprowadza gotówkę do automatu.
 6. System podlicza wprowadzoną gotówkę.
 7. System oblicza kwotę do zwrotu.
 8. System zwraca odpowiednią kwotę
 9. System uaktualnia swój stan wiedzy o ilości produktów.
 10. System przygotowuje i wydaje produkt.
 11. Klient odbiera produkt.

Rozszerzenia (ścieżki alternatywne):
------------------------------------

 1-4a. System wykrywa usterkę przed uiszczeniem opłaty: Naprawienie usterki (UC 4).

 5-11a. System wykrywa usterkę po uiszczeniu opłaty.
 
	1. System oddaje uprzednio wprowadzoną gotówkę.
	2. Naprawienie usterki (UC 4).

 2a. Klient wybiera produkt, który jest niedostępny.
 
	1. System powiadamia klienta o braku produktu.
	2. System powraca do punktu 2. scenariusza głównego.

 4b. System realizuje płatność kartą.
 
	1. Klient wprowadza kartę do czytnika.
	2. System wysyła zapytanie do zewnętrznego Systemu Autoryzacji Płatości i potwierdza możliwość wykonania transakcji.
	3. System prosi Klienta o potwierdzenie realizacji transakcji poprzez wpisanie pinu.
	4. System Autoryzacji Płatości pobiera należną kwotę z wprowadzonej karty.
	
		2a. Zewnętrzny System Autoryzacji Płatości nie potwierdza możliwości wykonania transakcji z powodu braku środków na koncie.
		
			1. System informuje Klienta o braku wystarczających środków na koncie.
			2. System powraca do punktu 4. scenariusza głównego.
			
		2b. Zewnętrzny System Autoryzacji Płatości nie potwierdza możliwości wykonania transakcji z innego powodu.
		
			1. System resetuje swoje połączenie z zewnętrznym Systemem Autoryzacji Płatości.
			2. System ponownie wysyła zapytanie do zewnętrznego Systemu Autoryzacji Płatości.
			3. System otrzymuje potwierdzenie możliwości wykonania transakcji.
			4. System idzie do punktu 4b3. scenaiusza alternatywnego.
			
				3a. System otrzymuje potwierdzenie możliwości wykonania transakcji.
				
					1. System powraca do punktu 4. scenariusza głównego.
			
		3a. Klient wprowadza zły pin.
		
			1. System informuje Klienta o złym kodzie pin.
			2. System ponownie prosi Klienta o potwierdzenie realizacji transakcji poprzez wpsanie pinu.
				
				2a. Klient ponownie wprowadza zły pin.
				
					1. System informuje Klienta o złym kodzie pin.
					2. System powraca do punktu 4. scenaiusza głównego.
	
 6a. Wprowadzona przez klienta ilość pieniędzy nie jest wystarczająca.
		
	1. System powiadamia klienta o zbyt małej ilości środków.
	2. System zwraca Klientowi wprowadzoną gotówkę.
	3. System powraca do punktu 4. scenariusza głównego.
					
 10a. Klient wybrał ciepły produkt wymagający pomocy obsługi.
 
	1. System wysyła informację o potrzebie przygotowania danych produktów.
	2. Pracownik obsługi przygotowuje dane produkty.
	3. Pracownik obsługi przynosi gotowe produkty na taśmę autmatu.
	4. Klient odbiera gotowe produkty.

Wymagania specjalne:
--------------------

 - Interfejs użytkownika wyświetla komunikaty w języku polskim i angielskim.

 - Automat posiada klawiaturę numeryczną, terminal do płatności kartą oraz urządzenie do rozpoznawania banknotów i monet.

Wymagania technologiczne oraz ograniczenia na wprowadzane dane:
---------------------------------------------------------------

 4. Automat posiada urządzenie do rozpoznawania banknotów i monet.
 
 4b. Automat posiada terminal do płatności kartą.
 
 4b3. Kod pin składa się z 4 cyfr.

Kwestie otwarte:
----------------

 - Jaki powinien być czas oczekiwania na produkty przygotowywane przez obsługę?
 
 - Co jaki okres czasu automat powinien sprawdzać czy nie doszło do usterki?
