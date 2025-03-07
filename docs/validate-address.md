## Validate Address

Kullanıcının ikamet adres numarasını doğruladığı servistir. E-devlette kayıtlı olan adres numarasını doğrular.

**REQUEST URL** : https://wallet-api-test.pratikislem.com.tr/api/Onboarding/ValidateAddress

**REQUEST METHOD** : POST

### İstek (Request):

#### Parametreler:

| Parametre   | Tip       | Zorunlu | Açıklama                                      |
|------------|----------|---------|---------------------------------|
| `addressNo` | `integer` | Evet    | Kullanıcının e-devlette kayıtlı adres numarası. |

#### REQUEST BODY

```json
{
  "addressNo": 0
}
```

#### Örnek Curl REQUEST

```bash
curl -X 'POST' \
  'https://wallet-api-test.pratikislem.com.tr/api/Onboarding/ValidateAddress' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer <TOKEN>' \
  -H 'x-session-id: <SESSION_ID>' \
  -H 'x-channel-info: API' \
  -H 'Content-Type: application/json' \
  -d '{
  "addressNo": 5
}'
```

#### Örnek RESPONSE

```json
{
  "statusCode": 200,
  "IsSuccess": true,
  "MessageTR": "Adres başarıyla kaydedildi",
  "MessageEN": "Address saved successfully",
  "data": "https://kyc.pratikislem.com.tr/api/v1/verification-sessions/76ac808b-41d0-4485-aa98-ad8ca92f37c3/qr-code",
  "requiresSecurityImageSelection": false
}
```
#### ⏭️ Bir Sonraki Adım

👉 Bu servise istek atılıp başarılı bir yanıt alındıysa, bir sonraki adım olarak dijital kimlik doğrulama adımına geçmek için, 
 <a href="#" onclick="loadMarkdown('docs/start-session.md')"><strong>Kimlik Doğrulama</strong></a> servisini çağırmalısınız.
