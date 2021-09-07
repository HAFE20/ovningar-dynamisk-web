## Firestore
[Tillbaka till start](README.md)

1a Logga in på Firebase och skapa ett nytt projekt. Välj "Web" som miljö.

1b Gå till Firebase console → Build → Firestore. Skapa en collection med minst ett doc. Till exempel kan du göra en collection med bok-document: `{ title, author, genre }`.

1c Skapa en privat nyckel för ditt firebase-konto och ladda ner den som json-fil.

1d Skapa ett projekt med npm init och git init. Lägg till en JavaScript-fil. Men json-filen ska inte finnas med i repot - lägg till filnamnet i .gitignore-filen.

1e Du ska ha minst ett document i databasen. När man kör JavaScript-filen ska den ansluta till databasen, hämta dokumentet och skriva ut innehållet med console.log.

1f Refaktorera: lägg koden för att hämta datan i en egen funktion. Namnförslag: getBookFromDb.

2 Lägg till funktioner för att a) lägga till, b) uppdatera, c) ta bort document. Testkör funktionerna och kontrollera innehållet i databasen direkt i *firebase console*, så du vet att det fungerar.

3 Skapa en Express-server i projektet. Gör ett REST API som kan användas för CRUD operationer på databasen.

4a Lägg till en collection `users` till databasen. En användare ska ha `name`, `id`, `password` och `permission`. Permission kan vara "user" eller "admin".

4b Vi ska snart lägga till en ny endpoint för `users`. Börja med två extra routes: `/users/login` och `/users/logout`.

4c Lägg till GET/POST/PUT/DELETE så att resursen `users` blir ett REST API. Nu när vi har två olika behörigheter måste det hanteras i funktionerna med if-satser. Skilladerna mot `/books` är att:

+ admin kan göra allt
+ är man inte inloggad får man inte använda någon metod
+ vanlig användare får inte använda POST och DELETE
+ vanlig användare kan hämta namn på andra användare - `GET /users`
+ vanlig användare kan ändra sina uppgifter - `PUT /users/:id`

5 Gör så att Express-servern servar en enkel statisk frontend. Frontenden ska använda vanilla JavaScript för att skicka request till webbservern och visa resultatet på webbsidan.
