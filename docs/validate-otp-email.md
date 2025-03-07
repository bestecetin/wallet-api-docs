## Validate OTP Email

Email doğrulamaya yarayan servistir.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/OTP/Validate_OTP?islem_tipi=USER_VALIDATE_EMAIL_ADDRESS&otp_tipi=MAIL

**REQUEST METHOD** : POST

### İstek (Request):

#### Parametreler:

| Parametre  | Tip      | Zorunlu | Açıklama                                  |
|------------|---------|---------|---------------------------------|
| `email`    | `string` | Evet    | Doğrulanacak email adresi. |
| `otp_Code` | `string` | Evet    | Kullanıcının aldığı OTP kodu. |

#### REQUEST BODY

```json
{
  "email": "example@pratik.com",
  "otp_Code": "375197"
}
```

#### Örnek Curl REQUEST
```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/OTP/Validate_OTP?islem_tipi=USER_VALIDATE_EMAIL_ADDRESS&otp_tipi=MAIL' \
  -H 'accept: */*' \
  -H 'Authorization: Bearer <TOKEN>' \
  -H 'x-session-id: <SESSION_ID>' \
  -H 'x-channel-info: API' \
  -H 'Content-Type: application/json' \
  -d '{
  "email": "example@pratik.com",
  "otp_Code": "375197"
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
#### ⏭️ Bir Sonraki Adım

👉 Kullanıcıya telefon eklemediyseniz: <a href="#" onclick="loadMarkdown('docs/add-phone.md')"><strong>Telefon Ekle</strong></a>  servisini çalıştırmalısınız.

👉 Kullanıcıya telefon eklendiyse, sözleşmeleri listelemek için <a href="#" onclick="loadMarkdown('docs/get-all-contracts.md')"><strong>Sözleşmeleri Listele</strong></a> servisini çağırmalısınız.
