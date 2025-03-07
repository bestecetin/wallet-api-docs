## Phone Number

Kullanıcının telefon numarasını kaydeder.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/UserAccount/Add_Phone_Number

**REQUEST METHOD** : POST

### İstek (Request):

#### Parametreler:

| Parametre      | Tip       | Zorunlu | Açıklama                                                         |
| -------------- | --------- | ------- | ---------------------------------------------------------------- |
| `phoneNumber`    | `string`  | Evet    | Kullanıcının telefon numarası. |
| `countryCode`     | `string`  | Evet    | Telefon numarasının ülke kodu (örn: +90). |

#### REQUEST BODY

```json
{
  "PhoneNumber": "5318842645",
  "CountryCode": "+90"
}
```
#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/UserAccount/Add_Phone_Number' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer <TOKEN>' \
  -H 'x-channel-info: API' \
  -H 'Content-Type: application/json' \
  -d '{
  "phoneNumber": "5318842645",
  "countryCode": "+90"
}'
```

#### Örnek RESPONSE

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "MessageTR": "Telefon numarası eklendi",
  "MessageEN": "Phone number added",
  "data": true,
  "requiresSecurityImageSelection": false
}
```

#### ⏭️ Bir Sonraki Adım

👉 Bu servise istek atılıp başarılı bir yanıt alındıysa, bir sonraki adım olarak OTP doğrulanmalıdır. Bunun için <a href="#" onclick="loadMarkdown('docs/validate-otp-phone.md')"><strong>Telefon Doğrula</strong></a> servisini çağırmalısınız.