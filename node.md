## 1 Node

_Förberedelser:_


* _skapa en mapp på din dator, där du kan lägga filer som vi jobbar med i övningarna_
* _ladda ner en bättre terminal än den som följer med operativsystemet._
* _skapa ett dokument där du skriver ner viktiga kommandon, så du kommer ihåg dem_

_Obs! Det är <span style="text-decoration:underline;">inte tillåtet</span> att använda den inbyggda terminalen i VS Code! Alla övningar ska göra i en separat terminal._

_Tips! npm-paketet colors låter dig använda färger med console.log._

---

1a Ladda ner och installera Node LTS från [https://nodejs.org/en/](https://nodejs.org/en/)

Kontrollera att du har gjort rätt genom att skriva i terminalen: node -v

1b Följ instruktionerna i [TypeScript](typescript.md) för att skapa ett projekt med stöd för TypeScript. Använd `tsc` för att kompilera din script.ts innan du kör den. Försök att använda datatyper på alla variabler och funktioner.

2a Skapa en fil med namnet script.ts och följande innehåll:

```
console.log('Welcome to script.js');
```


Kör den genom att skriva: `node script.js`

2b Ändra skriptet så att du använder features från vanlig "vanilla" JavaScript. Prova variabler, funktioner, arrayer och objekt.

2c Nu ska du prova moduler. Lägg en funktion i en annan fil. Använd _require_ för att importera funktionen.

_(Uppgift 3-5 utgår från npm, hoppa över dem om du inte är bekväm med npm än)_

3 Skapa en package.json fil med _npm init_. Installera npm-paketet _sanitize-html_ och använd det för att skriva en ny funktion, _printSafe_, som kan skriva ut strängar utan att man ser HTML-koden. [Dokumentation här](https://www.npmjs.com/package/sanitize-html)

```
let testData1 = 'This is a safe string';
let testData2 = 'This is a <strong>unsafe</strong> string, because it contains HTML';

function printUnsafe(fromUser) {
    // Hoppsan! Om fromUser innehåller HTML, så ska den inte skrivas ut
    console.log(fromUser);
}
```


4 Välj ut ett eller flera små npm-paket från [parro-it/awesome-micro-npm-packages](https://github.com/parro-it/awesome-micro-npm-packages) och skriv skriptfiler för att testa dem.

5 _nodemon_ är ett npm-paket som kan användas för att starta om ett skript när filer ändras. Prova att starta script.ts med det i stället: `npx nodemon script.js`

Gör sedan en ändring i script.js och spara filen. Vad händer? (Avsluta med Ctrl+C)

6 Skapa en ny fil med namnet "module.ts" med innehållet

```
function fun() {
    console.log('This is a function in a module');
}
// export the fun function
```

Exportera "fun", importera den i script.js och anropa den. Kontrollera att du får utskriften. Detta att lägga kod i olika filer använder vi för att strukturera vår kod.


7 Skapa en fil med namnet "personData.json". Den ska innehålla ett JavaScript-objekt i JSON-format som representerar en användare. Nu ska du använda Nodes fs-modul (fs == file system) för att hämta och ändra datan. Exempel på objekt:


```
{
    "name": "David",
    "email": "david@example.com"
}
```


8a Skapa en fil med namnet "readData.js". När man kör den ska skriptet läsa innehållet i "personData.json", omvandla det från JSON till ett JavaScript-objekt och skriva ut namn+email på konsolen. Använd fs.readFile för att läsa in hela filen på en gång.

8b* Använd fs.createReadStream i stället för fs.readFile. Vad är skillnaden mellan readFile och createReadStream?

9 Skapa en fil med namnet "writeData.js". När man kör den ska skriptet fråga användaren efter ett nytt namn och ny e-postadress. Det ska sparas i "personData.json". Använd process.stdin.

10 Skriv ett skript som skriver ut "What is your name?" och väntar på att användaren ska skriva in en sträng. Sedan ska skriptet skriva ut "Welcome, [namnet man skrev in]".

11* Du kan kombinera read/write till en fil och bygga ett enkelt textbaserat användargränssnitt. Exempel:


```
** Personal data editor **
Choose an option:
1 View data
2 Update data
> 2
New name?
> Nisse
New email?
> nisse@skogen.se
Data updated.
```


(visa menyn igen)

12* Skapa ett skript som slumpar ett tal mellan 1 och 100. Låt användaren gissa talet och räkna antal gissningar. Om man gissar för högt eller för lågt ska skriptet tala om det. Exempel på körning:


```
** Welcome to guess the number! **
Please enter a number between 1 and 100.
> 25
Too low! (1 guess)
> 81
Too high! (2 guesses)
> 73
Correct!! You win in 3 guesses.
```


Tips: skapa en funktion som kan returnera ett slumpat heltal.


```
function getRandomInt(min=1, max=100) {
  return Math.floor(Math.random() * Math.floor(max)) + min;
}
```


13* Prova några vanliga npm-paket; till exempel lodash, chalk och moment. [https://javascript.plainenglish.io/10-useful-npm-packages-you-should-be-aware-of-d72cab2a38f1](https://javascript.plainenglish.io/10-useful-npm-packages-you-should-be-aware-of-d72cab2a38f1)
