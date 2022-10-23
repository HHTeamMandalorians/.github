# 🗽️ LibreVote

Nasz projekt na edycję 2022 programu [*Hack Heroes*][hh]!

## Czym jest ten projekt?

Projekt jest obecnie **prototypem** demokratycznego systemu głosowania do przeznaczenia ogólnego, składający się z [serwera][serwer] (Node.js) i
[klienta][klient] (statyczna strona + zależności z NPM). Zgodnie z konceptem, system ten miałby być oparty na fizyczne karty USB (bądź inną formę poufnego
i w pełni anonimowego przekazywania danych klucza), której identyfikator nie może być odczytany, jeżeli nie w ogóle, to przed głosowaniem. Karta ta miałaby
być wylosowana, a użytkownik oddzielnie zapisany (aby nie mógł on wielokrotnie wziąć udziału), bez jakiejkolwiek informacji jaki identyfikator został
mu przydzielony (ma to być po prostu uniemożliwione fizycznie). Miałoby to umożliwić anonimowość użytkownika, przynajmniej w pewnym zakresie
(mogłaby być ona np. wzmocniona przez oprogramowanie tunelujące połączenie typu TOR).

## Jakie idee są powiązane z tym projektem?

- Ułatwienie dostępu do głosowań dla osób stale zmieniających miejsce pobytu (w tym głównie osób przebywających za granicą).
- Cyfryzacja głosowań i wykluczenie sprawdzania kart przez ludzi na rzecz komputerów, co miałoby przyspieszyć głosowania i zapewnić wstępne informacje
  tuż po czasie ukończenia głosowania.
- Zapewnienie możliwości organizowania anonimowych głosowań dla ograniczonej grupy osób bez zbierania jakichkolwiek danych.
- Umożliwienie darmowego i otwartoźródłowego systemu dla każdej organizacji zainteresowanej, również spoza Polski.
- Dostosowania systemu do norm prawnych względem danego państwa, zarówno obecnych jak i przyszłych.
- Wspólny rozwój oprogramowania dzięki społeczności otwartoźródłowej.
- Bezpieczeństwo: ograniczenie liczby zależności serwera, własnoręczna implementacja większości podstawowych funkcji, unikanie bibliotek na rzecz
  natywnych implementacji w Node.js.

## Obecna implementacja:

### 1. Serwer

Serwer został już w większości ukończony – przy instalacji, samodzielnie konfiguruje się dla celów testowych. W przypadku API w założeniach publikujących
dane na serwer (metoda `POST`). Dla pełnej implementacji należałoby dokończyć zarządzanie kluczami uwieżytelniającymi (odczytywanie i usuwanie z
systemu po udanym głosowaniu) i implementację HTTPS.

Dokładny opis implementacji serwera znajduje się w pliku `Readme.md` w [odpowiednim repozytorium][serwer].

### 2. Klient

W przypadku klienta webowego, implementacja wciąż wymaga sporo dopracowań – nie jestem przekonany, czy tak ostatecznie powinien wyglądać *front-end*.
Wymagana jest też implementacja samego głosowania (obecnie front-end za dużo nie robi). Wiele braków pokrywa się również z brakami w implementacji na
serwerze.

Korzystanie z *front-endu* powinno być jednak naturalne – instalacja wymaga dostosowania pliku konfiguracyjnego do serwera, instalacji zależności i
hostingu przy pomocy dowolnego serwera HTTP. W przyszłości [serwer] miałby być dostosowany do opcjonalnego hostingu klienta.

[hh]: https://www.hackheroes.pl/
[serwer]: https://github.com/HHTeamMandalorians/client
[klient]: https://github.com/HHTeamMandalorians/server
