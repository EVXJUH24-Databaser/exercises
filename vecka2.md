## Del 1: Grundläggande relationer

### 1. Skapa två relaterade tabeller

Skapa följande tabeller:

```sql
CREATE TABLE authors (
    author_id INT PRIMARY KEY,
    name TEXT,
    birth_year INT
);

CREATE TABLE books (
    book_id INT PRIMARY KEY,
    title TEXT,
    author_id INT,
    published_year INT,
    FOREIGN KEY (author_id) REFERENCES authors(author_id)
);
```

Övningar:

- Vilka relationer finns mellan tabellerna?
- Lägg till 3 författare
- Lägg till 6 böcker som kopplas till author_id
- Skriv en query för att visa alla böcker
- Skriv en query för att visa alla författare
- Försök lägga till en bok med en author_id som inte finns
- Välj ut en befintlig författare och skriv en query som visar upp alla böcker skrivna av författaren (använd JOINS om du vill ha en utmaning)

### 2. Skapa tabeller för en skola

Skapa följande tabeller:

```sql
CREATE TABLE classes (
    class_id INT PRIMARY KEY,
    name TEXT,
    room_number TEXT
);

CREATE TABLE students (
    student_id INT PRIMARY KEY,
    name TEXT,
    class_id INT,
    FOREIGN KEY (class_id) REFERENCES classes(class_id)
);
```

Övningar:

- Vilka relationer finns mellan tabellerna?
- Lägg till 3 klasser
- Lägg till 15 studenter fördelade i klasserna (koppla med class_id)
- Försök att ta bort en klass som har studenter (detta ska ge fel)
- Ta bort en klass som inte har studenter
- Välj ut en klass och skriv en query för att visa upp alla studenter i klassen

### 3. Designa ett spelbibliotek (likt Steam)

Skapa följande tabeller:

```sql
CREATE TABLE genres (
    genre_id INT PRIMARY KEY,
    name TEXT
);

CREATE TABLE games (
    game_id INT PRIMARY KEY,
    title TEXT,
    genre_id INT,
    release_date DATE,
    FOREIGN KEY (genre_id) REFERENCES genres(genre_id)
);
```

Övningar:

- Vilka relationer finns mellan tabellerna?
- Lägg till 5 genres
- Lägg till 10 spel
- Byt genre för två spel
- Försök att ta bort en genre med ett eller flera spel som använder den

## Del 2: Avancerade relationer

### 4. Idrottslag och spelare

En spelare kan vara med i flera lag (t.ex. A-lag och B-lag) och ett lag har flera spelare. Skapa följande tabeller:

```sql
CREATE TABLE teams (
    team_id INT PRIMARY KEY,
    team_name TEXT,
    division TEXT
);

CREATE TABLE players (
    player_id INT PRIMARY KEY,
    name TEXT,
    birth_year INT
);

CREATE TABLE team_players (
    team_id INT,
    player_id INT,
    jersey_number INT,
    join_date DATE,
    PRIMARY KEY (team_id, player_id),
    FOREIGN KEY (team_id) REFERENCES teams(team_id),
    FOREIGN KEY (player_id) REFERENCES players(player_id)
);
```

Övningar:

- Vilka relationer finns mellan tabellerna?
- Varför behövs mellantabellen (team_players)?
- Lägg till 5 lag
- Lägg till 20 spelare (utan lag än)
- Koppla alla spelare till ett lag var
- Välj ut 5 spelare och lägg till dem i ytterligare ett lag

### 5. Elever och hobbies

En elev kan ha flera hobbies och samma hobby kan utövas av flera elever. Skapa följande tabeller:

```sql
CREATE TABLE students (
    student_id INT PRIMARY KEY,
    name TEXT,
    grade INT
);

CREATE TABLE hobbies (
    hobby_id INT PRIMARY KEY,
    name TEXT,
    category TEXT
);

CREATE TABLE student_hobbies (
    student_id INT,
    hobby_id INT,
    years_experience INT,
    skill_level TEXT,  -- 'nybörjare', 'medel', 'avancerad'
    PRIMARY KEY (student_id, hobby_id),
    FOREIGN KEY (student_id) REFERENCES students(student_id),
    FOREIGN KEY (hobby_id) REFERENCES hobbies(hobby_id)
);
```

Övningar:

- Vilka relationer finns mellan tabellerna?
- Varför behövs mellantabellen (student_hobbies)?
- Lägg till 10 elever (utan hobbies än)
- Lägg till 3 hobbies
- Ge varje elev minst 2 hobbies
- Välj ut två elever som endast får en hobby: radera alla deras hobbies förutom en

## Del 3: Egen design av grundläggande relationer

### 6. Bokningssystem för frisör

Design en databas (tabeller) för en frisörsalong där:

- Personer kan registrera sig som kunder (kontosystem)
- Kunder kan boka tider
  - De kan välja behandling (klippning, färgning, välj fritt)
  - De kan välja frisör (namn text, eller separat tabell för större utmaning)

