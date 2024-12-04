## Del 1: Databastyper

1. Förklara skillnaden mellan följande databastyper:
   - Relationsdatabaser
   - NoSQL-databaser
   - In-memory databaser

2. Lista en fördel och en nackdel med relationsdatabaser jämfört med NoSQL-databaser.

3. Vilken databastyp och mest lämplig och anpassad för följande scenarios (motivera):
   - En e-handelsbutik med produkter, ordrar och kunder (e.g. Amazon, Elgiganten)
   - En realtids-chattapplikation (e.g. Discord, Teams)
   - Ett system för lagring av sensormätningar från IoT-enheter (e.g. temperatur)

4. Para ihop följande databaser med deras databastyper (var gärna specifik):
   - MongoDB
   - PostgreSQL
   - Redis

5. Ge flera exempel på specifika databaser av följande typer:
   - Relationsdatabaser (SQL)
   - Document-databaser
   - NoSQL-databaser
   - In-memory databaser

6. Ge minst två anledningar till varför PostgreSQL är bättre än MySQL.

## Del 2: Begrepp och koncept

7. Vad kan SQL rader jämföras med i C#?
8. Vad kan SQL kolumner jämföras med i C#?
9. Vad kan SQL constraints jämföras med i C#?
10. Vad kan SQL tabeller jämföras med i C#?
11. Förklara vad en modell är.
12. Vad är det för skillnad på en query och en rad (row)?
13. Vilket nyckelord används i SQL för att hämta data med en query?
14. Förklara vad följande termer betyder och ge ett exempel på varje:

- DML (Data Manipulation Language)
- DDL (Data Definition Language)
- DCL (Data Control Language)

15. Para ihop följande termer med rätt beskrivning:

Termer:

- ACID
- Schema
- Primary Key
- Foreign Key
- Index
- Query
- Transaction

Beskrivningar:

- En strukturerad fråga för att hämta eller modifiera data
- En serie databas-operationer som behandlas som en enhet
- En referens till en primary key i en annan tabell
- En datastruktur som förbättrar sökhastigheten
- Egenskaper som garanterar databas-integritet
- Den logiska strukturen för hur data organiseras
- Ett unikt identifierande värde för varje rad i en tabell

16. För följande data, identifiera lämpliga PostgreSQL datatyper och förklara ditt val:

- Personnummer
- E-postadress
- Telefonnummer
- Födelsedatum
- Prisinformation
- Status (aktiv/inaktiv)

17. Vad är en SQL relation?

## Del 3: Docker och PostgreSQL

18. Vad används Docker till?

19. Hur laddar man ned PostgreSQL med Docker?
20. Hur skapar man en PostgreSQL databas med Docker?
21. Vad är images?
22. Vad är containers?

23. Vad är Docker kommandot för att starta upp en container som tidigare har stoppats?

24. Lista stegen att ta för att komma åt en PostgreSQL databas som ligger i en container (exempelvis för att skapa en tabell. hints: exec, psql.)

25. Lista stegen för att:

- Kontrollera om en Docker-container körs
- Stoppa en körande container
- Ta bort en container

## Del 4: Skapa och modifiera tabeller

26. Skapa en tabell `persons` som har två kolumner: `name` (text) och `age` (nummer)
27. Skapa en tabell `products` som har tre kolumner: `name` (text), `description` (text), `price` (nummer)
28. Lägg in tre rader i `persons` tabellen med följande värden:

- Ironman, 47
- Superman, 33
- Batman, 26

29. Lägg in tre rader i `products` tabellen:

- Bread, "Fresh whole grain bread", 25.50
- Milk, "Organic whole milk", 12.99
- Coffee, "Dark roast coffee beans", 89.00

30. Lägg till en ny kolumn `category` (text) i `products` tabellen och uppdatera befintliga produkter med valfria kategorier

## Del 5: Grundläggande queries

31. Skapa en tabell `movies` med kolumnerna: `title` (text), `year` (nummer), `rating` (nummer från 1-5). Lägg in minst 30 filmer med olika årtal och betyg. Tips: använd AI för att generera dessa.
32. Skriv queries för att visa:

