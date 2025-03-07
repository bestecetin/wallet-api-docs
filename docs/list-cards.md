## List Cards

Kullanıcının kartlarını listeler.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/CardProcess/ListUserCards

**REQUEST METHOD** : GET

### İstek (Request):

#### Parametreler:

| Parametre         | Tip      | Zorunlu | Açıklama                                                   |
|------------------|---------|---------|------------------------------------------------|
| `CardProductCode` | `string` | Hayır   | Kart türü (FIZIKI_KART, SANAL_KART). Boş ise hepsini listeler. |

#### Örnek Curl REQUEST

```bash
curl -X 'GET' \
  'https://wallet-api-test.pratikislem.com.tr/api/CardProcess/ListUserCards?CardProductCode=SANAL_KART' \
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
    "cards": {
      "totalCount": 1,
      "pageCount": 1,
      "currentPage": 1,
      "pageSize": 10,
      "itemsOnThisPage": 1,
      "list": [
        {
          "cardNumber": "170853nkxrdr9425",
          "cardProductCode": "FIZIKI_KART",
          "createdDate": "2025-02-04T14:33:10.476316Z",
          "accountNo": 105828661,
          "accountName": "pratik"
        }
      ]
    }
  },
  "requiresSecurityImageSelection": false
}
```