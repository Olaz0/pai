# Analiza Aplikacji do Gromadzenia Lajków na Mecze

## Wprowadzenie
Aplikacja została stworzona w celu gromadzenia "lajków" na mecze, gdzie każdy użytkownik ma określoną liczbę głosów do wykorzystania. Poniżej przedstawiono analizę poszczególnych części aplikacji.

## Docker Compose
Plik `docker-compose.yml` definiuje konfigurację Docker Compose do uruchomienia trzech głównych usług: backendu meczu, backendu użytkownika, i frontendu. Ponadto, używana jest baza danych MongoDB. Poniżej analiza poszczególnych usług:

### 1. Backend Meczu (`backend-match`):
- Zbudowany z kontekstu `./match_api`.
- Działa na porcie 8080.
- Zależność od usługi MongoDB.

### 2. Backend Użytkownika (`backend-user`):
- Zbudowany z kontekstu `./user_api`.
- Działa na porcie 8081.
- Zależność od usługi MongoDB.

### 3. Frontend (`frontend`):
- Zbudowany z kontekstu `./view`.
- Działa na porcie 80.

### 4. MongoDB (`mongo`):
- Używa oficjalnego obrazu MongoDB.
- Działa na porcie 27017.

## Backend Meczu (`backend-match`)
- Działa na Express.js.
- Korzysta z MongoDB do przechowywania danych dotyczących meczów.
- Posiada endpointy CRUD (Create, Read, Update, Delete) dla meczów.
- Posiada endpointy do oddawania głosów przez użytkowników na konkretne mecze.

## Backend Użytkownika (`backend-user`)
- Działa na Express.js.
- Korzysta z MongoDB do przechowywania danych użytkowników.
- Udostępnia endpointy do rejestracji, logowania i uzyskiwania informacji o użytkowniku.

## Frontend (`frontend`)
- Interfejs użytkownika zbudowany w HTML, CSS i JavaScript.
- Strony obejmują rejestrację, logowanie, głosowanie na mecze, wyświetlanie listy meczów i ich edycję.

## Bezpieczeństwo
- Aplikacja używa protokołu HTTP, co może stanowić zagrożenie dla bezpieczeństwa przesyłanych danych.
- Przesyłanie loginu i hasła w ciasteczkach (`document.cookie`) nie jest najlepszą praktyką bezpieczeństwa, ze względu na narażenie na ataki typu CSRF (Cross-Site Request Forgery) i XSS (Cross-Site Scripting).

## Zakończenie
Powyższa analiza przedstawia strukturę i funkcjonalności każdej części aplikacji. Warto zauważyć, że aplikacja ma na celu demonstrację współpracy między dwoma API, co stanowi główny aspekt projektu. W rzeczywistym środowisku produkcyjnym, oprócz funkcji, należy uwzględnić dodatkowe środki bezpieczeństwa.

**Uwaga:**
Autorzy kodu wiedzą, że przesyłanie loginu i hasła w ciasteczkach nie jest zalecaną praktyką bezpieczeństwa. W rzeczywistych aplikacjach, należy stosować bardziej zaawansowane metody uwierzytelniania i autoryzacji, takie jak tokeny JWT (JSON Web Tokens), aby zminimalizować ryzyko ataków.
