## E-Mail

Müşterinin e-mail adresini kaydeder.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/UserAccount/Add_Email

**REQUEST METHOD** : POST

### İstek (Request):

#### Parametreler:

| Parametre      | Tip       | Zorunlu | Açıklama                                                         |
| -------------- | --------- | ------- | ---------------------------------------------------------------- |
| `email`        | `string`  | Evet    | Kullanıcının e-mail adresi. |
| `mainMail`    | `boolean` | Evet    | E-mailin ana mail olup olmadığını belirtir. |

#### REQUEST BODY

```json
{
  "email": "superpay@example.com",
  "mainMail": true
}
```

#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/UserAccount/Add_Email' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer <TOKEN>' \
  -H 'x-channel-info: API' \
  -H 'Content-Type: application/json' \
  -d '{
  "email": "superpay@example.com",
  "mainMail": true
}'
```
#### ⏭️ Bir Sonraki Adım

👉 Bu servise istek atılıp başarılı bir yanıt alındıysa, bir sonraki adım olarak OTP doğrulanmalıdır. Bunun için
<a href="#" onclick="loadMarkdown('docs/validate-otp-email.md')"><strong>Email Doğrula</strong></a> servisini çağırmalısınız.