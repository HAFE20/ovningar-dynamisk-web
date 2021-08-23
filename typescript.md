## TypeScript och Express
[Tillbaka till start](README.md)

För att göra övningarna på TypeScript behöver du:


1. skapa ett nytt projekt med `git init`, `npm init -y` i terminalen
2. installera TypeScript med `npm install typescript --save-dev`
3. generera inställningsfil med `npx tsc --init`
4. lägga till skript i package.json

_Obs! Detta blir annorlunda när man jobbar med ramverk. TypeScript integreras med ramverket och behöver inte installeras separat._

1a Ändra i "script" delen i din package.json till:


```
"scripts": {
"tsc": "tsc",
"start": "node dist/server.js"
}
```


Nu kan du skriva `npm run tsc` för att bygga alla .ts-filer och `npm run start` för att starta server-filen. (Obs, du måste lägga till minst en .ts-fil först: `server.ts`)

1b Lägg till i "tsconfig.json":


```
{
	"compilerOptions": {
		"outDir": "./dist",
		"allowJs": true,
		"target": "ES2015",
		"noImplicitReturns": true,
		"noImplicitAny": true,
		"strictNullChecks": true
	},
	"include": [
		"./src/**/*"
	]
}
```


2 Skapa filen server.ts och bygg en tom Express-server. Lägg till resursen GET /guestbook. När servern tar emot ett request ska den skicka tillbaka strängen "Du är besökare nr 1". Nästa gång den anropas ska servern öka värdet till 2, 3 osv. Alla variabler ska ha en datatyp.

3* Lägg till datatyp på req, res och callback-funktionen.

4 Lägg till resursen GET /sum som ska räkna ut summan av alla tal i en array. Hitta på en array med minst tre tal. Ange datatyp för arrayen. Prova sedan att lägga in en boolean eller en string i arrayen om kompilera koden.

5a Nu är det dags att bygga ett REST API som hanterar frukter. Vi håller det enkelt, så låt frukterna vara objekt i en array som du skapar i koden. Skapa ett interface för att beskriva ett frukt-objekt. Varje frukt ska ha egenskaperna "name" och "score". (score är en poäng mellan 1-5) Gör sedan resursen GET /fruits.

5b Flytta frukt-interfacet till en egen fil. Använd import och export.

5c Gör resurserna `POST /fruits`, `GET /fruits/:index` och. Parametern :index ska motsvara indexet i arrayen.

5d* Gör `DELETE /fruits/:index` och `PUT /fruits/:id`.
