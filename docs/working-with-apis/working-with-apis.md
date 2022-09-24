# Praca z API

Przykładowo endpoint `/auth/signIn` zwraca token jako plain text. Trzeba przejrzeć wszystkie endpointy i to poprawić aby zawsze był zwracany JSON

Endpoint `/public/account/register` zwraca przykładowo tylko samo id utworzonego użytkownika. zwrotka powinna wyglądać bardziej tak:

```json
{
  "status": "user_registered",
  "user_id": 2
}
```