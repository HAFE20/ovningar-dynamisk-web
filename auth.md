## Middleware och autentisering
[Tillbaka till start](README.md)

1 Skapa en Logger - en middleware som ska skriva ut information om alla inkommande requests med console.log.

2 Bygg vidare på övningen `/books`, Express övning 8. Du ska ha ett REST-API som stöder GET, POST, PUT och DELETE. Använd express.Router middleware för att flytta ut koden i en egen fil. Du ska ha en mapp som heter "routes" och en fil som heter "books.ts". (books.js om du inte använder TypeScript)

3 Lägg till middleware för att hantera ett request body. Det används när frontend skickar ett POST-request. (Testa att skicka POST med Insomnia.) Målet är att du ska skicka JSON-data med request body från Insomnia och ta emot den i app.post-metoden i Express. Skriv ut `req.body` för att kontrollera att du har gjort rätt.

Tips 1: använd express.json och express.urlencoded <br>
Tips 2: du behöver läsa i Express dokumentation hur man använder dem. <br>
Varning! Många artiklar på nätet har föråldrad information och hänvisar till body-parser, som du alltså *inte* ska använda.

4a Lägg till en statisk mapp med express.static. Inuti mappen ska du lägga minst en HTML-fil och en länkad CSS-fil. Kontrollera i webbläsaren att webbsidan och CSS fungerar.

4b Gör så att din logger inte skriver ut request till statiska mappen, genom att byta ordning på raderna.

5 Ta reda på vad CORS är och när man behöver installera den som middleware.

---
6a Nu ska vi börja med autentisering. Installera tre middleware: express-session, passport och cookie-parser. Skapa en ny endpoint `POST /login` som tar emot en FORM body: `{ "user": "guest", "password": "guest" }`. Om användarnamn eller lösenord är felaktigt ska du visa ett felmeddelande och en relevant HTTP statuskod. Använd Insomnia för att testa dina endpoints.

6b Ändra koden så att Passport används för att hantera inloggning med en LocalStrategy. Din strategi-funktion ska kontrollera att user==guest och password==guest. Om något är fel, ska användaren omdirigeras till /login-fail med `res.redirect('/login-fail')`. (Glöm inte skapa endpointen logn-fail.)

7 Gör en endpoint `/protected` som skickar tillbaka olika meddelanden beroende på om man är inloggad eller inte, när man besöker den.

8 Gör en endpoint `/logout` som loggar ut användaren.

9 Skapa en fejk-databas med användare == en array med påhittade user-objekt. User: `{ username, password }`. Du ska ha minst två användare. Använd `array.find` i din LocalStrategy för att kontrollera om man loggar in med någon av användarna i arrayen.

10 Lägg till information i dina User-objekt: `permission`, som kan vara "admin" eller "user". Gör två routes: `/protected` som ska vara åtkomlig för inloggade användare och admins, och `/admin` som bara en admin ska komma åt. Använd res.send eller res.sendFile för att skicka tillbaka svar till klienten.

11 Se till att du har en statisk frontend-mapp med en HTML-fil. Bygg ett formulär i frontend som postar till `/login`. Ändra i koden så att det inte är ett meddelande som skickas tillbaka, utan HTML-filer: success.html och fail.html.
