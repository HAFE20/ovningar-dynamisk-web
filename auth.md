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
