## Create Virtual Card

Kullanıcı için sanal kart oluşturur. Oluşturulan kartı cüzdana bağlar.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/CardProcess/CreateCard/{accountNumber}

**REQUEST METHOD** : POST

### İstek (Request):

#### Parametreler:

| Parametre     | Tip      | Zorunlu | Açıklama                                    
|--------------|---------|---------|---------------------------------|
| `accountNumber` | `integer` | Evet    | Kartın ekleneceği cüzdanın numarasıdır. |
| `cardLevel`    | `string`  | Evet    | Kart seviyesi (ASIL_KART). |
| `productCode`     | `string`  | Evet    | Kart türü (SANAL_KART). |

#### REQUEST BODY

```json
{
  "createCrdCardRequestDto": {
    "crdCardAccount": {
      "isPrintStmt": true,
      "isSendStmtBranch": true,
      "isSendStmtEmail": true,
      "isSendStmtSms": true,
      "isSendStmtFax": true,
      "isSeperateStatement": true,
      "crdCard": {
        "embossName1": "string",
        "embossName2": "string"
      }
    }
  }
}
```

#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/CardProcess/CreateCard/55000050?cardLevel=ASIL_KART&urunKodu=SANAL_KART' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer <TOKEN>' \
  -H 'x-session-id: <SESSION_ID>' \
  -H 'x-channel-info: API' \
  -H 'Content-Type: application/json' \
  -d '{
  "createCrdCardRequestDto": {
    "crdCardAccount": {
      "isPrintStmt": true,
      "isSendStmtBranch": true,
      "isSendStmtEmail": true,
      "isSendStmtSms": true,
      "isSendStmtFax": true,
      "isSeperateStatement": true,
      "crdCard": {
        "embossName1": "string",
        "embossName2": "string"
      }
    }
  }
}'
```

#### Örnek RESPONSE

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "MessageTR": "Kart oluşturuldu",
  "MessageEN": "Card created",
  "data": "539098pyxwvv9838",
  "requiresSecurityImageSelection": false
}
```
