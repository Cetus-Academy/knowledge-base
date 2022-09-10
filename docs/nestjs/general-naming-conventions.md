# Ogólne konwencje nazewnicze

## Nazewnictwo plików

Każdy plik powinien mieć następującą strukturę plików: <br/>
`NAZWA-NADRZĘDNEGO-MODUŁU.NAZWA-MODUŁU-LUB-FUNKCJA-PLIKU.TYP-PLIKU.TS`

- `NAZWA-NADRZĘDNEGO-MODUŁU` - Tu zazwyczaj nazwa roli użytkownika który ma dostęp do zasobu
- `NAZWA-POD-MODUŁU-LUB-FUNKCJA-PLIKU` - Ta część podaje nam opis funkcjonalności jaką pełni plik, lub jeśli jest to plik typu controller, service, moduł to część podaje nam nazwę pod-modułu w którym się znajdujemy
- `TYP-PLIKU` - Każdy plik powinien mieć określony typ 

### Przykłady

#### Użycie nazwy pod-modułu

- `serviceAdmin.servicePoints.controller.ts`
- `stripe.payment.controller.ts`
- `globalAdmin.users.service.ts`

#### Użycie funkcji pliku w nazwie

- `serviceAdmin.listOfReservations.entity.ts`
- `stripe.productNameWithPrice.type.ts`
- `stripe.webhookObject.payload.ts`
- `globalAdmin.servicePointTemplate.dto.ts`

W wyjątkowych przypadkach określam zarówno nazwę modułu jak i funkcję. <br/>

Najważniejszą rzeczą jest to by z po samej nazwie pliku było znane jego przeznaczenie. <br/> 
Na przykład: `serviceAdmin.servicePoints.canSwitchToPublic.validator.ts` <br/>
W przypadku gdy jesteśmy w folderze nadrzędnym - `auth.module.ts`
