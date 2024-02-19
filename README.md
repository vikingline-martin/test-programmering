# Viking Line programmeringstest

## Uppgift 1: Implementera bubbelsortering

Bubbelsortering är en sorteringsalgoritm där stora värden "bubblar" till slutet av en lista.
Algoritmen startar på listans första element och jämför det med nästa element i listan.
Om det första elementen är större än det andra skiftar elementen plats. Algoritmen fortsätter
sedan med nästa position i listan och fortsätter tills den når listans slut, och kommer på
vägen att ha "plockat med sig" det allra största elementet hela vägen till slutet. Därefter
börjar den om från början för att bubbla upp det näst största elementet, osv.

Din uppgift är att implementera bubbelsortering för en lista bestående av objekt. Objekten
ska sorteras alfabetiskt med avseende på egenskapen `name`, som finns på alla objekt
i listan. Implementera sorteringen som en funktion med namnet `bubbleSortByName` som ska
kunna anropas på detta sätt:

```
bubbleSortByName([ { name: 'Lisa' }, { name: 'Pella' }, { name: 'Anna' }, { name: 'Kalle' } ])
> [ { name: 'Anna' }, { name: 'Kalle' }, { name: 'Lisa' }, { name: 'Pelle' } ]
```

## Uppgift 2: Uppdatera inventarielista

Du har en inventarielista som är implementerad som en lista av objekt med egenskaperna `name`
och `quantity` enligt nedan:

```
[
  { name: 'Bowlingklot', quantity: 21 },
  { name: 'Fotboll', quantity: 2 },
  { name: 'Pingisboll', quantity: 1 },
  { name: 'Tennisboll', quantity: 5 }
]
```
Din uppgift är att skriva en funktion `updateInventory(current, incoming)` som tar denna
inventarielista och uppdaterar den med en leverens av nya objekt. För inkommande objekt
med `name` som matchar ett objekt i inventarielistan uppdateras `quantity` för objektet
i inventarielistan till summan av existerande och inkommande. Inkommande objekt med `name`
som inte matchar ett objekt i inventarielistan läggs direkt till i inventarielistan.
Funktionen ska till sist returnera den uppdaterade inventarielistan, sorterad på värdet
på varje objekts egenskap `name`. Använd funktionen `bubbleSortByName` från föregående
uppgift för att sortera objekten.

### Exempeldata och anrop
```
updateInventory(
  [
    { name: 'Bowlingklot', quantity: 21 },
    { name: 'Fotboll', quantity: 2 },
    { name: 'Pingisboll', quantity: 1 },
    { name: 'Tennisboll', quantity: 5 }
  ],
  [
    { name: 'Studsboll', quantity: 4 },
    { name: 'Fotboll', quantity: 5 },
    { name: 'Tennisboll', quantity: 2 },
    { name: 'Bowlingklot', quantity: 7 },
    { name: 'Badboll', quantity: 11 }
  ])
```
Resultat:
```
  [
    { name: 'Badboll', quantity: 11 }
    { name: 'Bowlingklot', quantity: 28 },
    { name: 'Fotboll', quantity: 7 },
    { name: 'Pingisboll', quantity: 1 },
    { name: 'Studsboll', quantity: 4 },
    { name: 'Tennisboll', quantity: 7 }
  ]
```
