## Transaction List

Kullanıcının cüzdanına ait işlemleri listeler.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/WalletOperations/ListTransactions

**REQUEST METHOD** : GET

### İstek (Request):

#### Parametreler:

| Parametre      | Tip       | Zorunlu | Açıklama                                                 |
|---------------|----------|---------|------------------------------------------------|
| `AccountNumber` | `integer` | Evet    | Kullanıcının cüzdan numarası. |
| `TxnType`      | `string`  | Hayır   | Spesifik işlem tipinde olan harcamaları getirmek için setlenir. |
| `StartDate`    | `string`  | Hayır   | İşlem başlangıç tarihi (YYYY-MM-DD). |
| `EndDate`      | `string`  | Hayır   | İşlem bitiş tarihi (YYYY-MM-DD). |

#### Örnek Curl REQUEST

```bash
curl -X 'GET' \
  'https://wallet-api-test.pratikislem.com.tr/api/WalletOperations/ListTransactions?AccountNumber=23123&StartDate=2024-12-18&EndDate=2025-01-01' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer <TOKEN>' \
  -H 'x-session-id: <SESSION_ID>' \
  -H 'x-channel-info: API' \
  -H 'Content-Type: application/json'
```

#### Örnek RESPONSE

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "data": {
    "totalCount": 8,
    "pageCount": 1,
    "currentPage": 1,
    "pageSize": 10,
    "itemsOnThisPage": 8,
    "list": [
      {
        "balanceBefore": 36804,
        "balanceAfter": 19104,
        "amount": -17700,
        "createdAt": "2025-02-12T16:25:26.89922Z",
        "txnInfo": {
          "processNumber": 48,
          "isSuccess": false,
          "createdDate": "2025-02-12T16:25:26.89922Z",
          "typeName": "CÜZDANDAN CÜZDANA PARA GÖNDERME",
          "typeCode": "PG.01"
        },
        "txnDetail": {
          "toUserName": "Gülemen superpay",
          "toHesapNo": 105828661,
          "cashbackRate": 0,
          "isCashback": false,
          "description": "Mob gülemen",
          "channelNo": "MOBILE",
          "ipAddress": "10.222.109.128:54296"
        }
      }
    ]
  },
  "requiresSecurityImageSelection": false
}
```