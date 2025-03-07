## Add Password

Kullanıcının şifresini ekleyen servistir.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/UserAccount/Add_Password

**REQUEST METHOD** : POST

### İstek (Request):

#### Parametreler:

| Parametre      | Tip       | Zorunlu | Açıklama                                                         |
| -------------- | --------- | ------- | ---------------------------------------------------------------- |
| `password`        | `string`  | Evet    | Kullanıcının belirlediği şifre. |
| `passwordAgain`  | `string`  | Evet    | Şifrenin tekrar girilmesi. |

#### REQUEST BODY

```json
{
  "password": "159357",
  "passwordAgain": "159357"
}
```

#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/UserAccount/Add_Password' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer <TOKEN>' \
  -H 'x-channel-info: API' \
  -H 'Content-Type: application/json' \
  -d '{
  "password": "159357",
  "passwordAgain": "159357"
}'
```

#### Örnek RESPONSE

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "MessageTR": "Şifre eklendi",
  "MessageEN": "Password added",
  "data": true,
  "requiresSecurityImageSelection": false
}
```
#### ⏭️ Kayıt Başarılı

👉 Bu servise istek atılıp başarılı bir yanıt alındıysa, kullanıcı sisteme kaydedilmiştir.

👉 Kullanıcıyı sözleşmeli hesaba geçirmek için  <a href="#" onclick="loadMarkdown('docs/save-info.md')"><strong>Sözleşmeli Hesaba Geç</strong></a> servisini çağırmalısınız.