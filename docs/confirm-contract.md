## Confirm Contract

Kullanıcının sözleşmesini onaylamak için kullanılan servistir.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/User/ConfirmContract

**REQUEST METHOD** : POST

### İstek (Request):

#### Parametreler:

| Parametre      | Tip       | Zorunlu | Açıklama                                  |
|---------------|----------|---------|---------------------------------|
| `uniqueValue` | `uuid`  | Evet    | Onaylanacak sözleşmenin benzersiz değeri. |

#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/User/ConfirmContract?uniqueValue=776aec9d-e6dd-49a3-97d7-88b557355b54' \
  -H 'accept: application/json' \
  -H 'x-channel-info: API' \
  -d ''
```

#### Örnek RESPONSE

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "data": {
    "uniqueValue": "54e53fdf-9d78-4587-a3d0-1c7fb681cb6e",
    "confirmationTime": "2025-03-05T15:35:50.6654413Z",
    "confirmIpAddress": "10.222.109.128:43586",
    "confirmationMessage": "Sözleşme onaylandı. UniqueValue: 54e53fdf-9d78-4587-a3d0-1c7fb681cb6e, OnaylamaZamani: 03/05/2025 15:35:50, ConfirmIpAddress: 10.222.109.128:43586"
  },
  "requiresSecurityImageSelection": false
}
```
#### ⏭️ Bir Sonraki Adım
👉 Bu servise istek atılıp başarılı bir yanıt alındıysa, Bir sonraki aşama olan kullanıcı ve sözleşmeyi eşleştirmek için <a href="#" onclick="loadMarkdown('docs/update-contracts.md')"><strong>Sözleşme Eşleştirme</strong></a> servisini çağırmalısınız.