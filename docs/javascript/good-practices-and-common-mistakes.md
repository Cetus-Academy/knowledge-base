# Dobre praktyki i częste błędy

- Zamiast `onclick` w HTML w przyciskach lepiej stosować `addEventListener`
- Warto stosować się do nowej składni ES6. Przykładowo nie należy stosować `var` do definiowania zmiennych, z racji tego, że w ES6 wprowadzono `let` oraz `const`. Takich elementów jest więcej i warto zobaczyć ten film: [ES6 – the best of ⌨️ hello roman #22 ](https://www.youtube.com/watch?v=eA2YRceiDwk)
- Pisanie niepotrzebnych komentarzy - lepiej pisać kod tak, aby był zrozumiały bez komentarzy.
```js
// czas
let h = 24;
let m = 60;
let s = 60;
let ms = 1000;
// ... nazwy zmiennych są nieczytelne

// czas
let hours = 24;
let minutes = 60;
let seconds = 60;
let milliseconds = 1000;
// ... nazwy zmiennych powodują, że komentarz nie jest potrzebny
```
- Podawanie sztywnych dat “max” w inputach daty:
```js
<input
    type="date"
    id="start"
    name="start"
    value="2022-08-11"
    min="2022-08-11"
    max="2023-01-01"
/>
```
Gdy podamy tutaj datę na sztywno, po upływie tego czasu trzeba będzie przejść do aplikacji i zmienić te daty jeszcze raz. 
Lepszą praktyką jest podmiana tych dat przez JavaScript. <br/>
Tutaj jest przykład który należy trochę zmodyfikować, ale możecie na tym bazować: 
[Set date input field's max date to today - Stackoverflow](https://stackoverflow.com/questions/32378590/set-date-input-fields-max-date-to-today)
- Kod JS warto dodać do osobnego pliku niż umieszczać go w kodzie HTML strony.
- Zamiast document.write lepiej jest używać `innerHTML`.
```js
document.write(`<br><br>Szacunkowa cena za paliwo: ${kosztPaliwa}`);
p.innerHTML = `<br><br>Szacunkowa cena za paliwo: ${kosztPaliwa}`
```
- Warto zamiast wpisywania liczb na sztywno definiować je w osobnych zmiennych.   
```js
// nie wiadomo, co 1.23 oznacza
let grossPrice = totalTripCost * 1.23;

// lepiej to wydzielić do osobnej zmiennej
const VAT_VALUE = 1.23;
let grossPrice = totalTripCost * VAT_VALUE;
// z nową zmienną nie trzeba się już niczego domyślać
```

