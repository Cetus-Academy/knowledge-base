# Zapisywanie kluczy i endpointów

- Endpointy i klucze prywatne należy przechowywać w pliku .env, czyli w zmiennych środowiskowych. <br/>
    Więcej informacji: [Adding Custom Environment Variables | Create React App](https://create-react-app.dev/docs/adding-custom-environment-variables/)

- Plik .env powinien być prywatny, więc musi być umieszczony w .gitignore.

## Jak powinniśmy zapisywać klucze

Plik .env:
```env
SECRET_KEY="BARDZO WAŻNY SEKRET"
```

Kod JavaScript:
```js
// nodejs sam nie importuje .env do środowiska, robi się to biblioteką dotenv
// https://www.npmjs.com/package/dotenv
require('dotenv').config()

console.log(process.env.SECRET_KEY)

```

## Jak nie powinniśmy zapisywać kluczy oraz endpointów
    
- W zwykłym pliku JSON
```json
// /src/assets/variables.json
{
    "proxy": "localhost:3000",
    "proxy2": "https://api.foodapp.academy.st.cetuspro.com",

    // noooo no tak się nie robi nie
    "trello_auth_key": "4259dda4-ddd2-41c7-9eae-95c036c836dd"
}
```

- bezpośrednio w kodzie aplikacji
```ts
export const getRestaurants = async (token) => {
    // utrudnia to wprowadzanie zmian w endpointach czy coś
    return await axios.get(`https://localhost:3000/user/restaurants`, {
        headers: {Authorization: `Bearer ${Token}` }
    })
}
```