Uppgift:

- Identifiera nödvändiga tabeller
- Skapa tabellerna med korrekta relationer
- Definiera lämpliga datatyper för alla kolumner
- Testa databasen med exempeldata

### 7. Träningsapp

Design en databas (tabeller) för en träningsapp där användare kan:

- Logga mätvärden över tid (vikt, löptid, välj fritt)
- Spara personliga rekord
- Sätta och följa upp träningsmål

Uppgift:

- Identifiera nödvändiga tabeller
- Skapa tabellerna med korrekta relationer
- Definiera lämpliga datatyper för alla kolumner
- Testa databasen med exempeldata

## Del 4: Egen design av avancerade relationer

### 8. Butiker och produkter

Skapa egna tabeller för butiker och produkter. En butik har många produkter och samma produkt kan finnas i flera butiker.

Hints:

```sql
CREATE TABLE stores (?);
CREATE TABLE products (?);
CREATE TABLE store_products (?);
```

Hur ska tabellerna se ut?

Extra övningar:

- Vilken relation bildas mellan tabellerna?
- Om man låtsas att en produkt kan finnas i endast en butik, vilken relation blir det istället då? Vilka tabeller hade behövts?

### 9. Recept och ingredienser

Design en databas (tabeller) för en receptapp där användare kan:

- Spara och dela recept
- Kategorisera recept (frukost, lunch, middag, dessert etc.)
- Lägga till ingredienser med mängder
- Betygsätta och kommentera recept
- Skapa inköpslistor baserade på recept

Uppgift:

- Skapa alla nödvändiga tabeller med relevanta kolumner
- Definiera alla relationer mellan tabellerna
- Lägg in testdata i tabellerna

## Del 5: Grundläggande joins

### 10. Klasser

Skapa tabellerna:

- `teachers` (teacher_id, name, subject)
- `classes` (class_id, name, teacher_id)

Lägg till 4 lärare och ge varje lärare 1-2 klasser.
Lista alla klasser med lärarens namn (klass + lärare).

### 11. Böcker

Skapa en tabell `authors` med kolumnerna:

- `id` (primary key)
- `name` (text)
- `birth_year` (nummer)

Skapa också en tabell `books` med kolumnerna:

- `id` (primary key)
- `title` (text)
- `author_id` (foreign key som refererar till `authors`)
- `publication_year` (nummer)
- `price` (nummer)

Lägg sedan till minst 5 författare och 10 böcker med korrekt relation mellan dem.
Skriv sedan en query som visar alla böcker med tillhörande författarnamn.

### 12. E-handel

Skapa två tabeller med en enkel relation:

- `customers` (customer_id, name, email)
- `orders` (order_id, customer_id, order_date, total_amount)

Lägg till 5 kunder och 10 ordrar.
Skriv en query som visar alla ordrar med kundernas namn (order + kund).

### 13. Artiklar

Skapa två tabeller:

- `categories` (category_id, name)
- `articles` (article_id, title, category_id, published_date)

Lägg till 3 kategorier och 6 artiklar.
Visa alla artiklar med sina kategorier.

### 14. Butik

Skapa tabellerna:

- `departments` (department_id, name)
- `products` (product_id, name, price, department_id)

Lägg till 3 avdelningar och 9 produkter.
Visa alla produkter grupperade efter avdelning.

### 15. Länder och städer

Skapa tabellerna:

- `countries` (country_id, name, population)
- `cities` (city_id, name, country_id, population)

Lägg till 4 länder och 12 städer.
Lista alla städer med tillhörande land.

## Del 6: Komplexa relationer

### 16. E-handel

Skapa ett system för en e-handelsbutik med följande tabeller:

- `customers` (id, name, email)
- `orders` (id, customer_id, order_date, status)
- `products` (id, name, price, stock)
- `order_items` (order_id, product_id, quantity, price_at_time)

Skriv sedan queries för att visa:

- Alla ordrar med kundnamn och totalsumma
- Produkter som aldrig har beställts
- Kunder som har handlat för mer än 1000 kr totalt

### 17. Anställda

Implementera en self-referencing relation:
Skapa en tabell `employees` med:

- `employee_id` (primärnyckel)
- `name` (text)
- `manager_id` (främmande nyckel som refererar tillbaka till employees)

Skriv en query som visar varje anställd med sin chefs namn.

### 18. Blogg

Skapa ett bloggsystem med:

- `users` (id, username, email)
- `posts` (id, user_id, title, content, created_at)
- `comments` (id, post_id, user_id, content, created_at)
- `post_tags` (post_id, tag_id)
- `tags` (id, name)

Skriv queries för att visa:

- Alla posts med antal kommentarer (post + count)
- Alla användare och antal posts de har skrivit
- Posts med sina tags
- De 3 mest använda taggarna
