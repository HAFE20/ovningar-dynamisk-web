## Sidoeffekter, livscykel, useEffect och AJAX
[Tillbaka till start](README.md)

1 Skapa en komponent med en state-variabel som är en tom sträng. När komponenten har renderats första gången (_mounted_) ska du ändra variabelns värde till "Hello world", med hjälp av useEffect.

Tips: `const [hello, setHello] = useState('');`.

2a Skapa en komponent som visar vad klockan är. Använd useEffect med setInterval.

Tips: Se slides och kodexempel för vilka funktioner du behöver.

2b Gör så att komponenten slutar uppdateras när den inte längre visas (unmount) med clearInterval.

3* Gör en "notifierings" komponent. Den ska visa ett meddelande (som den får via _props_) och _ta bort sig själv_ efter en viss tid. Använd CSS transitions för att göra en snygg övergång.

Tips: använd CSS för att göra komponenten osynlig.

4 Skapa en komponent som gör ett AJAX request när den renderats första gången. Använd `http://forverkliga.se/JavaScript/api/simple.php` med querystring `key=value`. API:et ska returnera en sträng i JSON-format som du kan omvandla till ett objekt. Objektet har då egenskaperna _message _och _time_. Komponenten ska visa deras värden, när svaret från servern kommer.

(Om API:et bråkar, använd [https://api.chucknorris.io/](https://api.chucknorris.io/) )

5* Skapa en komponent som hämtar och visar data från [https://swapi.dev/](https://swapi.dev/) , Star Wars API. Till exempel, de 10 första personerna. API:et har fler än 10 personer så man behöver kunna bläddra (klicka på en knapp för att skicka ett nytt request) för att se nästa 10. (Om API:et bråkar, leta upp ett annat: [public-apis/public-apis: A collective list of free APIs](https://github.com/public-apis/public-apis#public-apis--) )

6a Skapa en komponent som hämtar och visar data från [https://sunrise-sunset.org/api](https://sunrise-sunset.org/api) , Sunset and sunrise times. Lägg till knappar med texten: "Göteborg" och "Stockholm". När man klickar på dem ska appen visa "idag gick solen upp klockan [tid från API:et här] i Stockholm" respektive Göteborg.

Man kan göra detta på två sätt: 1) med fetch direkt i klickfunktionen, 2) med två state-variabler för latitud och longitud och useEffect som lyssnar på ändringar på state-variablerna.

Tips: `useEffect( () => {}, [lat, lng]);`.

6b* Lägg till knappar för olika datum, till exempel "idag" och "imorgon".

---

## Formulärelement och validering

1a Skapa en komponent med ett input-fält som gör om alla bokstäver man skriver till stora bokstäver.

1b* Nu ändrar vi så att första bokstaven blir stor, men resten blir små. Bra för att skriva in namn!

2a Skapa ett input-fält där man bara kan skriva in tal mellan 7 och 20. Om användaren t.ex. skrivit in ett för stort tal och lämnar (avfokuserar) fältet, ska fältet ändras till det högsta tillåtna värdet, 20.

2b Ändra så att övre och undre gränsen bestäms med props.

3 Skapa ett input-fält där man ska skriva in en e-postadress. (Så bra som möjligt, utan att använda regex eller kod från stack overflow.) Om man skriver in ett värde som inte är rätt, ska ett meddelande visas för användaren; i anslutning till input-fältet.

4a Gör en komponent med ett formulär. Det ska finnas en button, som man bara kan klicka på om alla input-fält validerar. Lägg in dina input-fält från de tidigare övningarna.

4b Gör så att eventuella felmeddelanden animeras.
