# Typy plików i ich przeznaczenie 

## Organizacja plików

- `module` - grupuje powiązaną ze sobą logikę w paczkę 
- `constants` - Przetrzymuje tutaj zmienne dla modułu np stałe 

## Routing

- `controller` - Obsługuje routing 
- `event` - Przyjmuje eventy

## Obsługa logiki biznesowej

- `service` - Wykonuje logikę biznesową
- `repository` - wyodrębnia logikę powiązaną z połączeniem z bazą danych do osobnego pliku. Korzystam z tego tylko w przypadku gdy service jest zbyt duży lub wykonuje dużo podobnych operacji w ramach jednego service

## Wydzielenie logiki do osobnych plików

- `guard` - Logika związana z dostępem do endpointa
- `middleware` - Wszelkie transformacje responsa są wykonywane przez middleware
- `decorator` - Zwraca interesujące nas dane lub dodaje metadane do endpointa
- `pipe` - Modyfikacja i walidacja danych np z querry

## Pliki do obsługi typów

- `dto` - Obsługuje walidacje i podstawowe transformacje body w wyjątkowych przypadkach może też obsłużyć query i params 
- `entity` - Każdy response powinien posiadać wyjątkowe entity 
- `payload` - Jest to typ danych przetrzymujący dane wysyłane w event emiterze
- `type` - Jeśli powyższe typy nie pasują opisem to używam type
