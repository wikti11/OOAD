Opis skrócony przypadków użycia
===============================

Aktorzy procesu i ich cele
--------------------------

Aktor                                        | Cel
                                            -|-
Klient                                       | Zakup produktu
Pracownik obsługi                            | Przygotowanie automatu do pracy
Analityk                                     | Zebranie informacji dotyczących sprzedaży

Słownik
-------

Hasło                  | Opis
                      -|-

Przypadki użycia
----------------

### Use case 1: Zakup produktu
Klient przychodzi do automatu i używa interfejsu do wybrania produktu. System wyświetla cenę produktu. Klient wprowadza informacje o sposobie realizacji płatności, które są weryfikowane i zapisywane przez system. System realizuje płatność. System uaktualnia swój stan wiedzy o ilości produktów. System przygotowuje i wydaje produkt. Klient odbiera produkt.

### Use case 2: Przygotowanie automatu do pracy
Pracownik obsługi przychodzi do automatu i uzyskuje dostępu do jego wnętrza. Pracownik obsługi uzupełnia braki towaru i zabiera gotówkę. Pracownik obsługi potwierdza wykonanie czynności. System uaktualnia swój stan wiedzy o ilości produktów. System blokuje dostęp do wnętrza automatu.

### Use case 3: Zebranie informacji dotyczących sprzedaży
Analityk przychodzi do automatu i uzyskuje dostęp do ukrytych funkcji. System udostępnia dane dotyczące sprzedaży w ostatnim okresie. Analityk otrzymuje kopię danych. Analityk potwierdza zakończenie czynności. System blokuje dostęp do ukrytych funkcji.

### Use case 4: Naprawienie usterki
System wykrywania usterek i wzywania serwisu wykrywa usterkę w działaniu automatu. System zbiera potrzebne informacje o usterce i automacie. System kontaktuje zewnętrzny system obsługi usterek i podaje mu potrzebne informacje. 
