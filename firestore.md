## Firestore
[Tillbaka till start](README.md)

1a Logga in på Firebase och skapa ett nytt projekt. Välj "Web" som miljö.

1b Gå till Firebase console → Build → Firestore. Skapa en collection med minst ett doc. Till exempel kan du göra en collection med bok-document: `{ title, author, genre }`.

1c Skapa en privat nyckel för ditt firebase-konto och ladda ner den som json-fil.

1d Skapa ett projekt med npm init och git init. Lägg till en JavaScript-fil. Men json-filen ska inte finnas med i repot - lägg till filnamnet i .gitignore-filen.

1e När man kör JavaScript-filen ska den ansluta till databasen och skriva ut innehållet i dokumentet med console.log.

1f Lägg koden för att hämta datan i en egen funktion.

2 Lägg till funktioner för att lägga till uppdatera respektive ta bort document. Testkör funktionerna och kontrollera databasen direkt i firebase console, så du vet att det fungerar.

3 Skapa en Express-server i projektet. Gör ett REST API som kan användas för CRUD operationer på databasen.

4 Gör så att Express-servern servar en enkel statisk frontend. Frontenden ska använda vanilla JavaScript för att skicka request till webbservern och visa resultatet på webbsidan.