- Alla filmer
- Alla filmer, men endast med `title`
- Alla filmer, men endast med `title` och `rating`
- Alla filmer med rating högre än 3
- Alla filmer, men endast `title`, för 2020, med rating högre än 3
- Antal filmer per årtal
- Alla filmer sorterade efter år (äldst först)

33. Skapa en tabell `books` med kolumnerna: `title` (text), `author` (text), `pages` (nummer), `published` (datum). Lägg in minst 3 böcker.
34. Skriv en query som visar böcker publicerade efter år 2000 och som har fler än 300 sidor.
35. Skapa en tabell `employees` med: `name`, `department`, `salary`. Lägg in 6 anställda i olika avdelningar med olika löner. Skriv sedan en query som visar genomsnittlig lön per avdelning.

## Del 6: Svårare queries

36. Skapa en tabell `orders` med kolumnerna:
    - `id` (serienummer som auto-ökar)
    - `customer_name` (text)
    - `order_date` (datum)
    - `total_amount` (nummer)
      Lägg in 5 olika orders och skriv sedan en query som visar alla orders från den senaste månaden (datumet för query:n skall inte hårdkodas.)

37. Modifiera `employees` tabellen genom att lägga till kolumnen `hire_date`. Uppdatera alla befintliga anställda med olika anställningsdatum. Skriv en query som visar alla som varit anställda längre än 2 år (datumet för query:n skall inte hårdkodas.)

38. Skapa en tabell `tasks` med:
    - `title` (text)
    - `status` (text: 'pending', 'in_progress', eller 'completed')
    - `created_at` (datum)
    - `completed_at` (datum, kan vara null)
      Lägg in 7 olika tasks och skriv en query som visar hur många tasks som finns i varje status.

39. Skapa en tabell `students` med:
    - `name` (text)
    - `grade` (nummer mellan 1-100)
    - `course` (text)
      Lägg in 10 studenter i olika kurser med olika betyg. Skriv en query som visar genomsnittsbetyget per kurs, men bara för kurser med minst 2 studenter.

## Del 7: Avancerade koncept

40. Skapa en tabell `articles` med:
    - `title` (text)
    - `content` (text)
    - `views` (nummer)
    - `published` (datum)
      Lägg in 8 artiklar och skriv en query som visar de 3 mest visade publicerade artiklarna.

41. Uppdatera `products` tabellen (från övning 2) genom att lägga till en kolumn `stock_quantity`. Skriv en query som visar alla produkter med mindre än 5 i lager och ett pris över 100.

42. Skapa en tabell `weather_data` med:
    - `date` (datum)
    - `temperature` (nummer)
    - `rainfall` (nummer)
      Lägg in väderdata för de senaste 10 dagarna. Skriv en query som visar genomsnittstemperaturen för dagar med regn (rainfall > 0).

43. Skapa en tabell `user_logins` med:
    - `user_id` (nummer)
    - `login_time` (datum)
    - `success` (boolean)
      Lägg in 15 loginförsök och skriv en query som visar användare med fler än 2 misslyckade inloggningar.

44. Skapa en tabell `transactions` med:
    - `account_id` (nummer)
    - `type` (text: 'deposit' eller 'withdrawal')
    - `amount` (nummer)
    - `transaction_date` (datum)
      Lägg in minst 10 transaktioner och skriv en query som visar det totala saldot per konto (summan av insättningar minus summan av uttag).

## Bonusövningar för extra utmaning

45. Skapa tabellerna `categories` och `products_v2`:

```sql
CREATE TABLE categories (
    id SERIAL PRIMARY KEY,
    name TEXT,
    description TEXT
);

CREATE TABLE products_v2 (
    id SERIAL PRIMARY KEY,
    name TEXT,
    price NUMERIC(10,2),
    category_id INTEGER REFERENCES categories(id)
);
```

Lägg in data i båda tabellerna och skriv en query som visar alla produkter med sina kategorier, även kategorier som inte har några produkter.

46. Uppdatera `weather_data` (från övning 17) tabellen för att inkludera `location` (text). Skriv en query som visar den varmaste och kallaste temperaturen per plats, men bara för platser med minst 3 mätningar.

47. Modifiera `user_logins` (från övning 18) tabellen för att inkludera `device_type` (text). Skriv en query som visar procentandelen lyckade inloggningar per enhetstyp.
