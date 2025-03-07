## Validate OTP Phone Number

Telefon numarası doğrulamaya yarayan servistir.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/OTP/Validate_OTP?islem_tipi=USER_VALIDATE_PHONE_NUMBER&otp_tipi=SMS

**REQUEST METHOD** : POST

### İstek (Request):

#### Parametreler:

| Parametre  | Tip      | Zorunlu | Açıklama                                  |
|------------|---------|---------|---------------------------------|
| `phoneNumber`    | `string` | Evet    | Doğrulanacak telefon numarası. |
| `otp_Code` | `string` | Evet    | Kullanıcının aldığı OTP kodu. |

#### REQUEST BODY

```json
{
  "phoneNumber": "5393490797",
  "otp_Code": "177726"
}
```

#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/OTP/Validate_OTP?islem_tipi=USER_VALIDATE_PHONE_NUMBER&otp_tipi=SMS' \
  -H 'accept: */*' \
  -H 'Authorization: Bearer <TOKEN>' \
  -H 'x-session-id: <SESSION_ID>' \
  -H 'x-channel-info: web' \
  -H 'Content-Type: application/json' \
  -d '{
  "phoneNumber": "5393490797",
  "otp_Code": "177726"
}'
```

#### Örnek RESPONSE

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "MessageTR": "OTP Kodu doğrulandı",
  "MessageEN": "OTP code validated",
  "requiresSecurityImageSelection": false
}
```

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

👉 Kullanıcıya mail eklemediyseniz: <a href="#" onclick="loadMarkdown('docs/add-email.md')"><strong>Mail Ekle</strong></a>  servisini çalıştırmalısınız.

👉 Kullanıcıya mail eklendiyse, sözleşmeleri listelemek için <a href="#" onclick="loadMarkdown('docs/get-all-contracts.md')"><strong>Sözleşmeleri Listele</strong></a> servisini çağırmalısınız.