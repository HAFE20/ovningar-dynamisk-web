## React
[Tillbaka till start](README.md)

1 Skapa en ny React-app med create-react-app. Installera React Developer Tools i din webbläsare. Prova att starta appen och inspektera den i webbläsaren.

Tips:

npx create-react-app _kom-på-ett-bra-namn-utan-åäö-och-mellanslag_ <br>
cd _namnet-på-din-app_ <br>
atom .   (code . om du kör VS Code) <br>
npm run start

2 Ta bort standardkoden i App.jsx (App.tsx) och App.css. Ersätt den med din egen kod. Gör en app som renderar text. Styla texten med CSS.


3 Lägg till kod i appen, som gör att den kan växla utseende mellan "dark mode" och "light mode". Använd en eller flera button-element.

Tips: använd en state-variabel med `useState` och attributet `className`.

4 Gör en inställningskomponent. Den ska visa minst tre inställningar, som kan vara på eller av. När man klickar på en inställning, ska appen ändra utseende med hjälp av CSS. Exempelvis dark mode.

5 Conditional rendering. Lägg till en menykomponent och en huvudsidakomponent. Menyn ska visa två buttons: "huvudsida" och "inställningar". När man klickar på någon av knapparna, ska menykomponenten avgöra vilken av de andra som ska visas.

Tips: använd en state-variabel och en if-sats i menykomponenten.

6 Lägg till ett menyalternativ och en komponent för varje felmeddelande som du råkar ut för under utvecklingen. När man klickar på menyalternativet ska appen visa information om felet, och hur man löser det. Fortsätt bygga på den här appen när du stöter på nya felmeddelanden.

7a Skapa en komponent som kan räkna. Den ska ursprungligen visa värdet 1 - alltså när den renderas första gången. Lägg till knappar med texten "+1" och "-1". När man klickar på dem ska värdet som visas uppdateras.

7b Lägg till en knapp med texten "Reset", som kan återställa värdet till 1.

7c Lägg till knappar med texten "`+5`" och "`*2`".

7d* Gör så att en lista med tidigare värden också visas.

8a Gör en app som kan visa vilka böcker du läser. (eller TV-serier) Appen ska visa en lista med titlar. Om man klickar på ett element i listan, så ska appen visa meddelandet "Du läser _vald bok_" - lägg in namnet på den valda boken.

8b Gör så att det listelementet som man har klickat på är markerat med CSS. Till exempel annan färg. Tips: använd en ny state-variabler.

9a* Gör en "Book" komponent. Den ska visa _delar av_ ett av Shakespeare's verk: [https://www.gutenberg.org/files/100/100-0.txt](https://www.gutenberg.org/files/100/100-0.txt) . Komponenten ska alltså innehålla en längre sträng, men bara visa 200 tecken åt gången. Under texten ska det finnas två knappar med texten "Previous" och "Next". När man klickar på "Next" ska nästa sida visas.

Tips 1: den totala texten ska vara en sträng, som inte behöver ändras. Använd en konstant.

Tips 2: texten som ska visas varierar beroende på vilken sida man är på. Använd state-variabler för _sidnummer_ och _text-som-ska-visas_.

9b Styla komponenten så att det ser ut mera som en bok.

9c** Om man alltid visar 200 tecken, så kan det brytas mitt i ett ord. Gör så att komponenten visar _högst _200 tecken, så att inga ord bryts av i mitten. (extrasvår)

10 Skapa en "spoiler" komponent. Den ska visa en button med texten "spoiler warning". När man klickar på den ska button bytas ut mot en text. Det handlar till exempel om att man inte vill spoila slutet på en bok eller en film.

---

## Komponentkommunikation

_[Lifting State Up – React](https://reactjs.org/docs/lifting-state-up.html) _

1 Förbättra spoiler-komponenten (uppgift 6.10) så att den tar texten som ska visas med _props_.

2a Vanliga checkboxes är för tråkiga. Gör en komponent som ska göra samma sak som en checkbox: man ska kunna klicka på den, och i stället för kryss i en ruta ska den visa olika bilder. Använd state. Som bilder kan du visa använda emojis: 🙂 😒   [https://emojipedia.org/](https://emojipedia.org/)

Exempel på hur man skriver ut en emoji i HTML på bästa sätt:


```
<span role="img" aria-label="sheep">🐑</span>
```


2b* Gör så att din egen checkbox kan visa fler än två bilder. Använd en array. När man klickar ska komponenten visa nästa bild i arrayen. Om man kommer till slutet ska första bilden visas igen.

2c Flytta _state_ till parent component. Checkboxen ska alltså inte ha någon egen state, utan få sitt värde via props. Använd tekniken "lifting state up" för att skicka state mellan parent och child.

3 Skapa en komponent som visar en lista med "Todo items", och en komponent där man kan skriva in en ny item. Exempel: TodoList-komponenten kan innehålla följande HTML

&lt;div className="todo-list">

… här visas en lista med tidigare todos

	&lt;div> ← detta ska vara en egen komponent

		&lt;input type="text" placeholder="Write a new todo" />

		&lt;button> Add todo &lt;/button>

	&lt;/div>

&lt;/div>

4 Skapa en komponent med namnet Tag. Den ska innehålla en button med texten `"Tag"`. När man klickar på den ska texten `"I'm it"` visas i komponenten. Lägg sedan till flera stycken Tag-komponenter i App. De ska dela state, så att bara en komponent visar texten åt gången.

5a Bygg en karusell. Dvs. en komponent som kan visa flera bilder, fast bara en åt gången. Bilderna ska man skicka till komponenten i en array, med props. Användaren ska kunna klicka för att visa nästa eller föregående bild. Man ska också kunna se vilken som visas för tillfället.

5b Parent component ska informeras när bilderna byts. Komponenten ska visa ett meddelande, till exempel "Nu visas bild nummer 2". Använd tekniken lifting state up.

---

## CSS

1a Skapa en komponent PrimaryButton som visar en typisk "call to action" button. Det är en button som är stylad för att visa att det är den här som användaren rekommenderas använda. Ofta med starkt färgad bakgrund och vit text, samt en hover-effekt. Använd en CSS-klass och en CSS-fil Button.css som du importerar i komponenten. Inspireras av: https://blog.hubspot.com/marketing/call-to-action-examples

1b Skapa en GhostButton. Det är en knapp med genomskinlig bakgrund och samma färg på kantlinje och text.

1c Animera hover-effekterna.

2 Bygg en grundläggande layout i App-komponenten med header, footer och main. Skapa CSS-variabler i index.css eller App.css i `:root {}` för de viktigaste färgerna. Se detta som en träning i att bygga en bra, flexibel layout, som du kan använda i andra projekt. Du ska ha CSS-variabler för:



* primär bakgrundsfärg (största delen av sidan, det som inte är header eller footer)
* primär textfärg
* bakgrundsfärg i header och footer (samma)
* textfärg i header och footer

3 Skapa eller ladda ner en eller två bilder. Använd import och &lt;img src> för att länka in dem i en komponent.

4 Animera karusell-komponenten i övning 7.5.

5 Gör en meny, som användaren kan klicka för att expandera. Givetvis animerad. När man klickar ska innehållet visas. Menyn som man har klickat på ska vara markerad.

Tips: använd CSS-klasser, transition och :hover.
