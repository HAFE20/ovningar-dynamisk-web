## Express
[Tillbaka till start](README.md)

_De här uppgifterna förutsätter att du installerar npm-paketet Express. Kom ihåg att skapa ett nytt projekt och ett Git-repository med .gitignore-fil._


```
npm init -y
git init
npm i express
echo "node_modules/" >> .gitignore
echo "DS_Store" >> .gitignore
git add --all
```


1 Skriv en fil med namnet _server.js_, som startar en Express webbserver på port 1337. (Fungerar inte 1337 så får du använda en annan port.) Öppna URL:en [http://localhost:1337/](http://localhost:1337/) i en webbläsare. Vad förväntar du dig ska hända?

2 Ändra i filen så att webbläsaren får texten "Hello from server" när man laddar om URL:en. Tips 1:  Lägg till en route som hanterar ett GET request till "web root", dvs. "`/`". Tips 2: använd res.send.

3a Lägg till en route `/guestbook` som skickar texten "Du är besökare nummer _1_". Antalet besökare ska räknas upp varje gång man laddar om sidan. Tips: använd en variabel på webbservern.

3b Nu är det dags att börja organisera koden. Börja med att skapa en fristående funktion för callback-funktionen som körs för route `/guestbook`. (När du läst om Router modules kan du använda det.)

3c Vi ska lägga all kod som har att göra med "gästboken" i en egen modul. Skapa en mapp med namnet _routes_. Lägg sedan funktionen i en egen fil med namnet _guestbook.js_ och importera den i _server.js_.

4a Skapa en mapp med namnet _public_. Gör en index.html, en CSS-fil och en JS-fil. Lägg till en route för varje fil. Exempel: `http://localhost:1337/index.html` ska skicka filen `index.html` till klienten. Gör en &lt;button> som man kan klicka på för att skriva ut ett meddelande på webbsidan. (alltså inte console.log) Testa i din webbläsare.

4b Det blir för besvärligt att ha en separat route för varje fil! Gör om så att mappen public servas med `express.static`.

4c Gör så att frontend skickar ett request till gästboken `/guestbook` och skriver ut serverns svar på webbsidan. (Alltså inte console.log) Denna frontend kan du bygga vidare på och använda i de senare övningarna.

5a Lägg till en route GET "/fruits". Skapa en array i din kod: `let fruits = ['strawberry', 'pear', 'apple', 'banana', 'orange']`.

När ett request matchar din route ska du skicka tillbaka hela arrayen.

5b Lägg koden i en fil med namnet `fruits.js` . Importera den med require, som vi har gått igenom på lektionen. (Router module)

5c* Men om ett request innehåller en querystring parameter med namnet _index_ så ska servern skicka tillbaka frukten med det indexet. Tänk på att skicka en lämplig _[HTTP status code](https://http.cat/) _om index inte är ett giltigt index.

Exempel på request: GET `http://localhost:1234/fruits?index=2`

5d* Om index är för högt ska servern skicka ett slumpvis valt element i arrayen, i stället för en felkod. Tips: använd `array.length`, `Math.random` och `Math.ceil`.

6 Lägg till en POST route för /fruits. En ny frukt ska skickas i request body. (`req.body`) Testa med Insomnia eller Postman.

7a Lägg till en PUT route för /fruits. Skicka den nya frukten i request body. Använd en URL parameter för att tala om vilken frukt som ska ändras. Tänk på att använda felhantering. Om requestet inte innehåller ett giltigt id för en frukt ska servern skicka en lämplig _[HTTP status code](https://http.cat/)_.

7b Lägg till en DELETE route för /fruits. Använd en URL parameter för att tala om vilken frukt som ska tas bort

8 Gör en ny modul för route `/books`. Den ska stödja GET, POST, PUT och DELETE. Varje bok-objekt ska ha egenskaperna { title, author }.

9 Skapa routes som använder URL respektive querystring parametrar, för att träna på det.
