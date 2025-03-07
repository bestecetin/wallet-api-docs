## Wallet List

Kayıtlı cüzdanları listeleyen servistir.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/Account/GetAllAccounts

**REQUEST METHOD** : GET

### İstek (Request):

#### Parametreler:

| Parametre   | Tip      | Zorunlu | Açıklama                           |
|------------|---------|---------|--------------------------------|
| `PageSize`  | `integer` | Hayır   | Sayfa boyutu (Maks: 50). |
| `PageNumber` | `integer` | Hayır   | Sayfa indexi. |

#### Örnek Curl REQUEST

```bash
curl -X 'GET' \
  'https://wallet-api-test.pratikislem.com.tr/api/Account/GetAllAccounts?PageSize=10&PageNumber=1' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer <TOKEN>' \
  -H 'x-channel-info: API' \
```

#### Örnek RESPONSE 1 (Hesap Bulunamadı)

```json
{
  "statusCode": 404,
  "IsSuccess": false,
  "MessageTR": "Hesap bulunamadı.",
  "MessageEN": "Accounts not found.",
  "requiresSecurityImageSelection": false
}
```

#### Örnek RESPONSE 2 (Hesaplar Bulundu)

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "MessageTR": "Hesaplar bulundu.",
  "MessageEN": "Accounts found.",
  "data": {
    "totalCount": 1,
    "pageCount": 1,
    "currentPage": 1,
    "pageSize": 10,
    "itemsOnThisPage": 1,
    "list": [
      {
        "accountNo": 105828661,
        "iban": "00014d3bd37645df1738610566041",
        "balance": 10017700,
        "createdAt": "2025-02-03T19:21:38.095971Z",
        "isActive": true,
        "favorite": true,
        "accountType": "NAKIT",
        "accountName": "pratik"
      }
    ]
  },
  "requiresSecurityImageSelection": false
}
```
